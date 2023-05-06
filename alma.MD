# AlmaLinux 9

An Open Source, community owned and governed, forever-free enterprise Linux distribution, focused on long-term stability, providing a robust production-grade platform. AlmaLinux OS is 1:1 binary compatible with RHEL® and pre-Stream CentOS.

## Updates

- Check for available package updates ``dnf check-update``

- Install a specific package update ``update package-name``

- Upgrade all of your system software ``dnf update``
  
## Software

### Git

- Install ``dnf install git``

- Configure
  ```
  git config --global user.name "your git username"
  git config --global user.email "email for git account"
  ```
  
### Python 3.10
  
- Prerequisites
  ```
  dnf install wget yum-utils make gcc openssl-devel bzip2-devel libffi-devel zlib-devel
  dnf update
  ```
  
- Install
  ```
  wget https://www.python.org/ftp/python/3.10.5/Python-3.10.5.tgz
  tar xzf Python-3.10.5.tgz 
  cd Python-3.10.5
  ./configure --with-system-ffi --with-computed-gotos --enable-loadable-sqlite-extensions 
  make -j ${nproc} 
  make altinstall 
  ```

### Podman

- Prerequisites ``dnf install epel-release``

- Install ``dnf install podman podman-compose``

### Azure CLI

- Prerequisites ``rpm --import https://packages.microsoft.com/keys/microsoft.asc``

- Install ``dnf install -y https://packages.microsoft.com/config/rhel/9.0/packages-microsoft-prod.rpm``

### Terraform 

- Prerequisites ``yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo``

- Install ``dnf install terraform``

### Utilities
  
- Tree ``dnf install tree``
