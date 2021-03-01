# Code review

For major projects, you should require code reviews before pushing to the develop branch. You may also add a code review for the main branch as well to confirm that everything has been reviewed. 

## How to add code review

When adding code review to a project. 

1. Select the project. 
2. Click on *Setting* at the top of the window.  
3. On the left side of the screen click *Branches*
4. Click *Add rule*
5. Enter the branch name you want to add the code review to. 
6. Check the box *Require pull request reviews before merging*. Leave the required approving review at 1. 
7. If you have a CODEOWNERS file (see below), then check the *Require review from Code Owners*
8. Check the box *Include administrators*
9. Click the *Create* button at the bottom of the page.

You should see the following:
![Branch Protection Rule](https://github.com/itpartnersillinois/tutorial/blob/main/images/branch_protection_rule.png)

## Codeowners File

All IT Partners should have a CODEOWNERS file that lists who should be responsible for code reviews. Under most circumstances, this should be the IT Code Review group, and this group should have write access to the project.

You can use the following file as your CODEOWNERS file. 

        # Code Owner Review when someone opens a pull request.

        *       @itpartnersillinois/itp-code-review

If this is present, then you can add the *Require review from Code Owners* checkbox, and it will automatically add everyone from the group to the code review. 

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
