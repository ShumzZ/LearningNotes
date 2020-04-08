## Git architecture
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Three-tree architecture
  - three trees:
    - repository: what's actually being tracked by Git; the changes that Git has and that it's going to hold onto and keep track of
    - staging index: changes that are about to be committed to repository
    - working copy/ directory: contains changes that may not be tracked by Git yet
  - architecture
    - pository
            ^
            |
        git commit file.txt
            |
    - staging index
            ^
            |
        git add file.txt
            |
    - working directory/copy

- Git workflows
  see graph above

- Hash Values(SHA-1)
  - Git use this to label and refer to the commits
  - how it works:
    - Git generates a checksum for each change set -- hash Values
    - Checksum algorithm convert data into a simple number
    - Same data always equals same Checksum
    - Data integrity is fundamental
    - Change data would change the checksum
  - Git uses SHA-1 hash algorithm to create Checksum
    - 40 character hexadecimal string (0-9, a-f)
  - when generating checksum, both data (code) and metadata (author, commit message etc.) are considered --> a chain of data integrity is preserved

- The HEAD pointer
  - what is HEAD
    - pointer to tip of current branch in *repository*
    - last state of repo, what was checked out
    - points to parent of next commit where writing commits takes place


[Back to top](#Git-architecture)
