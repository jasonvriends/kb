# React

React is a popular JavaScript library for building user interfaces. It was developed by Facebook and released in 2013. React is often used in single-page applications and is known for its component-based architecture.

## Package Manager

### Node Package Manager

npm is a package manager for the JavaScript programming language and is primarily used for managing dependencies in Node.js projects. npm allows developers to easily install, update, and remove packages or libraries in their projects.

- Install npm via command line

    ```bash
    sudo dnf install npm -y
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
    ```

#### Material UI package

- Install [Material UI](https://mui.com/material-ui/getting-started/installation/)

    ```bash
    npm install @mui/material @emotion/react @emotion/styled @mui/icons-material @mui/x-data-grid
    ```

### React Components

Components are independent and reusable bits of code. They serve the same purpose as JavaScript functions, but work in isolation and return HTML. Components come in two types: ^^Class^^ components and ^^Function^^ components. It's recommended to use Functional Components for new React applications.

=== "Function"

    ```jsx title="Car.js"
    function Car() {
      return <h2>Hi, I am a Car!</h2>;
    }
    ```

=== "Class"

    ```jsx title="Car.js"
    class Car extends React.Component {
      render() {
        return <h2>Hi, I am a Car!</h2>;
      }
    }
    ```


#### Fragments

In a component, you can only return one HTML element (i.e., H1). In order to return multiple HTML elements, you can either nest them inside a DIV or use a React Fragment.

=== "Shortform"

    ```jsx hl_lines="3 5"
    function ListGroup() {
      return (
        <>
          <h1>List Group</h1>
        </>
      );
    }
    
    export default ListGroup;
    ```

=== "Longform"

    ```jsx hl_lines="1 5 7"
    import { Fragment } from "react";
    
    function ListGroup() {
        return (
            <Fragment>
            <h1>List Group</h1>
            </Fragment>
        );
    }
    
    export default ListGroup
    ```

=== "Div"

    ```jsx hl_lines="3 5"
    function ListGroup() {
        return (
            <div>
              <h1>List Group</h1>
            </div>
        );
    }
    
    export default ListGroup
    ```

## React Router

React Router is a popular library for handling routing in React applications. It allows you to create declarative routing in your React components, enabling navigation between different pages or views within your application.

- Install [React Router](https://reactrouter.com/en/main)

    ```bash
    npm install react-router-dom
    ```

## References

- [Learn HTML and CSS](https://scrimba.com/learn/htmlandcss)
- [Learn JavaScript](https://scrimba.com/learn/learnjavascript)
- [Learn React](https://scrimba.com/learn/learnreact)
- [Learn React Router](https://scrimba.com/learn/reactrouter6)