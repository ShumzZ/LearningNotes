## Install
###### Back to [table of content](https://github.com/ShumzZ/LearningNotes/blob/master/Git/GitEssentialTraining-LinkedIn.MD#table-of-contents)

- Git on Mac/ Windows /Linux:
  - Installer http://git-scm.com;
  - Github Desktop https://github.com
  - Homebrew https://brew.sh  `brew install git` in Terminal

- Basic Git configuration
  - Three levels of configuration
    - System:
      - /etc/gitconfig
      - Program Files\Git\etc\gitconfig
    - User:
      - ~/.gitconfig
      - $HOME\.gitconfig
    - Project:
      - my_proj/.git/config  
    - access by: `git config [--system / --global / nothing]`
  - Examples:
    - git config --global user.name 'name'
    - git config --global user.email 'someone@nowhere.com'
    - git config --list
    - git config --global core.editor 'atom --wait'
      - a side note, to authorize Atom with Github, go to  https://github.atom.io/login as opposed to https://github.com
    - git config --gloabal color.ui true
  - to check config: cat .gitconfig

- Auto completion for git
  unix has its own auto-completion and the following is for git specifically
  - make the `.zsh` directory
    > `$ mkdir -p ~/.zsh`

  - download the scripts from https://github.com/git/git
    > `$ curl -o ~/.zsh/git-completion https://raw.githubusercontent.com/git/git/master/contrib/completion/git-completion.zsh`

  - add the following scripts to `~/.zshrc` file
    > `zstyle ':completion:*:*:git:*' script ~/.git-completion.zsh`
    > `fpath=(~/.zsh $fpath)`

- Git help
  - git help [subcommand] for detailed manual, `git help log`
  - OR `man git-log` , with man being a Unix command for help/manual

[Back to top](#Install)
