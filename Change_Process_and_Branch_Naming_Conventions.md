# Change Process and Branch Naming Conventions

## Change Process: Emergency/hotfix

Emergency/hotfix changes may be used if one of the conditions is true:
* A platform update is required and needs to be deployed immediately
* A security concern mandates an immediate change
* The application is down or is functionally unusable
* The program manager and lead developer agree that this is an emergency case

They are labelled as “hotfix/{netid}/{branch name}”, and are merged directly to the master branch.

## Change process: Regular/feature

Regular/feature changes are your typical, non-emergency changes. They are labelled as “{netid}/{branch name}”, and are merged directly to the develop branch
