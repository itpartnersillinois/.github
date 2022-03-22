# Branches and Server Information

Github projects should have a main and develop branch. Both should be protected and not allow people to directly deploy to them. If a code merge conflict requires the develop branch to be unprotected, this should be done only by the lead developer and the branch should be re-protected immediately.

The main branch should always mirror production, and the develop branch should always mirror a shared test environment if a test environment is being used. Continuous Integration/Continuous Deployment (CI/CD) will be in place to ensure this mirroring process, and development should never be done directly on the server. Do not update code directly on the server.

There may be a staging branch that sits between the main and develop branch. This is used for external review but before code is deployed to production. Like main and develop, the stanging branch should always mirror a shared environment. Continuous Integration/Continuous Deployment (CI/CD) will be in place to ensure this mirroring process, and development should never be done directly on the server.

_Ensure that all existing functionality works before merging your branches into develop or main branches._ If you accidentally merge code into the develop branch that causes existing functionality to break, then notify other developers and the PM so the merge can be reverted or fixed. 

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
