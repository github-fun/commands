# Steps for forking an upstream repository

### Step 1.  Fork the upstream repository in your GitHub account. 
Consider your teammate's repository as the upstream repository you will be making a contribution to. Follow the screenshot to fork your upstream repository. If you have multiple account (e.g. in the picture), select an account

   ![Fork upstream repo](/images/2019_09_10_09_27_08.png)

   - Forking in progress
   ![Forking](/images/2019-09-10_09-27-16.png)

### Step 2. Clone the forked repo
   ![Cloning](/images/2019-09-10_09-27-26.png)

   - Clone the repo. Open your terminal. Go to the path where you want to have your repo on your local machine.
   
   - `cd ~/<path where you want to clone your repository>` on UNIX/MAC
   - `cd C:\<path where you want to clone your repository>` on Windows
   - `git clone <repo-name>`

#### Note: You will be cloning the repository which is a fork of your teammate's repository also called upstream in this case.
   
   ![git clone console](/images/2019-09-10-09-28-36.png)

   - Check remote `git remote -v`. You should see url of your repository. Something like `https://github.com/<your_github_account_name>/<repository_name>.git` for e.g. `https://github.com/husky-parul/github-commands.git`

   ![git remote -v console](/images/git_remote_v.png)

   - Add upstream to remote `git remote add upstream <upstream repo link>`

   - Check remote again `git remote -v`. Now you should see two remotes, namely `upstream` and `origin`. Verify if the urls are corect. `upstream` should be your teammate's repo url. `origin` should be your repo url.

   ![git add upstream console](/images/add_upstream.png)

### Step 3. Add new feature/code by creating a new branch, say feature-1

   - Check current branch `git branch`
    
   ![git branch console](/images/git_branch.png)

   - Add new branch `git checkout -b feature-1`
   ![git branch console](/images/git_checkout_b.png)

   - Check the contents of the repo `ls`

   - Open the file `question.txt` and add a sentence, `This is my first upstream contribution`

   - Save the file.

   - Add the file to stage for git to track `git add question.txt`

   - Make a commit `git commit -m "My first upstream contribution"`

   - Push the file `git push origin feature-1`

   - Verify if the file was pushed by checking it on GitHub web page.











