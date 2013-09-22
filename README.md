# Chris's dotfiles

Shamelessly jacked from @paulirish

## install the necessary apps

My basic setup is captured in `install-deps.sh` which adds homebrew, z, nave, etc.

## private config

Toss it into a file called `.extra` which you do not commit to this repo and just keep in your `~/`

This is where i keep my git username config

```shell
# Git credentials
# Not in the repository, to prevent people from accidentally committing under my name
GIT_AUTHOR_NAME="Chris Lyons"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="chrislyons88@gmail.com"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
git config --global user.email "$GIT_AUTHOR_EMAIL"
```

## Syntax highlighting

…is really important. even for these files.

Install [Dotfiles Syntax Highlighting](https://github.com/mattbanks/dotfiles-syntax-highlighting-st2) via [Sublime Text 2 Package Control](http://wbond.net/sublime_packages/package_control)


### Sensible OS X defaults

When setting up a new Mac, you may want to set some sensible OS X defaults:

```bash
./.osx
```

## Similar projects

I recommend getting a [`.jshintrc`](https://github.com/jshint/node-jshint/blob/master/.jshintrc) and [`.editorconfig`](http://editorconfig.org/) defined for all your projects.


## overview of files

####  Automatic config
* `.ackrc` - for ack (better than grep)
* `.vimrc`, `.vim` - vim config, obv.

#### shell environment
* `.aliases`
* `.bash_profile`
* `.bash_prompt`
* `.bashrc`
* `.exports`
* `.functions`
* `.extra` - not included, explained above

#### manual run
* `install-deps.sh` - random apps i need installed
* `.osx` - run on a fresh osx machine
* `.brew` - homebrew initialization
* `sync.sh` - syncs dotfiles to ~

#### git, brah
* `.git`
* `.gitattributes`
* `.gitconfig`
* `.gitignore`

* `.inputrc` - config for bash readline


## Installation

```bash
git clone https://github.com/chrislyons88/dotfiles.git && cd dotfiles && ./sync.sh
./.osx
sudo source install-deps.sh
./.brew
sudo touch .extra && v .extra
# add in git creds in .extra
# config path?
```

To update later on, just run the sync again.

I personally have aliases set up for updating my dotfiles
```bash
# opens all dotfiles directory in Sublime
ea

# commits and pushes to github, then runs sync.sh
ua
```
