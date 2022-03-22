# Protecting Branches

## Default Branch

The default branch should be main

To change this, go to Settings --> Branches. Confirm the default branch is main

## Branch Protection

You should add two rules to your branches.

Branch name pattern: main
* Include administrators: true

Branch name pattern: develop
* Include administrators: true

Your screen should look like this:

![Branch Protection Listing](https://github.com/itpartnersillinois/tutorial/blob/main/images/branch_protection_listing.png)

If you have a separate staging branch, you should protect the staging branch as well. 

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
