##git##
---
###_log_###

quick and short way of showing logs:

    git reflog

display diff of last 2 commits:

    git log -p -2

show number of lines changed

    git log --stat
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
###_branching_###
---

create a new branch and switch to it:

    git checkout -b <newBranchName>

---
###_remote_###
---

    git remote -v
    git remote set-url orgin yourRemoteGitUrl
    git push <origin> <master>
    git push --tags


---
###_setting up_###
---
You only need to do this once, unless you started working on a different computer.

    git config --global user.name "You Name"
    git config --global user.email "you@example.com"

this will create a local file called `.gitconfig` in your home folder.

You can also set other parameters like editor, diff-tools the same way.

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
