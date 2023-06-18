# Python

Python is an easy-to-learn, versatile, and interpreted programming language with a simple syntax and a large standard library. It supports multiple programming paradigms and is cross-platform, making it a popular choice for developers worldwide.

## Virtual Environment

A Python virtual environment is a self-contained directory that contains a specific version of Python interpreter and any necessary dependencies for a particular project. It allows you to create an isolated environment for each project, so you can work on multiple projects with different dependencies without any conflicts.

The venv module is a built-in module in Python that provides support for creating and managing virtual environments. The venv module was introduced in Python 3.3 as a replacement for the older virtualenv package. It is used to create a new Python environment that includes its own installation of Python, pip, and other required libraries.

- Create a Python Virtual Environment

  ```bash
  python3.11 -m venv .venv
  ```

- Activate the Python Virtual Environment

  ```bash
  source .venv/bin/activate
  ```

## Package Manager

### Pip

pip is the package installer for Python, which is used to install, manage, and uninstall Python packages and their dependencies. It is a command-line tool that comes with Python and is used to install third-party libraries and modules that are not included in the standard library.

- Upgrade pip

  ```bash
  pip install --upgrade pip
  ```

- Install packages via command line

  ```bash
  pip install package1 package2
  ```

- Install packages via file

  ```bash title="requirements.txt"
  package1
  package2
  ```

  ```bash
  pip install -r requirements.txt
  ```

### Poetry

Poetry is arguably the most feature-rich dependency management tool for Python. It comes with a powerful CLI used for creating and managing Python projects.

- Install Poetry

  ```bash
  sudo curl -sSL https://install.python-poetry.org | python3.10 -
  ```

- Scaffold a new project

  ```bash
  poetry new sample-project
  cd sample-project
  ```

Dependencies are managed inside the `pyproject.toml` file.

- To add new a dependency, simply run:

  ```bash
  poetry add package1
  ```

### Pipenv

Pipenv attempts to solve the same problems that Poetry does:

- Managing dependencies and virtual environments
- Reproducing environments

- Install Poetry

  ```bash
  sudo dnf install python3-pip -y
  sudo pip3 install pipenv
  ```

- Scaffold a new project

  ```bash
  mkdir sample-project
  cd sample-project
  PYTHON_VERSION=$(python3.10 --version | awk '{print $2}')
  pipenv --python $PYTHON_VERSION
  ```

- To add new a dependency, simply run:

  ```bash
  pipenv install package1
  ```

## Visual Studio Code

Visual Studio Code is a popular code editor for Python developers, offering features such as syntax highlighting, code completion, code refactoring, debugging, and support for virtual environments. It also has a rich ecosystem of extensions, including those specifically designed for Python development, such as linters, test runners, and code formatters.

### Python Extension

A Visual Studio Code extension with rich support for the Python language (for all actively supported versions of the language: >=3.7), including features such as IntelliSense (Pylance), linting, debugging, code navigation, code formatting, refactoring, variable explorer, test explorer, and more!

- Install [Python extension for Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-python.python)

### black

Black is a popular Python code formatter that automatically formats your code according to a set of predefined rules. It is designed to improve the readability and maintainability of your code by enforcing a consistent style, such as the use of consistent indentation, line lengths, and spacing. Black uses a "blackened" style that is intended to be opinionated but also widely accepted and easy to read. It can be integrated into your development workflow through a command-line interface, IDE plugins, or pre-commit hooks.

!!! tip

    Be sure to create and activate a Python virtual environment before installing black.

- Install the black Python package via command line

  ```bash
  pip install black
  ```

- Type the ++ctrl++ `+`, or ++cmd++ `+`, to open the settings page in the VSCode.

- Search for ^^format on save^^ and check the checkbox.

- Search for ^^python formatting provider^^ and select the ^^black^^.

Now, if you open the python file and save, it will be auto formatted by the black!

### isort

isort is a Python library and command-line utility for sorting and organizing import statements in Python code. It analyzes your code to find import statements and automatically sorts them according to a specified style, such as alphabetical order or grouping by package. isort can also remove unused imports and automatically split long import statements into multiple lines, making your code more readable and organized. It integrates with various text editors and IDEs and can be used as a pre-commit hook to ensure consistent import formatting across a project. Overall, isort can save time and improve code maintainability by automatically handling one of the more tedious and error-prone aspects of Python coding.

!!! tip

    Visual Studio Code already has the built-in function to use isort so that we don't need to install it by pip.

- Type ++ctrl+shift+p++ or ++cmd+shift+p++

- Search for ^^Preferences: Configure Language Specific Settings^^ and press enter.

- Select ^^Python^^. It will open the ^^settings.json^^.

- Please add the following settings:

```
"editor.codeActionsOnSave": {
    "source.organizeImports": true
}
```

### flake8

Flake8 is a popular Python linter that checks Python code for style and syntax errors. It combines three tools: PyFlakes, a static analysis tool for detecting errors in Python code; pycodestyle (formerly known as pep8), a tool for enforcing the Python style guide; and McCabe complexity checker, which checks for overly complex code. Flake8 is highly configurable and can be customized with plugins, which allows it to be adapted to a wide range of projects and development workflows. By detecting errors and enforcing a consistent code style, Flake8 can help improve code quality, reduce errors, and make code more maintainable. It can be integrated into various text editors and IDEs, and is often used as a pre-commit hook to ensure code quality is maintained throughout a project.

!!! tip

    Be sure to create and activate a Python virtual environment before installing flake8.

- Install the flake8 Python package via command line

  ```bash
  pip install flake8
  ```

- Type ++ctrl+shift+p++ or ++cmd+shift+p++

- Search for ^^Python: Select Linter^^ and press enter.

- Select ^^flake8^^.

Linting runs automa.Linting runs automatically when you save a file.

## References

- [Learn Python](https://scrimba.com/learn/python)
