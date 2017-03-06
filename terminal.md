## Terminal

* http://samkapila.com/command-line-starter-kit/

## Project Basics

* Create Directory - `mkdir`
* Initialize Repo - `git init`
* Add Files - `git add <fileName>`
* Add All Files (in current directory) - `git add .`
* Commit - `git commit`
* Commit with inline message - `git commit -m "<message here>"`
* Change to new branch - `git checkout -b <branch name>`
* Change to existing branch - `git checkout <branch name>`

## Hub Commands

https://hub.github.com/

> **NOTE** We did not alias `hub` to `git` so wherever these docs say `git` use the `hub` command...

Hub is just a shortcut for URLs when using github.
When you run `git push` hub isn't doing anything extra!

## Git Vocab

- Cloning - Make a new director based on a remote repository's git history
- Staging - Marking a set of changes to be committed
- Commit - Packaging labeling and getting a unique identifier for a set of changes
- Remote - A repository on another device
- Stash - Putting aside changes in the current project that can be brought back later using `git stash pop`
  - Stash will only stash the changes in files tracked by git already (does not include new files unless you run `git add <filename>`)
- Fetching - Look for updates from a given remote (doesn't apply changes to local project)
- Merge - Apply changes on top of current project
- Rebase - Apply the current branch on top of an existing branch
- Pull - Will fetch and merge changes from a remote branch

## Github Vocab

- Fork - Create a copy of a Github repository based on another with a link back to the original
- Pull Request - A request to merge changes from one branch into another
