# Developer Cheat Sheet

## Mac Setup — Done Once
- `xcode-select --install` → Installs Apple's developer tools
- `brew install python` → Installs Python via Homebrew
- `brew install git` → Installs Git
- `git config --global user.name "Name"` → Sets your Git identity
- `git config --global user.email "email"` → Sets your Git email

## Starting a New Project — Every Time
- `mkdir ~/Developer/project-name` → Creates a new project folder
- `cd ~/Developer/project-name` → Navigates into the folder
- `python3 -m venv venv` → Creates a virtual environment
- `source venv/bin/activate` → Activates the virtual environment
- `echo "venv/" > .gitignore` → Creates .gitignore to exclude venv
- `git init` → Starts Git tracking in the folder

## Daily Git Workflow
- `git add .` → Stages all changed files
- `git commit -m "message"` → Saves a snapshot with a description
- `git status` → Shows what files have changed
- `git log` → Shows full commit history
- `deactivate` → Deactivates the virtual environment

## VS Code Shortcuts
- `Command + N` → New file
- `Command + S` → Save file
- `Command + Shift + X` → Open extensions
- `Command + Shift + P` → Open command palette
- `code filename` → Open a file in VS Code from terminal