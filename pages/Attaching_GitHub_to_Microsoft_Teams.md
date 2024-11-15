# Attaching GitHub to Microsoft Teams

When you check in a branch into any project within the IT Partners organization, it will automatically write a message to the _Github Pull Requests (EG)_ in the _ITP Automated Channels and Github_ team. You do not need to make any changes to your repository to include this. 

This allows everyone a single place to see what people are working on in terms of pulls and merges across the organization. 

## How this is done

In Microsoft Teams, choose a channel, the three dots, and choose Workflows.

You will be creating a webhook to write information to MS Teams. 

Enter a name for the Github Enterprise connection, and record the webhook it generates. 

Go to your Github Organization and choose Settings --> Webhooks. 

Add the webhook to the list and make sure it is sending in JSON format. We are triggering the webhook on the following options:

* Branch or tag creation
* Branch or tag deletion
* Commit comments
* Deployments
* Meta
* Projects
* Pull request review comments
* Pull request reviews
* Pull requests
* Pushes

Ensure the "Active" checkbox is clicked

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
