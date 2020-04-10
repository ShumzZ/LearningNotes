## Merge branch
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Merge
  - checkout to the branch where other branch will merge onto, then `git merge <branch>`

- Fast-forward VS true merge
  - Git handles it internally without bothering the user, but it helps to understand the difference

- Merge conflicts
 - when two branches conflict, Git will prompt and let us choose which version to use (resolve the conflict) and then add the conflict files back to stage and commit
 - right after the conflict prompts, working directory is changed(`git status` to check), then we have two options:
  - abort the merge and deal with it a a later time: `git merge --abort`
  - resolve the conflict manually, either `git diff --color-words <branch1>..<branch2>` or `git show --color-words` to highlight the differences/ conflicts and then resolve the conflict manually
    - then simply `git commit`
    - to rollback, `git reset --hard HEAD^` the parent of the current branch
  - Also, a `git mergetool` could be called and used, see manual for details

- Strategies to reduce conflict
  - keep short lines
  - keep small and focused commits
  - beware stray edits to whitespace(spaces, tabs, line returns), essentially stick to one style, to eliminate the trivial difference
  - merge often, and merge tested features regularly and use feature flags (advanced topic)
  - track changes in master often, merge master changes back to feature branches, called 'tracking'


[back to top](#Merge-branch)
