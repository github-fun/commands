# Git Objects

Git is a file system and it stores data as objects in .git/objects. To dig deeper, let's create an empty repository 

### Initialise a git repo

```
git init
Initialized empty Git repository in ~/code-geass/git-objects/.git/
ls -lah .git/objects/
total 12K
drwxrwxr-x.  3 geekcoder geekcoder 4.0K Oct  7 14:04 .
drwxrwxr-x. 41 geekcoder geekcoder 4.0K Oct  7 14:03 ..
drwxrwxr-x.  7 geekcoder geekcoder 4.0K Oct  7 14:04 .git

```
### Commit something

```
echo "Hello World" > sample.txt
git add .
git commit -m "Initial commit"

[master (root-commit) 70f928c] Initial commit
 1 file changed, 1 insertion(+)
 create mode 100644 sample.txt

ls -la .git/objects/

4e  4f  70  info  pack
```

As you can see three new files were created after the __Initial Commit__
