# Creating CI/CD for a Function App in Azure

1. Go to the [Azure Dev Ops IT Partners Pipeline Build](https://dev.azure.com/itpartnersillinois/Pipeline%20Repository%20from%20Gitlab/_build). 
2. Click on New Pipeline
3. Choose GitHub
4. Choose your repository. The IT Partners GitHub repository should be already connected. You will want to choose the "master" branch. 
5. Choose .NET Core Function App to Windows Azure
6. Choose your Azure subscription. 
7. Choose your Function App. For the Working Directory, enter your working directory of your CS Project (for example, if your CS project is in subfolder MyProject, enter $(System.DefaultWorkingDirectory)/MyProject). If your project is in your root, just enter $(System.DefaultWorkingDirectory)
8. Save and commit. 

This will place an azure-pipelines.yml file in your root directory. You can modify this as you need to to meet your needs. Make sure you migrate your master branch down to your develop branch so you pick up the .yml file. 

## Note about pipeline integration

If you add this, you may end up having it triggered on any code review. If you see this happening, you may need to change the CI/CD to only run during Continous Integration. To do this:

1. Go to the [Azure Dev Ops IT Partners Pipeline Build](https://dev.azure.com/itpartnersillinois/Pipeline%20Repository%20from%20Gitlab/_build).
2. Click on the pipeling and choose Edit. 
3. Click on the three dots and choose Triggers.
4. Choose "Pull request validation" --> Override the YAML pull request trigger from here, Disable pull request validation.

## Note about permissions

You need to be an owner of the subscription to be able to do this. 


[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/master/README.md)
