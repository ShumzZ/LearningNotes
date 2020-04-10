## Collaborate with a remote repo
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)


- Push changes to remote repo
  - `git push` since we set `-u` the first time we push, no need to specify which branch to push and which remote branch to push to.
  - `git diff origin/master..master` with origin/master is a local copy of remote repo branch

- Fetch changes from a remote repo
  - `git fetch`
  - note fetch do not change current master and HEAD, it only checks in with the remote server, not merged yet
  - fetch often, in fact every day
    - fetch before work on anything
    - fetch before push
    - fetch before go offline

- Merge in fetched changes
  - `git fetch` then `git merge` (usually while still on master branch)
  - `git pull` to combine the above two commands

- Check out remote branches
  - checkout a new branch out of a remote branch is not allowed, but:
    - `git branch branch_play_with origin/some_other_branch`
    - or `git checkout -b branch_play_with origin/some_other_branch`

- Push to an updated remote branch
  - if rejected, then fetch a latest commit, merge locally and push again.
  - Git won't be able to structure all the changes in the new timeline

- Delete a remote branch
  - remove a branch from the remote repo
    - useful when a feature branch is complete and merged
  - `git push origin :<remote_branch>` # the colon in front of it
    - `git push origin <branch1>:<branch1>`
  - `git push origin --delete <remote_branch>`

- Enable collaborating
  - in Github settings, add collaborator to an individual read/write access
  - Or in open source case, fork a project, make changes and create a pull request, formulate the motivation, process and result in an concise and clear way

- Example workflow
  - A: add a feature, push to remote for B to review
    - `git checkout master`
    - `git fetch`
    - `git merge origin/master`
    - `git checkout -b branch feedback_form`
    - `git add feedback_form.html`
    - `git commit -m 'Add customer feedback form'`
    - `git fetch`
    - `git push -u origin feedback_form`

  - B: review and add additional feature, push to remote for A to review

    - `git checkout master`
    - `git fetch`
    - `git merge origin/master`
    - `git checkout -b feedback_form origin/feedback_form`
    - `git log`
    - `git show <commit>`
    - `git commit -am 'Add addition XX feature'`
    - `git fetch`
    - `git push`

  - A: agree to the addition and push to master
    - `git fetch`
    - `git log -p feedback_form..origin/feedback_form`
    - `git merge origin/feedback_form`
    - `git checkout master`
    - `git fetch`
    - `git merge origin/master`
    - `git merge feedback_form`
    - `git push`

- Next steps:
  - create aliases for commonly-used commands
  - connect over SSH
  - Integrated Development Environments(IDEs)
  - Graphical User Interfaces (GUIs)

[back to top](#Collaborate-with-a-remote-repo)
