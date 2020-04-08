## Undo changes
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Undo working directory changes:
  - `git checkout -- <file>` # stay in the current branch, but restore the files from repository

- Undo staging index changes, i.e. un-stage files
  - `git reset HEAD <file>`

- Amend commits
  - changing the historical commits threats the data integrity and thus a more advanced topic, but changing the most recent commit/ where HEAD points to is allowed:
  - `git commit --amend -m`

- Retrieve old versions
  - use `git log` to locate the desired commit SHA
  - `git checkout <SHA> -- <file>` # now the older version is in staging already

- Revert a commit (Undo a commit)
  - Note this is not to say to edit the original commit, only making a new commit that reverse whatever changes that original commit made
  - simply `git revert`

- Remove untracked files (all at once)
  - `git clean -n` `-n` dry run, `-f` force run

[Back to top](#Undo changes)
