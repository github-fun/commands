## Set-up: installing and configuring git (steps 0.1 through 0.5)
### Step 0.1: Registering a GitHub account
If you already have a GitHub account you'd like to use, log in to that account.
Otherwise, register a GitHub account at https://github.com/.

At the end of registration, it'll ask you to set up a new repo. You can stop there without setting one up yet.

Tip: If you're creating an account and don’t have a username in mind, use `gitisawesome` + a number.

![PACSPull Plugin](/images/set-up/github-join.png)



### Step 0.2: Opening a terminal

The terminal allows you to interact with programs on your computer in a precise and powerful way. We will use it for everything in this workshop.

![PACSPull Plugin](/images/set-up/cli-fun.png)

#### Linux (Ubuntu)
Use `ctrl` + `alt` + `T` to open a terminal or [search](https://askubuntu.com/questions/122437/how-to-access-applications-menu-in-ubuntu-unity-desktop) for it in the Unity dash.
#### MacOS
Go to Applications → Utilities → Terminal to open a terminal.

#### Windows
You will be using Windows PowerShell. In the Start menu, search for PowerShell.


### Step 0.3 Checking git version
On all operating systems, enter the following command in the terminal (for all commands, type the command and hit `ENTER`):  
`git --version`  

After you enter the above command, you should see something like (although the version number may differ):  
`git version 2.20.1`  

If you see this, it means git is installed (skip the next step).  If you see nothing, git is not installed and you will need to install it, following the instructions in Step 0.4.

### Step 0.4 Installing git (if not already installed)
#### Linux (Ubuntu)
```
sudo apt-get update
sudo apt-get install git
```

#### MacOS
Use the the [Git for Mac Installer](https://sourceforge.net/projects/git-osx-installer/files/).

Alternatively, if you have homebrew installed, you can issue:  
`brew install git`

You can [install homebrew](https://brew.sh/) with   
```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```   
before entering the above command.

#### Windows
Use the [Git for Windows installer](https://gitforwindows.org/).


### Step 0.5 Configure git (if not already configured)
Configure git with your name and email. The name can be anything, but the email must match the one tied to your GitHub account (the one you used for registering the account). GitHub uses this for authentication.

On all operating systems, issue this command to check your current git configuration:  
`git config --list`  

If the command above doesn't show your name and email, you will need to configure git. To do so, issue the following (make sure to use your real email that was used to create your GitHub account):
```
git config --global user.name "Jane Doe"
git config --global user.email "jane@l337.com"

```
