# Personal-Git-Best-Practices
This is a compilation of my personal git best practices to be used as a reference and to help guide teaching new-to-git developers.

## Getting Started ##
1. Install git
    * https://git-scm.com/download
2. Set Username
    * **git config --global user.name "*Your Name*"**
    * Will be seen on the website/repo commit chain
3. Set Email
    * **git config --global user.email "*Your Email*"**
    * This probably should be credentials for your repository account so that your commits are properly synced with the online account
    * Will be seen on the website/repo commit chain
4. Navigate to the source code on bitbucket
5. Click Clone in the top right
6. Copy the command in the pop-up
7. Create folder to hold local clone of repository
8. Open Git Bash
    * Right Click in the folder and click Git Bash here
9. Clone Repository
    * Right click the bash and click paste or type **git clone *branch url* **

NOTE: It is beneficial to show hidden items in your folder explorer as this will show all the git, hidden files for later use

## Branches ##

### Create Branch ###
1. Navigate to Branches
2. Click Create Branch in the top right
3. Pick Branch to branch from

### Checkout Remote Branch ###
1. Navigate to the folder that
2. Update your local git caches
    * **git pull**
3. Ensure no uncommitted code
    * **git status**
4. Checkout the remote branch to your local computer
    * **git checkout -b *local branch name* *remote branch name* **
    * The local name can be anything, but if it does not match the remote branch names ending (i.e the part after the last \) you will have to manually set the upstream with ** git branch -u *remote branch name* **. If you do not, that is also fine, but when pushing code commits, there will be an additional requirement to clarify the remote branch you are pushing to

### Change Branch ###
1. Check if the branch is found locally
   * **git branch**
2. If your destination branch is found locally
    * **git checkout *your destination branch* **
    * The branch in the prompt should change to the name of the destination branch if done correctly
3. If your destination branch is NOT found locally, you will have to checkout the remote branch

### Delete Branch ###
1. Delete the local branch 
    * **git branch -d *your to be deleted branch* **

NOTE: Remotes branches can be deleted, but to reduce error do this via the branch tab. Typically, branches will be self deleted once a pull request has been approved for the desired branch so no need to manually delete them after

### Reset Branch ###
1. Reset your local commits
    * **git reset --hard**

NOTE: This will destroy all uncommitted code

### Revert Branch ###
1. Checkout a copy at that commit
    * **git checkout *commit ID* **
2. Commit the code and push to the remote branch to override the commits you want to be removed

### Rebase Branch ###
1. Be on the branch to be rebased
2. Rebase your current branch with the base branch
    * **git rebase *your base branch* **
3. Push the changes to the remote repository
4. If it states that the branches have diverged, force push it and overwrite the repository with the current code
    * **git push -f**

NOTE: Rebasing can be quite a difficult task. It is often better to merge instead of rebasing.

### Merge Branch ###
1. Checkout the branch that your branch diverged from
2. Merge the branch into the base branch
    * **git merge *your branch name* **
3. Push the changes to the repository


## Code Management ##

### Staging Code for Commit ##
1. Check if there is uncommitted code. This will be seen as red
    * **git status**
2. If all red, modified files are to be committed add all to the commit
    * **git add -A**
3. If you have to choose which files to be committed, add each one indivitually
    * **git add *your file name* **
4. Use **git status** to check if all the files to be committed have turned green

### Commit Code ###
1. Add all desired files to be committed.
2. Begin creating the commit
    * **git commit**
3. Write your commit message.
    * On the first line the font will be yellow if it will be seen in the title. Hit enter twice, and begin writing your commit message
    * All KanBan IDs should be present in the title to link with the repository
4. Check if there has been a commit added to your local repository
    * **git status**

NOTE: You make also use **git commit -m *your message here* ** to do the commit message in line.

### Push Commits ###
1. Ensure there are commits on your local branch
    * **git status** 
2. If the branch name is same as the remote branch's name, push the commit
    * **git push**
3. If the branch name is NOT the same as the remote branch's name or the previous step failed, look up all the branch names
    * **git branch --all**
4. Push the local commits to the repository for the specific branch
    * **git push origin *your remote branch's full name* **

### Pull Request ###
1. Navigate to Pull Requests
2. Select branch to be pulled
3. Select Reviewers
4. Check Close branch if you want the branch to be deleted after the pull request is approved


## Resources ##
* Download - https://git-scm.com/downloads
* Visual Studio Integration - https://docs.microsoft.com/en-us/vsts/git/gitquickstart?view=vsts&tabs=visual-studio
* Command List - https://confluence.atlassian.com/bitbucketserver/basic-git-commands-776639767.html
