## Stash changes
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Save changes in stash
  - `git stash save 'blablabla'` before checkout another branch without making commits
  - by default it does not track untracked files: `-u`

- View stashed changes
  - `git stash list`
  - `git stash show stash@{<index number in the stash list>}` or specify `-p` to see the changes per se as opposed to the stats
  - stashed changes are independent of branches and can be applied to any branches as desired

- Retrieve stashed changes
  - `git stash pop stash@{<stash index>}` will remove the stashed changes out of stash list and apply to working directory
  - `git stash apply stash@{<stash index>}` will apply to working directory WITHOUT remove from stash list
  - can have conflict, but can be resolved like a merge

- Clear the stash
  - `git stash drop stash@{0}` permanently clean the change
  - `git stash clear` clear all items 


[back to top](#Stash-changes)
