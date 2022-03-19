# 9 useful Git commands
2021-09-25

Check these 9 useful Git commands for your day to day work
Here we're going to explore some common Git commands, which help you work more fluid with Git, you can revisit this page when whenever you need these commands.

## Basic Commands

First we'll begin with some basic commands, these will help you to set up your enviroment and create a local reposiory:

*Note*: we can have two repositories a local repository (in your computer) and remote repository (generally a repo on GitHub, GitLab, etc)

```bash
# Config/Update your username/email
git config --global user.name "your_name"
git config --global user.email "your_name@gmail.com"
# Check your username/email
git config --global user.name
git config --global user.email
# Create your local repository
git init # you need to run this command in your project folder
# For an existing repository you can clone that repo
git clone repo-url
```

Now we are going to check a basic workflow to add changes in your project
```bash
# When you change a folder/file in your project you can
# show your current unstaged changes with this command
git status
# Add your new changes to staging area
# To do this you can use two commands
# You can add an especifically directory or file, e.g.
git add filename
# You can add all the changes 
git add -A # this command stages all your changes
git add . # stages new files and modifications, **without deletions**
# Commit (make a record of your changes)
# -m flag is used to add an inline commit message, instead of open an editor
git commit -m "Commit message" 
# Show commits history
git log
# Send changes to remote repo
git push origin branch-name
```

Once we know the basic git workflow to save/track changes in our projects, it's moment to see more commands and variation of above commands

## Basic Commands Variations

Instead of execute `git add` and `git commit` as differents commands we can do it in one command:
```bash
# -a automatically stage all tracked, modified files before the commit
git commit -am "Commit message"
```

Show one line commits history
```bash
git log --pretty=oneline
# Show a tree view
git log --graph --oneline --all
```

## Branch

Command to work with branches

Creating a new branch
```bash
# This command only creates the branch but you still are in the current branch
git branch new-branch
```

Show all branches
```bash
# This command only creates the branch but you still are in the current branch
git branch
```

Deleting a branch
```bash
git branch -D new-branch
```

## Checkout

This command is used to move between [branches](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell) or as alternative to create a branch, also you can restart your changes with this command.

Creating a new branch and moving to the new branch
```bash
git checkout -b branch-name
```

Moving to an specifict branch
```bash
git checkout specifict-branch
```

Return to previus branch
```bash
git checkout -
```

Remove unstaged changes
```bash
git checkout .
```

## Stash

This is a useful command, I think is like copy/paste but for your work when yout are working with Git. Usually you can run this command to move your work from a branch to another branch

Stashinng changes
```bash
git stash
```

List stashing changes
```bash
git stash list
```

Apply last stashed change
```bash
git stash apply
```

## Rebase

This is a command to combine your work with others work. It's similar to `merge` command, but you can do more things, like combine commits or rename them, etc.

Rebase your branch from master branch
```bash
git rebase master
```

Rebase your changes interactively
```bash
# rebase interactively with master branch
git rebase -i master
# rebase interactively your last 3 commits
git rebase -i HEAD~3
```

Interactively means that Git opens your default editor to allow you to manage your commits

## Reset and Revert

I usually use this command to reset last change than inentantionally I created. You can use revert when you want to create a explicit commit that show the revert changes,
this is specially to send public commits showing the revert changes

Reset/Remove last change
```bash
# Keeps the changes in the staging area
git reset --soft HEAD~1
# Remove all modifications in the last change
git reset --hard HEAD~1
```

Revert a commit
```bash
git revert commit-hash # a8c0c0b8q
```

## Fetch and Diff

Fetch is useful when you want to update your local branch with a remote one.
Diff allows you to compare the changes of your current branch with other branches


Fetch changes from a remote branch
```bash
git fetch origin branch-name
```

Compare your branch with others
```bash
git diff other-branch
```

##  Pull & Push

This allows you to send/get changes to/from a remote repository

Get changes from a remote branch
```bash
git pull origin branch-name
```

Send changes to a remote branch
```bash
git push origin branch-name
# when you made a rebase, generally you need to force a push
# we use --force-with-lease to don't override other's changes
git push origin branch-name --force-with-lease
```
