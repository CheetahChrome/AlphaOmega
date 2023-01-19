---
title: Git Alias With ET Motif
layout: default
---

# Alias ET Motif
To help with the standard process flow in Git, here are aliases that have the ET motif. It revolves around "Phone Home", where home is the remote repository. 

First step in getting items from `Origin\Main` one will do a `git phonehome` that does a fetch and merge. 

Then one will work in a new local branch to do the work at hand. Once done after a push, one needs to go back to the main branch.

The idea here, is that new changes are in the origin's main branch that need to be merged into the working branch.

So to get that new code, one has to  `git gohome` to checkout the main branch and do a `git phonehome` to get the latest main updated.

Finally we need to merge from `main` to the working branch. The usual checkout of the working local branch is done.

Once in the working branch, the finaly command `git callhome` is done to do the heavy lifting of the `merge` operation.

Once done with all work, if there are any untracked files use `git cleanhome` to bring everything to a pristine state.


```
[alias]
    gohome    = !git checkout main
    phonehome = !git fetch -p && git pull
    callhome  = !git merge main
    cleanhome = !git clean -f
```

{: .warning }
The command `callhome` is used when one is on a different branch and one wants to merge the `main` into the working branch.