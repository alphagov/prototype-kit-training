# Cheatsheets

## The terminal

The command line is a text interface for your computer. Just like Windows
Explorer on Windows or Finder on a Mac it lets you navigate through the files
and folders of your computer, but it is completely text based.

The command line can seem unfamiliar and scary, but it's really just a
different way of interacting with your computer. This tutorial only covers
safe commands that won't do anything bad to your computer, even if you get
them wrong.

*Windows users: Terminal is only available in OS X, for Windows use [Git Bash](https://git-scm.com/download/win
)*.

### Navigating around in the terminal

Once you opened up your terminal you should see a window like this:

![Screenshot of the Terminal app. The text says Last login: Sat May 18 11:08:55 on ttys002 ~$ ](/images/terminal.png)

Don't worry if the text in yours is a little different, it doesn't matter.

To run a command, just type the words and press `Enter`.

Try running:

```shell
pwd
```

#### `pwd` or print working directory

The `pwd` command prints to the command line the current directory (another
name for folder) you are in. If you just opened up your terminal, you are
probably in your "home" directory, and should get an output similar to this:

```
/Users/your-username
```

So your current "working directory" is `/Users/your-username`.

#### `cd` or change directory

The `cd` command allows you to move between directories. You tell `cd` which directory to move to by putting the path after the `cd`, like this:

```shell
cd Desktop
```

This moves you into the Desktop directory.

Other examples using cd include:

```shell
cd ..
```

This takes you up a directory level.

```shell
cd ~
```

This takes you to your home directory.


#### `ls` or list

You might wonder "how I do know which files are in a directory?", the `ls` command can do this:

```shell
ls
```

This should print a list of the files and folders inside the working
directory. If you're in your home directory, you'll probably see directories like `Applications`, `Desktop`,
`Documents` and `Downloads`.


### Terminal shortcuts

Press **up** and **down** on the keyboard to go through previous commands.

Press **ctrl c** to cancel a running app.

Press **cmd + K** to clear your terminal. This doesn't stop a running command, it just removes lines of content from view.

Press **tab** to autocomplete a file or folder name. You may need to press it a second time if there are no unambiguous matches.

### Getting things wrong on the command line

If you type a command that the command line doesn't understand, it will show
you an error message. Don't panic, if you see one of these - everything is fine!
Just have a look at the command you wrote and see if you can work out what was wrong.

Try this for example:

```shell
whargleblargle
```

You should see an error message like `-bash: whargleblargle: command not found`.

## Common git commands

### Create repositories

Creates a new local repository with the specified name.

```
$ git init [project-name]
```

Downloads a project and its entire version history.

```
$ git clone [url]
```

### Make changes

Lists all new or modified files to be committed.

```
$ git status
```

Snapshots the file in preparation for versioning.

```
$ git add [file-name]
```

Or, snapshot multiple files.

```
$ git add .
```

Records a snapshot of your file (a commit).

```
$ git commit -m"[descriptive message]"
```

### Synchronise local and remote repos

Uploads all local branch commits to GitHub.

```
$ git push [remote] [branch]
```

If pushing to a master branch from a local repo (a folder on your device), you can write the above as:

```
$ git push origin master
```

Downloads history from a remote directory and incorporates the changes in your local version

```
$ git pull
```