# Intro 00
## What is the command line?

  CLI is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines).

## Why is it useful?

  CLI is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines).

## Objectives

  CLI is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines).

## Assumed knowledge

  CLI is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines).

## What do you need to get started?

  CLI is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines).

  * terminal
  * text editor
  * internet connection (to download packages)

# History 01
## What is it?
  View & re-use every comand you type in

## Why is it useful?
  Don't have to remember what or how you did something; e.g. what was that command to ...

## You will be able to ...
  view commands
  search commands
  repeat command execution

## Examples
  history file
  scroll up though commands
  repeat last command
  repeat command by number
  search command with CTRL+R
  search command with grep filter

## Points to note
  history behavoiur is controlled from .bash_profile

## Recap
## Going further

# Keyboard speed 03
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  tab completion
  clear/exit/cancel
  cursor line movement
  cursor charachter movement
## Points to note
## Recap
## Going further

# Getting help 05
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  man -k
  scroll
  search
  sections/help/info
## Points to note
## Recap
## Going further

# Shell environment 07
## What is it?
## Why is it useful?
  Save functions, variables, alias loaded every time so you dont have to re-type

## You will be able to ...
## Examples
  loading .bash_profile
  variables
  * history timestamp
  * history filesize
  * executable PATH
  aliases
  functions

## Points to note
## Recap
## Going further

# Package management 09
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  install homebrew
  search/install
  remove
  install cask
  search/install

## Points to note
## Recap
## Going further

# Processes L 11
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  view ps/pstree
  view top/htop/activity monitor
  kill
  job control
  crontab hour/min
  crontab day/week
  crontab month
  at

## Points to note
## Recap
## Going further

# File display 15
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  less
  head
  tail
  tail filter
  open
  alias (editor)
## Points to note
## Recap
## Going further

# Directory navigation 17
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  cd ..
  cd -
  cd $CLI
  ls -l
  ls -R
  ls -tr
  tree
  file size
  file system layout

## Points to note
## Recap
## Going further

# Wildcards L 19
## What is it?
  abbreviate filenames or refer to groups of files

  Like a wildcard in a poker game, a wildcard in a filename can have any value.

## Why is it useful?

  Match groups of files so you don't have to specify each file name manually

## You will be able to ...

## Examples
  *zero or more
  *exactly one
  *any char in brackets
  *char range [a-z]
  *negation

## Points to note

  wildcards do not match files whose names begin with a dot ( . ), like .cshrc . [1] This prevents you from deleting (or otherwise mucking around with) these files by accident.

  To match those files, type the dot literally. For example, .[a-z]* matches anything whose name starts with a dot and a lowercase letter. Watch out for plain .* , though; it matches the directory entries . and .. (see article 15.5 for suggestions on solving that problem)

  wildcards only match names that already exist.

  program never sees wildcards. For example, typing:

  $ lpr *

  is exactly the same as typing:

  $ lpr file1 file2 file3 file4 file5

  Wildcards are simlar to but NOT regular expressions!

## Recap
## Going further

# Pattern expansion 23
## What is it?
  *pattern {foo,bar}

## Why is it useful?
  Most of the time, a program never sees wildcards. For example, typing:

  $ lpr *

  is exactly the same as typing:
  $ lpr file1 file2 file3 file4 file5

  you want to read some files from a tape, which requires the command tar x ( 20.4 ) , so you type the command tar x *.txt .

  The shell expands the wildcard \*.txt , according to what's in the current directory, before it hands the completed command line over to tar for execution.

  Problem: reference file archive not current directory.

  use {} to generate any string - not just filenames that already exist. You have to type the unique part of each name, but you only have to type the common part once.

  For example, to extract the files called project/wk9/summary , project/wk14/summary , and project/wk15/summary from a tar tape, you might use:

  $ tar xv project/wk{9,14,15}/summary
  x project/wk9/summary, 3161 bytes, 7 tape blocks
  x project/wk14/summary, 878 bytes, 2 tape blocks
  x project/wk15/summary, 2268 bytes, 5 tape blocks

## You will be able to ...

## Examples
  fix typo
  quick ext rename
  directory listing
  create new file
  create sub directory

## Points to note
## Recap
## Going further

# File search L 25
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  find by atttributes
  find by time
  operate on results
  logical operators
  text search grep/ack
## Points to note
## Recap
## Going further

# Text processing L 29
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  sed
  tr
  cut
  sort
  uniq
  wc
## Points to note
## Recap
## Going further

# File modification 33
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  touch
  redirection
  attributes
  mode
  owner
## Points to note
## Recap
## Going further

# Networking L 35
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  ping / tracroute
  lsof / nmap port scanner
  dns/nslookup/MX record
  ssh
  sftp/scp
  wget
## Points to note
## Recap
## Going further

# Outro 39
## Recap
## Going further
 ## Contact
