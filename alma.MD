# AlmaLinux 9

An Open Source, community owned and governed, forever-free enterprise Linux distribution, focused on long-term stability, providing a robust production-grade platform. AlmaLinux OS is 1:1 binary compatible with RHEL® and pre-Stream CentOS.

## Updates

- Check for available package updates ``sudo dnf check-update -y``

- Install a specific package update ``sudo update package-name -y``

- Upgrade all of your system software ``sudo dnf update -y``

- Enable automatic security updates
  ```
  sudo dnf install dnf-automatic -y
  sudo sed -i "s/apply_updates = no/apply_updates = yes/" /etc/dnf/automatic.conf
  sudo systemctl enable --now dnf-automatic.timer
  ```

## Software

### Git

- Install ``sudo dnf install git -y``

- Configure
  ```
  git config --global user.name "your git username"
  git config --global user.email "email for git account"
  ```
  
### Python 3.10
  
- Prerequisites
  ```
  sudo dnf install wget yum-utils make gcc openssl-devel bzip2-devel libffi-devel zlib-devel -y
  sudo dnf update -y
  ```
  
- Install
  ```
  wget https://www.python.org/ftp/python/3.10.5/Python-3.10.5.tgz
  tar xzf Python-3.10.5.tgz 
  cd Python-3.10.5
  ./configure --with-system-ffi --with-computed-gotos --enable-loadable-sqlite-extensions 
  sudo make -j ${nproc} 
  sudo make altinstall 
  ```

### Podman

- Prerequisites ``sudo dnf install epel-release -y``

- Install ``sudo dnf install podman podman-compose -y``

### Azure CLI

- Prerequisites ``sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc``

- Install ``sudo dnf install -y https://packages.microsoft.com/config/rhel/9.0/packages-microsoft-prod.rpm -y``

### Terraform 

- Prerequisites ``sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo -y``

- Install ``sudo dnf install terraform -y``

### Utilities
  
- Tree ``sudo dnf install tree -y``
