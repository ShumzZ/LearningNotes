## Make changes to files
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Add files
  `git add .` # add everything in the current directory
  `git add file1.txt file2.txt`

- Edit files
  - change files (content, not the name, changing name would 'delete' the file and 'add' a new file) in the editor
  - check  `git status` and Git recognizes it
  - `git add`

- View changes with diff
  - `git diff`, where '-' marks deleted lines and '+' marks the add lines
  - Note only differences between working directory and staging index are shown, once `git add`, no diff will show

-  View only staged changes
  - `git diff --staged` or `git diff --cached`

- Delete files
  - before adding to staging index, deleting the files won't make a difference.
  - after `git add`, manually remove the file out of the project directory, then `git status` will show the change; to sync with the staging index, `git rm file_to_rm.txt` then  `git commit`
  - Alternatively, directly type `git rm file_to_rm.txt` will first remove the file (Unix rm, permanently) and then set staging index same with working copy.

- Move and rename files


[Back to top](#Make changes to files)
