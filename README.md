# ACIT-2420 Assignment 2: Shell Scripting

## Introduction
This repository contains shell scripts designed to automate system setup and user management tasks. The project aims to demonstrate shell scripting skills essential for system administration, focusing on package installation, configuration management, and user creation.

## Project Structure
```
.
├── README.md
├── project1
│   ├── bin
│   │   ├── sayhi
│   │   └── install-fonts
│   ├── config
│   │   ├── kak
│   │   │   └── kakrc
│   │   └── tmux
│   │       └── tmux.conf
│   ├── home
│   │   └── bashrc
│   ├── main_script
│   ├── install_script
│   ├── packages
│   └── symlinks_script
├── project2
│   └── create_user_script
└── utils
    └── verify_root
```

## Project 1: System Configuration

### Overview
This project automates the initial setup of a new system by handling package installation and configuration file management. It's designed to save time when setting up new systems by automating repetitive tasks.

**Required Packages:**
- kakoune
- tmux

### Components
1. `main_script`: Runs both installation and symlink scripts to complete the setup
2. `install_script`: Installs packages from a specified list
3. `symlinks_script`: Sets up symbolic links for configuration files
4. `utils/verify_root`: Checks for root privileges before execution
5. `packages`: Contains the list of required packages

### Directory Structure After Setup
- `~/bin`: Contains utility scripts
- `~/.config`: Stores application configurations
- `~/.bashrc`: Shell configuration file

### Installation

#### Option 1: Full Setup (Recommended)
```bash
cd project1
sudo ./main_script
```

This will:
1. Check for root privileges
2. Install all required packages
3. Create necessary symbolic links

#### Option 2: Step-by-Step Installation
1. Install Packages:
```bash
sudo ./install_script -f packages
```
- `-f`: Specifies the package file path

2. Create Symbolic Links:
```bash
sudo ./symlinks_script
```

## Project 2: User Management

### Overview
This script automates new user creation without relying on existing user management tools. It directly manages system files to create and configure new user accounts.

### Features
- Custom shell selection
- Home directory creation
- Automatic `/etc/skel` content copying
- Primary and additional group management
- Password setup using `passwd`

### Usage
```bash
cd project2
sudo ./create_user_script -u username -s shell -d directory -g group
```

#### Parameters
- `-u`: Set username
- `-s`: Specify default shell (e.g., /bin/bash)
- `-d`: Set home directory path
- `-g`: Add user to additional groups

#### Example
```bash
sudo ./create_user_script -u newuser -s /bin/bash -d /home/newuser -g sudo
```

This creates a user with:
- Username: newuser
- Shell: `/bin/bash`
- Home: `/home/newuser`
- Groups: Primary group 'newuser' and additional group 'sudo'

## Technical Notes
- Scripts use `getopts` for command-line option handling
- Error handling included for common failure scenarios
- All scripts require root privileges
- Developed and tested on Arch Linux
- Uses absolute/relative paths instead of `cd` commands

## References
1. [Arch Linux Wiki - Pacman](https://wiki.archlinux.org/title/Pacman)
2. [Stack Overflow - Adding elements to arrays in Bash](https://stackoverflow.com/questions/1951506/add-a-new-element-to-an-array-without-specifying-the-index-in-bash)
3. [Stack Overflow - Shell script usage patterns](https://stackoverflow.com/questions/34567826/what-is-usage-in-shell-scripting)
4. [Unix Stack Exchange - Sudo user](https://unix.stackexchange.com/questions/190221/sudo-user-undefined-in-sudo-manual-clarification-would-be-lovely)
5. [Stack Overflow - Understanding [-z "$1"] in Bash](https://stackoverflow.com/questions/59468951/what-does-if-z-1-condition-means-in-bash-programming)
6. [Stack Overflow - Checking user existence in Bash](https://stackoverflow.com/questions/42792467/how-to-create-a-bash-script-in-linux-that-checks-if-the-user-is-local-or-not)
