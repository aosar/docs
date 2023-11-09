# Workflow Guide for Scrum Team B
For Scrum Team B at UIUC Software Development Group (SDG), Technology Services Dept, as of Fall 2023.
## Step 1: Create New Branch
Before starting a task, create a branch based on the agreed-upon primary development branch (eg `develop`, `link-aggregator-dev`).

### Potential Branch Naming Conventions
  - Unspecified general branches
    - `dev/<username>`
    - `feature/<category_name>`
    - `bugfix/<category_name>`
  - Based on Issue where `<N>` is the ticket number:
    - `feature/T<N>`
    - `issue/#<N>`
    - `dev/#<N>`

Push to remote
    - `git push -u origin <branch_name>`

## Step 2: Make Changes
### Tips
- **Commits**
  - Commit often and with short, clear, simple messages. Utilize present-tense verbs for conciseness, consistency, and clarity.
  - Commit messages should be atomic. If you find yourself writing a long commit message, consider splitting it into multiple commits. You may analyze your changes easily in the VSCode Source Control tab. [insert image]

- **Rebasing**
  - Rebase periodically to keep your branch up to date with the primary  branch. This is particularly important before merging (so, before PR creation).
  - If another team member made changes to the primary branch, you may need to rebase *into* your branch to keep it up to date and ensure their changes work on your system and do not conflict with yours. Communicate with teammates if you have questions on how to resolve certain rebase conflicts.
  - If you need to perform a force push, communicate with relevant team members. Be clear on why you are doing this.
  - Generally, you should only force push on branches that are anticipated to be squash merged onto a primary branch (done automatically by the merge button on a PR). This is most frequent with a rebase on a published branch that has a remote. [image]


## Step 3: Test code, rebase, clean, and review all changes before creating a PR
- You can preview a PR and all code changes before creating it through the Github Website. [image]. This is a good way to check for any issues or atomization needed before creating one.
- Perform any cleanup such as removing commented-out code, unused imports, unused variables, etc.
  - Keep in mind you can retrieve the commented code back from your git history. Even if you delete the branch, it will be preserved in git reflog for some time.
- It might be helpful to make a comment such as "Tested and ready to merge" so reviewers know you're ready and dont have any last minute changes.


## Step 4: Create a PR
- Create a PR on the Github website.
- Ensure you are comparing the correct branches.
[images]
- Modify the PR title and description to summarize your changes. Try to encompass as much as you can so that it can be easily understood when browsing commits.
- Add reviewers.
- If you forgot to test before creating, **please comment on the PR** and let the reviewers know so they don't preemptively merge it.

## Step 5 [REVIEWER]: Review PR
- Check the PR description and title for clarity and atomicity. You may suggest to split into multiple PRs.
- Review the PR and make comments as needed, requesting edits.
  - There is an inline comment feature helpful for pointing out specific lines of code.
  - There is also a code edit suggestion feature which is helpful for easily demonstrating the kind of changes you'd like to see.

- Submit general comments
- If feasible, try to check out the branch and run the code to test it. Make note of whether you've tested it.

## Step 6 [AUTHOR]: Make changes based on PR review
Pushing new commits to the branch will update the PR automatically.



