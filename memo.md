## project 1 - Weather App Build

---

### **vscode extensions**

    - vue language features(volar)
    - vue vscode snippets
    - tailwind css intellisense

- [stacks] using Vue 3, Tailwind CSS & the OpenWeather API.
- [ref] https://www.youtube.com/watch?v=gUsBaB5ViAo&t=29s

### vue project 시작

> npm init vue@latest

- 프로젝트 스캐폴드.
- https://ko.vuejs.org/guide/quick-start.html#creating-a-vue-application

```bash
Need to install the following packages:
  create-vue@3.7.5
Ok to proceed? (y) y

Vue.js - The Progressive JavaScript Framework

√ Project name: ... vue-project-weatherApp
√ Package name: ... vue-project-weatherapp
√ Add TypeScript? ... **No** / Yes
√ Add JSX Support? ... **No** / Yes
√ Add Vue Router for Single Page Application development? ... No / **Yes**
√ Add Pinia for state management? ... **No** / Yes
√ Add Vitest for Unit Testing? ... **No** / Yes
√ Add an End-to-End Testing Solution? » No
√ Add ESLint for code quality? ... **No** / Yes

Scaffolding project in C:\Workspace\vue3 practice\vue-project-weatherApp...

Done. Now run:

  cd vue-project-weatherApp
  npm install
  npm run dev

```

### vue 개발환경 시작

```bash
  cd vue-project-weatherApp
  npm install
  npm run dev
```

### tailwindcss 적용

```bash
npm i -D tailwindcss postcss autoprefixer
```

```bash
npx tailwindcss init -p


Created Tailwind CSS config file: tailwind.config.js
Created PostCSS config file: postcss.config.js
```

tailwind.config.js 의 코드를 수정한다.

```javascript
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./index.html", "./src/**/*.{vue,js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

src/assets 폴더에 tailwind.css 추가

> src/assets/tailwind.css

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

- 밑줄 경고 제거 -> "css.lint.unknownAtRules": "ignore"

main.js 에 css 추가

```javascript
import "./assets/tailwind.css";
```

> tailwind.config.js 코드 수정 / index.html 코드 추가

**tailwind.config.js**

```javascript
module.exports = {
  content: ["./index.html", "./src/**/*.{vue,js,ts,jsx,tsx}"],
  theme: {
    extend: {
      colors: {
        "weather-primary": "#00668A",
        "weather-secondary": "#004E71",
      },
    },
    fontFamily: {
      Roboto: ["Roboto, sans-serif"],
    },
    container: {
      padding: "2rem",
      center: true,
    },
    screens: {
      sm: "640px",
      md: "768px",
    },
  },
  plugins: [],
};
```

**index.html**

```html
<head>
  <meta charset="UTF-8" />
  <link rel="icon" href="/favicon.ico" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link
    href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap"
    rel="stylesheet"
  />
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"
    integrity="sha512-z3gLpd7yknf1YoNbCzqRKc4qyor8gaKU1qmn+CShxbuBusANI9QpRohGBreCFkKxLhei6S9CQXFEbbKuqLg0DA=="
    crossorigin="anonymous"
    referrerpolicy="no-referrer"
  />
  <title>Vite App</title>
</head>
```

### font-awesome Link 추가

- https://cdnjs.com/libraries/font-awesome

```html
<head>
  <meta charset="UTF-8" />
  <link rel="icon" href="/favicon.ico" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <link
    href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500&display=swap"
    rel="stylesheet"
  />
  <link
    rel="stylesheet"
    href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"
    integrity="sha512-z3gLpd7yknf1YoNbCzqRKc4qyor8gaKU1qmn+CShxbuBusANI9QpRohGBreCFkKxLhei6S9CQXFEbbKuqLg0DA=="
    crossorigin="anonymous"
    referrerpolicy="no-referrer"
  />
  <title>Vite App</title>
</head>
```
