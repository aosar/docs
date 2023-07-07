# How to Cherry Pick

I often use this when I have changes in a work-in-progress branch that I want to apply to another branch, but I don't want to merge the entire branch. If I want all the changes I will rebase.

That way I can keep working in the messy WIP branch but also utilize the changes I've made without copy/pasting huge sets of files, and keep the organization of commits and messages.

What it is:
- Copy commit from one branch to another

I find this helpful when:
- Im developing 2 branches in tandem
- Im collaborating with someone and want to cherry pick my/their changes into a common branch
- Im trying to isolate a bug and/or troubleshooot

How:
- `git cherry-pick <commit-id>`

Sample process:
```
$ git log --oneline
1e2b3c4d (HEAD -> main) Commit message
5f6g7h8i (origin/main, origin/HEAD) Commit message
9j0k1l2m Commit message

$ git checkout -b new-branch
Switched to a new branch 'new-branch'

$ git cherry-pick 9j0k1l2m
[main 9j0k1l2m] Commit message
 Date: Wed Jan 1 00:00:00 2020 -0000
 1 file changed, 1 insertion(+)
```

Variations:
- `git cherry-pick <commit-id>..<commit-id>`
  - Apply all commits between the specified commits
- `git cherry-pick <commit-id>^..<commit-id>`
  - Apply all commits between the specified commits, excluding the first commit
- `git cherry-pick <commit-id>^!`
  - Apply all commits after the specified commit