# Angular

AngularJS is a JavaScript-based open-source framework developed by Google for building dynamic web applications. It is often referred to as "Angular 1" to distinguish it from later versions of Angular, such as Angular 2+.

## Package Manager

### Node Package Manager

npm is a package manager for the JavaScript programming language and is primarily used for managing dependencies in Node.js projects. npm allows developers to easily install, update, and remove packages or libraries in their projects.

- Install npm via command line

  ```bash
  sudo dnf install npm -y
  ```

- Updating npm

  ```bash
  sudo npm install -g npm
  ```

## Getting Started

### Angular CLI

- Install the [Angular CLI](https://angular.io/cli) package

  ```bash
  npm install -g @angular/cli
  ```

### Scaffold a new project

```bash
npm init @angular <project-name>
cd <project-name>
npm start
```

### UI Frameworks

#### Angular Material

- Install the [Angular Material](https://akveo.github.io/nebular/) package

  ```bash
  npm install @angular/material
  ```

#### Nebular

- Install the [Nebular](https://material.angular.io/) package

  ```bash
  npm install @nebular/theme @nebular/auth @nebular/security @nebular/moment @nebular/date-fns
  ```

- [NGX Admin](https://akveo.github.io/ngx-admin/)

#### Bootstrap

- Install the [Bootstrap]() package

  ```bash
  npm install bootstrap bootstrap-icons
  ```

  [ ] TODO: how to integrate it

### Components

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML.

- Create a component with the CLI

  ```bash
  ng generate component <component-name>
  ```

## References

- [HTML](https://developer.mozilla.org/docs/Learn/HTML)
- [JavaScript](https://developer.mozilla.org/docs/Web/JavaScript)
- [TypeScript](https://www.typescriptlang.org/)
- [Learn HTML and CSS](https://scrimba.com/learn/htmlandcss)
- [Learn JavaScript](https://scrimba.com/learn/learnjavascript)
