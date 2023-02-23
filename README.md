# VUE + VITE + TAILWINDCSS + GENERATE PAGE + GENERATE LAYOUT

## FOR USE THIS TEMPLATE

### just clone this repo

```bash
git clone
```

### remove the .git folder

```bash
rm -rf .git
```

### install the dependencies

```bash
$ pnpm install
$ npm install
```

### if you don't have pnpm install it

```bash
npm install pnpm
```

### run the project

```bash
$ pnpm run dev
$ npm run dev
```

# CREATE A NEW PROJECT WITH VUE + VITE + TAILWINDCSS

## 1. VUE + VITE + TAILWINDCSS

### Install Vite

```bash
pnpm create vite
```

https://vitejs.dev/guide/

### follow the instructions

```bash
cd vite-project
pnpm install
```

### install tailwindcss

```bash
pnpm add -D tailwindcss@latest postcss@latest autoprefixer@latest

npx tailwindcss init -p
```

https://tailwindcss.com/docs/installation

### in the file tailwind.config.js add the following

```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ['./index.html', './src/**/*.{vue,js,ts,jsx,tsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

### in the style.css file add the following

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### dont forget to import the style.css file in the main.js or main.ts file

```js
import './style.css';
```

## 2. ROUTER DYNAMIC

### install vue-router

```bash
pnpm install vue-router@latest
npm install vue-router@latest
```

https://router.vuejs.org/installation.html

### in the file main.ts add the following

```js
import { createApp } from 'vue';
import App from './App.vue';
import router from './modules/router';

import './style.css';

const app = createApp(App);

app.use(router);
app.mount('#app');
```

### create a folder called modules

#### create a file called router.ts in the modules folder

<hr />

### create a folder called layouts

#### create a file called default.vue and 404.vue in the layouts folder

#### in the file default.vue add the following

```html
<script setup lang="ts"></script>

<template>
  <div id="default">
    <RouterView />
  </div>
</template>
```

#### in the file 404.vue add the following

```html
<script setup lang="ts">
  import { useRouter } from 'vue-router';
  const router = useRouter();
</script>

<template>
  <div>
    <button @click="router.back()">Retour</button>
    <RouterView />
  </div>
</template>
```

<hr />

### create a folder called pages

#### create a file called index.vue and [...all].vue in the pages folder

#### in the file index.vue add the following

```html
<script setup lang="ts"></script>

<template>
  <div id="index">
    <h1 class="text-3xl font-bold underline">Hello world!</h1>
  </div>
</template>
```

#### in the file [...all].vue add the following

```html
<script setup lang="ts"></script>

<template>
  <h1>Page introuvable</h1>
</template>

<route lang="yaml"> meta: layout: 404 </route>
```

<hr />

### install vite-plugin-pages

```bash
pnpm add vite-plugin-pages
npm add vite-plugin-pages
```

https://github.com/hannoeru/vite-plugin-pages

### install vite-plugin-vue-layouts

```bash
pnpm add vite-plugin-vue-layouts
npm add vite-plugin-vue-layouts
```

https://github.com/johncampionjr/vite-plugin-vue-layouts

### in the file vite.config.js add the following

```js
import { defineConfig } from 'vite';
import vue from '@vitejs/plugin-vue';
import Pages from 'vite-plugin-pages';
import Layouts from 'vite-plugin-vue-layouts';

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [vue(), Pages({ extensions: ['vue'] }), Layouts()],
});
```

### in tsconfig.json add the following in the Compiler Options

```json
"types": ["vite/client", "vite-plugin-pages/client", "vite-plugin-vue-layouts/client"]
```

```json
  "compilerOptions": {
    "target": "ESNext",
    "useDefineForClassFields": true,
    "module": "ESNext",
    "moduleResolution": "Node",
    "strict": true,
    "jsx": "preserve",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "esModuleInterop": true,
    "lib": ["ESNext", "DOM"],
    "skipLibCheck": true,
    "noEmit": true,
    "types": ["vite/client", "vite-plugin-pages/client", "vite-plugin-vue-layouts/client"]
  },
```

### in the file modules/router.ts add the following

```js
import { createRouter, createWebHistory } from 'vue-router';
import { setupLayouts } from 'virtual:generated-layouts';
import generatedRoutes from 'virtual:generated-pages';

const routes = setupLayouts(generatedRoutes);
const router = createRouter({
  history: createWebHistory(),
  routes,
});

export default router;
```

### 3. RELOAD VSCODE

### 4. START THE PROJECT

```bash
pnpm run dev
npm run dev
```

#### and go to http://localhost:PORT

#### now u see the page index.vue with your Hello world!

#### try to go to http://localhost:PORT/NONEXISTINGPAGE
