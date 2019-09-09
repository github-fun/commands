# github-commands
Follow along here to see the exact commands and URLs you need to use in this workshop. You can copy and paste these easily into the browser or terminal.

## Set-up: installing and configuring git (steps 0.1 through 0.4)
### Step 0.1: Registering a GitHub account
Register a GitHub account at https://github.com/.

### Step 0.2: Opening a terminal
#### Linux
Use ctrl + alt + T to open a terminal or search for it in Apps.

#### MacOS
Go to Applications → Utilities → Terminal to open a terminal.

#### Windows
Use Windows + R to open “Run” box and type “cmd” to open a terminal.


### Step 0.3 Checking git version
On all operating systems, enter the following command in the terminal (you do not type the `$` -- it denotes a user prompt, i.e. something that you type rather than output from the machine):  
`$ git --version`  

After you enter the above command, you should see something like:  
`git version 2.20.1`  

If you see this, it means git is installed and you can skip Step 0.4.  
If you see nothing, git is not installed and you should follow the instructions in Step 0.4.

### Step 0.4 Installing git (if not already installed)
#### Linux
```
$ sudo apt-get update
$ sudo apt-get install git
```

#### MacOS
If you have homebrew installed, you can issue:  
`$ brew install git`

Otherwise, you can either [install homebrew](https://brew.sh/) with   
```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```   
before entering the above command or you can download git with the [Git for Mac Installer](https://sourceforge.net/projects/git-osx-installer/files/).

#### Windows
Use the [Git for Windows installer](https://gitforwindows.org/).


## Creating a repo

## Making changes and pushing to remote

## Working with branches
