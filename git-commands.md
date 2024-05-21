<!--
title: 'git-commands.md'
author: 'Elias Albuquerque'
created: '2023-11-30'
update: '2024-05-04'
-->


<!-- omit from toc -->
# Git Commands

- [Create a repository from local repository](#create-a-repository-from-local-repository)
- [Create and switch to a new branch](#create-and-switch-to-a-new-branch)
- [Update your local working branch](#update-your-local-working-branch)
- [How to commit:](#how-to-commit)
  - [Best practices to commit](#best-practices-to-commit)
  - [View the last commit](#view-the-last-commit)
  - [Change the subject or add a new file to a previous commit](#change-the-subject-or-add-a-new-file-to-a-previous-commit)
  - [How to uncommit last commit in git](#how-to-uncommit-last-commit-in-git)
- [Check differences between two repository branches](#check-differences-between-two-repository-branches)




<!-- 01 -->
## Create a repository from local repository

To create a GitHub repository from a local repository, you can follow these 
steps:

1. Initialize a local Git repository (if not already done):
   
   ```terminal
   git init
   ```

2. Change to *main branch*:
   
   ```terminal
   git checkout -b main
   ```

3. Add and commit your files (if not already done):
   
   ```terminal
   git add .
   ```
   ```terminal
   git commit -m "Initial commit"
   ```

5. Create a new repository on GitHub: 
   
   - You can do this via the GitHub website. Do not initialize the repository 
     with a README, .gitignore, or License. This new repository should be 
     completely empty.
   - If you still need to add a README or license, follow *steps 5, 7 and 6* of 
     this tutorial

6. Link the local repository to the GitHub repository:
   
   ```terminal
   git remote add origin https://github.com/username/repository.git
   ```
   
   Replace `<https://github.com/username/repository.git>` with the URL of your 
   newly created GitHub repository.

7. Push the local repository to GitHub:
   
   ```terminal
   git push -u origin main
   ```
   
   This will push your local master branch to the origin remote (your GitHub 
   repository).

8. If there is an error when merging repositories (“refusing to merge unrelated 
   histories”), use the command:
   
   ```terminal
   git pull origin main --allow-unrelated-histories
   ```

Now your local repository is connected to your GitHub repository. Any changes 
you make locally can be pushed to GitHub using git push.


<!-- 02 -->
## Create and switch to a new branch

1. You can create a new branch and switch to it using git checkout -b 
   `<new-branch>`, where `<new-branch>` should be the name of the branch.
   
   ```terminal
   git checkout -b <new-branch>
   ```

2. Push the new branch to the GitHub repository:
   
   ```terminal
   git push -u origin <new-branch>
   ```

These commands create and pushes the new branch to the origin remote (your 
GitHub repository). The `-u` option sets the upstream for the branch, which 
means that in the future, you can just use `git push` and `git pull` without 
specifying the branch.


<!-- 03 -->
## Update your local working branch

You should use `git pull` regularly on the branches you are working on locally. 
Without `git pull`, your local branch wouldn’t have any of the updates that are 
present on the remote.

Here’s how you can use `git pull`:

```terminal
git pull
```

This command updates your local working branch with commits from the remote.

There are also options you can use with `git pull`:

- `git pull --rebase`: This updates your local working branch with commits from 
the remote, but rewrites history so any local commits occur after all new 
commits coming from the remote, avoiding a merge commit.

- `git pull --force`: This option allows you to force a fetch of a specific 
remote tracking branch when using the `<refspec>` option that would otherwise 
not be fetched due to conflicts.


<!-- 04 -->
## How to commit:

To commit changes in Git, you can follow these steps:

1. Stage your changes: Before you can commit your changes, you need to stage 
   them. Staging is a way to select which changes you want to commit. You can 
   stage files using the `git add` command:

   ```terminal
   git add <file>
   ```
   
   Replace `<file>` with the path to the file you want to stage. If you want to 
   stage all changes, you can use `.` or `-A` instead of `<file>`.

2. Commit your changes: After staging your changes, you can commit them using 
   the `git commit` command:

   ```terminal
   git commit -m "<subject>" -m "<description>"
   ```
   
   The first `-m` option is the *subject* (short description), and the next is 
   the extended *description* (body).

   Replace `<subject>` with a short description of the changes you’ve made and 
   `<description>` for a brief description of what is being resolved in this 
   release. This message will be associated with the commit and can help you 
   and others understand what changes were made.

3. Push your changes: If you’re working with a remote repository, you can push 
   your changes to it using the `git push` command:

   ```terminal
   git push
   ```
   
This will push your commits to the remote repository.

<!-- ## How to commit: -->
<!-- 4.1 -->
### Best practices to commit

1. **Fix**: This type of commit message is used when you make a bug fix.

   ```terminal
   fix(server): fix server connection issue
   ```
   
   In this example, a server connection issue was fixed.

2. **Feat**: This type of commit message is used when you introduce a new 
   feature.

   ```terminal
   feat(login): add login feature
   ```
   
   In this example, a login feature was added.

3. **Breaking Change**: This type of commit message is used when you make a 
   change that breaks the API or requires other developers to make changes in 
   their code.

   ```terminal
   feat(database): change database library
   
   BREAKING CHANGE: The database connector for MySQL has been removed. It 
   has been replaced by a connector for PostgreSQL.
   ```
   
   In this example, the database library was changed, which is a breaking 
   change.

4. **Types**: Here are some examples of other types of commit messages:

   ```terminal
   docs(readme): update readme
   style(server): fix indentation
   refactor(database): refactor database connection
   test(login): add tests for login
   ```
   
   In these examples, the readme was updated, the indentation in the server 
   code was fixed, the database connection was refactored, and tests for login 
   were added.

5. **Footers**: This is an example of a commit message with a footer:

   ```terminal
   feat(login): add login feature
   
   The login feature uses OAuth 2.0 for authentication.
   
   Issue #123
   ```
   
   In this example, the footer Issue #123 links the commit to an issue in the 
   issue tracker.

<!-- ## How to commit: -->
<!-- 4.2 -->
### View the last commit

To see the last commit, you can use the `git log` command. Here are some steps:

1. **View the Commit History**: Use the `git log` command to list the commits 
   made in the repository in reverse chronological order. Each commit will be 
   listed with its SHA-1 checksum, the author’s name and email, the date 
   written, and the commit message.

   ```terminal
   git log
   ```

2. **View the Last Commit**: If you want to see the last commit, you can use 
   the `-1` option with `git log`.

   ```terminal
   git log -1
   ```
   
   This will show the author, the date and time that the commit was made, 
   the full hash id, and the commit message.

3. **View the Files of the Last Commit**: If you want to see just the names of 
   the files that were changed in the last commit, you can use the 
   `--name-status` option:

   ```terminal
   git log --name-status -1
   ```

4. **See a summary in last commit**: And if you want to see a summary of the 
   changes made in the last commit, you can use the `--stat` option:

   ```terminal
   git log --stat -1
   ```

<!-- ## How to commit: -->
<!-- 4.3 -->
### Change the subject or add a new file to a previous commit

To add a new file to the most recent commit in Git, you can follow these steps:

1. Stage the new file for commit using the `git add` command:

   ```terminal
   git add <file-name>
   ```

2. Amend the previous commit with the new file using the `git commit --amend` 
   command:

   ```terminal
   git commit --amend -m "New commit message"
   ```
   
   This will open a text editor where you can modify the commit message. If 
   you don’t want to change the commit message, you can use the `--no-edit` 
   option:

   ```terminal
   git commit --amend --no-edit
   ```

<!-- ## How to commit: -->
<!-- 4.4 -->
### How to uncommit last commit in git

To uncommit the last commit in Git, you can use the `git reset` command. Here 
are some options:

1. Keep the Changes: If you want to uncommit your last commit but keep the 
   changes in your working directory, you can use the `--soft` option.

   ```terminal
   git reset --soft HEAD~1
   ```
   
   This command will undo your last commit, but it will keep your changes and 
   your staging intact.

2. Discard the Changes: If you want to uncommit your last commit and discard 
   the changes, you can use the `--hard` option.

   ```terminal
   git reset --hard HEAD~1
   ```
   
   This command will undo your last commit and discard the changes.



<!-- 05 -->
## Check differences between two repository branches 

You can check if there are changes to push to a remote repository in Git using 
the following commands:

1. `git status`: This command shows the status of your working directory and 
   staging area. If there are changes that have been committed locally but not 
   yet pushed to the remote repository, `git status` will indicate this.

   ```terminal
   git status
   ```

2. You can compare two branches in Git using the `git diff` command. Here’s how 
   you can do it:

   ```terminal
   git diff <branch1>..<branch2>
   ```
   
   Replace `<branch1>` and `<branch2>` with the names of the branches you want 
   to compare. This command will show the differences between the latest 
   commits of the two branches.

3. If you want to see a list of commits that are in one branch but not the 
   other, you can use the `git log` command:

   ```terminal
   git log <branch1>..<branch2>
   ```
   
   This command will show the commits that are in `<branch2>` but not in 
   `<branch1>`.
