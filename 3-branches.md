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
