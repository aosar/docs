# Branch Management & Developer Workflows

These are git-based developer workflows I have used for managing branches. I usually do this regardless of collaboration with others for organization purposes and to reduce commit pollution.

## Volatile Projects (migrations, refactors, etc)

In the past during volatile projects, I have used a personal dev branch such as `osar-dev` or `dev/aosar`. From there I might:
1. Branch further by task, be it specifc number or a descriptor (eg T123, T124; refactor-db, add-config)
2. During proper stopping points (preferably completions), squash-merge back into my user-dev branch (optional PR)
3. Rebase communal-dev branch into my user-dev branch, preferably periodically so that it is up-to-date
4. Create PR to land user-dev onto communal-dev branch

Typically I do a set of related tasks per PR. I've done this to reduce commit noise from WIP branches but still maintain a clear history while continuing with rapid development. The downside is this can require a bit more coordination, especially for those less familiar with rebasing. Misunderstandings about the process can cause conflicts that make safe pushes impossible, and require several changes to "undo" locally. This can cause further confusion and frustration. I believe it is woth working through, as I find it important to maintain a clean and clear commit history.

As to why I began do this... I've partially based this process on a git wrapper I used to use called Differential, which was used by Phabricator (project management system). While annoying to learn, I've found it much better in the long run. But maybe that's just the vim user in me.
 
An example of the above list in action (roughly):
- *working on theoretical tasks `T1234` and `T1235`*
- *am in `develop` branch*
- create branch `dev/aosar`
- create branch `T1234` based on Task 1234 (usually remains local unless complex)
- rebase develop into `dev/aosar` and `T1234` as needed
- squash-merge `T1234` onto `dev/aosar`
- *am in `dev/aosar` or `T1234`, depending on how much I want to preserve history*
- create branch `T1235`
- rebase as needed
- squash-merge `T1235` onto `dev/aosar`
- rebase develop into `dev/aosar`
- submit PR to merge `dev/aosar` into `develop`, which includes the tasks `T1234` and `T1235`