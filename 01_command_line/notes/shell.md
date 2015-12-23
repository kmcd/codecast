## Shell environment 2m

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
## Next steps

## Shell environment 4m

  A command can be one of four things:

  An executable program like all those files we saw in /usr/bin. Within this category, programs can be compiled binaries, such as programs written in C and C++, or programs written in scripting languages, such as the shell, Perl, Python, Ruby, and so on.

  A command built into the shell itself. bash supports a number of com- mands internally called shell builtins. The cd command, for example, is a shell builtin.

  A shell function. Shell functions are miniature shell scripts incorporated into the environment. We will cover configuring the environment and writing shell functions in later chapters, but for now just be aware that they exist.

  An alias. An alias is a command that we can define ourselves, built from other commands.

  type—Indicate how a command name is interpreted.
  which—Display which executable program will be executed.

  Identifying Commands

  It is often useful to know exactly which of the four kinds of commands is being used, and Linux provides a couple of ways to find out.
  type—Display a Command’s Type

  The type command is a shell builtin that displays the kind of command the shell will execute, given a particular command name. It works like this:
  type command
  where command is the name of the command you want to examine. Here are
  some examples:

  [me@linuxbox ~]$ type type
  type is a shell builtin

  [me@linuxbox ~]$ type ls
  ls is aliased to ls --color=tty'

  [me@linuxbox ~]$ type cp
  cp is /bin/cp

  Here we see the results for three different commands. Notice that the ls command (taken from a Fedora system) is actually an alias for the ls com- mand with the --color=tty option added. Now we know why the output from ls is displayed in color!

  which—Display an Executable’s Location

  Sometimes more than one version of an executable program is installed on a system. While this is not very common on desktop systems, it’s not unusual on large servers. To determine the exact location of a given executable, the which command is used:

  [me@linuxbox ~]$ which ls /bin/ls
  which works only for executable programs, not builtins or aliases that are substitutes for actual executable programs. When we try to use which on a shell builtin (for example, cd), we get either no response or an error message:
  [me@linuxbox ~]$ which cd
  /usr/bin/which: no cd in (/opt/jre1.6.0_03/bin:/usr/lib/qt-3.3/bin:/usr/kerber os/bin:/opt/jre1.6.0_03/bin:/usr/lib/ccache:/usr/local/bin:/usr/bin:/bin:/home /me/bin)
  This is a fancy way of saying "command not found."

  A login bash will read .bash_profile , .bash_login , or .profile . A bash subshell - but not a login shell - will read a file named .bashrc in your home directory.

  The difference between *environment variables* and regular shell variables ( 6.8 ) is that a shell variable is local to a particular instance of the shell (such as a shell script), while environment variables are "inherited" by any program you start, including another shell ( 38.4 ) . That is, the new process gets its own copy of these variables, which it can read, modify, and pass on in turn to its own children. In fact, every UNIX process (not just the shell) passes its environment variables to its child processes.

  echo $TERM
  echo $PWD
  echo $HOME

  Many UNIX utilities, including the shell, need information about you and what you're doing in order to do a reasonable job.

  Lots of UNIX programs (like mail programs) include a command to start an editor as a subprocess; they like to know your favorite editor. And so on.

  *alias* define abbreviations for commonly used commands

  alias g='git '
  alias h='history | grep '
  alias j='open -a /Applications/jEdit.app '
  alias jpf='j ~/.bash_profile'
  alias ls='ls -Gp '
  alias rbd='open ~/Documents/tech/ruby2.0_rdoc/index.html '
  alias rl='source ~/.bash_profile'
  alias rrd='open ~/Documents/tech/rails4_rdoc/index.html '
  alias rrg='open http://guides.rubyonrails.org'
  alias rrl='tail -f log/guard.log log/development.log'
  alias rsr='ka ruby; ka _test; nohup bundle exec guard > log/guard.log &'
  alias td='j ~/.todo.txt'
  alias tree='tree -C '
  alias wf='ghi list -L bug; ghi list -M 2 -N bug'

  $ unalias rm
  $ alias

  functions

  bug () { ghi open -m "$1" -L bug ; }
  feature () { ghi open -m "$1" -L feature ; }
  ka () { ps waux | grep $1 | awk '{print $2}' | xargs kill -9 ; }
  jo () {  j ` find . -name "$*" ` ; }

  The spaces and the semicolon ( ; ) are both important!

  The "$@" ( 44.15 ) is replaced by the command-line arguments (other options, or directory and filenames), if you use any:

  the shell will replace that string with a quoted ( 8.14 ) set of the script's command-line arguments. Then you can pass as many arguments as you want, including pathnames with unusual characters

  You have a stash of personal utilities you like to use, but you are not root on the sys- tem and can’t place them into the normal locations like /bin or /usr/local/bin, or there is some other reason to separate them.

  $ PATH="$PATH:~/bin"

  Now if dot were listed first, then someone else’s version of ls would supersede the normal ls command and you might unwit- tingly run that command. Don’t believe us? Try this:

  $ bash
  $ cd
  $ touch ls
  $ chmod 755 ls
  $ PATH=".:$PATH"
  $ ls
  $

  sudo—Execute a Command as Another User

  The sudo command is like su in many ways but has some important addi- tional capabilities. The administrator can configure sudo to allow an ordin- ary user to execute commands as a different user (usually the superuser) in a very controlled way. In particular, a user may be restricted to one or more specific commands and no others. Another important difference is that the use of sudo does not require access to the superuser’s password. To authen- ticate using sudo, the user enters his own password. Let’s say, for example, that sudo has been configured to allow us to run a fictitious backup program called backup_script, which requires superuser privileges.

  With sudo it would be done like this:

  [me@linuxbox ~]$ sudo backup_script Password:

  System Backup Starting...

  After entering the command, we are prompted for our password (not the superuser’s), and once the authentication is complete, the specified command is carried out. One important difference between su and sudo is that sudo does not start a new shell, nor does it load another user’s environ- ment. This means that commands do not need to be quoted any differently than they would be without using sudo. Note that this behavior can be over- ridden by specifying various options. See the sudo man page for details.
  To see what privileges are granted by sudo, use the -l option to list them:
  [me@linuxbox ~]$ sudo -l
  User me may run the following commands on this host:
  (ALL) ALL

  9.16  backquotes ( ` ` ) does command substitution
  Process substitution ( 9.18 )

   < ( process )
   `\`
   $()

### VO 300w

  *bash_profile

  A login bash will read .bash_profile , .bash_login , or .profile . A bash subshell - but not a login shell - will read a file named .bashrc in your home directory.

  .bashrc mention?

  EDITOR ~/.bash_profile
  source ~/.bash_profile

  *export

  Many UNIX utilities, including the shell, need information about you and what you're doing in order to do a reasonable job.

  e.g. git $EDITOR

  a shell variable is local to a particular instance of the shell (such as a shell script) environment variables are "inherited" by any program you start, including another shell

  echo $TERM
  echo $PWD
  echo $HOME

  *export PATH

  You have a stash of personal utilities you like to use, but you are not root on the sys- tem and can’t place them into the normal locations like /bin or /usr/local/bin, or there is some other reason to separate them.

  $ PATH="$PATH:~/bin"

  *commands

  An executable program: compiled binaries or interpreted scripting languages, such as the shell, Perl, Python, Ruby, and so on

  $ ls /usr/bin

  A command built into the shell itself; e.g. cd

  $ man bash
  $ help
  $ help cd

  *alias

  An alias. An alias is a command that we can define ourselves, built from other commands.

  define abbreviations for commonly used commands

  alias ls='ls -Gp '
  alias ll='ls -lahGp '
  alias g='git '

  alias rl='source ~/.bash_profile'

  *functions

  A shell function: takes args, executes, returns ouput

  feature () { ghi open -m "$1" -L feature ; }
  jo () {  j ` find . -name "$*" ` ; }

  The "$@" ( 44.15 ) is replaced by the command-line arguments (other options, or directory and filenames), if you use any:

  the shell will replace that string with a quoted ( 8.14 ) set of the script's command-line arguments. Then you can pass as many arguments as you want, including pathnames with unusual characters

  *self-directed
  * prompt customisation export PS1="\[\e[34;1m\]\w\[\e[0m\] $ "
  * create a desk clone
