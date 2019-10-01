## Creating a repo
### Step 1.1 Creating a repo on GitHub
In your GitHub account, find the Repositories tab and click. Then click the green New button.

![PACSPull Plugin](/images/repo/github-new-repo.png)

Choose a name for your repo (ex. `myawesomerepo`). Choose the button to make the repo public and select “Initialize this repository with a README.” Leave all other choices on the default setting.

### Step 1.2 Cloning the repo locally
Copy the repo's URL. In your GitHub account, click the Repositories tab and click on your new repo. Click the green “clone or download” button on the right. Make sure "use HTTPS" is selected (not SSH).

![PACSPull Plugin](/images/repo/github-clone-repo.png)

In the terminal, enter:
```
cd ~
git clone <URL> 
cd <repo name>
```

These commands will bring you to your home directory, clone the repo you created, then change directory into your repo. Now you will be able to see any files in the local copy of your repo by entering `ls`. Try it out - you should see `README.md` listed.

Tips: Do not put brackets around the URL that you are cloning. Right click to paste the repo's URL into the terminal (`ctrl` + `v` usually won't work) and hit enter.
