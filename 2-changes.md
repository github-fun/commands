## Making changes
### Step 2.1 Creating a file
Create a file called `question.txt` in your new repo (inside the folder you downloaded with `git clone`) and add the question “What makes you excited about programming?” (Or add your own question!) Feel free to do this however you are most comfortable creating and editing files (MS Word is fine), but please save it as a `.txt` file instead of `.doc` or any other file extension.

### Step 2.2 Tracking changes
Check the status of your new file with:  
`git status`  

You should see something like:  

```
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	question.txt

nothing added to commit but untracked files present (use "git add" to track)

```


Add the file to git's tracking with:  
`git add question.txt`.  

Use `git status` to check the status of your file again. What is different? Now you should see something like:  
```
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
```

### Step 2.3 Committing changes

To commit your changes and create a save point, use:

`git commit -m "added question.txt file"`  

Tip: `-m ` allows you to specify a commit message. The commit message should be short and descriptive about the purpose of the commit or what you changed in the repo.

### Step 2.4 Storing changes remotely
To see which remote branches your branch is tracking, use:  
`git remote -v` 

Then to push your committed changes from your local machine to the remote GitHub repo, where others can see it or clone it, use:  
`git push origin master` 
