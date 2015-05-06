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

`git fetch` sync remote data to local, `git pull` is roughly speaking `git merge` followed by `git fetch`. 

do `git branch -a` first, then

    git diff <remote/origin/master> <localBranch> <filename>
    git diff <remote/origin/master>..<localBranch> <filename>

the two dots `..` are optional.

---
###_setting up_###
---
You only need to do this once, unless you started working on a different computer.

    git config --global user.name "You Name"
    git config --global user.email "you@example.com"

this will create a local file called `.gitconfig` in your home folder.

You can also set other parameters like editor, diff-tools the same way.

    git mergetool --tool=<tool>

help:

    git mergetool --tool-help

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
