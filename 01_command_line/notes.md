# TOC
## Intro 1m

  Title
  Time required
  Required materials
  Presumed knowledge
    * cp,mv,cd,rm
  behavioral/knowledge objectives
    * Two or three interesting but relevant questions
    * Showing a picture/s, a chart or a model
    * A situation Statement of Aim: Announcement of the statement of the lesson in a clear, concise, like this "Today, we shall study the..."

## Getting help 2m

  Instruction:
  * man
  * man -k
  * help

  Self-directed:
  * info

  Evaluation:
  * find out how to X

## Shell environment 4m

  ~/.bashrc
  variables, e.g. $EDITOR
  ~/bin, $PATH
  aliases
  functions (show with type)

  Chapter 6: Shell and Environment Variables
  1.6 Shell quoting

  Aliases ( 10.2 )
  Shell functions ( 10.9 )
  16.9 Keeping a Private Stash of Utilities by Adding ~/bin

  Self-directed
  * prompt customisation
  * create a desk clone (later with find?)

  Evaluation
  * Create an alias for X
  
  9.16  backquotes ( ` ` ) does command substitution
  Process substitution ( 9.18 )

## Keyboard shortcuts 2m

  Faster erasing ( 9.2 )
  Filename completion ( 9.8 , 9.9 , 9.10 )
  Build Strings with { }
  102 Command Line Editing
  clear
  exit

## History 2m

  Chapter 11: The Lessons of History
  16.12 Setting Shell History Options
  106 Using History

## Directory navigation 4m

  e.g. Rails source

  pwd, cd, ls
  file globbing/wildcards
  ls -R
  tree
  man hier (file system layout)
  /Volumes see: OSX page
  df

  Chapter 9: Saving Time on the Command Line

  Chapter 15: Wildcards (split into two sections?)

## File display 4m

  e.g. Rails source

  cat
  less
  (syntax highlight)
  du
  wc?
  head / tail
  open

  Chapter 25: Showing What's in a File
  59 Calculating File Size and Disk Space
  165 Launching GUI Applications

## File search 4m

  e.g. Rails source

  find
  locate
  mdfind
  grep / ack (Basic regex)

  Chapter 17: Finding Files with find
  Chapter 27: Searching Through Files

  19.15 Shell wildcards vs. Regular expressions

  128 Shining a Light on Spotlight

  9.1 Finding All Your MP3 Files
  9.2 Handling Filenames Containing Odd Characters
  9.5 Finding Files Irrespective of Case
  9.6 Finding Files by Date
  9.7 Finding Files by Type
  9.9 Finding Files by Content
  9.8 Finding Files by Size

  103 Shell games
  219 Searching for files

## File modification 2m

  (CRUD)

  cp *-dt-*-nt-~
  cp foo.{txt,md}
  ln
  chown (permissions)
  chmod
  touch
  tar / gzip

  Chapter 13: Redirecting Input and Output
  http://docstore.mik.ua/orelly/unix/upt/ch25_02.htm
  Chapter 22: File Security, Ownership, and Sharing
  17.1 Renaming Many Files
  109 Permissions

## Text processing 4m

  awk
  xargs
  cmp / diff
  cut
  sort
  uniq
  sed
  for/while loop

  Chapter 34: The sed Stream Editor
  Chapter 36: Sorting

  8.1 Sorting Your Output
  8.2 Sorting Numbers
  8.4 Cutting Out Parts of Your Output
  8.5 Removing Duplicate Lines
  8.9 Translating Characters

  141 Pipes and Filters

  265 Text processing

  4.3 Running Several Commands in Sequence
  4.4 Running Several Commands All at Once
  4.10 Running All Scripts in a Directory (loop)
  2.14 Saving or Grouping Output from Several Commands
  
  211 Command Line

## Networking 2m

  ftp
  curl / wget / httrack
  ssh
  scp
  SSH config
  lsof
  ifconfig

  176 Transferring Files
  207 Networking

## Processes 4m

  e.g. Rails develeopment: start/stop server, background jobs

  Chapter 12: Job Control
  ps / pstree
  top / htop / activity monitor
  job control: bg, fg
  kill / killall
  nohup
  at
  cron
  cron format
  Deamon processes
  init
  OSX launchctl

  Job control ( 12.1 )
  
  Chapter 38: Starting, Stopping, and Killing Processes
  Chapter 39: Time and Performance
  Chapter 40: Delayed Execution

  154 Running a Command in the Background
  155 Checking on a Process
  162 Canceling a Process

  127 Processes

## Package management 2m

  (Move to start?)

  e.g. install cheat
  e.g. install PostgreSQL 9.3

  brew install ...
  install home brew
  find app
  install app
  boot config
  taps/custom
  xcode-select -p
  xcode-select --install
  remove app
  ruby/prog lang env
  
  http://coolestguidesontheplanet.com/installing-homebrew-os-x-yosemite-10-10-package-manager-unix-apps/

## OUTRO 1m

  List behavioral/knowledge objectives
  Recap
  Further reading

  # REFERENCE

# Reference
## Links
  * http://blog.sanctum.geek.nz/series/unix-as-ide/
  * http://www.ee.surrey.ac.uk/Teaching/Unix/unix5.html
  * http://blog.sanctum.geek.nz/series/unix-as-ide/
  * http://lifehacker.com/eight-terminal-utilities-every-os-x-command-line-user-s-1593793109
  * http://www.learnenough.com/command-line-tutorial
  
## UNIX Power Tools

  Faster erasing ( 9.2 )
  Filename completion ( 9.8 , 9.9 , 9.10 )
  Build Strings with { }
  9.16  backquotes ( ` ` ) does command substitution
  Process substitution ( 9.18 )
  xargs http://docstore.mik.ua/orelly/unix/upt/ch09_21.htm
  Job control ( 12.1 )
  Aliases ( 10.2 )
  Shell functions ( 10.9 )

  Chapter 2: Logging In
  Chapter 5: Setting Up Your Terminal
  Chapter 6: Shell and Environment Variables
  Chapter 7: Setting Your Shell Prompt
  Chapter 9: Saving Time on the Command Line
  Chapter 10: Aliases
  Chapter 11: The Lessons of History
  Chapter 12: Job Control
  Chapter 13: Redirecting Input and Output
  Chapter 15: Wildcards
  Chapter 17: Finding Files with find
  Chapter 22: File Security, Ownership, and Sharing
  Chapter 25: Showing What's in a File
  Chapter 27: Searching Through Files
  Chapter 34: The sed Stream Editor
  Chapter 36: Sorting
  Chapter 38: Starting, Stopping, and Killing Processes
  Chapter 39: Time and Performance
  Chapter 40: Delayed Execution

## Bash cookbook

  1.6 Shell quoting
  2.14 Saving or Grouping Output from Several Commands
  4.1 Running Any Executable
  4.3 Running Several Commands in Sequence
  4.4 Running Several Commands All at Once
  4.10 Running All Scripts in a Directory (loop)
  8.1 Sorting Your Output
  8.2 Sorting Numbers
  8.4 Cutting Out Parts of Your Output
  8.5 Removing Duplicate Lines
  8.9 Translating Characters
  9.1 Finding All Your MP3 Files
  9.2 Handling Filenames Containing Odd Characters
  9.5 Finding Files Irrespective of Case
  9.6 Finding Files by Date
  9.7 Finding Files by Type
  9.9 Finding Files by Content
  9.8 Finding Files by Size
  16.2 Customizing Your Prompt
  16.9 Keeping a Private Stash of Utilities by Adding ~/bin
  16.12 Setting Shell History Options
  17.1 Renaming Many Files
  17.6 Logging an Entire Session or Batch Job
  17.15 Using sudo on a Group of Commands
  19.15 Shell wildcards vs. Regular expressions

## UNIX for OSX

  59 Calculating File Size and Disk Space
  128 Shining a Light on Spotlight
  135 Standard Input and Standard Output
  141 Pipes and Filters
  154 Running a Command in the Background
  155 Checking on a Process
  162 Canceling a Process
  165 Launching GUI Applications
  176 Transferring Files

## Prag prog

  103 Shell games

## Productive Programmer

  211 Command Line

## The Linux Command Line

  102 Command Line Editing
  106 Using History
  109 Permissions
  127 Processes
  207 Networking
  219 Searching for files
  265 Text processing