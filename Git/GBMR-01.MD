## Navigate the Commit Tree
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Reference commits
  - tree-ish: a directory, a commit or a reference
    - e.g. SHA-1 hash; HEAD pointer reference; Branch reference; Tag reference; Ancestry of those mentioned
  - SHA-1, a complete 40-character string
    - minimum: 4 chars; to be unambiguous: 8-10 chars
    - `git show de14521f`
  - HEAD pointer, tip of current branch, usually found in:
    - .git/HEAD
    - .git/refs/heads/master # default branch on the new project
    - `git show HEAD`

- Ancestry
  - to locate direct parents, append `^` or `~` to any commit identifier : `de14621f^` or `HEAD~`, `master^`
  - to grandparent: add more `^` or `~` `HEAD~2`, `master^^`
  - by convention if tracing back more than 2 times, `~` is preferred

- Tree listings
  - `git ls-tree <tree-ish> <file>`
    - `git ls-tree HEAD` show the tree listings at the time of HEAD
    - tree is directory, blob(binary large object) is file
    - `git ls-tree HEAD assets/`

- Filter the commit log
  - filter the number of commits shown `git log -3`
  - filter the time `git log --since=2019-04-13`, `git log --before/until`, `git log --after=2.weeks --before=3.days`
  - filter the author `git log --author="Name"`
  - filter by regular expression `git log --grep="Initial"`
  - filter by refs `git log <SHA>..<SHA>`
  - filter a particular file `git log <directory/file>` # only changes related with this directory/file

- Format the commit log
  - `git log -p` # change patch
  - `git log --stat` # statistics about the commits
  - `git log --format=medium(default)/short/oneline/full/fuller/email/raw`
  - `git log --oneline` # even shorter
  - `git log --graph --all --online --decorate` # check this out later after you have multiple branches


[back to top](#Navigate-the-Commit-Tree)
