# Code review

All production projects require a code reviews before pushing to the develop branch. 

This is set up on an organizational level. To add this, go to *Settings* --> *Custom Properties* and set the repository status to "Production" and choose your college. This will automatically enable the code review rules. 

![Custom Properties](https://github.com/itpartnersillinois/tutorial/blob/main/images/custom_properties.png)

## Codeowners File

All IT Partners should have a CODEOWNERS file that lists who should be responsible for code reviews. Under most circumstances, this should be the IT Code Review group, and this group should have write access to the project.

You can use the following file as your CODEOWNERS file. 

        # Code Owner Review when someone opens a pull request.

        *       @itpartnersillinois/itp-code-review

[Back to Main](https://github.com/itpartnersillinois/tutorial/blob/main/README.md)
