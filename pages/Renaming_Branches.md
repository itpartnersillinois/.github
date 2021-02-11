# Renaming Branches

## Remote Branch

Follow instructions at https://docs.github.com/en/github/administering-a-repository/renaming-a-branch. 

The short instructions are to click on the branches label, and click on the edit icon to rename the branch. 

## Local Branch

All individuals will need to run the following commands at their git repository. This will need to be done for each repository that is being renamed.

```
git branch -m master main
git fetch origin
git branch -u origin/main main
```

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
