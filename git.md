##git##
---
###_log_###

quick and short way of showing logs:

    git reflog

display diff of last 2 commits:

    git log -p -2

show number of lines changed

    git log --stat

Note that git use `less`-like way to display results.

---

"git way" of renaming files

    git mv oldname newname
    git commit -m "rename oldname to newname"
---
###_add&commit_###
---
interactively "add", very helpful tool:

    git add -i 
 
quick way of committing single change:

    git commit -am "commit description"

note that newly created files cannot be added by `-a`, but can be added by `-A`, and `-Am` does not work.

---
###_reset_###
---
unstage a file or all (if no FileName sepcified)

    git reset HEAD optionalFileName

in case something has already been commited, (like a revert or merge)

    git reset --hard HEAD~1

---
###_git diff_###
---

    git diff --name-only

    git diff master your-branch --name-only
---
###_branching_###
---

create a new branch and switch to it:

    git checkout -b <newBranchName>

Or:

    git checkout -b <newBranchName> <remoteName>/<branch>

Checkout a remote branch (create a branch that tracks remote)

    git checkout --track origin/serverfix
    git checkout --track <localname> origin/serverfix

show local branches:

    git branch

check which branches are tracking what:

    git branch -vv

show only remote branch:

    git branch -r

show both local and remote branches

    git branch -a

---
###_merge and rebase_###
---

`rebase` is roughly speaking run "recording" on to a different branch.

`git rebase onto` TODO


---
###_remote_###
---

    git remote -v
    git remote set-url orgin yourRemoteGitUrl
    git push <origin> <master>
    git push --tags

push to remote and track it too:

    git push -u orign <yourBranch>

`git fetch` sync remote data to local, `git pull` is roughly speaking `git merge` followed by `git fetch`. 

do `git branch -a` first, then

    git diff <remote/origin/master> <localBranch> <filename>
    git diff <remote/origin/master>..<localBranch> <filename>

the two dots `..` are optional.


---
###_creating a remote repo_###
---

To create a remote repository.

(assume you have already set up a user with name `git` for this purpose.)

    sudo git init --bare sample.git
    sudo chown -R git:git sample.git

    git clone git@localhost:/RepoDir/sample.git/

the last `/` is optional.

---
###_stash_###
---

to stash, list, and restore to stashed stage (apply):

    git stash
    git stash list
    git stash apply
    git stash apply stash@{2}
    git stash drop stash@{0}

---
###_setting up_###
---
You only need to do this once, unless you started working on a different computer.

    git config --global user.name "You Name"
    git config --global user.email "you@example.com"
    git config --global color.ui auto

this will create a local file called `.gitconfig` in your home folder.

You can also set other parameters like editor, diff-tools the same way.

    git mergetool --tool=<tool>

help:

    git mergetool --tool-help

check version:

    git --version

---
###_.gitignore_###
---

    #comments
    *.[oa]
    #not
    !exception.o


---
###_.gitattributes_###
---


---
###_diff_###
---

    diff -Naur old_file new_file > diff_file
    patch < diff_file

`-u`, output (default 3) lines of unified context

`-a`, treat all files as text

`-N` treat absent files as empty



output:

    patching file old_file