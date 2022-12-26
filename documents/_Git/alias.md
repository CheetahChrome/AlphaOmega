---
title: Git Alias
layout: default
---

# Alias ET Motif
These are aliases that have the ET motif. When getting items from `Origin\Main` one will do a `git phonehome` that does a fetch and merge. 
The `git gohome` checkouts the main branch.


```
[alias]
    gohome    = !git checkout main
    phonehome = !git fetch -p && git pull
    callhome  = !git merge main
    cleanhome = !git clean -f
```

{: .warning }
The command `callhome` is used when one is on a different branch and one wants to merge the `main` into the working branch.