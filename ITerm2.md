# Configuration of ITerm2.

* Open ITerm2 -> Preferences -> Profiles -> Colors -> Color Presets.. -> Import or choose existing one.

  I use this:

  https://github.com/dracula/dracula-theme/

* Put checkbox "Cursor guide"

* Be sure, that field "Minimum Contrast" is not on the max level.

* Open you bash_profle, using this command
```
vim ~/.bash_profile
```
  And insert these:
```
# Set CLICOLOR if you want Ansi Colors in iTerm2
export CLICOLOR=1
export LSCOLORS=GxFxCxDxBxegedabagaced
export PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

# Set colors to match iTerm2 Terminal Colors
export TERM=xterm-256color
```
* In order to check it, type "ls" in your terminal
