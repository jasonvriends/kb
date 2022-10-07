# Update all packages
sudo dnf update -y

# Install Git

sudo dnf install git -y

# Configure Git

git config --global user.name "YOUR NAME"
git config --global user.email "YOUR EMAIL"

# Install PowerShell

## Register the Microsoft RedHat repository
curl https://packages.microsoft.com/config/rhel/8/prod.repo | sudo tee /etc/yum.repos.d/microsoft.repo

## Install PowerShell
sudo dnf install --assumeyes powershell