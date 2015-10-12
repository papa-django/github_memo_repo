```
# git clone (http://stackoverflow.com/questions/651038/how-do-you-clone-a-git-repository-into-a-specific-folder)
git clone [url] [dir_name]

# list local branch
git branch -l

# delete local branch
git branch -d local_branch_name

# delete a local branch with diff from other branch
git branch -D local_branch_name

# create and pull a remote branch from a remote
git checkout -b < new_branch > origin/< new_branch >

# create a local branch, do stuff, then push that new branch to the remote repo
git checkout -b mynewfeature
... edit files, add and commit ...
git push -u origin mynewfeature

# delete last commit (will not delete modifications, just the commit)
git reset HEAD^

# rename last commit msg
git commit --amend -m "New commit message"

# rollback local repo after a git pull
use git log to find the hash of the desired commit
then git reset --hard 1234abcd where 1234abcd is the hash of the desired commit.

# checking difference between 2 branches and put that log into a file
git diff main-branch..alt-branch > file.name.diff

# pull rebase instead of merge when pulling, good for keeping a clean history
# mandatory when origin maintainer squashes on origin published branche
# warning : a rebase does not replay merge's commit, --rebase=preserve is to force git rebase to replay theses commits
# see http://stackoverflow.com/a/18930599
# see http://gitready.com/advanced/2009/02/11/pull-with-rebase.html
# see http://stackoverflow.com/questions/15915430/what-exactly-does-gits-rebase-preserve-merges-do-and-why
git pull --rebase=preserve

# cancel a merge (git version >= 1.7.4)
git merge --abort

# merge conflict in favor of "their" changes (origin changes)
git merge --strategy-option theirs

# cherr-pick a specific commit from one branch to another 
# (https://ariejan.net/2010/06/10/cherry-picking-specific-commits-from-another-branch/)
# here master is the targeted branch (ie : where the commit will go)
git checkout master
git cherry-pick 1234abcd
```