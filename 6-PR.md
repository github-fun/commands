# Steps to creating a Pull Request (PR)

### Step 1. Sync your local repository with upstream

Ensure that your local repository is up-to-date with the changes in upstream. 

   - Sync your branch with upstream  `git fetch upstream master`

   - Pick commits from upstream `git rebase -i upstream/master`. In case you get conficts, resolve the conflicts manually by going to the files having conflicts. Either accept the incoming changes from upstream or keep your local changes. 

   - Add the file `git add .` In case there was conflicts, do `git rebase --continue` followed by `git add .`

   - Now make a commit with comments `git commit - m 'first commit' `

   - Push changes `git push origin +feature-1`

   - Check if file was added to `feature-1` branch of `origin` 

   ![git branch console](/images/check_feature_1.png)

   ![git branch console](/images/check_feature_2.png)

 ### Step 2. Create a pull request

   - Go to upstream repository on GitHub web page. Click on `Pull Request Tab`. Now click on `New Pull Request` green button on right hand side.

   ![git branch console](/images/pr_1.png)

   - Add a title. Leave a comment describing what is in your PR

   - Add reviewer. In this case your teammate wil act as your reviewer. 
   
   ![git branch console](/images/add_reviewer_pr.png)

   - Click on the green button that says `Create pull request` 

   - Check PR
   
   ![git branch console](/images/pending_review.png)

   - Check your commits in PR
   
   ![git branch console](/images/check_commit_in_pr.png)

   - Check modified files in PR
   
   ![git branch console](/images/check_files_in_pr.png)