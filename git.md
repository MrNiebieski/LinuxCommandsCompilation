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

    giv mv oldname newname
    git commit -m "rename oldname to newname"
---
###_add&commit_###
---
interactively "add", very helpful tool:

    git add -i 
 
quick way of committing single change:

    git commit -am "commit description"

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
###_.gitignore_###
---

    #comments
    *.[oa]
    #not
    !exception.o