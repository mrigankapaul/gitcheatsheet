```
git --version
git config --list //to display user information such as user.name and user.email
git status
git status --s //for short status
git help init //for accesing the help for a commnad in this case init
git -h init //for concise help
git config --global user.name="Mriganka Paul" //global flag for every repository that you use on your computer, system applies to every repository for all users on your computer
git config --global user.email="paul.mriganka@gmail.com"
//no flag applies to only current repository
git config user.name //local --> global
git diff a.txt //diff for modified file with commited version
git diff --cached a.txt //diff for added file with commited version
git init //initializes the local repository
git rm --cached a.txt //for unstaging a staged file, then undo the changes and re-connit file
git add <file name>
git add <directory name>
git commit -m "initial commit"
git log --oneline -2
git clone https://mrigankapaul@bitbucket.org/mrigankapaul/projectb.git <localprojectname>
git remote --v //details of remote repository
git remote add origin https://mrigankapaul@bitbucket.org/mrigankapaul/projecta.git //to add a remote repo to an existing local repository
git push -u origin master //for first push to remote repository -u is for tracking relationship between remote and local repository

References
git log --oneline --graph
git show sha1-hash or git show <<part of sha1 hash>> or git show <<reference>>
git show HEAD //for HEAD information
git show HEAD~ //for showing the parent of HEAD
git show HEAD~2 //for showing the parent's parent
git show <<branch label>>~
git show <<part of sha>>~
git show master^ first parent of the commited
git show master^2 second parent of a merge commit
git show master^^ first parent's parent
git show <<tag name>>
git tag // display all the tags of the repo
git tag -a [-m <msg> | -F <file>] <tagname> [<commit]] //for anotated tag
git tag -a -m "includes feature2" v2.0
git tag -a -m "includes feature2" v2.0 HEAD^
git push origin --tags //pushing all tags
git push origin v1.0 //pushing a single tag
git tag -a -m "just a temp tag" temp HEAD~
git tag -d temp

// lightweight tag not recommended
git tag v1.0
git tag v0.1 HEAD^

// Branch
git branch //to see the list of branches on the local repository
git branch dev //to create a branch
git checkout <<branch name>> //for checking out a branchg
git checkout <<sha1 commt> //for checking out a commit - detached HEAD
git checkout -b dev //to create and checkout a branch
git checkout -b test f2b38b0 // to checkout a branch from a specific label
git branch -d dev //deleting a branch
git branch -D dev //to force delete a branch if the commits of a branch has not been deleted
git reflog //list of all teh deleieted commits which can be checkout using the sha1
git log --oneline --graph --all //shows all local branches
git checkout -b featureX 72e0058 //to recover a deleted branch

// Merging
// fast forward - Possible if no other commits have been made to the base branch since branching
git checkout master
git merge  featureX
git branch -d featureX
git merge --no-ff featureX //if the fast forward merge is to be avoided and only merge commits are to be done

// Remotes
git branch --all // to list the tracking branch and local branches
git remote set-head origin develop //change the default tracking branch
git log -all
git fetch
git pull // get fetch + get merge FETCH_HEAD git pull --ff, --no-ff --ff-only --rebase

// Rebase
git checkout featureX
git rebase master
// Above 2 commands equivalent to - git rebase master featureX
//merge conflicts in rebase
//after resolving the merge conflict and adding to the staging area
git rebase --continue // or the following
git rebase --abort


// amending commit history
git commit --amend -m "add fileC.txt" //amending a commit message
git commit --amend --no-edit //updating the commit contents without updating the commit message

git rebase -i <<after this commit>>

// squash merge
git checkout master
git merge --squash featureX
git commit
    accept or modify the squash message
git branch -D featureX

// Pull Request
git push --set-upstream origin featureX //pushing to a new branch
```
