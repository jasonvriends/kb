# AlmaLinux 9

An Open Source, community owned and governed, forever-free enterprise Linux distribution, focused on long-term stability, providing a robust production-grade platform. AlmaLinux OS is 1:1 binary compatible with RHEL® and pre-Stream CentOS.

## Updates

- Check for available package updates
``` bash
sudo dnf check-update -y
```

- Install a specific package update
``` bash
sudo update package-name -y
```

- Upgrade all of your system software
``` bash
sudo dnf update -y
```

- Enable automatic security updates
``` bash
sudo dnf install dnf-automatic -y
sudo sed -i "s/apply_updates = no/apply_updates = yes/" /etc/dnf/automatic.conf
sudo systemctl enable --now dnf-automatic.timer
```

## Software

### Git

A distributed version control system that allows multiple people to collaborate on a project by tracking changes to files and coordinating their work. It enables developers to create branches, make modifications, merge changes, and handle conflicts efficiently. Git is widely used in software development to manage source code and maintain a history of changes.

- Install
``` bash
sudo dnf install git -y
```

- Configure
``` bash
git config --global user.name "your git username"
git config --global user.email "email for git account"
```
  
### Python 3.10
  
A high-level, interpreted programming language known for its simplicity and readability. It emphasizes code readability and offers a wide range of libraries and frameworks that make it versatile for various applications. Python supports multiple programming paradigms, including procedural, object-oriented, and functional programming. It is widely used for web development, data analysis, scientific computing, artificial intelligence, and automation tasks.

- Prerequisites
``` bash
sudo dnf install wget yum-utils make gcc openssl-devel bzip2-devel libffi-devel zlib-devel -y
sudo dnf update -y
```
  
- Install
``` bash
wget https://www.python.org/ftp/python/3.10.5/Python-3.10.5.tgz
tar xzf Python-3.10.5.tgz 
cd Python-3.10.5
./configure --with-system-ffi --with-computed-gotos --enable-loadable-sqlite-extensions 
sudo make -j ${nproc} 
sudo make altinstall 
```

### Podman

A containerization platform that allows users to manage and run containers on a Linux system. It provides a command-line interface (CLI) for creating, running, and managing containers, similar to Docker. However, Podman offers some advantages over Docker, such as running containers without requiring a daemon process, supporting rootless mode, and providing a more secure and isolated container runtime environment.

- Prerequisites 
``` bash
sudo dnf install epel-release -y
```

- Install
``` bash
sudo dnf install podman podman-compose -y
```

### Azure CLI

A cross-platform command-line tool provided by Microsoft for managing and interacting with Azure resources. It allows users to manage and automate various Azure services and resources through a command-line interface rather than a graphical user interface (GUI). Azure CLI provides a set of commands and parameters that can be used to perform operations such as creating and managing virtual machines, deploying applications, managing storage accounts, configuring networking, and more. It is available for Windows, macOS, and Linux platforms and supports scripting and automation.

- Prerequisites
``` bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```

- Install
``` bash
sudo dnf install -y https://packages.microsoft.com/config/rhel/9.0/packages-microsoft-prod.rpm -y

sudo dnf install azure-cli -y
```

### Terraform 

An open-source infrastructure-as-code tool used for provisioning and managing cloud infrastructure resources. It allows you to define and create infrastructure components such as virtual machines, storage, and networks using declarative configuration files. Terraform supports multiple cloud providers, including AWS, Azure, and Google Cloud Platform, enabling you to manage your infrastructure in a consistent and reproducible manner.

- Prerequisites
``` bash
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo -y
```

- Install
``` bash
sudo dnf install terraform -y
```

### Utilities
  
- Tree

A command-line utility that displays the directory structure of a file system in a tree-like format. It shows the hierarchy of directories and their subdirectories, along with the files contained within them. The tree command helps users visualize the organization of files and directories on their system.

``` bash
sudo dnf install tree -y
```
