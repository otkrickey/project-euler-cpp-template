# Project Euler CPP Template

## Pre-requisites

- [ ] Windows 11 22H2 (or Windows 10 21H2 with WSL 2)


## Setup

### 1. Install WSL 2
- [ ] Install [WSL 2](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
- [ ] Install [Ubuntu 22.04](https://www.microsoft.com/store/apps/9N6SVWS3RX71)


### 2. Install VSCode (and extensions)
- [ ] Install [VSCode](https://code.visualstudio.com/)
- [ ] Install [VSCode WSL Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl)
- [ ] Install [VSCode C++ Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools)

Check if the extensions are installed on VSCode in WSL.

```bash
code --list-extensions

# output example:
# Extensions installed on WSL: Ubuntu:
# ms-vscode.cpptools
# ms-vscode-remote.remote-wsl
```


### 3. Install C++ Compiler

```bash
# update and upgrade
sudo apt update
sudo apt upgrade -y
```

```bash
# install compiler
sudo apt install build-essential -y
sudo apt install gdb -y

# for GCC9 (default)
sudo apt-get update
sudo apt-get install gcc-9 g++-9 -y
```

Check if the compiler & debugger are installed.
```bash
g++ --version

# output example:
# g++ (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0

gcc --version

# output example:
# gcc (Ubuntu 9.4.0-1ubuntu1~20.04.1) 9.4.0

gdb --version

# output example:
# GNU gdb (Ubuntu 9.2-0ubuntu1~20.04.1) 9.2
```


### 4. Clone this repository

```bash
git clone https://github.com/otkrickey/project-euler-cpp-template.git

# or

git clone https://github.com/otkrickey/project-euler-cpp-template.git ${YOUR_DIRECTORY}
```


### 5. Setup Ubuntu alias

```bash
# open .bashrc
code ~/.bashrc
```

```bash
# scroll to the bottom and add the following lines
alias pe='/home/${username}/${path_to_this_repo}/template/pesetup.sh'
```


### 6. Setup VSCode

- [ ] Press `Ctrl+K Ctrl+S` to open the keyboard shortcuts settings.
- [ ] Search `"tasks"` and set the following keybindings.
    - [ ] Set Shortcut for `"Tasks: Run Build Task"` to `"Ctrl+Shift+B"`
    - [ ] Set When for `"Tasks: Run Build Task"` to `config.otkrickey.workspaceKeyBindings.enabled && editorTextFocus && editorLangId == 'cpp'`


## Usage

### 1. Create a new directory for a contest

```bash
# create a new directory for a contest
pe ${contest_number}
```

This will create a new directory for the contest and copy the template into each problem file.

```
.
├── ...
├── src
│   ├── ${problem_number}.cpp
│   └── ...
└── ...
```


### 2. Build

- [ ] Press `Ctrl+Shift+B` to build the code.

The message will appear on the bottom terminal if the build is failed. (Nothing will happen if the build is successful.)


### 3. Run

```bash
# run the code
./problem.exe < problem.in
```


### 4. Debug

- [ ] Press `F5` to run the code.

The Debug Console will appear on the bottom terminal.
For details, please refer to [this](https://code.visualstudio.com/docs/editor/debugging).


## Test

### Test Build & Run

- [ ] Open `template.cpp` and press `Ctrl+Shift+B` to build the code.

```bash
# run the code
./problem.exe < problem.in

# output example(default):
# 1
```


### Test Debug

- [ ] Open `template.cpp` and press `F5` to run the code.

The Debug Console will appear on the bottom terminal.

```bash
# output example(default):
# 1
```


## Directory Structure

```
.
├── .vscode
│   ├── c_cpp_properties.json  # intellisense
│   ├── launch.json            # debug
│   ├── settings.json          # settings
│   └── tasks.json             # build
├── src
├── README.md
├── ac-library                 # ac-library
│   ├── ac-library.zip
│   └── atcoder
├── problem.exe                # executable file
├── problem.in                 # input file
└── template
    ├── pesetup.sh             # setup directory
    └── template.cpp           # template file
```

