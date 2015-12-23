## Directory navigation 2m

  e.g. Rails source

  pwd, cd, ls
  file globbing/wildcards
  ls -R
  tree
  man hier (file system layout)
  /Volumes see: OSX page
  df

  export CC_CLI=DIR
  cd $CC_CLI
  alias cdc="cd DIR"

  Chapter 9: Saving Time on the Command Line

  Chapter 15: Wildcards (split into two sections?)
  
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
## Next steps

### Directory navigation 2m

  pwd
  cd
  ls -R
  tree
  man hier (file system layout)
  /Volumes see: OSX page
  df

  tree                               

  Tree  is  a  recursive  directory  listing program that produces a depth indented listing of files, which is colorized ala dircolors if the LS_COLORS environment variable is set and output is to tty.

  With  no  arguments,  tree  lists the files in the current directory.  When directory arguments are given, tree lists all the files and/or directories found in the given  directories  each  in  turn.

  Upon  completion  of  listing  all  files/directories found, tree returns the total number of files and/or directories listed.

  By default, when a symbolic link is encountered, the path that  the  symbolic  link  refers  to  is printed after the name of the link in the format:

     name -> real-path

  If  the  \`-l'  option  is given and the symbolic link refers to an actual directory, then tree will
  follow the path of the symbolic link as if it were a real directory.

  -a     All files are printed.  By default tree does not print hidden files (those beginning with  a dot  \`.').   In  no event does tree print the file system constructs `.' (current directory)
  and \`..' (previous directory).

  -d     List directories only.

  -f     Prints the full path prefix for each file.

  -x     Stay on the current file-system only.  Ala find -xdev.

  -L level Max display depth of the directory tree.

  -P pattern
  List only those files that match the wild-card pattern.  Note: you must use the -a option to
  also  consider those files beginning with a dot `.'  for matching.  Valid wildcard operators
  are `*' (any zero or more characters), `?' (any single character), `[...]' (any single char-
  acter  listed  between  brackets (optional - (dash) for character range may be used: ex: [A-
  Z]), and `[^...]' (any single character not listed in brackets) and `|' separates  alternate
  patterns.

  -I pattern
  Do not list those files that match the wild-card pattern.

  SORTING OPTIONS
  -v     Sort the output by version.

  -r     Sort the output in reverse alphabetic order.

  -t     Sort the output by last modification time instead of alphabetically.

  -C     Turn colorization on always


  See: https://developer.apple.com/library/mac/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html

  cd
  Changes the working directory to your home directory.

  cd cd -
  Changes the working directory to the previous working directory.

  cd ~username
  Changes the working directory to the home directory of username. For example, cd ~bob changes the directory to the home directory of user bob.

  An absolute pathname begins with the root directory and follows the tree branch by branch until the path to the desired directory or file is com- pleted. For example, there is a directory on your system in which most of your system’s programs are installed. The pathname of that directory is /usr/bin. This means from the root directory (represented by the leading slash in the pathname) there is a directory called usr that contains a direct- ory called bin.

  [me@linuxbox ~]$ cd /usr/bin [me@linuxbox bin]$ pwd /usr/bin
  [me@linuxbox bin]$ ls

  Where an absolute pathname starts from the root directory and leads to its destination, a relative pathname starts from the working directory. To do this, it uses a couple of special symbols to represent relative positions in the file- system tree. These special symbols are . (dot) and .. (dot dot).


  1.16 Wildcards

  The shells provide a number of wildcards that you can use to abbreviate filenames or refer to groups of files. For example, let's say you want to delete all filenames in the current directory ( 1.21 ) ending in .txt . You could delete these files one by one, but that would be boring if there were only five and very boring if there were a hundred. Instead, you can use a wildcarded name to say, "I want all files whose names end with .txt , regardless of what the first part is." The wildcard is the "regardless" part. Like a wildcard in a poker game, a wildcard in a filename can have any value.

  The wildcard you see most often is * (asterisk), but we'll start with something simpler: ? (question mark). When it appears in a filename, the ? matches any single character. For example, letter? refers to any filename that begins with letter and has one character after that. This would include letterA , letter1 , as well as filenames with a non-printing character as their last letter, like letter ^C.

  The * wildcard matches any character or group of zero or more characters. For example, *.txt matches all files whose names end with .txt , *.c matches all files whose names end with .c (by convention, source code for programs in the C language), and so on.

  The * and ? wildcards are sufficient for 90 percent of the situations that you will find. However, there are some situations that they can't handle. For example, you may want to list files whose names end with .txt , mail , or let . There's no way to do this with a single * ; it won't let you exclude the files you don't want. In this situation, use a separate * with each filename ending:

      *.txt *mail *let

  Sometimes you need to match a particular group of characters. For example, you may want to list all filenames that begin with digits, or all filenames that begin with uppercase letters. Let's assume that you want to work with the files program. n , where n is a single-digit number. Use the filename:

      program.[0123456789]

  In other words, the wildcard [ character-list ] matches any single character that appears in the list. The character list can be any group of ASCII characters; however, if they are consecutive (e.g., A-Z, a-z, 0-9, or 3-5, for that matter), you can use a hyphen as shorthand for the range. For example, [a-zA-Z] means any alphabetic character.

  There is one exception to these wildcarding rules. Wildcards never match / , which is both the name of the filesystem root ( 1.19 ) and the character used to separate directory names in a path ( 1.21 ) .

  If you are new to computers, you probably will catch on to UNIX wildcarding quickly. If you have used any other computer system, you have to watch out for one very important detail. Virtually all computer systems except for UNIX consider a period ( . ) a special character within a filename. Many operating systems even require a filename to have a period in it. With these operating systems, a * does not match a period; you have to say *.* . Therefore, the equivalent of rm * does virtually nothing on most operating systems. Under UNIX, it is very dangerous: it means "delete all the files in the current directory, regardless of their name." You only want to give this command when you really mean it.

  But here's the exception to the exception. The shells and the ls command consider a . special if it is the first character of a filename. This is often used to hide initialization files and other files that you aren't normally concerned with; the ls command doesn't show these files unless you ask ( 16.11 ) for them. If a file's name begins with . , you always have to type the . explicitly. For example, .*rc matches all files whose names begin with . and end with rc . This is a common convention for the names of UNIX initialization files.

  Table 1-1 has a summary of the different sorts of wildcards available.
  Table 1.1: Shell Wildcard 	Matches
  ? 	Any single character
  * 	Any group of zero or more characters
  [ab] 	Either a or b
  [a-z] 	Any character between a and z, inclusive

  Wildcards can be used at any point or points within a path. Remember, wildcards only match names that already exist. You can't use them to create new files ( 9.4 ) - though some shells have curly braces ( {} ) ( 9.5 , 15.3 ) for doing that. Article 1.18 has more about how wildcards are handled.

  1.18 Who Handles Wildcards?

  Wildcards ( 1.16 ) are actually defined by the UNIX shells, rather than the UNIX filesystem. In theory, a new shell could define new wildcards, and consequently, we should discuss wildcarding when we discuss the shell. In practice, all UNIX shells (including ksh , bash , and other variants ( 1.8 ) ) honor the same wildcard conventions, and we don't expect to see anyone change the rules. (But different shells do different things when a wildcard doesn't match ( 15.4 ) .)

  You may see different wildcarding if you buy a special-purpose shell that emulates another operating system (for example, a shell that looks like DEC's DCL)-in this case, your shell will obey the other operating system's wildcard rules. But even in this case, operating system designers stick to a reasonably similar set of wildcard rules.

  The fact that the shell defines wildcards, rather than the filesystem itself or the program you're running, has some important implications for a few commands. Most of the time, a program never sees wildcards. For example, typing:

      %

      lpr *

  is exactly the same as typing:

      %

      lpr



      file1 file2 file3 file4 file5

  In this case everything works as expected. But there are other situations in which wildcards don't work at all. Assume you want to read some files from a tape, which requires the command tar x ( 20.4 ) , so you type the command tar x *.txt . Will you be happy or disappointed?

  You'll be disappointed - unless older versions of the files you want are already in your current directory ( 1.21 ) . The shell expands the wildcard *.txt , according to what's in the current directory, before it hands the completed command line over to tar for execution . All tar gets is a list of files. But you're probably not interested in the current directory; you probably want the wildcard * to be expanded on the tape, retrieving any *.txt files that the tape has.

  There's a way to pass wildcards to programs, without having them interpreted by the shell. Simply put \*.txt in quotes ( 8.14 ) . The quotes prevent the UNIX shell from expanding the wildcard, passing it to the command unchanged. Programs that can be used in this way (like uucp and rcp ( 1.33 ) ) know how to handle wildcards, obeying the same rules as the shell (in fact, these programs usually start a shell to interpret their arguments). You only need to make sure that the programs see the wildcards, that they aren't stripped by the shell before it passes the command line to the program. As a more general rule, you should be aware of when and why a wildcard gets expanded, and you should know how to make sure that wildcards are expanded at an appropriate time.

  NOTE: If your shell understands the {} characters ( 9.5 ) , you can use them because they can generate any string - not just filenames that already exist. You have to type the unique part of each name, but you only have to type the common part once. For example, to extract the files called project/wk9/summary , project/wk14/summary , and project/wk15/summary from a tar tape, you might use:

      %

      tar xv project/wk{9,14,15}/summary


      x project/wk9/summary, 3161 bytes, 7 tape blocks
      x project/wk14/summary, 878 bytes, 2 tape blocks
      x project/wk15/summary, 2268 bytes, 5 tape blocks

  Some versions of tar understand wildcards, but many don't. There is a clever workaround ( 20.9 ) .

  Calculating Available Disk Space

  You can calculate your system’s free disk space with df -h (the -h produces more user- friendly output):
  $ df -h Filesystem /dev/disk0s2 devfs
   Size   Used  Avail Capacity  Mounted on
  465Gi  387Gi   77Gi    84%    /
  182Ki  182Ki    0Bi   100%    /dev
  $ df -H Filesystem /dev/disk0s2 devfs
  Size   Used  Avail Capacity  Mounted on
  499G   416G    83G    84%    /
  186k   186k     0B   100%    /dev
  0Bi    0Bi    0Bi   100%    /net
  0Bi    0Bi    0Bi   100%    /home
  map -hosts
  map auto_home
  localhost:/F_S7P7m8KJ6Yohz2Qm0HM2  465Gi  465Gi    0Bi   100%    /Volumes/...
  Here’s the breakdown for the output from the command:
  • The first column (Filesystem) shows the Unix device name for the volume.
  • The second column (Size) shows the total disk size, and it’s followed by the amount of disk space used up (Used) and the amount that’s available (Avail).
  • The Capacity column shows the percentage of disk space used. Many devices are shown at 100% because they’re not regular disks, but special Unix devices. All you really need to pay attention to is your main hard drive (mine is /dev/disk0s2).
  • The Mounted on column displays the paths for the volumes mounted on your com­ puter. The / is the root of your filesystem (a volume that is named Macintosh HD by default). /dev contains files that correspond to hardware devices, and /.vol ex­ poses some internals of the OS X filesystem called HFS+ file ID.
  Notice that I have one hard disk on my system, /dev/disk0s2 (which is 465 GB in size, of which 387 GB are used and 77 GB are still available).
  The df command has a second, more friendly output that uses the more common divide-by-10 rule for calculating sizes, rather than the more mathematically precise divide-by-2 rule of the -h flag:
  0B     0B     0B   100%    /net
  0B     0B     0B   100%    /home
  map -hosts
  map auto_home
  localhost:/F_S7P7m8KJ6Yohz2Qm0HM2   499G   499G     0B   100%    /Volumes/...
   62 | Chapter 3: Exploring the Filesystem            
  These figures make more sense because I know that the hard disk mounted at /dev/ disk0s2 is actually 500 GB in size (though why it shows up as 499GB instead of 500GB is anyone’s guess!). You might prefer the more accurate -h output, but many people prefer -H since disk sizes are shown consistent with expectations.
  Yet another way to look at the data is to use the -m flag to have df show you 1 MB blocks, which rounds down all the tiny OS partitions like devfs and .vol to zero:
  $ df -m
  Filesystem 1M-blocks Used Available Capacity Mounted on /dev/disk0s2 476120 396514 79355 84% /
  devfs
  map -hosts
  map auto_home
  localhost:/F_S7P7m8KJ6Yohz2Qm0HM2    476120 476120
  Finally, in addition to raw disk space, another factor to keep track of with your OS X system is the number of inodes available. Inodes are the fundamental disk blocks that are grafted together to make space for all the different-sized files in your filesystem. A given disk in Unix has a finite number of files and directories that can be created, and even if there’s additional disk space available, running out of inodes effectively stops the disk from being used. This unusual event can happen if you have lots and lots (I’m talking millions and millions) of tiny files.
  The -i flag to df shows how you’re doing with inodes, providing details on how many inodes are allocated and available on each filesystem.
  Generally disks have plenty of unused inodes, so there’s nothing to worry about. For example, as you can see here, disk 0s2 has 20,315,203 available inodes:
  $ df -i
  Filesystem 512-blocks Used Available Capacity iused ifree %iused ... /dev/disk0s2 975093952 812060328 162521624 84% 101571539 20315203 83% ...
  devfs              363       363      0      100%       629
  0  100%  ...
  0  100%  ...
  0  100%  ...

  pwd
  cd
  "Print Working Directory". Shows the current location in the directory tree.
  cd
  cd, chdir
  "Change Directory". When typed all by itself, it returns you to your home directory.
  cd directory
  cd directory
  Change into the specified directory name. Example: cd /usr/src/linux
  cd ~
  "~" is an alias for your home directory. It can be used as a shortcut to your "home", or other directories relative to your home.
  cd ..
  cd..
  Move up one directory. For example, if you are in /home/vic and you type "cd ..", you will end up in /home.
  cd -
  Return to previous directory. An easy way to get back to your previous location!
  ls
  dir /w
  List all files in the current directory, in column format.
  ls directory
  dir directory
  List the files in the specified directory. Example:ls /var/log
  ls -l
  dir
  List files in "long" format, one file per line. This also shows you additional info about the file, such as ownership, permissions, date, and size.
  ls -a
  dir /a
  List all files, including "hidden" files. Hidden files are those files that begin with a ".", e.g. The .bash_history file in your home directory.
  ls -ld          
  directory
  A "long" list of "directory", but instead of showing the directory contents, show the directory's detailed information. For example, compare the output of the following two commands:
  ls -l /usr/bin
  ls -ld /usr/bin
  ls /usr/bin/d*
  dir d*.*
  List all files whose names begin with the letter "d" in the /usr/bin directory.

### VO 300w
  ( download rails src)

  See: https://developer.apple.com/library/mac/documentation/FileManagement/Conceptual/FileSystemProgrammingGuide/FileSystemOverview/FileSystemOverview.html

  $ man hier

  pwd
  "Print Working Directory". Shows the current location in the directory tree.

  cd
  Changes the working directory to your home directory.

  cd cd -
  Changes the working directory to the previous working directory.

  cd ~username
  Changes the working directory to the home directory of username. For example, cd ~bob changes the directory to the home directory of user bob.

  An absolute pathname begins with the root directory
  a relative pathname starts from the working directory
  ./
  ../

  cd directory
  Change into the specified directory name. Example: cd /usr/src/linux

  cd ..
  Move up one directory. For example, if you are in /home/vic and you type "cd ..", you will end up in /home.

  ls List all files in the current directory, in column format.

  ls directory
  List the files in the specified directory. Example:ls /var/log

  ls -l
  List files in "long" format, one file per line.
                      
  ls -a

  List all files, including "hidden" files. Hidden files are those files that begin with a ".", e.g. The .bash_history file in your home directory.

  ls -ld directory   

  A "long" list of "directory", but instead of showing the directory contents, show the directory's detailed information. For example, compare the output of the following two commands:

  ls -l /usr/bin
  ls -ld /usr/bin
              
  ls -lR recursive
                       
  *tree

  -a     All files are printed.
  -d     List directories only.                  
  -f     Prints the full path prefix for each file.
  -x     Stay on the current file-system only.  Ala find -xdev.
  -L level Max display depth of the directory tree.
  -P pattern
  List only those files that match the wild-card pattern.
  -I pattern
  Do not list those files that match the wild-card pattern.
  -r     Sort the output in reverse alphabetic order.
  -t     Sort the output by last modification time instead of alphabetically.

  *du/df

  You can find the size of a file with the du (disk usage) command:

  $ du Documents/Outline.doc
  300     Documents/Outline.doc

  The size is reported in kilobytes, so Outline.doc is 300 KB in size.

  If you give du the name of a directory, it calculates the sizes of everything inside that directory, including any subdirectories and their contents:


