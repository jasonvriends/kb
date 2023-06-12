# Angular

Angular is a development platform, built on TypeScript. As a platform, Angular includes:

- A component-based framework (i.e., Model View Component or MVC) for building scalable web applications
- A collection of well-integrated libraries (i.e., routing, HTTP, validation, etc.) that cover a wide variety of features, including routing, forms management, client-server communication, and more
- A suite of developer tools (i.e., testing tools, build, run, etc.) to help you develop, build, test, and update your code

With Angular, you're taking advantage of a platform that can scale from single-developer projects to enterprise-level applications. Angular is designed to make updating as straightforward as possible, so take advantage of the latest developments with minimal effort. Best of all, the Angular ecosystem consists of a diverse group of over 1.7 million developers, library authors, and content creators.

## Prerequisites

---

### Knowledge

To develop applications using the Angular framework, a prerequisite is to possess a proficient understanding of HTML, CSS, JavaScript, and TypeScript. These fundamental web technologies form the building blocks for Angular development.

#### HTML

HyperText Markup Language (HTML) is a standard markup language used for creating web pages. It employs a set of tags and attributes to structure and present content on the web. HTML documents consist of elements enclosed in opening and closing tags, allowing the definition of headings, paragraphs, images, links, tables, forms, and more. [Learn HTML](https://developer.mozilla.org/docs/Learn/HTML)

#### CSS

Cascading Style Sheets (CSS) is a style sheet language used to define the visual appearance and presentation of HTML and XML documents. It allows web developers to separate the content and structure of a webpage from its design, enabling them to specify colors, fonts, spacing, positioning, and other visual properties. CSS works by selecting HTML elements and applying styles to them, either inline, within the HTML document, or in external CSS files. [Learn CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)

#### JavaScript

JavaScript is a versatile and widely used programming language that enables dynamic behavior and interactivity on web pages. It allows developers to create interactive elements, manipulate and modify content, handle events, and communicate with servers. JavaScript is primarily executed on the client-side, meaning it runs in the web browser, providing the ability to respond to user actions in real-time without requiring page reloads [Learn JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript)

#### TypeScript

TypeScript is a programming language that extends the capabilities of JavaScript by adding static typing to it. It provides developers with optional type annotations, which enable the specification of the data types of variables, function parameters, and return values. This allows for early error detection and improved code reliability. TypeScript code is transpiled into JavaScript, making it compatible with existing JavaScript environments and enabling developers to leverage modern JavaScript features while benefiting from the added type checking and enhanced tooling support offered by TypeScript. [Learn TypeScript](https://www.typescriptlang.org/)

### Environment & Tools

To develop applications using the Angular framework, you'll need a computer or laptop that meets the system requirements and has the necessary software, tools, and configurations to build, test, and debug Angular applications locally. This can be achieved through various means, such as using a physical machine, a Mac, or a virtual machine. For example, you can utilize [Windows Subsystem for Linux](https://thevriends.com/technology/operating-systems/windows/wsl/) running [AlmaLinux 9](https://thevriends.com/technology/operating-systems/linux/almalinux/) as the underlying operating system. WSL provides a compatibility layer that allows running Linux distributions on Windows, while AlmaLinux is a Linux distribution known for its stability and compatibility.

#### Node.js

Node.js is an open-source, server-side JavaScript runtime environment built on the Chrome V8 JavaScript engine. It allows developers to execute JavaScript code outside of a web browser, making it possible to run JavaScript on servers and build scalable and high-performance network applications. Node.js provides an event-driven, non-blocking I/O model that makes it efficient and suitable for handling concurrent requests. It also offers a rich set of built-in modules and a vast ecosystem of third-party libraries, enabling developers to easily create web servers, APIs, real-time applications, command-line tools, and more using JavaScript.

To install the latest version of Node.js on AlmaLinux 9:

```bash
sudo dnf install nodejs -y
```

#### NPM

Node Package Manager (NPM) is a package manager for JavaScript and Node.js. It is a command-line tool that simplifies the process of installing, managing, and sharing reusable code packages or modules. NPM allows developers to easily incorporate third-party libraries and frameworks into their projects, saving time and effort in writing code from scratch.

To install the latest version of NPM on AlmaLinux 9:

```bash
sudo dnf install npm -y
```

!!! warning annotate "Local vs global package scope"

    Local NPM packages are project-specific dependencies, confined to a particular directory, while global packages are installed at the system level and accessible across projects. Using the  `-g` command will configure the package scope to globhal thus use this with caution.

Update to the latest version of NPM on AlmaLinux 9:

```bash
sudo npm install -g npm@latest
```

List installed packages:

```bash
npm list
```

Install packge(s):

```bash
npm install <package> <package> <package>
```

Uninstall packge(s):

```bash
npm uninstall <package> <package> <package>
```

Update package(s):

```bash
npm update <package> <package> <package>
```

Clean and install project dependencies based on the `package-lock.json` file:

```bash
npm ci
```

#### Angular CLI

The Angular CLI (Command Line Interface) is a powerful tool that simplifies and automates various development tasks when working with the Angular framework. It provides a command-line interface for creating, managing, and building Angular projects effortlessly. The Angular CLI streamlines the process of generating components, services, modules, and other project structures, reducing manual effort and ensuring consistent code organization. It also facilitates quick scaffolding of boilerplate code, running tests, serving the application locally for development, and bundling the code for deployment. With its extensive set of commands and options, the Angular CLI enhances developer productivity and helps maintain best practices while working on Angular projects.

To install the [Angular CLI](https://angular.io/cli) NPM package globally on AlmaLinux 9:

```bash
npm install -g @angular/cli
```

To see what version of the Angular CLI you are using:

```bash
ng version
```

The Angular CLI is considered one of the highlights of the Angular framework, making it highly recommended to explore the [CLI Overview and Command Reference](https://angular.io/cli) for detailed information on its usage.

## Getting Started

---

### Angular workspace

!!! Note annotate "Angular versions"

    If you require a specific version of Angular, you have the option to utilize the `--version` switch. To illustrate, when working with Angular CLI and needing version 16.0.5, you can indicate this by specifying `--version=16.0.5`.

Create a new Angular workspace:

```bash
ng new <workspace-name>
```

- Would you like to add Angular routing? (y/N): ==Y==
- Which stylesheet format would you like to use? (Use arrow keys): ==CSS==

Navigate to your newly created Angular workspace directory:

```bash
cd <workspace-name>
```

Run your Angular application:

```bash
ng serve
```

Terminate your Angular application by pressing ++ctrl+c++.

### Folder and File Structure

The Angular CLI will create the following folder and file structure after executing the `ng new <workspace-name>` command:

```bash title="workspace-name"
.
├── README.md
├── angular.json
├── node_modules
├── package-lock.json
├── package.json
├── src
│   ├── app
│   │   ├── app-routing.module.ts
│   │   ├── app.component.css
│   │   ├── app.component.html
│   │   ├── app.component.spec.ts
│   │   ├── app.component.ts
│   │   └── app.module.ts
│   ├── assets
│   ├── favicon.ico
│   ├── index.html
│   ├── main.ts
│   └── styles.css
├── tsconfig.app.json
├── tsconfig.json
└── tsconfig.spec.json
```

The [Angular coding style guide](https://angular.io/guide/styleguide#!#application-structure-and-angular-modules) outlines an opinionated guide to Angular syntax, conventions, and application structure.

However, different projects will have different requirements, and the idea of one size fits all, like so many other things, simply wont always work. Have a near-term view of implementation and a long-term vision. Start small but keep in mind where the app is heading down the road.

The Angular CLI produces a workspace and a good suggested default layout. As such, we are mainly concerned about looking at the `src/app` folder, where all the actual logic is going to go.

####

### UI Frameworks

An Angular UI framework is a collection of pre-built user interface components, styles, and tools specifically designed to work seamlessly with Angular applications. These frameworks provide a set of reusable and customizable UI components that enable developers to quickly build interactive and visually appealing user interfaces for their Angular projects. Some popular Angular UI frameworks include [Angular Material](https://material.angular.io), [PrimeNG](https://primeng.org/), [Nebular](https://akveo.github.io/nebular/), and [Clarity](https://clarity.design/). I prefer using [Tailwind CSS](https://tailwindcss.com/) and [Flowbite](https://flowbite.com/). Below, I will provide instructions on how to integrate them into your Angular workspace.

#### Tailwind CSS

Install [Tailwind CSS with Angular](https://tailwindcss.com/docs/guides/angular):

```bash
npm install -D tailwindcss postcss autoprefixer
```

Initialize Tailwind CSS:

```bash
npx tailwindcss init
```

!!! note ""

    This command will create a default `tailwind.config.js` file in your workspace directory.

Configure content paths inside the `tailwind.config.js` file:

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

Add the Tailwind directives to your CSS:

```css title="./src/styles.css"
@tailwind base;
@tailwind components;
@tailwind utilities;
```

#### Flowbite

Install the [Flowbite](https://flowbite.com/docs/getting-started/quickstart/) NPM package:

```bash
npm install flowbite
```

Configure Tailwind CSS to use Flowbite:

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

Add the Stylesheet and JavaScript code that powers Flowbite:

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

Angular applications are constructed using various fundamental elements such as Components, Templates, Directives, Pipes, and Services. These building blocks are essential in creating comprehensive applications. However, as the size of the application expands, it becomes challenging to manage and organize these blocks effectively. This is where Angular modules, also known as ngModules, come into play.

#### Modules

Angular Modules are utilized to group and consolidate related Components, Templates, Directives, Pipes, and Services, enabling cohesive units and managing dependencies between different parts of an application. To organize modules effectively, it is recommended to categorize them into four distinct categories:

##### Root Module

Angular requires one module to be loaded as the application starts. We call this as root module. The root module loads the root component and all other modules. The root module is conventionally called `AppModule` and created in the root of the `/src/app` folder.

##### Feature Module

The Feature module implements a specific feature of the Application. All the Components, Templates, Directives, Pipes, and Services which comprise of the feature become part of the module.

##### Shared Module

There are many Components, Templates, Directives, Pipes, and Services we may like to share across various modules. All these items should go into the shared module.

##### Core Module

- Create a module via the Angular CLI

  ```bash
  ng generate module <module-name>
  ```

- Create a component, register it within a module, and add it to its exports property so that other modules can use it.

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

#### Components

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML.

- Create a component with the CLI

  ```bash
  ng generate component <component-name>
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

- [Angular Tutorial for Beginners](https://www.youtube.com/watch?v=k5E2AVpwsko)

### Tutorials

- [Angular Basics](https://www.fabiobiondi.dev/tutorials/angular/angular-basics/1-angular-hello-world)
- [Core Module and Navigation Bar](https://www.fabiobiondi.dev/tutorials/angular/angular-ng-modules-and-router/2-core-module-and-navbar)
- [Create a simple CRUD app](https://www.fabiobiondi.dev/tutorials/angular/simple-crud-in-angular/3-template-driven-forms)
- [Create an application with ngModules and nested routes](https://www.fabiobiondi.dev/tutorials/angular/angular-ng-modules-and-router/1-create-the-project)
- [Create a Project with Standalone Components and Routing](https://www.fabiobiondi.dev/tutorials/angular/angular-standalone-apps)
- [Enable Type Checking](https://www.fabiobiondi.dev/tutorials/react/vite-and-vitest/1-react-vite-and-typescript)
