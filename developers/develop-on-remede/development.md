---
description: Modify the source code in Vue to add functionalities !
---

# 🧸 Development

The main code of Remède is in the `app` folder. The following documentation concerns this folder, so you should move to it before continuing.

This project is developed using **Ionic**. It **acts like a Vue website** (that's why we provide a web version of the application).

## Structure

* `public/`: Public resources, served under `/`
* `src/`: The Vue project
  * `assets/`: Assets
  * `components/`: Vue components
  * `views/`: Application pages
  * `functions/`: Native functionalities / dictionary or API calls...
  * `router/`: Router files
  * `theme/`: CSS styles
  * `App.vue`: main Vue file
  * `main.ts`: main typescript file
* `ionic.config.json`: Ionic configuration
* `capacitor.config.json`: Capacitor configuration
* `package.json`

Not all the files are listed, you can find more configurations files in these folders...

## Scripts

* Development start

```shell
npm run dev 
```

* Build project

```shell
npm run build 
```

* Lint project

```shell
npm run lint 
```

* Lint project and fix problems

```shell
npm run lint:fix 
```

## How to develop

You can navigate through the folders and files to understand more how it is working.

* Also check the [Ionic Vue](https://ionicframework.com/docs/vue/overview) and [Ionic Ui Components](https://ionicframework.com/docs/components) documentation
* Contact us at [software@camarm.dev](mailto:software@camarm.dev) for more information
