# Essential Git Commands and Concepts

## Git and GitHub
Git is a free, open-source version control system (VCS) that allows developers to track changes in their codebase over time. It's designed to manage source code, collaborate with others, and maintain a record of changes.

GitHub is a web-based platform for version control and collaboration, built on top of Git. It provides a centralized location for developers to host, manage, and share their code

## Creating a Repository
1. Log in to your GitHub account.
2. Click the "+" button in the top-right corner.
3. Select "New repository".
4. Fill in the repository details:
    - Repository name
    - Description (optional)
    - Public or Private visibility
    - Initialize repository with:
        - README file
        - .gitignore file
        - License
5. Click "Create repository"

## Cloning a Repository
To clone a git repository, 
- open GitHub Desktop
- Enter the repository repository-name and select the repository
- Copy the repository url and open Terminal or Command Prompt
- Navigate to the directory where you want to clone the repository
- Run the command - git clone repository-url

## Creating Branches
Here's a step-by-step guide on how to create branches in GitHub:

Using GitHub Web Interface
1. Log in to your GitHub account.
2. Navigate to your repository.
3. Click on the "Branches" tab.
4. Click the "New branch" button.
5. Enter the branch name.
6. Choose a base branch (optional).
7. Click "Create branch".

Using Git Command Line
1. Navigate to your local repository.
2. Run: git branch [branch-name].

To switch to the new branch:  git checkout [branch-name]

## Committing Changes
Here's a step-by-step guide on how to commit changes in Git:

Using Git Command Line
1. Navigate to your local repository.
2. Stage changes: git add [file-name] or git add .

(to stage all changes)
1. Commit changes:
git commit -m "[commit-message]"
(replace [commit-message] with a brief description of changes)

Using GitHub Desktop
1. Open GitHub Desktop.
2. Navigate to your repository.
3. Select changes to commit.
4. Enter a commit message.
5. Click "Commit".

## Reverting Commits
Here's a step-by-step guide on how to revert commits in Git:

Revert Commit Methods

1. Revert: Create a new commit that undoes changes.
2. Reset: Move commit history pointer (HEAD) to a previous commit.
3. Rebase: Interactive history rewriting.

Revert Commit Commands

1. git revert [commit-hash]: Revert a specific commit.
2. git revert HEAD: Revert the most recent commit.
3. git revert [branch-name]~[number]: Revert a commit on a specific branch.

Reset Commit Commands

1. git reset [commit-hash]: Move HEAD to a specific commit.
2. git reset HEAD~[number]: Move HEAD to a previous commit.
3. git reset --hard [commit-hash]: Move HEAD and discard changes.

Rebase Commit Commands

1. git rebase -i [commit-hash]: Interactive rebase.
2. git rebase --abort: Cancel rebase.
3. git rebase --continue: Continue rebase.

Revert vs. Reset vs. Rebase

| Method | Description | Use Case |
| --- | --- | --- |
| Revert | Create a new commit | Public branches, shared code |
| Reset | Move HEAD pointer | Private branches, experimental changes |
| Rebase | Interactive history rewriting | Complex changes, feature branches |

## Pulling and Pushing Changes (Downstream and Upstream)
Here's a step-by-step guide on how to pull and push changes (downstream and upstream) in Git:

Pulling Changes (Downstream)

1. Fetch changes from remote repository:

git fetch [remote-name]

1. Pull changes from remote repository:

git pull [remote-name] [branch-name]

1. Pull changes with rebase:

git pull --rebase [remote-name] [branch-name]

Pushing Changes (Upstream)

1. Add changes to staging area:

git add .

1. Commit changes:

git commit -m "[commit-message]"

1. Push changes to remote repository:

git push [remote-name] [branch-name]

1. Push changes with tags:

git push [remote-name] [branch-name] --tags

1. Push changes with force (overwrite remote):

git push [remote-name] [branch-name] --force

##  Fetching Changes
Here's a step-by-step guide on how to fetch changes in Git:

Fetch Changes Commands
1. Fetch changes from all remotes:

git fetch --all

1. Fetch changes from a specific remote:

git fetch [remote-name]

1. Fetch changes from a specific branch:

git fetch [remote-name] [branch-name]

1. Fetch changes with tags:

git fetch --tags

1. Fetch changes with pruning:

git fetch --prune

Fetch Options

1. --all: Fetch changes from all remotes.
2. --tags: Fetch tags.
3. --prune: Remove obsolete references.
4. --verbose: Show detailed output.
5. --dry-run: Show what would be fetched

## Fetching Changes
Here's a step-by-step guide on how to fetch changes in Git:

Fetch Changes Commands

1. Fetch changes from all remotes: git fetch --all
2. Fetch changes from a specific remote: git fetch [remote-name]
3. Fetch changes from a specific branch: git fetch [remote-name] [branch-name]
4. Fetch changes with tags: git fetch --tags
5. Fetch changes with pruning: git fetch --prune

Fetch Options

1. --all: Fetch changes from all remotes.
2. --tags: Fetch tags.
3. --prune: Remove obsolete references.
4. --verbose: Show detailed output.
5. --dry-run: Show what would be fetched.

Git Fetch Variations

1. git fetch origin: Fetch changes from origin remote.
2. git fetch upstream: Fetch changes from upstream remote.
3. git fetch --depth [number]: Fetch changes with limited depth.

Post-Fetch Steps

1. Review fetched changes: git log -p
2. Merge fetched changes: git merge
3. Rebase fetched changes: git rebase

## Merging Branches
Here's a step-by-step guide on how to merge branches in Git:

Merging Branches Commands

1. Merge branch into current branch: git merge [branch-name]
2. Merge specific commit: git merge [commit-hash]
3. Merge branch with no-fast-forward: git merge --no-ff [branch-name]
4. Merge branch with squash: git merge --squash [branch-name]
5. Merge branch with rebase: git rebase [branch-name]

Merging Options

1. --no-ff: Prevent fast-forward merge.
2. --squash: Squash commits.
3. --rebase: Rebase instead of merge.
4. --abort: Abort merge.
5. --continue: Continue merge.
   Merging Strategies

1. Fast-Forward Merge: git merge [branch-name]
2. No-Fast-Forward Merge: git merge --no-ff [branch-name]
3. Squash Merge: git merge --squash [branch-name]
4. Rebase Merge: git rebase [branch-name]

Resolving Merge Conflicts

1. Identify conflicts: git status
2. Resolve conflicts manually.
3. Use merge tools: git mergetool
4. Abort merge: git merge --abort
5. Continue merge: git merge --continue

## Renaming Branches
Here's a step-by-step guide on how to rename branches in Git:

Rename Local Branch

1. Checkout the branch: git checkout [old-branch-name]
2. Rename the branch: git branch -m [new-branch-name]

Rename Remote Branch

1. Push the updated branch name: git push origin -u [new-branch-name]
2. Delete the old branch name: git push origin --delete [old-branch-name]

Rename Current Branch

1. Rename the current branch: git branch -m [new-branch-name]

Rename Branch with Git Version 2.23+

1. Rename the branch: git branch --move [old-branch-name] [new-branch-name]

Git Rename Branch Options

1. -m: Move/rename a branch.
2. --move: Move/rename a branch (Git version 2.23+).
3. -u: Set upstream tracking.
4. --delete: Delete a remote branch.

## Creating Pull Requests
Here's a step-by-step guide on how to create pull requests in Git:

Using GitHub Web Interface

1. Log in to GitHub.
2. Navigate to your repository.
3. Click "Pull requests" > "New pull request".
4. Select the base branch (e.g., main).
5. Select the compare branch (e.g., feature/new-feature).
6. Add title and description.
7. Click "Create pull request".

Using Git Command Line

1. Navigate to your local repository.
2. Commit changes: git commit -m "[commit-message]"
3. Push changes: git push origin [branch-name]
4. Create pull request using GitHub CLI: gh pr create

Pull Request Options

1. --draft: Create a draft pull request.
2. --reviewers: Assign reviewers.
3. --labels: Add labels.
4. --milestone: Set milestone.

## Reviewing and Merging Pull Requests
Here's a step-by-step guide on how to review and merge pull requests in Git:

Reviewing Pull Requests

1. Go to GitHub repository.
2. Click "Pull requests".
3. Select the pull request.
4. Review changes: git diff [branch-name].
5. Comment on changes.
6. Approve or request changes.

Merging Pull Requests

1. Go to GitHub repository.
2. Click "Pull requests".
3. Select the pull request.
4. Click "Merge pull request".
5. Choose merge method:
   - Merge (default).
   - Squash and merge.
   - Rebase and merge.
6. Confirm merge.


   Git Merge Commands

7. Merge pull request: git merge [branch-name].
8. Squash and merge: git merge --squash [branch-name].
9. Rebase and merge: git rebase [branch-name].
10. Abort merge: git merge --abort.

Merge Options

1. --no-ff: Prevent fast-forward merge.
2. --squash: Squash commits.
3. --rebase: Rebase instead of merge.
4. --no-commit: Don't commit automatically

## Reverting Pull Requests
Here's a step-by-step guide on how to revert pull requests in Git:

Reverting a Merged Pull Request

1. Go to GitHub repository.
2. Click "Pull requests".
3. Select the merged pull request.
4. Click "Revert".
5. Confirm revert.

Reverting a Pull Request using Git Command Line

1. Checkout the branch: git checkout [branch-name].
2. Revert the merge: git revert -m 1 [commit-hash].
3. Push changes: git push origin [branch-name].

Reverting a Pull Request using GitHub CLI

1. Install GitHub CLI: brew install gh.
2. Revert pull request: gh pr revert [pr-number].

Revert Options

1. -m 1: Revert the first parent commit.
2. -m 2: Revert the second parent commit.
3. --no-edit: Skip editing the revert commit message.
4. --no-commit: Don't commit automatically.








