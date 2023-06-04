# React

React is a popular JavaScript library for building user interfaces. It was developed by Facebook and released in 2013. React is often used in single-page applications and is known for its component-based architecture.

## Prerequisites

### Package Manager

npm (comes pre-bundled with Node.js) or Yarn can be used to download and install **React** and **React DOM** packages along with component and other third-party libraries.

#### Npm

npm is the go-to package manager for the JavaScript ecosystem, providing a seamless solution for installing, managing, and uninstalling JavaScript packages and their dependencies. Serving as a command-line tool, npm comes bundled with Node.js and facilitates the effortless integration of third-party libraries and modules that extend the capabilities of JavaScript applications beyond the standard library.

- Install npm via command line
``` bash
sudo dnf install npm -y
```

#### Yarn

Yarn is a package manager for JavaScript that was introduced as an alternative to npm (Node Package Manager). It was created by Facebook, Exponent, Google, and Tilde to address some of the limitations and performance issues of npm.

- Install yarn via command line
``` bash
sudo npm install -g yarn
```

### Module Bundler

A module bundler is a tool used in web development to combine and package multiple modules or files into a single file, typically for use in a web application. It takes care of resolving dependencies, optimizing code, and creating a production-ready bundle that can be served to the browser.

#### Parcel

#### Webpack

#### Browserify

### Compiler

React itself is not compiled, Babel is commonly used to transform JSX syntax and modern JavaScript features into compatible code that can run in different browsers and environments.

## Frameworks

React is a versatile JavaScript library for building user interfaces, and it can be used with various frameworks and tools to enhance development efficiency and provide additional features. Here are some popular React frameworks and libraries.

### Vanilla

- Scaffold a new project
``` bash
npm init react-app app
```

### React-Admin

- Scaffold a new project
``` bash
npx create-react-admin@latest <project-name> --template typescript
```