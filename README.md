# ACIT-2420 Assignment 2

## Project Structure
```
.
├── README.md
├── project1
│   ├── bin
│   ├── config
│   ├── home
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
Project 1 automates the setup of essential software packages and configuration files for a new system. It consists of the following components:

- `main_script`: Primary script that orchestrates the entire setup process by executing both the installation and symlink scripts
- `install_script`: Handles the installation of specified packages
- `symlinks_script`: Manages the creation of symbolic links for configuration files
- `utils/verify_root`: Utility script to verify root user privileges

### Installation

#### Option 1: Automated Setup (Recommended)
Run the main setup script:
```bash
cd project1
sudo ./main_script
```

This will:
1. Execute `install_script` with the packages file to install necessary software
2. Run `symlinks_script` to configure symbolic links

#### Option 2: Manual Installation
If you need more control, you can run the scripts individually:

1. Install Packages:
```bash
sudo ./install_script -f packages
```
The `-f` flag specifies the path to the package file.

### Create Symbolic Links:
```bash
sudo ./symlinks_script
```
This will create symbolic links from the `config` and `home` directories to their appropriate locations.

## Project 2: User Management

### Overview
Project 2 provides a script for creating new users with custom configurations.

### Usage
```bash
cd project2
sudo ./create_user_script -u username -s shell -d directory -g group
```

#### Parameters
- `-u`: Username for the new account
- `-s`: Default shell (e.g., /bin/bash)
- `-d`: Home directory path
- `-g`: Additional group membership

#### Example
```bash
sudo ./create_user_script -u newuser -s /bin/bash -d /home/newuser -g sudo
```
This creates a user "newuser" with:
- Shell: `/bin/bash`
- Home directory: `/home/newuser`
- Added to the `sudo` group

---
### References
Each script includes detailed comments with references to the sources used for guidance and inspiration. This is the list of references used:
1. https://wiki.archlinux.org/title/Pacman
2. https://stackoverflow.com/questions/1951506/add-a-new-element-to-an-array-without-specifying-the-index-in-bash
3. https://stackoverflow.com/questions/34567826/what-is-usage-in-shell-scripting
4. https://unix.stackexchange.com/questions/190221/sudo-user-undefined-in-sudo-manual-clarification-would-be-lovely
5. https://stackoverflow.com/questions/34567826/what-is-usage-in-shell-scripting
6. https://stackoverflow.com/questions/59468951/what-does-if-z-1-condition-means-in-bash-programming#:~:text=%241%20means%20an%20input%20argument,defined%20when%20running%20the%20script
7. https://stackoverflow.com/questions/42792467/how-to-create-a-bash-script-in-linux-that-checks-if-the-user-is-local-or-not