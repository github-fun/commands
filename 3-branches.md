## Working with branches
### Step 3.1 Creating a new branch
To check which branch you are currently on, use:  
`git branch`  

It should say:  
`* master`

To create a new branch and switch into that branch at the same time, use:  
`git checkout -b my-new-branch` 

You should see:  
`Switched to a new branch 'my-new-branch'`

This new branch will be an exact copy of the branch you were on when you called the command, which in this case is `master`.

### Step 3.2 Modifying the branch
Using whatever method you are comfortable with, create a file called `random.txt` inside your repo (in the same folder as `question.txt`), but feel free to leave it empty.  
Then, edit `question.txt` to ask an additional question (Ex. "What is your favorite animal and why?").

### Step 3.3 Committing branch changes
You will need to add the file to git's tracking before making a commit, so first view the current changes with:  
`git status`

You should see that you have an untracked file:
```
On branch my-new-branch
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   question.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	random.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

Add the new file with:
`git add random.txt`

Check the status again with `git status` and see that it no longer shows an untracked file. You should see:
```
On branch my-new-branch
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	new file:   random.txt

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   question.txt
```

Then you can make a commit and add a commit message:  
`git commit -m "new question, added random file"`  

The `-m` option allows you to write a message labeling the commit. Ideally, your commit message is descriptive about what changed in this commit compared to the previous one. However, it should also be short (just a few words).

You should see something like:
```
[my-new-branch 70e28f4] new question, added random file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 random.txt
```

### Step 3.4 Compare branches
List the files in your directory while you're on `my-new-branch` with:  
`ls` 

What do you see?  
You should see your new file, `random.txt`, as well as the older file, `question.txt`.

Now view all your branches with:  
`git branch`

This should show you both branches, with the current one highlighted and with an asterisk (the order in which they are listed doesn't matter):
```
master
* my-new-branch
```

To back to the `master` branch, use:  
`git checkout master`.

Now that you are on the original `master` branch, use `ls` again to list the files in your repo. What is different from the last time you looked at the contents of this folder? 

You should see that `random.txt` has disappeared! This is expected; this file was only added in `my-new-branch` and does not show up in other branches. If you switch back to `my-new-branch` using `git checkout my-new-branch` and enter `ls`, you will see the file again.

### Step 3.5 Merging the branch
To check that you're on the `master` branch, use:  
`git branch`

You should see:
```
* master
my-new-branch
```

Then, to merge changes from `my-new-branch` into your current branch (`master`), use:
`git merge my-new-branch`

You should see:  
```
Updating 3074f57..7f54cca
Fast-forward
 question.txt | 1 +
 random.txt   | 0
 2 files changed, 1 insertion(+)
 create mode 100644 random.txt
```

Use `ls` again to see your files. You should see that now `random.txt` shows up in the `master` branch. By merging `my-new-branch` into the `master` branch, you have brought the changes from `my-new-branch` into `master`.

### Step 3.6 Push changes to remote
Push your original `master` branch to remote. 

Make sure you are on the `master` branch with:  
`git branch`

You should see:  
```
* master
my-new-branch
```

If you don't see this, you can switch to the `master` branch by using:  
`git checkout master`

Check that you have no untracked files with:  
`git status`

Push the new changes to remote with:
`git push origin master`

You can check that your changes made it to remote by looking on your GitHub profile in the repo you created. 

### Bonus Step
If you have extra time, delete your new branch to clean up. Make sure you are on the master branch with `git branch` (or change to master with `git checkout master`) because you cannot delete a branch you're currently on. Then delete the other branch with `git branch -d my-new-branch`. Check that the delete worked by using `git branch` to list all local branches.
