# Getting Started with Create React App

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

## Available Scripts

In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

The page will reload if you make edits.\
You will also see any lint errors in the console.

### `npm test`

Launches the test runner in the interactive watch mode.\
See the section about [running tests](https://facebook.github.io/create-react-app/docs/running-tests) for more information.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Prettier

How to install all required packages to enable ESLint and Prettier in VSCode editor. This [guide](https://levelup.gitconnected.com/configure-eslint-and-prettier-for-your-react-project-like-a-pro-2022-10287986a1b6) was used to setup linter and formatter.

### Create ESLint config

```bash
npm init @eslint/config
```

### Install Prettier

```bash
npm install --save-dev --save-exact prettier
```

### Add scripts to the `package.json`

```bash
"lint": "eslint src/**/*.{js,jsx,ts,tsx,json}",
"lint:fix": "eslint --fix src/**/*.{js,jsx,ts,tsx,json}",
"format": "prettier --write src/**/*.{js,jsx,ts,tsx,css,md,json,scss} --config ./.prettierrc"
```

### Create .prettierrc file and write these lines inside it

```json
{
  "semi": true,
  "tabWidth": 2,
  "printWidth": 80,
  "singleQuote": true,
  "trailingComma": "es5",
  "jsxSingleQuote": true,
  "bracketSpacing": true
}
```

### And add these lines to the `.vscode/setting.json` file.

```json
{
  "editor.codeActionsOnSave": { "source.fixAll.eslint": true },
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```

## Internalization (i18n)

### Install i18n packages

```bash
npm install --save i18next react-i18next
```

### Configure `i18n` instance

```typescript
import i18n from 'i18next'
import { initReactI18next } from 'react-i18next'

i18n.use(initReactI18next).init({
  resources: {
    en: {
      translation: {},
    },
  },
  lng: 'en',
  fallbackLng: 'en',
  interpolation: {
    escapeValue: false,
  },
})

export default i18n
```

### Register module in the `App.tsx`

```typescript
import './i18n'

function App(): JSX.Element {
  return <div>React app!</div>
}
```

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).

To learn React, check out the [React documentation](https://reactjs.org/).
