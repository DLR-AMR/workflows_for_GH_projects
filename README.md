# Workflows for GitHub-projects
This Repository provides and maintains a couple of workflow files to support our Lifecycle of an issue.

Using the provided files together with an instance of the template project [Issue Lifecycle](https://github.com/orgs/DLR-AMR/projects/7) the managing of your issues is nearly fully automated.

# Requirements
You need to provide a personal access Token for github that has read/write access for projects and issues on organizaton level.

# How to setup a repository.
The workflows are triggered by a repository. The projects can be on organization level.
1. Copy the files [move_card.yml, issue_event_moves_card.yml, pr_event_moves_card.yml, quick_pr.yml ]from ".github/workflows" into the workflow folder of your repository.
2. Replace the secret variables with a secret containing a PAT with write-rights to your projects and issues.

# How to setup a project. 
1. Use the template [Issue Lifecycle](https://github.com/orgs/DLR-AMR/projects/7)
2. On the project side click on the "..." symbol (upper right corner)
3. Click on "Workflows"
4. Select "Auto-add to project", go on "Edit" and replace the filter with your repository and "is:issue is:open". If not all issues should land in this project you can also add "label:YOUR_LABEL_NAME" to only add issues that have a certain label.
5. Create the labels "workload:high", "workload:medium", "workload:low", "priority:high", "priority:medium" and "priority:low" in your github repository.

# What will happen
All issues that match the filter will land in your project. Having a look at your Board you will see that all freshly opened issues will land in "In-Box". 

As soon as an issues has been labeled with a workload and a priority it is ready to be worked on and will move to the column "ToDo".

Once an assignee for that issue has been found it will move to "In Progress", preventing that two developers will work on the same Issue. 

If a PR is opened, reopened or a draft PR is set to "ready to review" and the Issue that is solved by that PR is referenced by "#ISSUE_NUMBER" the card is moved to "Needs Review". 

Once someone is assigned to do the review the issue is moved to "In Review". 

Merging the PR will close the Issue and it will be moved to "Done" 

Once it has been communicated to other developers what has been done the card can manually be moved to "Can be archived".
All closed issues will automatically be archived after 2 weeks. 

For quick-fixes you can also open up a "quick Pull request". It can be annoying for a developer to open up an Issue for every small typo / bug-fix / one-line-change in a repository. To make this a more comfortable process we allow developers to open a quick-PR, which is a PR that does not reference an Issue. In that case an Issue is created and linked to the PR by adding "Closes #ISSUE_NUMBER" to the top of the body of the PR. 
