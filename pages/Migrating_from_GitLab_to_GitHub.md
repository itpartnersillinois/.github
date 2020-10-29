# Migrating from Gitlab to GitHub

## Before you start

Make sure you do not have any temporary branches (this means that you usually will only have two branches, master and develop)

Make sure you don't have any local changes. 

## Migration pattern

From your command line, make sure you have the latest code. 

     git pull --all
     
Mirror your repository to the new Github URL

      git push --no-verify --mirror {github url}
      
Change your remote to the new Github URL

      git remote set-url --push origin {github url}
      
Archive your old Gitlab account by going to Settings --> General --> Advanced --> Archive Project

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/master/README.md)
