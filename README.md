# 2420 assignment 2

## File structure
```
. 
├── README.md
├── project1
│   ├── bin
│   ├── config
│   ├── home
│   ├── install_script
│   ├── packages
│   └── symlinks_script
└── project2
    └── create_user_script
```

## Project 1
### Installation
1. Run the install script
```bash
cd project1
sudo ./install_script -f packages
```
- Remember to type `packages_file_path` after the `-f` flag.  

2. Run the symlinks script
```bash
sudo ./symlinks_script
```

## Project 2
### Create user script
1. Run the create user script
```bash
cd project2
sudo ./create_user_script -u username -s shell -d directory -g group
```
- Remember to type the username, shell, directory and group after the `-u`, `-s`, `-d` and `-g` flags respectively.
