# Creating CI/CD for a Function App in Azure

1. Go to the [Azure Dev Ops IT Partners Pipeline Build](https://dev.azure.com/itpartnersillinois/Pipeline%20Repository%20from%20Gitlab/_build). 
2. Click on New Pipeline
3. Choose GitHub
4. Choose your repository. The IT Partners GitHub repository should be already connected. 
5. Choose .NET Core Function App to Windows Azure
6. Choose your Azure subscription. 
7. Choose your Function App. For the Working Directory, enter your working directory of your CS Project (for example, if your CS project is in subfolder MyProject, enter $(System.DefaultWorkingDirectory)/MyProject). If your project is in your root, just enter $(System.DefaultWorkingDirectory)
8. Save and commit. 

This will place an azure-pipelines.yml file in your root directory. You can modify this as you need to to meet your needs. 
