# Windows Subsystem for Linux

The Windows Subsystem for Linux (WSL) is a feature of the Windows operating system that enables you to run a Linux file system, along with Linux command-line tools and GUI apps, directly on Windows, alongside your traditional Windows desktop and apps.

## Prerequisites

- x64 and Arm CPU
- Virtualization enabled in the UEFI/BIOS

## Installation

---

### Windows 10/11

- Open **PowerShell** or **Windows Command Prompt** in administrator mode by right-clicking and selecting **Run as administrator**.

- Enter `wsl --install` and press enter.

- Restart your machine.

### Windows Server 2019

- Open **PowerShell** in administrator mode by right-clicking and selecting **Run as administrator**.

- Enter `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux` and press enter.

- Enter `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart` and press enter.

- Download and run the [Linux kernel update package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi).

### Windows Server 2022

- Open **PowerShell** in administrator mode by right-clicking and selecting **Run as administrator**.

- Enter `wsl --install` and press enter.

- Restart your machine.

### Set WSL 2 as your default version

- Open **PowerShell** or **Windows Command Prompt** in administrator mode by right-clicking and selecting **Run as administrator**.

- Enter `wsl --set-default-version 2` and press enter.

### Distributions

You can browse the Microsoft Store for WSL distributions such as [Ubuntu](https://www.microsoft.com/store/productId/9PDXGNCFSCZV) or [AlmaLinux 9](https://www.microsoft.com/store/productId/9P5RWLM70SN9), or even [import any Linux distribution to use with WSL](https://learn.microsoft.com/en-us/windows/wsl/use-custom-distro).

## Using Visual Studio Code with WSL

---

Visual Studio Code, along with the Remote Development extension pack, enables you to use WSL as your full-time development environment directly from VS Code. You can:

- Develop in a Linux-based environment
- Use Linux-specific toolchains and utilities
- Run and debug your Linux-based applications from the comfort of Windows while maintaining access to productivity tools like Outlook and Office
- Use the VS Code built-in terminal to run your Linux distribution of choice
- Take advantage of VS Code features like Intellisense code completion, linting, debug support, code snippets, and unit testing
- Easily manage your version control with VS Code's built-in Git support
- Run commands and VS Code extensions directly on your WSL projects
- Edit files in your Linux or mounted Windows filesystem (for example /mnt/c) without worrying about pathing issues, binary compatibility, or other cross-OS challenges

### Install VS Code

- Visit the [VS Code install page](https://code.visualstudio.com/download) and select the 32 or 64 bit installer. Install Visual Studio Code on Windows (not in your WSL file system).

- When prompted to **Select Additional Tasks** during installation, be sure to check the **Add to PATH option** so you can easily open a folder in WSL using the code command.

### Install Remote Development extension pack

- Install the [Remote Development extension pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack). This extension pack includes the WSL extension, in addition to the Remote - SSH, and Dev Containers extensions, enabling you to open any folder in a container, on a remote machine, or in WSL.

### Open a WSL folder in VS Code

- To open a project from your WSL distribution, open the distribution's command line and enter: `code .`
