![git-model 2x](https://user-images.githubusercontent.com/7909404/35677656-5661e9be-0772-11e8-86bb-3ed1cfb78154.png)


# Branch Naming
Branch names should include their branch type (release/feature), issue number, and a brief description.  Follow the forms below.

- Release: release/XXX(where XXX is the release number; e.g. 01)
- Feature:  feature/issue-no-<minor-desc-or-issue-name>

# Merging

**Note:** There is no Staging branch mentioned in the diagram but we create it for Locked and Stable code. Also the **develop** branch is actually **qa** branch.

- Master --> Release
- Master --> Staging
- Master --> qa

Below is the branch merging strategy from Master

Master can ALWAYS be merged into the highest current release branch/qa branch/staging branch and SHOULD be merged to release after every Hotfix

- Master --> **Hotfix Branches**

Hotfix branches are those which will be created from Master directly if there is an urgent bug/issue to be solved. And this Hotfix branch can be directly merged to Master. Master can ALWAYS be merged into hotfix branches and SHOULD be merged to WIP hotfix branches whenever a completed hotfix is merged to master

- Release --> QA Branch

release branches can ALWAYS be merged into qa and SHOULD be merged to qa after every hotfix or new feature is added (this helps prevent dirty merge requests to qa)

- Release --> Feature Branches

release branches can ALWAYS be merged into feature branches and it's recommended that developers keep their feature branches "watered" with the latest from release so as to discover/resolve conflicts early beginning of each new sprint.

- Feature Branch --> QA
feature branches are merged into qa when they are ready for testing
 
- QA --> Release Branch
QA branch after tested will be merged to Current Release branch

- Release Branch --> Staging
To fully lock the code and set on staging for Demo. Release branch code will be merged to Staging

- Release Branch --> Master
For final production deployment last Release branch will be merged to Master.

