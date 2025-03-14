# Python Setup Guide for VS Code and PyCharm

This guide provides detailed instructions for setting up and configuring Visual Studio Code and PyCharm for Python development.

## Table of Contents
- [Visual Studio Code Setup](#visual-studio-code-setup)
  - [Installation](#vscode-installation)
  - [Python Extension](#python-extension)
  - [Configuring Python Interpreter](#configuring-python-interpreter-in-vs-code)
  - [Setting Up a Virtual Environment](#setting-up-a-virtual-environment-in-vs-code)
  - [Running and Debugging Python](#running-and-debugging-python-in-vs-code)
  - [Useful Extensions](#useful-vs-code-extensions-for-python-development)
  - [Settings and Customization](#vs-code-settings-and-customization)
- [PyCharm Setup](#pycharm-setup)
  - [Installation](#pycharm-installation)
  - [Creating a New Project](#creating-a-new-project-in-pycharm)
  - [Configuring Python Interpreter](#configuring-python-interpreter-in-pycharm)
  - [Setting Up a Virtual Environment](#setting-up-a-virtual-environment-in-pycharm)
  - [Running and Debugging Python](#running-and-debugging-python-in-pycharm)
  - [Useful Plugins](#useful-pycharm-plugins)
  - [Settings and Customization](#pycharm-settings-and-customization)
- [Comparing VS Code and PyCharm](#comparing-vs-code-and-pycharm)
- [Troubleshooting](#troubleshooting)

## Visual Studio Code Setup

### VSCode Installation

1. **Download and Install VS Code**:
   - Go to [code.visualstudio.com](https://code.visualstudio.com/)
   - Download the appropriate version for your operating system
   - Follow the installation instructions

2. **First-time Setup**:
   - Launch VS Code after installation
   - Familiarize yourself with the welcome screen and interface
   - VS Code will automatically detect and suggest extensions based on the files you open

### Python Extension

1. **Install the Python Extension**:
   - Open the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X`
   - Search for "Python"
   - Select the Python extension by Microsoft (usually the first result)
   - Click "Install"

2. **Additional Python Extensions** (optional but recommended):
   - Pylance (enhanced language support)
   - Python Docstring Generator
   - Python Test Explorer

### Configuring Python Interpreter in VS Code

1. **Select Python Interpreter**:
   - Press `Ctrl+Shift+P` (Windows/Linux) or `Cmd+Shift+P` (macOS) to open the Command Palette
   - Type "Python: Select Interpreter" and select the command
   - Choose your installed Python version from the list
   - If your desired interpreter isn't listed, click "Enter interpreter path..." and browse to the Python executable

2. **Verify Selected Interpreter**:
   - Look at the status bar at the bottom of VS Code
   - You should see the selected Python version (e.g., "Python 3.10.x")
   - Click on this indicator to change interpreters at any time

### Setting Up a Virtual Environment in VS Code

1. **Create a Virtual Environment**:
   - Open a terminal in VS Code (`Terminal > New Terminal`)
   - Navigate to your project directory
   - Create a virtual environment:
     ```bash
     # Windows
     python -m venv .venv

     # macOS/Linux
     python3 -m venv .venv
     ```

2. **Activate the Virtual Environment**:
   - VS Code should detect the new environment and prompt you to use it
   - Or select it manually using "Python: Select Interpreter"
   - Terminal activation commands:
     ```bash
     # Windows
     .venv\Scripts\activate

     # macOS/Linux
     source .venv/bin/activate
     ```

3. **Install Packages in the Virtual Environment**:
   ```bash
   pip install package_name
   ```

### Running and Debugging Python in VS Code

1. **Running Python Files**:
   - Open a Python file
   - Click the "Run" button (▶️) in the top-right corner of the editor
   - Alternatively, right-click in the editor and select "Run Python File in Terminal"
   - Or use the keyboard shortcut `Ctrl+F5` (Windows) or `Ctrl+F5` (macOS)

2. **Debugging**:
   - Set breakpoints by clicking in the gutter (left margin) of the code editor
   - Press `F5` to start debugging
   - Use the debug toolbar to step through, step over, and step out of functions
   - Inspect variables in the Variables panel

3. **Configure Launch Settings**:
   - Create or modify `.vscode/launch.json` for custom run configurations
   - Example configuration:
     ```json
     {
         "version": "0.2.0",
         "configurations": [
             {
                 "name": "Python: Current File",
                 "type": "python",
                 "request": "launch",
                 "program": "${file}",
                 "console": "integratedTerminal",
                 "justMyCode": true
             }
         ]
     }
     ```

### Useful VS Code Extensions for Python Development

1. **Python-specific**:
   - **Pylance**: Enhanced type checking and IntelliSense
   - **Python Docstring Generator**: Automatic docstring generation
   - **Python Test Explorer**: Visual interface for tests
   - **Jupyter**: For working with Jupyter notebooks

2. **General Development**:
   - **GitLens**: Enhanced Git integration
   - **Code Spell Checker**: Catches common spelling errors
   - **indent-rainbow**: Makes indentation more visible
   - **Path Intellisense**: Autocompletes filenames

### VS Code Settings and Customization

1. **Python-specific Settings**:
   - Open settings (`Ctrl+,` or `Cmd+,`)
   - Search for Python-related settings
   - Common settings to adjust:
     ```json
     {
         "python.linting.enabled": true,
         "python.linting.pylintEnabled": true,
         "python.formatting.provider": "black",
         "python.formatting.blackArgs": ["--line-length", "88"],
         "editor.formatOnSave": true,
         "python.analysis.typeCheckingMode": "basic"
     }
     ```

2. **Setup Code Linting**:
   - Install a linter: `pip install pylint`
   - VS Code will use the installed linter automatically
   - Customize linting rules in a `.pylintrc` file or settings

3. **Setup Code Formatting**:
   - Install a formatter: `pip install black`
   - Configure VS Code to use it as shown above
   - Format document with `Shift+Alt+F` (Windows/Linux) or `Shift+Option+F` (macOS)

## PyCharm Setup

### PyCharm Installation

1. **Download PyCharm**:
   - Go to [jetbrains.com/pycharm/download](https://www.jetbrains.com/pycharm/download/)
   - Choose Community (free) or Professional (paid) edition
   - Download the appropriate version for your operating system

2. **Install PyCharm**:
   - Run the installer and follow the installation wizard
   - For macOS, drag the PyCharm app to the Applications folder
   - For Linux, extract the tarball and run the script in the bin directory

3. **First Launch Configuration**:
   - Start PyCharm
   - Choose UI theme and default plugins
   - Optionally sign in with JetBrains account for settings sync

### Creating a New Project in PyCharm

1. **Start a New Project**:
   - Click "New Project" on the welcome screen
   - Choose project location and name
   - Select the project type (Pure Python, Django, Flask, etc.)

2. **Project Structure**:
   - PyCharm will create a project with a default structure
   - View the project structure in the Project tool window (left side)

### Configuring Python Interpreter in PyCharm

1. **Configure the Interpreter**:
   - Go to `File > Settings` (Windows/Linux) or `PyCharm > Preferences` (macOS)
   - Navigate to `Project: [ProjectName] > Python Interpreter`
   - Click the gear icon and select "Add..."
   - Choose "System Interpreter" and select your Python installation
   - Or choose "Conda Environment" or "Virtualenv Environment" for isolated development

2. **View Installed Packages**:
   - In the interpreter settings, view installed packages
   - Use the "+" button to install new packages
   - Use the refresh button to update the package list

### Setting Up a Virtual Environment in PyCharm

1. **Create a Virtual Environment During Project Creation**:
   - When creating a new project, select "New environment using" option
   - Choose "Virtualenv" or "Conda" as the environment type
   - Specify the location and base interpreter

2. **Add Virtual Environment to an Existing Project**:
   - Go to `File > Settings > Project > Python Interpreter`
   - Click the gear icon and select "Add..."
   - Choose "Virtualenv Environment"
   - Select "New environment" and configure location and base interpreter
   - Click "OK" to create and activate it

3. **Install Packages in the Virtual Environment**:
   - Use the "+" button in the interpreter settings
   - Search for and install packages
   - PyCharm will install them in the active virtual environment

### Running and Debugging Python in PyCharm

1. **Running Python Files**:
   - Open a Python file
   - Right-click in the editor and select "Run 'filename'"
   - Or use the green "Run" button in the toolbar
   - Or use the keyboard shortcut `Shift+F10` (Windows/Linux) or `Ctrl+R` (macOS)

2. **Debugging**:
   - Set breakpoints by clicking in the gutter (left margin)
   - Right-click and select "Debug 'filename'"
   - Or use the green "Debug" button
   - Or use the keyboard shortcut `Shift+F9` (Windows/Linux) or `Ctrl+D` (macOS)
   - Use the debug toolbar to control execution
   - Inspect variables in the Variables panel

3. **Run Configurations**:
   - Go to `Run > Edit Configurations`
   - Create and customize run configurations for different files or projects
   - Set command-line parameters, environment variables, and working directory

### Useful PyCharm Plugins

1. **Installed by Default**:
   - Git Integration
   - Markdown support
   - Python Console

2. **Recommended Additional Plugins**:
   - **Pylint**: Enhanced code inspection
   - **CSV Plugin**: For working with CSV files
   - **Requirements**: Manage requirements.txt files
   - **Rainbow Brackets**: Color-coded matching brackets
   - **Key Promoter X**: Learn keyboard shortcuts

### PyCharm Settings and Customization

1. **Code Style Settings**:
   - Go to `File > Settings > Editor > Code Style > Python`
   - Customize indentation, spaces, tabs, and more
   - Import code style from popular frameworks (PEP 8, Google, etc.)

2. **Editor Settings**:
   - Go to `File > Settings > Editor > General`
   - Configure auto-save, soft-wraps, coding assistance

3. **External Tools Integration**:
   - Configure tools like Black, isort, mypy
   - Go to `File > Settings > Tools > External Tools`
   - Add custom tools with appropriate arguments

## Comparing VS Code and PyCharm

### VS Code Advantages:
- Lightweight and fast
- Free and open-source
- Highly customizable with extensions
- Great for multi-language projects
- Lower memory footprint

### PyCharm Advantages:
- More Python-specific features out of the box
- Integrated tools for code refactoring
- Enhanced Django/Flask support (Professional edition)
- Database tools and SQL support (Professional edition)
- Deeper code analysis

### Performance Considerations:
- VS Code is better for smaller machines or simpler projects
- PyCharm offers more features but requires more system resources
- PyCharm has a more comprehensive indexing system that improves over time

## Troubleshooting

### Common VS Code Issues:

1. **Python Extension Not Detecting Interpreter**:
   - Manually specify the interpreter path
   - Check if Python is installed correctly
   - Verify PATH environment variable

2. **Linting or Formatting Not Working**:
   - Ensure linters/formatters are installed in the active environment
   - Check VS Code settings for enabled linters
   - Verify paths to executables

### Common PyCharm Issues:

1. **High CPU/Memory Usage**:
   - Increase IDE memory allocation in `Help > Change Memory Settings`
   - Reduce the scope of project indexing
   - Disable plugins you don't use

2. **Interpreter Not Found or Package Installation Failed**:
   - Verify Python installation
   - Check network connectivity for package downloads
   - Ensure sufficient permissions for the environment directory

3. **Project Indexing Takes Too Long**:
   - Exclude large directories from indexing
   - Mark directories as "Excluded" in project structure
