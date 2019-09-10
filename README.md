# github-commands
Follow along here to see the exact commands and URLs you need to use in this workshop. You can copy and paste these easily into the browser or terminal. Some steps do not have corresponding commands or URLs, so they are skipped in this document.

## Set-up: installing and configuring git (steps 0.1 through 0.5)
### Step 0.1: Registering a GitHub account
If you already have a GitHub account you'd like to use, log in to that account.
Otherwise, register a GitHub account at https://github.com/.

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


### Step 0.5 Configure git (if not already configured)
On all operating systems, issue this command to check your current git configuration:  
`$ git config --list`  

To configure git, issue the following (make sure to use your real email that is attached to your GitHub account):
```
$ git config --global user.name "Jane Doe"
$ git config --global user.email "jane@l337.com"

```

## Creating a repo
### Step 1.3 Cloning the repo locally
Tip: Right click on the terminal to paste the git URL. In most cases, you can’t use `Ctrl+V` in the terminal.  

#### MacOS and Linux
```
$ cd ~ && mkdir Repos && cd Repos
$ git clone https://github.com/github-fun/github-appendix.git && cd github-appendix
```

#### Windows
```
> cd C:\Users\gituser && mkdir Repos && cd Repos
> git clone https://github.com/github-fun/github-appendix.git && cd github-appendix
```


## Making changes and pushing to remote
### Step 2.0 Creating a file
Create a new file called "question.txt" in the root of your new repo directory and use a text editor to write a question in that file.
Some example text editors are listed below, but feel free to do this in whichever way is easiest for you, including graphical navigation or MS Word. If you use Word, make sure to save the file with a ".txt" extension.

#### Linux: common text editors include nano, gedit, vim, emacs
`$ touch question.txt && gedit question.txt`

#### Windows: common text editor is notepad
`> touch question.txt`

### Step 2.1 Tracking the file with git
`$ git add question.txt`



## Working with branches
