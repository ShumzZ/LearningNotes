## Intro
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Purpose: version control of a text document.
  - also called: Version Control System (VCS) / Source Code Management (SCM)
  - Similar VCS/ SCM:
    - File naming - surffix;
    - MS Word - track changes;
    - Adobe PS - history;
    - Wiki;
    - Undo - Ctrl/ CMD + Z

- History, VCS's that predated Git
  - History: Source Code Control System (SCCS), store original and changes;
  - Revision Control System (RCS), store latest and changes;
  - Concurrent Version System (CVS) multiple files, multi-user;
  - Apache Subversion (SVN) track texts and images, track file changes collectively/ treat the directory as a whole;
  - BItKeeper SCM (proprietary) Distributed version control;
  - Git: 2005 Apr, also created by Linus (created Linux), multi-platform Linux/ MacOS/ Windows, faster, safer

- Distributed, what and why:
  - Changes are stored as change sets
    - track changes, not versions;
    - different from CVS and CVM, which track versions;
    - change sets can be exchanged between repositories;
    - merge in change sets / apply patches
  - No single master/ central repository + Many working copies + Each with their own combination of change sets.
  - Advantages:
    - no need to communicate with a central server
      - faster
      - no network access required
      - no single failure point;
    - encourages participation and forking of projects
      - developers can work independently;
      - submit change sets for inclusion or rejection

[Back to top](#Intro)
