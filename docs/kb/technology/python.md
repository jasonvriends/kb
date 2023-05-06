Python is an easy-to-learn, versatile, and interpreted programming language with a simple syntax and a large standard library. It supports multiple programming paradigms and is cross-platform, making it a popular choice for developers worldwide.

## Virtual Environment

A Python virtual environment is a self-contained directory that contains a specific version of Python interpreter and any necessary dependencies for a particular project. It allows you to create an isolated environment for each project, so you can work on multiple projects with different dependencies without any conflicts.

- Create a Python Virtual Environment
``` bash
python3.10 -m venv .venv
```

- Activate the Python Virtual Environment
``` bash
source .venv/bin/activate
```

## Package Manager

pip is the package installer for Python, which is used to install, manage, and uninstall Python packages and their dependencies. It is a command-line tool that comes with Python and is used to install third-party libraries and modules that are not included in the standard library.

- Upgrade pip
``` bash
pip install --upgrade pip
```

- Install packages via command line
``` bash
pip install package1 package2
```

- Install packages via file
``` bash title="requirements.txt"
package1
package2
```
``` bash
pip install -r requirements.txt
```
