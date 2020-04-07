## Git with a real project
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- The Explore California website
  - download files from [LinkedIn.com/learning](https://www.linkedin.com/learning/git-essential-training-the-basics/the-explore-california-website) or use the copy from the root directory of current directory, named: "Ex_Files_Git_EssT"

- View file edits
  - e.g. 'contact.html', say we need to change a phone number from 4314 to 4314, replace in all files in project
  - a side note, what we see with command like `git diff` is the output of a paginator ( more often called a pager)
    - other options in pager: type `-S` to toggle line wrap mode
    - `q` exit
    - `git diff --color-words`
    - to pipe the result to `less` (another pager) for easier scrolling, pipe the operation: `git diff --color=always | less -R` or `git diff --color-words | less -R`
    - [ref1](https://askubuntu.com/questions/19718/how-to-activate-pagination-for-ls-command) and [ref2](https://askubuntu.com/questions/19718/how-to-activate-pagination-for-ls-command)

- Stage and Commit shortcut
  - `git commit --all` or `git commit -a`: stages and commits all changes to tracked files, and do not include untracked files

- View a previous commit
  - e.g. change "you'll" to "you will" in the index.html
  - `git commit -am 'changes you"ll to you will'`
  - `git log` to take note of the SHA-1 value of a particular commit
  - `git show [SHA-1 value of a commit] --color-words | less -R`

- Compare commits
  - `git diff [SHA-1 for commit_1]..[SHA-1 for commit_2]`
  - `git diff HEAD..[SHA-1 for another commit]`

- Multiline commit messages
  - `git commit [-a]` without the `-m` flag
  - also `git log --oneline` condensed version of git log

- Make atomic commits (best practice)
  - small commits
  - only affect a single aspect
  - easier to understand, to work with and to find bugs
  - improve collaboration
  - HOWTO: use the staging index as a 'buffer', add and commit the changes logically belong to a certain aspect
    - side note, rename commit will wrap minor changes in the content without showing them in `git status`

- Client edits
  - Big Sur Retreat $620 -> $750
  - Cali Calm $250 -> $270
  - change tile of explore pages 'come make a few friends' -> 'make new friends'



[Back to top](#Git with a real project)
