# Advanced SSH-ing

[Edit this page](https://github.com/DrK-Lo/lotterhoslabprotocols/edit/main/bioinformagics_2-3_advanced_sshing.qmd)

These instructions will cover the following topics:
1. Connecting to Discovery using `ssh`
1. Setting up your `ssh` folder
     - Connecting to Discovery using `ssh` without a password
     - `ssh`-ing with aliases

This tutorial assumes you are familiar with using terminal - see also [instructions for installing iTerm](https://drk-lo.github.io/lotterhoslabprotocols/bioinformagics_1_install_iterm.html)

Below, if I want you to execute a terminal command, I’ll preface the command with “do” - eg “do `ls`”.

To connect to Discovery, and most servers used in academia, we can use a Secure SHell (`ssh`) that will allow our computer to plug in our monitor to the server. Just like our home monitors show what’s going on ‘inside’ our computer, the ssh tunnel allows us to use the server like we would use our own computer.

I’m assuming everyone has the credentials on the IT side of things to be able to connect to discovery. Ask Katie if this is not the case.

Before actually getting into doing the ‘connecting’, we should cover some basic commands to navigate in terminal, where we’ll eventually execute the `ssh` command.
If you are not familiar with basic terminal commands, see the [lab protocols page here](https://drk-lo.github.io/lotterhoslabprotocols/code_unixcommands.html). Generally the types of ‘native’ commands used will be BASH - BAsic SHell; think of BASH like a computer language and the terminal as a session of BASH).
The BASH commands from this protocol that we’ll need immediately are `cd` and `ls` . Read those sections then come back here and continue.

The following instructions cover connecting "Computer A" (e.g., your laptop) to "Server B" (e.g., Discovery). But if you wanted to connect to another server from Discovery, you would follow these steps for creating and editing files on Discovery - in other words, Discovery would now be "Computer A" and the new server would be "Server B".

---

## 1. Connecting to Discovery using `ssh`

Once you have your discovery credentials, you should be able to ssh to discovery like this: `ssh your_login@login.discovery.neu.edu`. It will then prompt you for a password. You can keep entering a password every time you log in (which can get annoying, if the long login isn’t annoying enough) or we can create a file (see next step) that will tell Discovery that you’re really you and you won’t have to enter a password afterward.


## 2. `ssh`-ing to Discovery without a password

### Setting up your `ssh` folder

Before we can `ssh` without a password, we need to create a folder on your laptop.

On mac and linux, the short cut to your “home” directory is `~`. So if you had a folder called ‘documents’ in your home directory, you could access that file path with `~/documents`.  On a mac, that path is something like `/Users/yourusername`. You can also ask BASH to tell you your username with `echo $USER`. Or you can ask for the actual home path `echo $HOME`.

To connect to Discovery with `ssh` we’re going to need a place to put files. That place by default is in a hidden folder called `.ssh` in your home directory on your laptop (note the `.`). So let’s first change directories to the home directory on your laptop (do `cd ~`) and see if you have it (to do this step you should not be `ssh`-ed to Discovery yet). Normally to see files you would use `ls` but to see hidden files  (those that start with `.`) you need to add `-a` to the command - let’s get the long form list of all files (do `ls -la`).

If you don’t see `.ssh`, make the directory - do `mkdir .ssh`.

then do `cd .ssh`

### Create RSA key for passwordless ssh

The file that Discovery uses to ‘trust’ us is called an RSA key (abbr is creators names Rivest–Shamir–Adleman). To create that key, make sure you ARE NOT ssh-ed to discovery (ie you are in your laptop’s filesystem in the `~/.ssh` folder) and execute this command `ssh-keygen -t rsa`.
     - Executing this command should ask you to create the file id_rsa in your $HOME/.ssh folder; agree.
     - When it asks you for a password, just hit the return key (and again for the confirmation). In other words, don’t enter a password.

You should now see the `id_rsa` file (and maybe a couple others with that prefix) if you do `ls -l`.

### Send RSA key to Discovery

Okay, we’ve created the key for Discovery, but now we have to give that key to discovery.

Before we send the file, we’ll need a destination (directory) to send it to on Discovery. do `ssh your_login@login.discovery.neu.edu mkdir -p .ssh` - you’ll get a password prompt since we haven’t completed the setup yet. This command first logs in to Discovery then makes the hidden directory called `.ssh` in your Discovery home directory. In the screenshot I make a directory I’ll delete later.

The key Discovery will use to authenticate us is actually the content within the file called `id_rsa.pub`. To send this key to Discovery,  we’re going to use a command called `cat` which basically prints the content of a file (try doing `cat id_rsa.pub` by itself). We’re also going to use a pipe `|` (on keyboard above return key; use shift) - the pipe let’s you take standardout (like something that’s printed) and pass it to another command. So we could print the rsa key and pass it to a command to send it to discovery like so: do `cat .ssh/id_rsa.pub | ssh your_login@login.discovery.neu.edu 'cat >> .ssh/authorized_keys'`. You’ll be prompted for your login password again. If it works, there won’t be any fanfare - it will just give you a new prompt for your local filesystem (it makes a connection, sends the info, then ends the connection).

The command prints the file contents (`cat id_rsa.pub`) then sends that printout to an ssh connection `| ssh me@domain` then after connecting uses another cat command (`'cat`) to send the contents of the original file on our laptop to a discovery file `>> .ssh/authorized_keys'`. The command executed after connection is surrounded by single quotes: `'` . Note that we used `>>` to append to the discovery file. Had we used just `>` it would have overwritten/created the file with just the new content. We’ll often have multiple computers that we use to ssh (eg a different server connecting to discovery) so we may have many keys in this authorized key file (which is why we append the new content with `>>`).

You should now be able to ssh without a password: do `ssh your_login@login.discovery.neu.edu`.


