## Reset Branches
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Reset types
  - change files in staging index and/or working directory to the state they had when a specified commit was made: 'make my project look like it did back then'
  - moves HEAD pointer to a specific commit
  - soft: move HEAD, no change in staging index nor working directory `git reset --soft <tree-ish>`
  - hard: move HEAD, change both staging and working dir to match repo; rollback, `git reset --hard <tree-ish>`
  - mixed: move HEAD, change staging index to match repo

- Soft reset
  - 'return to an old state and leave code changes staged'
  - useful for amending one or more commits
  - similar to `git commit --amend`
  - note previous commits will be discarded, so be careful about amending commits which have been shared with others
  - but without further commits, we can move HEAD to any given commit and all the commits will still be there, but once new commit is made, all the commits after the reset point will be discarded

- Mixed reset 

[back to top](#Reset-Branches)
