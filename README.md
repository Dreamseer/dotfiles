# dotfiles

My homegrown dotfiles repository which in the meantime is VERY much inspired by the work of [Mathias Bynens](http://mths.be/dotfiles) and Github’s [dotfiles page](http://dotfiles.github.com/). If you really want your own dotfiles repository, fork the one by Mathias. It’s awesome!

## Installation

### Using Git and the bootstrap script

You can clone the repository wherever you want. (I like to keep it in `~/Sites/dotfiles`, with `~/dotfiles` as a symlink.) The bootstrapper script will pull in the latest version and copy the files to your home folder.

```bash
git clone https://github.com/dreamseer/dotfiles.git && cd dotfiles && ./bootstrap.sh
```

To update, `cd` into your local `dotfiles` repository and then:

```bash
./bootstrap.sh
```

Alternatively, to update while avoiding the confirmation prompt:

```bash
./bootstrap.sh -f
```

### Git-free install

To install these dotfiles without Git:

```bash
cd; curl -#L https://github.com/dreamseer/dotfiles/tarball/master | tar -xzv --strip-components 1 --exclude={README.md,bootstrap.sh}
```

To update later on, just run that command again.

### Add custom commands without creating a new fork

If `~/.extra` exists, it will be sourced along with the other files. You can use this to add a few custom commands without the need to fork this entire repository, or to add commands you don’t want to commit to a public repository.

My `~/.extra` looks something like this:

```bash
# PATH additions
export PATH="~/bin:$PATH"
export NODE_PATH="/usr/local/lib/node_modules"

# Git/GitHub credentials
# Not in the repository, to prevent people from accidentally committing under my name
GIT_AUTHOR_NAME="Marc Görtz"
GIT_COMMITTER_NAME="$GIT_AUTHOR_NAME"
git config --global user.name "$GIT_AUTHOR_NAME"
GIT_AUTHOR_EMAIL="git@marcgoertz.de"
GIT_COMMITTER_EMAIL="$GIT_AUTHOR_EMAIL"
git config --global user.email "$GIT_AUTHOR_EMAIL"
GITHUB_USER_NAME="Dreamseer"
git config --global github.user "$GITHUB_USER_NAME"
```

### Sensible OS X defaults

When setting up a new Mac, you may want to set some sensible OS X defaults:

```bash
./.osx
```

### Install Homebrew formulae

When setting up a new Mac, you may want to install some common Homebrew formulae (after installing [Homebrew](http://mxcl.github.com/homebrew/), of course):

```bash
./.brew
```

## How does it look

<a href="http://cl.ly/I1Dk"><img src="http://cl.ly/I1Dk/Bash.png" alt="Just like this." title="Colorful bash prompt and stuff."></a>

## Feedback

Suggestions/improvements [welcome](https://github.com/dreamseer/dotfiles/issues)!

## Thanks to…

* [Mathias Bynens](http://mathiasbynens.be/) for sharing his [amazing collection of dotfiles](https://github.com/mathiasbynens/dotfiles)
* [Paul Irish](http://paulirish.com/) and his [dotfiles fork](https://github.com/paulirish/dotfiles)

## License

Copyright (c) 2012 Marc Görtz, http://marcgoertz.de/

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
