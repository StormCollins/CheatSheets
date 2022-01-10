# CheatSheets

## Git 

### Config File
View location of global config file:

```
git config --list
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
