# Workflows for GitHub-projects
This Repository provides and maintains a couple of workflow files to support our Lifecycle of an issue.

Copy the files from ".github/workflows" into the workflow folder of your repository.
Using the provided files together with an instance of the template project [Issue Lifecycle](https://github.com/orgs/DLR-AMR/projects/7) the managing of your issues is nearly fully automated.
# How to setup a project. 
1. Use the template [Issue Lifecycle](https://github.com/orgs/DLR-AMR/projects/7)
2. On the project side click on the "..." symbol (upper right corner)
3. Click on "Workflows"
4. Select "Auto-add to project", go on "Edit" and replace the filter with your repository and "is:issue is:open". If not all issues should land in this project you can also add "label:YOUR_LABEL_NAME" to only add issues that have a certain label.
5. Create the labels "workload:high", "workload:medium", "workload:low", "priority:high", "priority:medium" and "priority:low" in your github repository.
All issues that match the filter will land in your project. Having a look at your Board you will see that all freshly opened issues will land in "In-Box". 

As soon as an issues has been labeled with a workload and a priority it is ready to be worked on and will move to the column "ToDo".

Once an assignee for that issue has been found it will move to "In Progress", preventing that two developers will work on the same Issue. 

If a PR is opened, reopened or a draft PR is set to "ready to review" and the Issue that is solved by that PR is referenced by "#ISSUE_NUMBER" the card is moved to "Needs Review". 

Once someone is assigned to do the review the issue is moved to "In Review". 

Merging the PR will close the Issue and it will be moved to "Done" 

Once it has been communicated to other developers what has been done the card can manually be moved to "Can be archived".
All closed issues will automatically be archived after 2 weeks. 