## Ignore files
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Use .gitignore files
  - project/.gitignore
    - a list of rules to determine which files to ignore
    - changes made to .gitignore will be ignored by Git
  - rules:
    - file names
    - pattern matching (basic regular expression)
      - `?[aeiou][0-9]`, `logs/*.txt`
    - negative expressions
      - `*.php`, `!index.php`
    - ignore all files in a directory:
      - a trailing slash `assets/videos/`
    - comments
      - `# this is a comment`
    - blank lines are skipped
   - a demo/ example
    - >```
    .DS_Store
    *.zip
    *.gz
    log/*.log
    log/*.log.[0-9]
    assets/photoshop/
    assets/videos/
    !assets/videos/tour_*.mp4

    access.log
    ```
  - also note that `git commit -am` won't add files that are untracked, in that case, `git add` is required
  - side note: do not ignore .gitignore, this defeat the purpose of LISTING the files that should be ignored and LETTING Git know it.
    - rather, see this [SOF discussion](https://stackoverflow.com/a/10177000/6947937) for more subtle usage

-What to ignore
  - depend on project, but typically:
  - compiled source
  - packages and compressed files
  - logs and databases
  - operating system generated files
  - user-uploaded assets(images, PDFs, videos)
  - a good starting point: at https://github.com/github/gitignore

- Globally ignore files
  - motivation:
    - ignore files in all repos
    - settings are not tracked in repo
    - user-specific instead of repo-specific
  - `git config --global core.excludesfile ~/.gitignore_global`

- Ignore tracked files
  - Note .gitignore only ignores UNTRACKED files
  - what if we want to ignore the tracked files? `git rm <file>` is one way, but sometimes we want to remove from staging index but not from working copy:
    - add file to .gitignore and `git rm --ca ched <file>`
  - note what has been committed (if any) is still in the repo, we are just not tracking it any more, previous version will remain in the repo and can be pulled upon request, we just stopped future versions from being tracked.

- Track empty directory
  - `git ls-tree` to list the files in the tree at the HEAD, it shows that Git does not track empty directory
  - add a file called `.gitkeep` (by convention) to the empty directory
    - e.g. in Unix, `touch empty-directory/.gitkeep`





[Back to top](#Ignore files)
