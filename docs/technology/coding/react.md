# React

React is a popular JavaScript library for building user interfaces. It was developed by Facebook and released in 2013. React is often used in single-page applications and is known for its component-based architecture.

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

### Yarn

Yarn is a package manager for JavaScript that was introduced as an alternative to npm. It was created by Facebook, Exponent, Google, and Tilde to address some of the limitations and performance issues of npm.

- Install yarn via command line

  ```bash
  sudo npm install -g yarn
  ```

## Getting Started

### Scaffold a new project

[Create React App](https://create-react-app.dev/) and [Vite](https://vitejs.dev/guide/) (my preference) are two of the most popular methods for scaffolding new React projects.

#### Create React App

```bash
npx create-react-app <project-name>
```

#### Vite

```bash
npm create vite@latest
```

### UI Frameworks

#### Bootstrap

- Install the [Bootstrap](https://getbootstrap.com/) package

  ```bash
  npm install bootstrap
  ```

- Import the Bootstrap object

  ```jsx title="main.tsx"
  import 'bootstrap/dist/css/bootstrap.css'
  import 'bootstrap/dist/js/bootstrap.bundle.min'
  ```

#### Material UI

- Install [Material UI](https://mui.com/material-ui/getting-started/installation/)

  ```bash
  npm install @mui/material @emotion/react @emotion/styled @mui/icons-material @mui/x-data-grid
  ```

#### Flowbite React

- Install the [Flowbite React](https://www.flowbite-react.com/) package

  ```bash
  npm install flowbite flowbite-react
  ```

- [Flowbite Integration](https://flowbite.com/docs/getting-started/react/)

- [Admin Dashboard](https://github.com/themesberg/flowbite-admin-dashboard)

### Styling and CSS

React uses `className` instead of `class` is because `class` is a reserved keyword in JavaScript, and JSX (the syntax extension used by React) is essentially JavaScript code. JSX allows you to write HTML-like code within JavaScript, but since `class` has a specific meaning in JavaScript (used for defining classes), it cannot be used as an attribute name in JSX.

```jsx
render() {
  return <span className="menu navigation-menu">Menu</span>
}
```

### Components

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML.

```jsx title="Navbar.js"
const Navbar = () => {
  return <>{/* Your navbar content goes here */}</>
}

export default Navbar
```

## React Router

React Router is a popular library for handling routing in React applications. It allows you to create declarative routing in your React components, enabling navigation between different pages or views within your application.

- Install [React Router](https://reactrouter.com/en/main)

  ```bash
  npm install react-router-dom
  ```

## References

- [HTML](https://developer.mozilla.org/docs/Learn/HTML)
- [JavaScript](https://developer.mozilla.org/docs/Web/JavaScript)
- [TypeScript](https://www.typescriptlang.org/)
- [Learn HTML and CSS](https://scrimba.com/learn/htmlandcss)
- [Learn JavaScript](https://scrimba.com/learn/learnjavascript)
- [Learn React](https://scrimba.com/learn/learnreact)
- [React Tutorial for Beginners](https://www.youtube.com/watch?v=SqcY0GlETPk)
- [Learn React Router](https://scrimba.com/learn/reactrouter6)
