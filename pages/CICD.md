# Continuous Integration and Continuous Delivery

[Continuous integration and continuous delivery (CI/CD)](https://www.atlassian.com/continuous-delivery/continuous-integration) is the practice of automating the build and deployment from source control to the development and production servers. CI/CD is central to our coding process at IT Partners. 

There are two types of CI/CD processes we use: [GitHub Actions and Azure Pipelines](https://docs.microsoft.com/en-us/dotnet/architecture/devops-for-aspnet-developers/actions-vs-pipelines). 

How CI/CD is set up should be documented in the README.md, along with a GitHub badge or link to the pipeline. 

## GitHub Actions

This is a lightweight process connected to the individual GitHub repository. This is used when we need to connect our GitHub code repository to Azure servers for a simple build/test/deploy pipeline flow using the .NET Core command-line interface. 

## Azure Pipelines

This is used to connect our GitHub code repository to on-premises servers, or there are additonal steps that cannot be handled by the GitHub Actions flow. All builds are handled inside our [Azure Dev Ops IT Partners Pipeline Build](https://dev.azure.com/itpartnersillinois/Pipeline%20Repository%20from%20Gitlab/_build). 

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
