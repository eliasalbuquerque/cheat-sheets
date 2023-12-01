<!-- omit from toc -->
# Git Commands

- [Create a repository from local repository](#create-a-repository-from-local-repository)
- [Create and switch to a new branch](#create-and-switch-to-a-new-branch)
- [How to commit changes](#how-to-commit-changes)
- [Conventional commits](#conventional-commits)
- [Update your local working branch](#update-your-local-working-branch)
- [Check changes in the repository for different branches](#check-changes-in-the-repository-for-different-branches)


## Create a repository from local repository

To create a GitHub repository from a local repository, you can follow these 
steps:

1. Initialize a local Git repository (if not already done):

        git init

2. Add and commit your files (if not already done):

        git add .
        git commit -m "Initial commit"

3. Create a new repository on GitHub: You can do this via the GitHub website. 
Do not initialize the repository with a README, .gitignore, or License. This 
new repository should be completely empty.

4. Link the local repository to the GitHub repository:

        git remote add origin https://github.com/username/repository.git

    Replace `<https://github.com/username/repository.git>` with the URL of your 
    newly created GitHub repository.

5. Push the local repository to GitHub:

        git push -u origin master

    This will push your local master branch to the origin remote (your GitHub 
    repository).

Now your local repository is connected to your GitHub repository. Any changes 
you make locally can be pushed to GitHub using git push.


## Create and switch to a new branch

1. You can create a new branch and switch to it using git checkout -b 
`<new-branch>`, where `<new-branch>` should be the name of the branch.

        git checkout -b <new-branch>

2. Push the new branch to the GitHub repository:

        git push -u origin <new-branch>

These commands create and pushes the new branch to the origin remote (your 
GitHub repository). The `-u` option sets the upstream for the branch, which 
means that in the future, you can just use `git push` and `git pull` without 
specifying the branch.


## How to commit changes

To commit changes in Git, you can follow these steps:

1. Stage your changes: Before you can commit your changes, you need to stage 
them. Staging is a way to select which changes you want to commit. You can 
stage files using the `git add` command:

        git add <file>

    Replace `<file>` with the path to the file you want to stage. If you want to 
    stage all changes, you can use `.` or `-A` instead of `<file>`.

2. Commit your changes: After staging your changes, you can commit them using 
the `git commit` command:

        git commit -m "<message>"

    Replace `<message>` with a short description of the changes you’ve made. 
    This message will be associated with the commit and can help you and others 
    understand what changes were made.

3. Push your changes: If you’re working with a remote repository, you can push 
your changes to it using the `git push` command:

        git push

This will push your commits to the remote repository.


## Conventional commits

The conventional commits¹ contains the following structural elements, to 
communicate intent to the consumers of your library:

1. **fix:** a commit of the type fix patches a bug in your codebase (this 
2. correlates with PATCH in Semantic Versioning).

3. **feat:** a commit of the type feat introduces a new feature to the codebase 
4. (this correlates with MINOR in Semantic Versioning).

5. **BREAKING CHANGE:** a commit that has a footer `BREAKING CHANGE:`, or 
appends a `!` after the type/scope, introduces a breaking API change 
(correlating with MAJOR in Semantic Versioning). A BREAKING CHANGE can be part 
of commits of any type.

6. **types** other than *fix:* and *feat:* are allowed, for example 
*@commitlint/config-conventional* (based on the Angular convention) recommends 
`build:`, `chore:`, `ci:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, 
and others.

7. **footers** other than `BREAKING CHANGE: <description>` may be provided and 
follow a convention similar to git trailer format.

Additional types are not mandated by the Conventional Commits specification, and 
have no implicit effect in Semantic Versioning (unless they include a BREAKING 
CHANGE). A scope may be provided to a commit’s type, to provide additional 
contextual information and is contained within parenthesis, e.g., `feat(parser): 
add ability to parse arrays`.

¹ref.: https://www.conventionalcommits.org/en/v1.0.0/#summary


## Update your local working branch

You should use `git pull` regularly on the branches you are working on locally. 
Without `git pull`, your local branch wouldn’t have any of the updates that are 
present on the remote.

Here’s how you can use `git pull`:

    git pull

This command updates your local working branch with commits from the remote.

There are also options you can use with `git pull`:

- `git pull --rebase`: This updates your local working branch with commits from 
the remote, but rewrites history so any local commits occur after all new 
commits coming from the remote, avoiding a merge commit.

- `git pull --force`: This option allows you to force a fetch of a specific 
remote tracking branch when using the `<refspec>` option that would otherwise 
not be fetched due to conflicts.


## Check changes in the repository for different branches 

You can check if there are changes to push to a remote repository in Git using 
the following commands:

1. `git status`: This command shows the status of your working directory and 
staging area. If there are changes that have been committed locally but not yet 
pushed to the remote repository, `git status` will indicate this.

        git status

2. You can compare two branches in Git using the `git diff` command. Here’s how 
you can do it:

        git diff <branch1>..<branch2>

    Replace `<branch1>` and `<branch2>` with the names of the branches you want 
    to compare. This command will show the differences between the latest 
    commits of the two branches.

3. If you want to see a list of commits that are in one branch but not the 
other, you can use the `git log` command:

        git log <branch1>..<branch2>

    This command will show the commits that are in `<branch2>` but not in 
    `<branch1>`.

