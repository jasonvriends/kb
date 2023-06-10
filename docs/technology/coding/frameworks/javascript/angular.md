# Angular

AngularJS is a JavaScript-based open-source framework developed by Google for building dynamic web applications. It is often referred to as "Angular 1" to distinguish it from later versions of Angular, such as Angular 2+.

## Prerequisites
---

### Node.js

Node.js is an asynchronous event-driven JavaScript runtime, Node.js is designed to build scalable network applications.

- To install Node.js

  ```bash
  sudo dnf install nodejs -y
  ```

### Node Package Manager

Node.js is all about modularity, and with that comes the need for a quality package manager; for this purpose, npm was made. npm is a package manager for Node.js packages or modules.

- To install npm

  ```bash
  sudo dnf install npm -y
  ```

- To install a packge or module using npm

  ```bash
  npm install <package-name>
  ```

- To utilize the precise dependency versions specified in a `package-lock.json` file when installing npm packages

  ```bash
  npm ci
  ```

### Angular CLI

The Angular Command-Line Interface (CLI) helps you not only to create an application but also to test, scaffold, and deploy it. It creates a workspace folder and generates a structure for the application.

- To install the [Angular CLI](https://angular.io/cli) npm package globally (i.e., outside of a specific project)

  ```bash
  npm install -g @angular/cli
  ```

- Refer to the [CLI Overview and Command Reference](https://angular.io/cli) for usage information.

## Getting Started
---

### Create a new Angular workspace

- Using the ^^latest^^ version of the Angular CLI

  ```bash
  ng new <project-name>
  cd <project-name>
  ```

  - Would you like to add Angular routing? `Y`
  - Which stylesheet format would you like to use? `CSS`

- Using a ^^specific^^ version of the Angular CLI
  ```bash
  ng new <project-name> --version=16.0.5
  ```

  - Would you like to add Angular routing? `Y`
  - Which stylesheet format would you like to use? `CSS`

- To see what version of the Angular CLI you are using

  ```bash
  ng version
  ```

### Folder Structure

The [Angular coding style guide](https://angular.io/guide/styleguide) suggests using a [shared module](https://angular.io/guide/styleguide#shared-feature-module) and a [module for each feature](https://angular.io/guide/styleguide#feature-modules).

### UI Frameworks

There are serveral popular UI Frameworks available for building Angular applications. Below are some notable ones.

#### Angular Material

- Install the [Angular Material](https://material.angular.io/guide/getting-started) npm package

  ```bash
  ng add @angular/material
  ng add @angular/cdk
  ```

  - Would you like to proceed? `Y`

  - Choose a prebuilt theme name, or "custom" for a custom theme: `Indigo/Pink`

  - Set up global Angular Material typography styles? `Y`

  - Include the Angular animations module? `Include and enable animations`

#### Tailwind CSS + Flowbite

- Install the [Tailwind](https://tailwindcss.com/docs/guides/angular) npm package

  ```bash
  npm install -D tailwindcss postcss autoprefixer
  npx tailwindcss init
  ```

- Configure your template paths inside the `tailwind.config.js` file:

  ```bash title="tailwind.config.js" hl_lines="3 4 5"
  /** @type {import('tailwindcss').Config} */
  module.exports = {
    content: [
      "./src/**/*.{html,ts}",
    ],
    theme: {
      extend: {},
    },
    plugins: [],
  }
  ```

- Add the Tailwind directives to your CSS

  ```css title="./src/styles.css"
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  ```

- Install the [Flowbite](https://flowbite.com/docs/getting-started/quickstart/) npm package

  ```bash
  npm install flowbite
  ```

- Configure Flowbite inside the `tailwind.config.js` file:

  ```bash title="tailwind.config.js" hl_lines="5 11"
  /** @type {import('tailwindcss').Config} */
  module.exports = {
    content: [
      "./src/**/*.{html,ts}",
      "./node_modules/flowbite/**/*.js"
    ],
    theme: {
      extend: {},
    },
    plugins: [
      require('flowbite/plugin')
    ],
  }
  ```

- Add the Stylesheet and JavaScript code that powers Flowbite:

  ```bash title="index.html" hl_lines="10 15"
  <!doctype html>
  <html lang="en">

  <head>
    <meta charset="utf-8">
    <title>App</title>
    <base href="/">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="icon" type="image/x-icon" href="favicon.ico">
    <link href="https://cdnjs.cloudflare.com/ajax/libs/flowbite/1.6.5/flowbite.min.css" rel="stylesheet" />
  </head>

  <body class="bg-gray-50 dark:bg-gray-800">
    <app-root></app-root>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/flowbite/1.6.5/flowbite.min.js"></script>
  </body>

  </html>
  ```

A great starter template that you can use to copy HTML from is the [Flowbite Admin Dashboard](https://github.com/themesberg/flowbite-admin-dashboard.)

### Fundamentals

The basic building blocks in Angular applications are: Components, Templates, Directives, and Services.

#### Components

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML.

- Create a component with the CLI

  ```bash
  ng generate component <component-name>
  ```

#### Modules

Modules are a way to organize and bundle related components, directives, services, and other code into cohesive units. They provide a mechanism for managing the dependencies between different parts of an application.

- Create a module via the Angular CLI

  ```bash
  ng generate module <module-name>
  ```

- Create a component,  register it within a module, and add it to its exports property so that other modules can use it.

  - Angular CLI syntax

    ```bash
    ng generate component <module-name>/<component-name> --module=<module-name> --export
    ```  

  - Example

    ```bash
    ng generate component core/header --module=core --export
    ```  

    ```bash title="app/core/core.module.ts" hl_lines="3 13"
    import { NgModule } from '@angular/core';
    import { CommonModule } from '@angular/common';
    import { HeaderComponent } from './header/header.component';

    @NgModule({
      declarations: [
        HeaderComponent
      ],
      imports: [
        CommonModule
      ],
      exports: [
        HeaderComponent
      ]
    })

    export class CoreModule { }
    ```

  - Import the module into the AppModule to register the module globally in AppModule

    ```bash title="app.module.ts" hl_lines="6 17"
    import { NgModule } from '@angular/core';
    import { BrowserModule } from '@angular/platform-browser';

    import { AppRoutingModule } from './app-routing.module';
    import { AppComponent } from './app.component';
    import { CoreModule } from './core/core.module';


    @NgModule({
      declarations: [
        AppComponent,

      ],
      imports: [
        BrowserModule,
        AppRoutingModule,
        CoreModule

      ],
      providers: [],
      bootstrap: [AppComponent]
    })

    export class AppModule { }
    ```

#### Templates

TODO

#### Directives

TODO

#### Services

A service is a class that provides shared functionality or data to multiple components in your application. Services are used to centralize common functionality, such as data fetching from an API, sharing data between components, or performing utility operations.

- Create a service via Angular CLI

  ```bash
  ng generate service <service-name> 
  ```  

## References

- [HTML](https://developer.mozilla.org/docs/Learn/HTML)
- [JavaScript](https://developer.mozilla.org/docs/Web/JavaScript)
- [TypeScript](https://www.typescriptlang.org/)
- [Angular Tutorial for Beginners](https://www.youtube.com/watch?v=k5E2AVpwsko)