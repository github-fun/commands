## Creating a repo
### Step 1.1 Creating a repo on GitHub
In your GitHub account, find the Repositories tab and click. Then click the green New button.

![PACSPull Plugin](/images/set-up/github-new-repo.png)

Choose a name for your repo (ex. `myawesomerepo`). Choose the button to make the repo public and select “Initialize this repository with a README.” Leave all other choices on the default setting.

### Step 1.2 Cloning the repo locally
Copy the repo's URL. In your GitHub account, click the Repositories tab and click on your new repo. Click the green “clone or download” button on the right. Make sure "use HTTPS" is selected (not SSH).

(image)

In your terminal, optionally navigate to the folder where you want to keep your git repo. Otherwise, just use the current directory. Use `git clone <URL>` to clone the repo (DO NOT include the `<` and `>` brackets). You can paste the URL into the terminal after typing `git clone`.

Tip 1: Right click on the terminal to paste the git URL. In most cases, you can’t use `Ctrl+V` in the terminal.  
Tip 2: On Linux/Mac, you can enter the first few letters of your repo's name and hit the tab key to auto-complete it.
Tip 3: If you don't know your repo's name after cloning, enter `ls` to show it.
```
git clone <URL> 
cd <repo name>
```
