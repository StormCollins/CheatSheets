# CheatSheets

## Git 

### Config File
View location of global config file:

```
git config --list
```

### Delete Local, Merged Branches 

```
git branch --merged | egrep -v "(master|dev)" | xargs git branch -D
```

### Pulling a Not-Checked-Out Branch
If you're in one branch, say `master`, but you want to pull and update another branch, say `dev` without checking `dev` out.

```
git pull origin dev:dev
```

### Remove a File from Git History

Say the file is in the third last commit you did. You need to interactively rebase the last 3 commits then via the following command.

``` 
git rebase -i HEAD~3
```

This will open a file in VIM. Change `pick` next to the relevant commit to `edit`. 

This will allow you to delete the file via:

```
git rm <offending_file_name>
git commit --amend
git rebase --continue
git push -f
```

### Tags
Create a tag:

```
git tag -a v1.4 -m "Version 1.4"
```

List all tags:
```
git tag
```

Show details for specified tag:
```
git show v1.3
```

Checkout tag:
```
git checkout v1.4
```

Push tags:
```
git push --tags
```
