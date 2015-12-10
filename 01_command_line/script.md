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

  cd ~/src/git

  ls *
  ls a*

  *exactly one

  ls at*.c
  ls at?.c

  *any char in brackets

  ls -1 test-[mp]*
  ls -1 test-[dg]*

  *char range [a-z]

  ls -1 test-[a-z]*
  ls -1 test-[d-f]*
  ls -1 test-[d-g]*

  *negation

  ls -1 test-[^d-g]*
  ls -1 test-[!d-g]*

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
  *fix typo

  touch april_1.txt
  mv april_{1,2}.txt

  *quick ext rename

  touch README.txt
  cp README{,.bak}

  *directory listing

  tree  action{mailer,view}/lib/action*/

  *create new file

  $ vi /usr/foo/file{a,b,c,d,e,f,g,h,i,j}

  for n in ({0,1,2}{0,1,2,3,4,5,6,7,8,9}{0,1,2,3,4,5,6,7,8,9})
  end

  *create sub directory

  mkdir man/{man,cat}{1,2,3,4,5,6,7,8}

  *non-existent tar file listing

  man tar
  tar zcvf rails.tgz rails
  man tar
  ls rails/[^.git]*
  tar zcvf rails.tgz rails/[^.git]*
  man tar
  tar zcv --exclude .git -f rails.tgz rails
  tar ztf rails.tgz
  tar ztf rails.tgz | sort
  tar ztf rails.tgz rails/{tools,tasks}

## Points to note
## Recap
## Going further

# File search L 25
## What is it?
  find is one of UNIX's most useful and important utilities. It finds files that match a given set of parameters, ranging from the file's name to its modification date.

## Why is it useful?
## You will be able to ...
## Examples
  *find by name

  find path operators

  find .

  find rails -name "active*"
  find rails -name "active*rb"
  find rails -name "Active*rb"
  find rails -iname "Active*rb"

  (history 50 | grep find | cut -c 8-99 | pbcopy)

  *find by atttributes

  -user   name
  -group   name

  find . -user kmcd
  find . -group staff

  -size   n

  find . -size +1M
  find . -size +500k
  find . -size +50k
  find . -size +100k

  *find by time

  cd ~/src/support_flow/
  find . -type f -print0 | xargs -0 ls -lt


  Modified within last 2 months

  find [!.git]* -mtime -8w -print
  ll -t `find [!.git]* -type f -mtime -8w -print`

  Modified 2 months ago

  find [!.git]* -mtime +8w -print
  ll -t `find [!.git]* -type f -mtime +8w -print`

  *operate on results

  -print
  -exec   command

   {} pathname of the file; must end with a backslash followed by a semicolon ( \;

  $ find -name "*.o" -exec rm -f {} \;

  tells find to delete any files whose names end in .o .

  -ok

  Same as -exec , except that find prompts you for permission before executing command . This is a useful way to test find commands. See article 17.10 .

  MP3 audio files scattered all over your filesystem; move them where you want. For example:

  $ find . -name '*.mp3' -print -exec mv '{}' ~/songs \;
  $ find . -name '*.mp3' -print -exec rm '{}' ~/songs \;

  $ -delete

  *logical operators

  find -and -not -perms 0700

  find ~ (-type f -not -perms 0600) -or (-type d -not -perms 0700)
  -and
  -or
  -not

  *text search grep/ack

  grep global regular expression print

  grep - handy for filtering
  ack - fast for large number of files

  cd ~/src/rails

  -i Ignore case. --ignore-case.
  -v Invert match.
  -c Print the number of matches instead of the lines themselves.
  -l Print the name of each file that contains a match instead of the lines
  -L Like the -l option, but print only the names of files that do not contain matches. May also be specified --files-without-match.
  -n Prefix each matching line with the number of the line within the file.
  -h For multifile searches, suppress the output of filenames.
  
  -B before
  -A after
  -C context
  
  cd ~/src/rails
  
  ack validates 
  ack -i validates
  ack validates -c
  ack -l validates 
  ack -h validates
  ack validate
  ack validate activemodel/lib/active_model
  ack validates_length_of activemodel/test/
  ack -A 2 validates_length_of activemodel/test/
  ack -B 2 validates_length_of activemodel/test/
  ack -C 2 validates_length_of activemodel/test/cases/validations_test.rb
  ack validates_length_of activemodel/test/cases/validations_test.rb
  ack -C 2 validates_length_of activemodel/test/cases/validations_test.rb
  ack -C 2 -n validates_length_of activemodel/test/cases/validations_test.rb
  man ack
  ack -C 2 -n validates_length_of activemodel/test/cases/validations_test.rb
  ack validates_length_of activemodel/test/cases/validations_test.rb
  ack -C 2 -n --with-filename validates_length_of activemodel/test/cases/validations_test.rb
  j activemodel/test/cases/validations_test.rb
  
  ack validate guides --pager='less -r'


## Points to note
## Recap
## Going further
  mdfind, mdls, mdutil

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

  find . -perm -u=x -name "*.*"

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
