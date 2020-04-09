## Creating, switching and comparing branches
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Branch overview
  - branches are cheap
    - try new ideas
    - isolate features or sections of work
  - only one working directory exists
  - fast context switching

- Create branches
  - check existing branches `git branch`
  - `git branch new_feature`
  - check the HEAD: `cat .git/HEAD`
  - check the directory: `ls -al .git/refs/heads/`
  - and check the log to understand that right after creating a branch, HEAD points to the the same commit:
    - `cat .git/refs/heads/master`
    - `cat .git/refs/heads/new_feature`
    - `git log --oneline`

- Switch branch
  - `git checkout new_feature`
  - `git log --graph --oneline --all --decorate`

- Create and switch branches together in one line
  - `git checkout -b shorten_title`

- Switch branches with uncommitted changes
  - Git will not allow switch if changes in working directory conflict
  - but can switch if changes in working directory could be applied WITHOUT conflict
  - can switch if files are not being tracked
  - to deal with this situation:
    - commit the changes to the current branch
    - remove the change, checkout the file again
    - stash the changes (elaborate later)

- Compare branches
  - `git diff <branch1>..<branch2>` # also note I do not have to be in either branch1 or branch2
  - typically, 'older' first then the 'newer' branch
  - also we can throw in other flags such as `--color-words` or compare ancestors `master..new_feature^`
  - check what branches have been merged: `git branch --merged` or not full included by `git branch --no-merged`

- Rename branches
  - `git branch -m [<old_branch>] <new_branch>`

- Delete branches
  - `git branch -d`
    - make sure I am not on the branch to be deleted
    - will not delete if commits are not fully merged, `git branch --merged/--no-merged`, if desired, use `-D` flag to force delete un-merged branch

- Configure command prompt
  - add current branch name to command prompt
  - similar to .git-completion.bash
  - https://github.com/git/git in the contrib, follow instructions in git-prompt.sh

  - unfortunately the above does not work for me, and I found a much easier configuration in the git [doc](https://git-scm.com/book/en/v2/Appendix-A%3A-Git-in-Other-Environments-Git-in-Zsh)

  - previously the prompt string `echo $PS1` (or `echo $PROMPT`) gives "%n@%m %1~ %#" and about its meaning: [ref](http://www.nparikh.org/unix/prompt.php), and a more comprehensive guide to [moving to zsh](https://scriptingosx.com/2019/07/moving-to-zsh-06-customizing-the-zsh-prompt/)
  "when you insert a number n between the % and the ~, then only the last n elements of the path will be shown"


[back to top](#Creating,-switching-and-comparing-branches)
