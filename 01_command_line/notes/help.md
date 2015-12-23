## Getting help 2m

Instruction:
* man
* man -k
* help

Self-directed:
* info

Evaluation:
* find out how to X


## Getting help 2m
  man COMMAND
  * scroll
  * search
  man -k
  help
  man hier

  man—Display a command’s manual page.

  Most executable programs intended for command-line use provide a formal piece of documentation called a manual or man page. A special paging pro- gram called man is used to view them, like this:

  man program

  where program is the name of the command to view.

  Man pages vary somewhat in format but generally contain a title, a syn-
  opsis of the command’s syntax, a description of the command’s purpose, and a listing and description of each of the command’s options. Man pages, however, do not usually include examples, and they are intended as a refer- ence, not a tutorial. As an example, let’s try viewing the man page for the ls command:

  [me@linuxbox ~]$ man ls
  On most Linux systems, man uses less to display the manual page, so all of the familiar less commands work while displaying the page.

  The "manual" that man displays is broken into sections and covers not only user commands but also system administration commands, program- ming interfaces, file formats, and more. Table 5-1 describes the layout of the manual.

  Table 5-1: Man Page Organization
   Section
  1 2 3 4 5 6 7 8
  Contents
  User commands
  Programming interfaces for kernel system calls Programming interfaces to the C library Special files such as device nodes and drivers File formats
  Games and amusements such as screensavers Miscellaneous
  System administration commands

  Sometimes we need to look in a specific section of the manual to find what we are looking for. This is particularly true if we are looking for a file format that is also the name of a command. If we don’t specify a section num- ber, we will always get the first instance of a match, probably in section 1. To specify a section number, we use man like this:

  man section search_term For example:
  [me@linuxbox ~]$ man 5 passwd

  will display the man page describing the file format of the /etc/passwd file.

  --help —Display Usage Information

  Many executable programs support a --help option that displays a descrip- tion of the command’s supported syntax and options. For example:

  [me@linuxbox ~]$ mkdir --help

  Some programs don’t support the --help option, but try it anyway. Often it results in an error message that will reveal the same usage information.

  help—Get Help for Shell Builtins

  bash has a built-in help facility for each of the shell builtins. To use it, type help followed by the name of the shell builtin. For example:

  [me@linuxbox ~]$ help cd
  cd: cd [-L|-P] [dir]

  A note on notation: When square brackets appear in the description of a command’s syntax, they indicate optional items. A vertical bar character indicates mutually exclusive items. An example is the cd command above: cd [-L|-P] [dir].

  This notation says that the command cd may be followed optionally by either a -L or a -P and further, optionally followed by the argument dir.

  Self-directed:

  apropos—Display a list of appropriate commands.
  man -k

  whatis—Display a very brief description of a command.
  info—Display a command’s info entry.
  
### VO 300w

  OJ
  * get help
  * search for man pages
  * understand man page format
  * search within a man page
  * getting help when no man pages available

  To search the available manual pages, type

  $ man -k

  You know the ls command list's a directory contents.

  (?)
  $ a TAB
  $ whatis a2p

  Let's add nice color output to your directory listing

  $ man ls

  To scroll in a manual page, type

  Enter CTRL+U to Scroll UP
  Enter CTRL+D to Scroll DOWN
  Enter / to search
  Enter n to go forward
  Enter N to go back
  Enter - to toggle case sensitive search

  $ man less

  Some programs don’t support the --help option, but try it anyway. Often it results in an error message that will reveal the same usage information.

  bash has a built-in help facility for each of the shell builtins. To use it, type help followed by the name of the shell builtin. For example:

  [me@linuxbox ~]$ help cd
  cd: cd [-L|-P] [dir]

  square brackets indicate optional items.
  A vertical bar character indicates mutually exclusive items.

  the command cd may be followed optionally by either a -L or a -P and further, optionally followed by the argument dir.

  SLIDE: Man Page Organization
   Section
  1 2 3 4 5 6 7 8
  Contents
  User commands
  Programming interfaces for kernel system calls Programming interfaces to the C library Special files such as device nodes and drivers File formats
  Games and amusements such as screensavers Miscellaneous
  System administration commands

  Sometimes we need to look in a specific section of the manual to find what we are looking for. This is particularly true if we are looking for a file format that is also the name of a command. If we don’t specify a section num- ber, we will always get the first instance of a match, probably in section 1. To specify a section number, we use man like this:

  man section search_term For example:
  [me@linuxbox ~]$ man 5 passwd

  will display the man page describing the file format of the /etc/passwd file.

  Man pages, usually don't have examples, and they are intended as a refer ence, not a tutorial. Install cheat (skip to section) for examples:

  cheat ls

  RC:
  * search for man pages
  * understand man page format
  * search within a man page
  * getting help when no man pages available

  EV:
  * search for X man page
  * within a man page X, search for Y
  * find 2 sections for crontab
  

