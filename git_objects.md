# Git Objects

Git is a file system and it stores data as objects in .git/objects. To dig deeper, let's create an empty repository 

### Initialise a git repo

```
git init
Initialized empty Git repository in ~/code-geass/git-objects/.git/

ls .git/objects/
total 12K
info  pack
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

As you can see three new directories were created after the __Initial Commit__. You can check the files by 

```
find .git/objects -type f
.git/objects/70/f928c3b426a4949d8968334e4d30e92bc31687
.git/objects/4e/bf5763311653c68f44db6b66c300192a7e11c4
.git/objects/4f/52b57b2a3a96457d18049ea34c6085de0e09a4
```
Each new directories has a file inside it.

### Check object type, size and contents

You can check git objects type, size and contents. 
- __type__ `git cat-file -t <object>`
- __size__ `git cat-file -s <object>`
- __contents__ `git cat-file -p <object>`

where `<object>` is `dir-name` followed by first two chars of `file-name`. If referrign to the example above 

```
git cat-file -p 70f9

tree 4ebf5763311653c68f44db6b66c300192a7e11c4
author husky-parul <nerd@nred.com> 1570471501 -0400
committer husky-parul <nerd@nred.com>1570471501 -0400

Initial commit

```

To know about all the objects types run,

```
for i in 70f9 4ebf 4f52; do git cat-file -t $i; done
commit
tree
blob

for i in 70f9 4ebf 4f52; do git cat-file -s $i; done
181
38
13

```

### Blob objects
Blob is an abbreviation of “Binary Large Object”. It contains contents of the file only. 

Now let's try to update `sample.txt`, create a new file and make another commit and see what happens to these objects.

```
echo "Update a sent" > sample.txt
echo "Hello World2" > sample2.txt
git add .
git commit -m "Second commit"
[master a0cf9b0] Second commit
 2 files changed, 2 insertions(+), 1 deletion(-)
 create mode 100644 sample2.txt

find .git/objects -type f
.git/objects/70/f928c3b426a4949d8968334e4d30e92bc31687
.git/objects/b2/b6f00d3432b3a12bc47e2ae31ee679f2baae92
.git/objects/a0/cf9b04d176d7a6dd1ccc16cbd035bb9592d6de
.git/objects/f8/6effb19a7ee6cea51166c3a1438ba313794fc8
.git/objects/4e/bf5763311653c68f44db6b66c300192a7e11c4
.git/objects/4f/52b57b2a3a96457d18049ea34c6085de0e09a4
.git/objects/d2/fc8330756fc2dd131ff428a48e5a402d515cfe

for i in 70f9 b2b6 a0cf f86e 4ebf 4f52 d2fc; do git cat-file -t $i; done
commit
blob
commit
blob
tree
blob
tree

```
As you can see two blob objects have been added. Note that the existing blob object 4f52 has not been updated or deleted. That means a blob object is a snapshot of the file.

### Commit objects
Similarly you can see commit objects. The commit objects contain the reference to a tree object, author, committer and commit message. Except for the initial commit, commits also have the reference to the tree object of the parent. There may be multiple parents. 

```
git cat-file 70f9 -p
tree 4ebf5763311653c68f44db6b66c300192a7e11c4
author husky-parul <nerd@nerd.com> 1570471501 -0400
committer husky-parul <nerd@nerd.com> 1570471501 -0400

Initial commit

git cat-file a0cf -p
tree d2fc8330756fc2dd131ff428a48e5a402d515cfe
parent 70f928c3b426a4949d8968334e4d30e92bc31687
author husky-parul <parsingh@redhat.com> 1570472704 -0400
committer husky-parul <parsingh@redhat.com> 1570472704 -0400

Second commit


```

Unlike blob, commit object is metadata and has no content.

### Tree objects

Tree objects contain one line per file or subdirectory. Each line has file permission, object type, and object hash and filename.

```
git cat-file d2fc -p
100644 blob f86effb19a7ee6cea51166c3a1438ba313794fc8	sample.txt
100644 blob b2b6f00d3432b3a12bc47e2ae31ee679f2baae92	sample2.txt

```


