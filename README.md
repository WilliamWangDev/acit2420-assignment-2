# ACIT-2420 assignment 2

## File structure
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
└── project2
    └── create_user_script
```

## Project 1: System Configuration
### Overview
Project 1 automates the setup of essential software packages and configuration files for a new system. It includes:
- `main_script`: Executes both `install_script` and `symlinks_script` to complete the setup.
&nbsp;
- `install_script`: Installs packages specified in a package file.
&nbsp;
- `symlinks_script`: Creates symbolic links for configuration files.

### Installation Steps
1. **Run the Main Setup Script**
```bash
cd project1
sudo ./main_script
``` 
This will:
- Run `install_script` with packages file as an argument to install necessary packages.
- Run `symlinks_script` to set up symbolic links for configuration files.
2. **Alternative: Manual Execution** If you need to run the scripts individually, use the following steps:
- **Install Packages**
```bash
sudo ./install_script -f packages
```
The `-f` flag specifies the path to the package file. The `packages` file is provided as an example.
- **Create Symbolic Links**:
```bash
sudo ./symlinks_script
```
This script will link configuration files from the `config` and `home` directories to the correct locations in your home directory.

---
## Project 2: New User Creation Script
### Overview
Project 2 provides a script to create a new user on the system with specified configurations.
### Usage
1. **Run the Create User Script**
```bash
cd project2
sudo ./create_user_script -u username -s shell -d directory -g group
```
- `-u`: Specify the username
- `-s`: Specify the default shell for the user
- `-d`: Specify the home directory for the user
- `-g`: Specify the additional group for the user

### Example
```bash
sudo ./create_user_script -u newuser -s /bin/bash -d /home/newuser -g sudo
```
This will create a user named `newuser` with `/bin/bash` as the shell, `/home/newuser` as the home directory, and add the user to the `sudo` group.

---
This setup provides a streamlined process for system initialization and user management. For any further instructions or troubleshooting, refer to the comments in each script.