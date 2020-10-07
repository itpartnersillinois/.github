# Migrating from Gitlab to GitHub

From your command line, make sure you have the latest code. 

     git pull --all
     
Mirror your repository to the new Github URL

      git push --no-verify --mirror {github url}
      
Change your remote to the new Github URL

      git remote set-url --push origin {github url}
      
Archive your old Gitlab account by going to Settings --> General --> Advanced --> Archive Project

[Setting Permissions and Topics](https://github.com/itpartnersillinois/tutorial/blob/master/Setting_Permissions_and_Topics.md) -- [Attaching GitHub to Microsoft Teams](https://github.com/itpartnersillinois/tutorial/blob/master/Attaching_GitHub_to_Microsoft_Teams.md)
