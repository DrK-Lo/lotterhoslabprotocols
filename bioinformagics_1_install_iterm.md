# install iTerm terminal app for MacOS

[Edit this page](https://github.com/DrK-Lo/lotterhoslabprotocols/edit/main/bioinformagics_1_install_iterm.qmd)

These instructions will instruct users on how to install iTerm terminal app for MacOS and further install iTerm's "shell integration".

iTerm2 is a program that allows you to have a command-line interface with the computer. Generally this type of program is called a ‘terminal’. Mac has a native Terminal app, but iTerm has more bells and whistles. The terminal is used to run programs (or custom scripts) “manually”.

------------------------------------------------------------------------

### 1. download iTerm

First, download and install iTerm2 (if you haven’t already). https://iterm2.com

### 2. install shell integration

Once the program is installed, we’ll want to install a feature called “shell integration”. There are some cool features that this allows, like viewing pdfs/images in the command line, right-click to download and a few other useful ones I’ll show you. More info here: https://iterm2.com/3.0/documentation-shell-integration.htmlTo do this, open iTerm2, then in menubar Shell > New Window. Then go to the menubar again and iTerm2 > Install Shell Integration.

-	The next window you want to check Allow install iTerm2 Utilities.
-	Then Download and Run Installer (+ continue)
-	Done!
- Note that we just installed shell integration for your local laptop. For shell integration to work on other servers, you'll need to be ssh-ed to the server and then go to the menubar again and iTerm2 > Install Shell Integration.

Once complete, it should print a bunch of information to the terminal window. At the end, it will list all of the new tools you can use and how to use them. For some, you only enter the tool name and hit enter to use it in command-line (`imgls`), while others it shows you you need another word after the tool name (`it2dl [filename]`) before the tool will work. Each tool also has an indented description of what it does.If you can ssh to Discovery (or other servers) you’ll need to install shell integration with each server.

- For shell integration and the new tools to work, you will need to either start a new session (e.g., open a new terminal tab +/- ssh) or `source $HOME/.bash_profile`. Doing either option will execute the commands added to your `$HOME/.bash_profile` file by iTerm. if you `vim $HOME/.bash_profile` you should see something like this:

     ```
     test -e "${HOME}/.iterm2_shell_integration.bash" && source "${HOME}/.iterm2_shell_integration.bash"
     ```


