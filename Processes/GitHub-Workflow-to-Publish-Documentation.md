# How To Publish EOS Documentation in GitHub

This document provides instructions to use GitHub to publish documentation to the [EOS Documentation portal](https://docs.eosnetwork.com).

## Definitions
The following table provides definitions for Github branches used in this process:

| **Branch** | **Definition** | 
| --- | --- |
| Current | The current branch is the present branch. This branch has focus. | 
| Default | Each repository contains one default branch, which is typically called main. GitHub creates this branch when a repository is initialized. | 
| Local | The local branch resides in your local environment. Changes made to the local branch are merged into a target branch. | 
| Main | The main branch is typically the default branch. PRs merge a source branch to the main branch. | 
| Remote | The remote branch is typically your local branch. | 
| Source | The source branch contains updates to be merged into the target branch. Typically the changes you made previously to the target branch become the source branch for the final merge into the main branch. | 
| Target | The repository and branch location where you want your new or updated content to reside | 

## How to Publish New or Updated Content to EOS Documentation

### Before You Begin
Ensure you have the following items ready before you begin this procedure:
* Infrastructure - appropriate repository(ies) available for PR/Commit
* Access to Github Engineering and DevRel repositories, as necessary
* Release version; major or minor
  * Release version determined by the developers making the release branch
* Knowledge of the code branch/tag
* Content ready for publish in .md format
   * Are Templates applied?


## To Create/Edit Files
Complete the following steps to create/edit files:
1. Open the target github repository from your web browser.

    **Note**: The target GitHub repository is the location where you want to edit or add new content, the repo where you want to push your changes. For the docs repository, the target branch is “main.”


**For example**: When adding glossary items to the glossary, the target GitHuib repository is the “docs” repository, which contains the glossary file.   


2. Launch the GitHub web editor. Click . (to use the same tab) or > (to use a new tab).  

3. Create a new (or select existing) branch devrel#N, where #N is the issue number. This branch will be the source branch for your PR.

    **Note**: The current branch is shown on the bottom left corner of your screen. 

If the source branch is already shown, proceed to step 4, otherwise continue.  

 1.1 Click on the current branch on the bottom left corner.

  A drop down *Switch to Branch or Tag* dialog opens  

 1.2. Click on the *Create new branch from …* option. 

 1.3. Select the target branch for your PR; typically the target branch is the main branch.  

 1.4. Type the New branch name in the textbox; this is typically devrel#N, where #N is the issue number. (Example: `fix-devrel#12`)

    The branch naming convention is `<feature|fix>-devrel#<issue#>`

    Use `feature` if adding new content

    Use `fix` if updating or deleting 
    existing content 

    The `issue#` is the issue number listed on the devrel project board (the number on the right, not the left)

    (Use *devrel#N* because we need to know where issue resides). 

**Note**: If doing a feature and a fix, split them into 2 PRs  

 1.5. Click on *Switch to Branch* to confirm that you want to switch to the newly created target branch

**Note**: Because your PR will make changes to the target branch, your new branch must be based from it.

**Caution**: Check the name at the bottom left corner of your window. Make sure the name of the branch has changed to the new branch. DO NOT DIRECTLY MAKE CHANGES TO THE MAIN BRANCH.  

4. From the Explorer tab (1st tab on left navigation vertical bar), hover over the [repository name] [GitHub] directory to view the selection icons.  

   4.1. To select or create a folder, click on the folder icon.  

   4.2. To select or create a file, click on the file option
 
       4.2.1. To create a new file, enter the name of the file in the textbox, then copy and paste your .md file into the editor or start developing your content. 

       4.2.2. If editing an existing file, double-click the filename, the contents of the file will appear in the file editor
5. Update/edit the file in the file editor

## To Create Commits/Push Changes
Complete the following steps to create commits/push changes:  

1. Complete the Create/Edit Files procedure. 

2. Save your file changes.

   **Note**: The Github Editor automatically saves your changes. The Source Control view of the left navigation vertical bar (3rd icon from the top) indicates the number of changes made to the file.  

3. Click on the Source Control view (3rd one on left nav bar).

   The left navigation vertical bar displays files that have changes.  

4. Click on the plus (+) icon for each file you want to include in your commit to staging.

**Note**: The staging site is the location for the updated/new file.

**Best Practice**: Stage one file per commit unless you’re performing a blast action, such as delete, replace, etc., on a group of files.  

5. Enter a descriptive commit message in the Message text box in present tense.

**For example**: Add new how-to template or fix minor typos in explainer. 

6. Click on the checkmark icon to push (publish) changes from the editor to the target branch.

**Note**: The target branch is also known as the remote branch. The target branch is the source branch when you create a PR to push changes to publish on the main branch.

7. Perform a Pull Request to request review.


## To Review Changes on the Remote/Target Branch
Complete the following steps to review changes on the remote/target branch:
1. Open the target github repository from your web browser.  

2. Select your existing target branch from the combobox.

**Note**: Scroll down the page until you see the commit(s) you pushed in the "create commits / push changes" steps above.
3. Review the changes made to the target branch and make additional changes as necessary

## To Pull Remote Changes From Your Remote Branch
1. If using the github web editor:
no action needed, just open the github editor and select your branch (this will bring the changes from remote).  

2. Else, if using a local editor:
from within the repo folder, invoke "git pull" from a shell terminal. (this will bring the changes from remote)

## To Rename Files
Complete the following steps to rename files:
1. Open the GitHub editor and select your branch. 

2. From the Explorer tab (icon on the left navigation vertical bar), right-click on the filename you want to rename. 

3. Select Rename from the menu. 

4. Enter the new filename. 

5. Press Enter