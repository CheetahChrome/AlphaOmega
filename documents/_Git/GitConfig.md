---
title: Configuration Operations
layout: default
---

## Git Configuration Setups

This details how to utilize the config files to add aliass and other processes which are not appearent at the first blush.

### Opening up The Git Environment Configs

Setting up a git environment is required for a smooth working operations. The following commands work with git config to allow one to specify flags.

| Command | Description | Notes |
| - | - | - |
|`git config --list`| Show all config enivornment variables|
|`git config --list --show-origin`| Show where the commands are in the config files|
|`git config --{local|global|system}`| Open the local or global or system files|
|`git config --{environemnt} -- edit`| Edit the target environement|


### Personal Aliases Used

`shove` adds all items, and them does a git commit. `Stati` is short for a status but in single line format. The `alias` shows all the aliases that have been setup.

```
[alias]
    shove = !git add -A && git commit
    stati = !git status -s
    alias = !git config --get-regexp alias
```


### Historical Commit Aliases

These list the log, either in human readable format or by single line to view all commits.

```
[alias]
    histogram = !git log -20 --date=human --pretty=format:\"%ad %h %an | %s\" --graph 
    histowho = !git log -10 --date=human --format=format:\"%C(yellow)%h%C(reset) (%C(blue)%an%C(reset)) %ad | %s\"
    loghead = !git log -18 --decorate --date=human –oneline
```

### Setup Araxis Merge to Work with Git

Put put these into the `global` environment so they span all repositories you are working on. Note that if you install Araxis for just you, the location of `compare.exe` is not in the program files, but the AppSettings local. 

```
[diff]
    tool = araxis
[difftool "araxis"]
    path = C:\\Program Files\\Araxis\\Araxis Merge\\compare.exe
[merge]
    tool = araxis
[mergetool "araxis"]
   path = C:\\Program Files\\Araxis\\Araxis Merge\\compare.exe	
```