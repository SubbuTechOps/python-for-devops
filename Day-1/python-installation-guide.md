# Python Installation and Environment Setup Guide

This guide provides step-by-step instructions for installing Python and setting up a development environment on Windows, Linux, and macOS.

## Table of Contents
- [Windows Installation](#windows-installation)
- [macOS Installation](#macos-installation)
- [Linux Installation](#linux-installation)
- [Virtual Environments](#virtual-environments)
- [Package Management with pip](#package-management-with-pip)
- [IDEs and Code Editors](#ides-and-code-editors)
- [Troubleshooting](#troubleshooting)

## Windows Installation

### Method 1: Microsoft Store (Recommended for Beginners)
1. Open the Microsoft Store
2. Search for "Python"
3. Select the latest version (Python 3.12 or newer)
4. Click "Get" or "Install"
5. After installation, open Command Prompt and type `python --version` to verify

### Method 2: Official Installer
1. Visit [python.org/downloads](https://www.python.org/downloads/)
2. Download the latest Windows installer (64-bit recommended)
3. Run the installer
4. **Important**: Check "Add Python to PATH" during installation
5. Choose "Customize installation" if you want to change the install location
6. Complete the installation
7. Open Command Prompt and type `python --version` to verify

### Method 3: Chocolatey Package Manager
1. Install Chocolatey if not already installed (see [chocolatey.org](https://chocolatey.org/install))
2. Open PowerShell as Administrator
3. Run: `choco install python`
4. Open a new Command Prompt and type `python --version` to verify

## macOS Installation

### Method 1: Official Installer
1. Visit [python.org/downloads](https://www.python.org/downloads/)
2. Download the macOS installer
3. Run the installer package
4. Follow the installation wizard
5. Open Terminal and type `python3 --version` to verify

### Method 2: Homebrew (Recommended for Developers)
1. Install Homebrew if not already installed:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
2. Install Python:
   ```bash
   brew install python
   ```
3. Verify installation:
   ```bash
   python3 --version
   ```

### Note for macOS
macOS comes with Python 2 pre-installed. Always use `python3` command to ensure you're using Python 3.

## Linux Installation

### Ubuntu/Debian
1. Update package index:
   ```bash
   sudo apt update
   ```
2. Install Python:
   ```bash
   sudo apt install python3 python3-pip python3-venv
   ```
3. Verify installation:
   ```bash
   python3 --version
   ```

### Fedora
1. Install Python:
   ```bash
   sudo dnf install python3 python3-pip
   ```
2. Verify installation:
   ```bash
   python3 --version
   ```

### Arch Linux
1. Install Python:
   ```bash
   sudo pacman -S python python-pip
   ```
2. Verify installation:
   ```bash
   python --version
   ```

## Virtual Environments

Virtual environments allow you to create isolated spaces for Python projects, avoiding package conflicts.

### Creating and Using Virtual Environments
1. Create a virtual environment:
   ```bash
   # Windows
   python -m venv myenv

   # macOS/Linux
   python3 -m venv myenv
   ```

2. Activate the virtual environment:
   ```bash
   # Windows (Command Prompt)
   myenv\Scripts\activate

   # Windows (PowerShell)
   myenv\Scripts\Activate.ps1

   # macOS/Linux
   source myenv/bin/activate
   ```

3. Deactivate when done:
   ```bash
   deactivate
   ```

### Using Conda (Alternative)
1. Install Anaconda or Miniconda from [anaconda.com](https://www.anaconda.com/products/distribution)
2. Create a conda environment:
   ```bash
   conda create -n myenv python=3.10
   ```
3. Activate environment:
   ```bash
   conda activate myenv
   ```
4. Deactivate when done:
   ```bash
   conda deactivate
   ```

## Package Management with pip

Pip is Python's package installer.

### Basic pip Commands
```bash
# Install a package
pip install package_name

# Install specific version
pip install package_name==1.2.3

# Install from requirements file
pip install -r requirements.txt

# List installed packages
pip list

# Uninstall a package
pip uninstall package_name

# Upgrade a package
pip install --upgrade package_name

# Upgrade pip itself
pip install --upgrade pip
```

### Creating requirements.txt
```bash
# Generate from current environment
pip freeze > requirements.txt
```

## IDEs and Code Editors

### Popular Options
1. **VS Code**
   - Download from [code.visualstudio.com](https://code.visualstudio.com/)
   - Install the Python extension
   - Configure Python interpreter path (Ctrl+Shift+P → "Python: Select Interpreter")

2. **PyCharm**
   - Download Community (free) or Professional edition from [jetbrains.com/pycharm](https://www.jetbrains.com/pycharm/)
   - Set up project with appropriate Python interpreter

3. **Jupyter Notebook/Lab**
   - Install: `pip install jupyterlab notebook`
   - Run: `jupyter lab` or `jupyter notebook`

4. **IDLE** (comes with Python)
   - Simple built-in editor, good for beginners
   - Run with `idle` command after installation

## Troubleshooting

### Common Issues

#### Python Command Not Found
- Ensure Python is added to PATH
- On Windows, try using `py` instead of `python`
- On macOS/Linux, use `python3` instead of `python`

#### Permission Issues on Linux/macOS
- Use `sudo apt install` on Ubuntu
- For pip, use `pip3 install --user package_name` to install to user directory

#### Multiple Python Versions
- Use `python --version` and `python3 --version` to check installed versions
- Use version-specific commands like `python3.9` or `py -3.9` (Windows)
- Use virtual environments to isolate project dependencies

#### Path Issues with pip
- Try `python -m pip install package_name`
- On macOS/Linux: `python3 -m pip install package_name`

### Upgrading Python
- Windows: Download and install new version from python.org
- macOS: `brew upgrade python` (if installed via Homebrew)
- Linux: Use package manager (e.g., `sudo apt install python3.10`)

### Getting Help
- Official documentation: [docs.python.org](https://docs.python.org/)
- Stack Overflow: [stackoverflow.com/questions/tagged/python](https://stackoverflow.com/questions/tagged/python)
- Python community: [python.org/community](https://www.python.org/community/)
