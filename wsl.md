# Windows Subsystem for Linux

The Windows Subsystem for Linux (WSL) lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup. Its defacto standard for my development enviornment.

## Requirements

- Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11

## Deployment Instructions

- [Set up a WSL development environment](https://learn.microsoft.com/en-us/windows/wsl/setup/environment)

- Install [AlmaLinux 8](https://www.microsoft.com/store/productId/9NMD96XJJ19F) from the Microsoft Store.

### Update Packages
```
sudo dnf update -y
```

### Install Packages

Git
```
sudo dnf install git -y
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR EMAIL"
```

PowerShell
```
# Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/8/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

# Install PowerShell
sudo dnf install --assumeyes powershell
pwsh
```

Azure PowerShell
```
Install-Module -Name Az -Repository PSGallery -Force
```

Azure CLI
```
# For RHEL 8 or CentOS Stream 8, add packages-microsoft-com-prod repository:
sudo dnf install -y https://packages.microsoft.com/config/rhel/8/packages-microsoft-prod.rpm

# Install with the dnf install command
sudo dnf install azure-cli
```

Terraform
```
sudo yum install -y yum-utils
sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/RHEL/hashicorp.repo
sudo yum -y install terraform
```

## Known Issues

[Issues with Terraform and WSL: Unable to list provider registration status](https://manualbashing.github.io/posts/terraform-wsl/)