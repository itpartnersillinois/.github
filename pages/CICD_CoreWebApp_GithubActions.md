# Creating CI/CD for .NET Core Web Apps using Github Actions

1. In your Azure Function App, download a Publish Profile
2. In your GitHub project --> Settings --> Secrets, add the following secret 
     * AZURE_PUBLISH_PROFIE
3. Create a .github/workflows/deploy_main.yml file that has the following information:
     
```json
name: deploy_main

on:
  push:
    branches: [ main ]

env:
  AZURE_NAME: uofi-itp-courses
  AZURE_PACKAGE_PATH: '.' 
  DOTNET_VERSION: '3.1' 
  PROJECT_FOLDER: CourseLoad
  TEST_PROJECT_FOLDER: CourseLoadUnitTest
  DOTNET_PUBLISH_RUNTIME: win-x64

jobs:
  publish:

    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Setup .NET Core
      uses: actions/setup-dotnet@v1
      with:
        dotnet-version: ${{ env.DOTNET_VERSION }}

    - name: Install dependencies
      run: dotnet restore
      
    - name: Build
      run: |
        cd ${{ env.PROJECT_FOLDER }}
        dotnet build --configuration Release --no-restore
        dotnet publish -c Release -o ../dotnet-webapp -r ${{ env.DOTNET_PUBLISH_RUNTIME }} --self-contained true /p:UserAppHost=true

    - name: Test
      run: |
        cd ${{ env.TEST_PROJECT_FOLDER }}
        dotnet test --no-restore --verbosity normal

    - name: Deploy
      uses: azure/webapps-deploy@v2
      with:
        app-name: ${{ env.AZURE_NAME }}
        package: '${{ env.AZURE_PACKAGE_PATH }}/dotnet-webapp'
        publish-profile: ${{ secrets.AZURE_PUBLISH_PROFIE }}
```
Change the environment variables
* AZURE_NAME: *The web app name in Azure*
* AZURE_PACKAGE_PATH: '.' 
* DOTNET_VERSION: '3.1' 
* PROJECT_FOLDER: *The project folder*
* TEST_PROJECT_FOLDER: *The project folder for unit tests -- if this does not exist, make sure to remove the Test section*
* DOTNET_PUBLISH_RUNTIME: *The runtime identifier: https://docs.microsoft.com/en-us/dotnet/core/rid-catalog*

4. Update the README describing the CI/CD and add the status bar

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
