# Steps for forking an upstream repository and creating pull request (PR)

### Step 1.  Fork the upstream repository in your GitHub account. If you have multiple account (e.g. in the picture), select an account
   ![Fork upstream repo](/images/2019_09_10_09_27_08.png)

   - Forking in progress
   ![Forking](/images/2019-09-10_09-27-16.png)

### Step 2. Clone the forked repo
   ![Cloning](/images/2019-09-10_09-27-26.png)

   - Clone the repo. Open your terminal. Go to the path where you want to have your repo on your local machine.
   
   `cd ~/my_codes_live_here` on UNIX/MAC
   `cd C:\my_codes_live_here` on Windows
   `git clone <repo-name>`

   ![git clone console](/images/2019-09-10-09-28-36.png)

   - Check remote `git remote -v`

   ![git remote -v console](/images/git_remote_v.png)

   - Add upstream to remote `git remote add upstream <upstream repo link>`

   - Check remote again `git remote -v`
   ![git add upstream console](/images/add_upstream.png)

### Step 3. Add new feature/code by creating a new branch, say feature-1

   - Check current branch `git branch`
    
   ![git branch console](/images/git_branch.png)

   - Add new branch `git checkout -b feature-1`
   ![git branch console](/images/git_checkout_b.png)

   - Check the contents of the repo `ls -la`

   - Create a new file, say FORK.md `vi FORK.md`

   - Add a sentence. Press `ESC` followed by `:` followed by `i` and then type `Add commands here.`

   - Save the file. Press `ESC` followed by `:` followed by `wq`

   - Check if new file was created `ls -la`
   ![git branch console](/images/create_new_file.png)

   


### Step 3. Creating a pull request
   - Sync your branch with upstream  `git fetch upstream master`

   - Pick commits from upstream `git rebase -i upstream/master`

   - Add the file `git add .`

   - Commit the file with comments `git commit - m 'first commit' `

   - Push changes `git push origin feature-1`

   - Check if file was added to `feature-1` branch of `origin` 
   ![git branch console](/images/check_feature_1.png)

   ![git branch console](/images/check_feature_2.png)

   - Create a pull request

   ![git branch console](/images/pr_1.png)

   - Add reviewer
   
   ![git branch console](/images/add_reviewer_pr.png)

   - Check PR
   
   ![git branch console](/images/pending_review.png)

   - Check your commits in PR
   
   ![git branch console](/images/check_commit_in_pr.png)

   - Check modified files in PR
   
   ![git branch console](/images/check_files_in_pr.png)











