Before committing files need to be added to staging area
```
git add file1
```
all files in dir can be added
```
git add .
```
if any file in staging area is updated or needs to be removed the same command is used. To take a snapshot of the files in the staging area
```
git commit -m "Note for commit"
```
The staging area can also be skipped by using -a (all modified files)
```
git commit -a -m "Note for commit"
```
to push to GitHub master branch
```
git push origin master
```
To initialize
```
git init
```
To push to github
```
git push -u origin main
```