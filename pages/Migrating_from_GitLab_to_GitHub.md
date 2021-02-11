# Migrating from Gitlab to GitHub

## Before you start

Make sure you do not have any temporary branches (this means that you usually will only have two branches, main/master and develop)

Make sure you don't have any local changes. 

Make sure you are on the main/master branch

    git status
    git checkout master

## Migration pattern

From your command line, make sure you have the latest code. 

     git pull --all
     
Mirror your repository to the new Github URL

      git push --no-verify --mirror {github url}
      
Change your remote to the new Github URL

      git remote set-url --push origin {github url}
      
Archive your old Gitlab account by going to Settings --> General --> Advanced --> Archive Project

Confirm your existing local copy is pointing to only the Github version

      git remote -v
      
If it isn't, then remove the origins and re-add them

      git remote rm origin
      git remote add origin {github url}
      git reset --hard
     

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
