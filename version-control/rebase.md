# Rebase instead of Merging

A manifesto:

I prefer to rebase and/or cherry-pick commits in lieu of merging whenever possible. This reduces excess and redundant commit messages and keeps the commit history clean. This makes it easier to track changes and revert if necessary. It also makes future cherry-picking easier if you want to test an isolated set of changes.

Of course, there are downsides. Many are not familiar with this process, and teams tend to use workflows that rely on squashing commits to reduce commit noise that occurs during development. This can cause problems when trying to rebase back the other way.** However, when well-coordinated, I think the benefits can shine through. Unfortunately, it can be difficult to get started since it is more manual than the default merge workflow, and uses commands developers are less familiar with.

I will not talk about what rebase, merge, or cherry-picking is here. Google is your friend.

*\*\** (There **is** a use for "reverse rebasing". Let's say you are working in a branch, landed changes, and made more changes. The main branch recieves more commits from other development branches, and you would like to incorporate them into your working branch)

## The Process

If you have made a commit and have not pushed or synced changes, you can do the following:

### SETUP: Disable fast-forwarding on pull
```
git config --global pull.ff only
```
### SETUP: Set default to rebase on pull (if desired)
```
git config --global pull.rebase true
```

### METHOD 1: Rebase command
From the working branch you are trying to land, run this:
```
git rebase origin/<branch-name>
```

Manually merge changes if there are conflicts.

It goes through commits in the order which they were submitted. With multi-commit rebases, you may have to resolve conflicts multiple times, depending how bad your changes diverged. However, I find this beneficial for having an in-depth understanding of what changes have been made, and tweaking anything that looks off or could be corrected. This mitigates bugs and, if merging someone else's code, gives you a better understanding of what they did.

### METHOD 2: Hard Reset and Cherry pick
```
git log
```
Copy your commit ID(s) and the original base commit ID
```
git pull
git reset --hard <previous-commit-ID>
git cherry-pick <commit-id>
```
If you have multiple commits, cherry pick in the order in which they were committed, and continue cherry picking until finished.

