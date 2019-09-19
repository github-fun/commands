# github-commands
Follow along in this document to see the exact commands and URLs you need to use in this workshop. You can copy and paste commands you see `in gray` into the terminal or URLS into the browser. 

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

#### Linux
Use ctrl + alt + T to open a terminal or search for it in Apps.

#### MacOS
Go to Applications → Utilities → Terminal to open a terminal.

#### Windows
Use Windows + R to open “Run” box and type “cmd” to open a terminal.


### Step 0.3 Checking git version
On all operating systems, enter the following command in the terminal:  
`git --version`  

After you enter the above command, you should see something like (although the version number may differ):  
`git version 2.20.1`  

If you see this, it means git is installed (skip the next step).  If you see nothing, git is not installed and you should follow the instructions in Step 0.4.

### Step 0.4 Installing git (if not already installed)
#### Linux
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
Configure git with your name and email. The name can be fake, but the email must match your GitHub account! GitHub uses this for authentication.

On all operating systems, issue this command to check your current git configuration:  
`git config --list`  

If the command above doesn't show your name and email, you will need to configure git. To do so, issue the following (make sure to use your real email that was used to create your GitHub account):
```
git config --global user.name "Jane Doe"
git config --global user.email "jane@l337.com"

```

## Creating a repo
### Step 1.1 Creating a repo on GitHub
In your GitHub account, find the Repositories tab and click. Then click the green New button.

(image)

Choose a name for your repo (ex. `myawesomerepo`). Choose the button to make the repo public and select “Initialize this repository with a README.” Leave all other choices on the default setting.

### Step 1.2 Cloning the repo locally
Copy the repo's URL. In your GitHub account, click the Repositories tab and click on your new repo. Click the green “clone or download” button on the right. Make sure "use HTTPS" is selected (not SSH).

(image)

In your terminal, optionally navigate to the folder where you want to keep your git repo. Otherwise, just use the current directory. Use `git clone <URL>` to clone the repo. You can paste the URL into the terminal after typing `git clone`.

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


## Making changes
### Step 2.1 Creating a file
Create a file called “question.txt” in your new repo (inside the folder you downloaded with `git clone`) and add the question “What makes you excited about programming?” (Or add your own question!) Feel free to do this however you are most comfortable creating and editing files (MS Word is fine), but please save it as a `.txt` file instead of `.doc` or any other file extension.


---------
Keep this section?  

If you want to try creating the file in the terminal, you can use `touch question.txt` to create the file on Mac/Linux and (FILL IN LATER) on Windows. Then open the file in a text editor like notepad, gedit, vim, etc.  

#### Linux: common text editors include nano, gedit, vim, emacs
`$ touch question.txt && gedit question.txt`

#### Windows: common text editor is notepad
`> touch question.txt`

Use `git status` to check the status of your new file.

-----------------------

### Step 2.2 Tracking changes
`git add question.txt`  
 Use `git status` to check the status of your file again. What is different?
 
### Step 2.3 Committing changes
`git commit -am "added question.txt file"`  
Tip: `-am ` allows you to specify a commit message. The commit message should be short and descriptive about the purpose of the commit or what you changed.

### Step 2.4 Storing changes remotely
Use `git remote -v` to see which remote branches your branch is tracking.  
`git push origin master` will push the committed changes from your local machine to the GitHub repository, where others can see it or clone it.

## Working with branches
### Step 3.1 Creating a new branch
Use `git branch` to check which branch you are on. It should say `master`.  
Then enter `git checkout -b my-new-branch` to create a new branch and switch into that branch at the same time. This will be an exact copy of the branch you were on when you called the command, which in this case is `master`.

### Step 3.2 Modifying the branch
Using the method from Step 2.0, create a file called `random.txt`, but leave it blank. Then edit `question.txt` to ask an additional question (Ex. "What is your favorite animal and why?").

### Step 3.3 Committing branch changes
You will need to add the file to git's tracking before making a commit.  
Use `git status` to see the current changes. You should see that you have an untracked file.  
Add the new file with `git add random.txt`.  
Check the status again with `git status` and see that it no longer shows an untracked file.
Then you can make a commit and add a commit message:  
`git commit -m "new question, addition of random file"`  
The `-m` option allows you to write a message labeling the commit. Ideally, your commit message is descriptive about what changed in this commit compared to the previous one. However, it should also be short (just a few words).

### Step 3.4 Compare branches
List the files in your directory while you're on `my-new-branch` with `ls`. What do you see?  
You should see your new file, `random.txt`, as well as the older file, `question.txt`.

Now change back to your original branch. You can see all your branches with `git branch`, and the current branch you are on will be highlighted. To switch between branches, use `git checkout <branch>`, ex. `git checkout master`.

Now that you are on the original `master` branch, use `ls` again to list the files in your repo. What is different? 

You should see that `random.txt` has disappeared! This is expected; this file was only added in `my-new-branch` and does not show up in other branches. If you switch back to `my-new-branch`, you will see the file again.

### Step 3.5 Merging the branch
Use `git branch` to check that you're on the `master` branch.
Then use `git merge my-new-branch` to merge the changes from `my-new-branch` into your current branch (`master`).

Use `ls` again to see your files. You should see that now `random.txt` shows up. By merging `my-new-branch` into the `master` branch, you have brought in the changes from `my-new-branch`.

### Step 3.6 Push changes to remote
Push your original `master` branch to remote. 
Make sure you are on the `master` branch with `git branch`. If so, use `git push` to push new changes to remote. (Otherwise, change to the master branch with `git checkout master`; then use `git push` the same way.)

You can check that your changes made it to remote by looking on your GitHub profile in the repo you created. 

### Bonus Step
If you have extra time, delete your "new" branch to clean up. Make sure you are on the master branch with `git branch` (or change to master with `git checkout master`) because you cannot delete a branch you're currently on. Then delete the other branch with `git branch -d my-new-branch`. Check that the delete worked by using `git branch` to list all local branches.
