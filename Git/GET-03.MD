## Getting Start
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Initialize a repository
  - `git init` created a `.git` directory

- Where git files are stored
  - inside `.git` directory
  - notice the `config` file inside the directory where the project-level configuration is stored
  - every change to the repository is centralized into this `.git` directory (unlike SVN or subversion)

 - First commit
  - create a file in source code editor
  - `git add .` # add all changes in the current directory
  - `git commit -m 'Initial commit'`

- Write commit messages
  - a short single-line summary (< 50 characters)
  - optionally followed by a blank line and a more complete description
  - keep each line to less than 72 characters
  - write commits in in present tense, not past tense
  - bullet points: asterisks or hyphens
  - can add 'tracking numbers' from bugs or support requests
  - can develop shorthand for your organization
    - "[css, js]"
    - "bugfix:"
    - 'ghi2394 - ' # github issue #
  - be clear and descriptive
    - BAD "fix type"
    - GOOD "Add missing hyphen in project section of HTML"
    - BAD "Update login code"
    - GOOD "Change user authentication to use Blowfish

- View the git log
  - `git log` inside git repository
    - unique ID for every git commit
    - author
    - date and time
    - commit messages
  - `git log -n 5` 5 most recent commits
  - `git log --since=2020-01-01`
  - `git log --until=2019-12-31`
  - `git log --author='Kevin'`
  - `git log --grep='bugfix'` # globally search for regular expression  

[Back to top](#Getting Start)
