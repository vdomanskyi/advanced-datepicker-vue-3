# VCalendar Plugin for Vue 3

A Vue plugin for for attributed calendars date pickers using Vue 3, Typescript and Rollup.

### Install Plugin

```shell
yarn add v3-date@next
```

### Use Plugin

:warning: **As of `v3.0.0-alpha.7`, all installation methods require manual import of component styles. This is due to Vite build restrictions in libary mode.**

```js
import 'v3-date/dist/style.css';
```

#### Method 1: Use Globally

```js
import VCalendar from 'v3-date';

// Use plugin with defaults
app.use(VCalendar, {})
```

```html
<!-- Component.vue template -->
<template>
  <v3-date />
  <v-date-picker v-model="date" />
</template>
```

### Method 2: Use Components Globally

```js
// main.js
import { SetupCalendar, Calendar, DatePicker } from 'v3-date';

// Setup plugin for defaults or `$screens` (optional)
app.use(SetupCalendar, {})
// Use the components
app.component('Calendar', Calendar)
app.component('DatePicker', DatePicker)
```

```html
<!-- Component.vue template -->
<template>
  <Calendar />
  <DatePicker v-model="date" />
</template>
```

### Method 3: Use Components As Needed

```js
// main.js
import { SetupCalendar } from 'v3-date';

// Setup plugin for defaults or `$screens` (optional)
app.use(SetupCalendar, {})
```

```html
<!-- Component.vue template -->
<template>
  <Calendar />
  <DatePicker v-model="date">
</template>
```

```js
// Component.vue script
import { Calendar, DatePicker } from 'v3-date';

export default {
  components: {
    Calendar,
    DatePicker,
  },
  data() {
    return {
      date: new Date(),
    };
  },
}
```

## Source setup

Please follow below mentioned steps to clone and build this project:

### Clone the repo

```sh
git clone https://github.com/vdomanskyi/v3-date

# Move to directory
cd v3-date
```

### Install dependencies

```sh
yarn
```

### Switch to `/next` branch

```sh
git checkout next
```

### Build Library

```sh
# ES, CommonJS, IIFE and CSS
yarn build
```

### Lint and fix files

```sh
yarn lint
```
