## Local and remote repos
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Local and remote repos
  - local git repo do not require a network connection
  - remote repos ( "remotes") are hosted by servers over a network an allows easy collaboration, push local repo changes to remote or fetch changes to local repo
  - Git is designed to be distributed version control, so all repos are the same, it is just a convention that we designate a central clearing house/ primary repo for collaboration
  - a local `origin/master` keeps syncing with the remote repo, and this can be treated like anther branch

- Set up a Github account
  - check remote `git remote`
  - add remote `git remote add origin <git-url>`
  - add `-v` verbose flag to check remote details
  - `cat .git/config`
  - to remove `git remote rm origin`

- Create a remote branch
  - `git push -u origin master`
  - `git branch -r` `git branch -a`
  - stored at `ls -la .git/refs/remotes`

- Clone a remote repo
  - find the reference in github.com and copy the reference
  - create a directory and clone the repo using terminal

- Track remote branches
  - when adding remote repo or cloning remote repo, the `-u` flag told Git to track the remote branch, so that every time we push or pull, we don't need to specify push to or pull from which branch.
  - to un-track, use `git branch --unset-upstream <branch>`


[back to top](#Local-and-remote-repos)
