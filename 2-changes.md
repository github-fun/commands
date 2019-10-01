## Making changes
### Step 2.1 Creating a file
Create a file called `question.txt` in your new repo (inside the folder you downloaded with `git clone`) and add the question “What makes you excited about programming?” (Or add your own question!) Feel free to do this however you are most comfortable creating and editing files (MS Word is fine), but please save it as a `.txt` file instead of `.doc` or any other file extension.

### Step 2.2 Tracking changes
Use `git status` to check the status of your new file.  
Add the file to git's tracking with `git add question.txt`.
Use `git status` to check the status of your file again. What is different?  
 
### Step 2.3 Committing changes
`git commit -m "added question.txt file"`  
Tip: `-m ` allows you to specify a commit message. The commit message should be short and descriptive about the purpose of the commit or what you changed.

### Step 2.4 Storing changes remotely
Use `git remote -v` to see which remote branches your branch is tracking.  
`git push origin master` will push the committed changes from your local machine to the GitHub repository, where others can see it or clone it.
