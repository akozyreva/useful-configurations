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
#export PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
export PS1="[\[$(tput sgr0)\]\[\033[38;5;190m\]\T\[$(tput sgr0)\]\[\033[38;5;15m\]] \[$(tput sgr0)\]\[\033[38;5;2m\]\u\[$(tput sgr0)\]\[\033[38;5;15m\]@\[$(tput sgr0)\]\[\033[38;5;13m\]\W\[$(tput sgr0)\]\[\033[38;5;15m\]:\\$ \[$(tput sgr0)\]"

# Set colors to match iTerm2 Terminal Colors
export TERM=xterm-256color

# tip for renaming the tab dynamically
export PROMPT_COMMAND='echo -ne "\033]0;${PWD/#$HOME/~}\007"'

#for different colors of tabs
if [ -f ~/my_script_folder/iterm2_rainbow_tabs/iterm2_rainbow_tabs.sh ];
 then . ~/my_script_folder/iterm2_rainbow_tabs/iterm2_rainbow_tabs.sh
fi
```
* Use this repo in order to recieve colored tabs
https://github.com/lfender6445/iterm2_rainbow_tabs
* In order to check it, type "ls" in your terminal - you see something like this:
![screen shot 2018-10-02 at 17 08 31](https://user-images.githubusercontent.com/40454842/46358011-5c29b080-c666-11e8-8e55-e30b7e2a3f98.png)

Finally - the screen of color settings:

![screen shot 2018-10-02 at 17 13 47](https://user-images.githubusercontent.com/40454842/46358105-8f6c3f80-c666-11e8-807c-e3d326582803.png)
