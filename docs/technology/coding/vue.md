# Vue.js

Vue is an open-source JavaScript framework used for building user interfaces. It adopted some of the best practices from React and Angular. That said, compared to React and Angular, it's much more approachable, so beginners can get up and running quickly. It's also just as powerful, so it provides all the features you'll need to create modern front-end applications.

## Package Manager

npm is the go-to package manager for the JavaScript ecosystem, providing a seamless solution for installing, managing, and uninstalling JavaScript packages and their dependencies. Serving as a command-line tool, npm comes bundled with Node.js and facilitates the effortless integration of third-party libraries and modules that extend the capabilities of JavaScript applications beyond the standard library.

- Install npm via command line
``` bash
sudo dnf install npm -y
```

- Scaffold a new project
``` bash
npm create vue@3
```
    - Project name: **app**
    - Add TypeScript: **Yes**
    - Add JSX Support: **No**
    - Add Vue Router for Single Page Application development: **Yes**
    - Add Pinia for state management: **Yes**
    - Add Vitest for Unit Testing: **Yes**
    - Add an End-to-End Testing Solution: **Cypress**
    - Add ESLint for code quality: **Yes**
    - Add Prettier for code formatting: **Yes**


- Build the project
``` bash
cd app
npm install
npm run lint
npm run dev
```