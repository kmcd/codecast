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
  
# File modification 33
## What is it?
## Why is it useful?
## You will be able to ...
## Examples
  *touch/cp/mv/rm

  (create day,month,year files & directories)

  cd tmp/
  mkdir -p test/dir-{00{1..9},0{10..99},100}
  tree test
  touch test/dir-{00{1..9},0{10..99},100}/file-{A..Z}
  tree test
  cp -R test test_1
  cp -R test test.bak
  rm test.bak
  rm -Rf test.bak
  mv test test.bak

  *redirection

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt

  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  save the output of a command to a file, instead of displaying it to the screen.

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  { date; who; ls; } > log

  <
  Input from a file

  &> ~/tmp/wget.log
  redirect all to file

  &> /dev/null
  ignore all output (redirect all to null device)

  *change file attritutes

  -rwx------
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.

  -rw-r--r--
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.

  -rwxr-xr-x
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.

  -rw-rw----
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.

  Lrwxrwxrwx
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.

  drwxrwx---
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.

  drwxr-x---
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  *change file mode

  u Short for user but means the file or directory owner.
  g Group owner.
  o Short for others but means world.
  a Short for all; the combination of u, g, and o.

  If no character is specified, all will be assumed.

  The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.

  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.

  *change file owner

  chown [owner][:[group]]
  chown -R

  SELF DIRECTED:
  * chmod octal

  find . -perm -u=x -name "*.*"

## File modification 2m

  CRUD

  $ touch
  $ echo
  $ rm
  $ mkdir
  $ cp *-dt-*-nt-~
  $ cp foo.{txt,md}
  $ ln
  $ chown (permissions)
  $ chmod
  $ touch
  $ tar / gzip

  cat chap1 chap2 chap3 > book

  Redirection

  Function 	csh 	sh
  Send stdout to file 	prog > file 	prog > file
  Send stderr to file 		prog 2> file
  Send stdout and stderr to file 	prog >& file 	prog > file 2>&1
  Take stdin from file 	prog < file 	prog < file
  Send stdout to end of file 	prog >> file 	prog >> file
  Send stderr to end of file 		prog 2>> file
  Send stdout and stderr to end of file 	prog >>& file 	prog >> file 2>&1
  Read stdin from keyboard until c (see article 8.18 ) 	prog << c 	prog << c
  Pipe stdout to prog2 	prog | prog2 	prog | prog2
  Pipe stdout and stderr to prog2 	prog |& prog2 	prog 2>&1 | prog2

  { date; who; ls; } > log

  If you're running a program and you want to send its output to a file - but you want to see the output on your screen, too, so you can stop the program if something goes wrong - you can use tee . The tee program reads its standard input and writes it to one or more files. (The CD-ROM has the GNU version.)

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  There are times when it is useful to save the output of a command to a file, instead of displaying it to the screen. For example, if we want to create a file that lists all of the MP3 files in a directory, we can do something like this, using the ">" redirection character:

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt

  A similar command can be written so that instead of creating a new file called mp3files.txt,
  we can append to the end of the original file:
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  Reading, Writing, and Executing

  Access rights to files and directories are defined in terms of read access, write access, and execution access. If we look at the output of the ls com- mand, we can get some clue as to how this is implemented:
  [me@linuxbox ~]$ > foo.txt
  [me@linuxbox ~]$ ls -l foo.txt
  -rw-rw-r-- 1 me me 0 2012-03-06 14:52 foo.txt
     The first 10 characters of the listing are the file attributes (see Figure 9-1). The first of these characters is the file type. Table 9-1 lists the file types you are most likely to see (there are other, less common types too).
  The remaining nine characters of the file attributes, called the file mode, represent the read, write, and execute permissions for the file’s owner, the file’s group owner, and everybody else.
  Figure 9-1: Breakdow<!--  -->n of file attributes
   Permissions 79
  When set, the r, w, and x mode attributes have certain effects on files and directories, as shown in Table 9-2.
  Table 9-1: File Types
  Attribute File Type
  - A regular file.
  d A directory.
  l A symbolic link. Notice that with symbolic links, the remaining file attributes are always rwxrwxrwx and are dummy values. The real file attributes are those of the file the symbolic link points to.
  c A character special file. This file type refers to a device that handles data as a stream of bytes, such as a terminal or modem.
  b A block special file. This file type refers to a device that handles data in blocks, such as a hard drive or CD-ROM drive.

  Table 9-2: Permission Attributes
   Attribute
  Files
  Allows a file to be opened and read.
  Allows a file to be written to or trun- cated; however, this attribute does not allow files to be renamed or deleted. The ability to delete or rename files is determined by directory attributes.
  Allows a file to be treated as a pro- gram and executed. Program files writ- ten in scripting languages must also be set as readable to be executed.
  Directories
  Allows a directory’s contents to be listed if the execute attribute is also set.
  Allows files within a directory to be created, deleted, and renamed if the execute attribute is also set.
  Allows a directory to be entered; e.g.,
  cd directory.
  r
  w
  x
  Table 9-3: Permission Attribute Examples
           Table 9-3 shows some examples of file attribute settings.
   File Attributes
  -rwx------
  -rw-------
  Meaning
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.
  T
  able 9-3 (continued )
  File Attributes
  -rw-r--r--
  -rwxr-xr-x
  -rw-rw----
  Lrwxrwxrwx
  drwxrwx---
  drwxr-x---
  Meaning
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  chmod—Change File Mode

  To change the mode (permissions) of a file or directory, the chmod com- mand is used. Be aware that only the file’s owner or the superuser can change the mode of a file or directory. chmod supports two distinct ways of specifying mode changes: octal number representation and symbolic repres- entation. We will cover octal number representation first.

  Symbolic Representation
  chmod also supports a symbolic notation for specifying file modes. Symbolic notation is divided into three parts: whom the change will affect, which opera- tion will be performed, and which permission will be set. To specify who is affected, a combination of the characters u, g, o, and a is used, as shown in Table 9-5.
  Table 9-5: chmod Symbolic Notation

  Symbol
  u g o a
  Meaning
  Short for user but means the file or directory owner. Group owner.
  Short for others but means world.
  Short for all; the combination of u, g, and o.
          If no character is specified, all will be assumed. The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.
  Permissions are specified with the r, w, and x characters. Table 9-6 lists some examples of symbolic notation.
  Table 9-6: chmod Symbolic Notation Examples
  Notation Meaning
  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.
  (continued )

  Permissions 83
  Table 9-6 (continued )
  Notation
  o-rw go=rw
  u+x,go=rx
  Meaning
  Remove the read and write permissions from anyone besides the owner and group owner.
  Set the group owner and anyone besides the owner to have read and write permission. If either the group owner or world previously had execute permissions, remove them.
  Add execute permission for the owner and set the permissions for the group and others to read and execute. Multiple speci- fications may be separated by commas.
        84 Chapter 9

  Some people prefer to use octal notation; some folks really like the sym- bolic. Symbolic notation does offer the advantage of allowing you to set a single attribute without disturbing any of the others.
  Take a look at the chmod man page for more details and a list of options. A word of caution regarding the --recursive option: It acts on both files and directories, so it’s not as useful as one would hope because we rarely want files and directories to have the same permissions.

  chown—Change File Owner and Group

  The chown command is used to change the owner and group owner of a file or directory. Superuser privileges are required to use this command. The syntax of chown looks like this:

  chown [owner][:[group]] file...
  chown can change the file owner and/or the file group owner depending
  on the first argument of the command. Table 9-7 lists some examples.
  Table 9-7: chown Argument Examples
  Argument
  bob
  bob:users
  :admins
  bob:
  Results
  Changes the ownership of the file from its current owner to user bob.
  Changes the ownership of the file from its current owner to user bob and changes the file group owner to group users.
  Changes the group owner to the group admins. The file owner is unchanged.
  Change the file owner from the current owner to user bob and changes the group owner to the login group of user bob.

  Undo with sudo

  e.g. PostgreSQL user
  e.g. shell script


### VO 300w
  *touch/cp/mv/rm
  
  (create day,month,year files & directories)

  we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files

  $ mkdir -p playground/dir-{00{1..9},0{10..99},100}
  $ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  *redirection

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  save the output of a command to a file, instead of displaying it to the screen.

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  { date; who; ls; } > log
  
  < 
  Input from a file
  
  &> ~/tmp/wget.log
  redirect all to file

  &> /dev/null
  ignore all output (redirect all to null device)
  
  *change file attritutes

  -rwx------
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.

  -rw-r--r--
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.

  -rwxr-xr-x
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.

  -rw-rw----
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.

  Lrwxrwxrwx
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.

  drwxrwx---
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.

  drwxr-x---
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  *change file mode

  u Short for user but means the file or directory owner.
  g Group owner.
  o Short for others but means world.
  a Short for all; the combination of u, g, and o.

  If no character is specified, all will be assumed.

  The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.

  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.

  *change file owner

  chown [owner][:[group]]
  chown -R
                          
  SELF DIRECTED:
  * chmod octal
  
  find . -perm -u=x -name "*.*"

## File modification 2m

  CRUD

  $ touch
  $ echo
  $ rm
  $ mkdir
  $ cp *-dt-*-nt-~
  $ cp foo.{txt,md}
  $ ln
  $ chown (permissions)
  $ chmod
  $ touch
  $ tar / gzip

  cat chap1 chap2 chap3 > book

  Redirection

  Function 	csh 	sh
  Send stdout to file 	prog > file 	prog > file
  Send stderr to file 		prog 2> file
  Send stdout and stderr to file 	prog >& file 	prog > file 2>&1
  Take stdin from file 	prog < file 	prog < file
  Send stdout to end of file 	prog >> file 	prog >> file
  Send stderr to end of file 		prog 2>> file
  Send stdout and stderr to end of file 	prog >>& file 	prog >> file 2>&1
  Read stdin from keyboard until c (see article 8.18 ) 	prog << c 	prog << c
  Pipe stdout to prog2 	prog | prog2 	prog | prog2
  Pipe stdout and stderr to prog2 	prog |& prog2 	prog 2>&1 | prog2

  { date; who; ls; } > log

  If you're running a program and you want to send its output to a file - but you want to see the output on your screen, too, so you can stop the program if something goes wrong - you can use tee . The tee program reads its standard input and writes it to one or more files. (The CD-ROM has the GNU version.)

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  There are times when it is useful to save the output of a command to a file, instead of displaying it to the screen. For example, if we want to create a file that lists all of the MP3 files in a directory, we can do something like this, using the ">" redirection character:

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt

  A similar command can be written so that instead of creating a new file called mp3files.txt,
  we can append to the end of the original file:
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  Reading, Writing, and Executing

  Access rights to files and directories are defined in terms of read access, write access, and execution access. If we look at the output of the ls com- mand, we can get some clue as to how this is implemented:
  [me@linuxbox ~]$ > foo.txt
  [me@linuxbox ~]$ ls -l foo.txt
  -rw-rw-r-- 1 me me 0 2012-03-06 14:52 foo.txt
     The first 10 characters of the listing are the file attributes (see Figure 9-1). The first of these characters is the file type. Table 9-1 lists the file types you are most likely to see (there are other, less common types too).
  The remaining nine characters of the file attributes, called the file mode, represent the read, write, and execute permissions for the file’s owner, the file’s group owner, and everybody else.
  Figure 9-1: Breakdow<!--  -->n of file attributes
   Permissions 79
  When set, the r, w, and x mode attributes have certain effects on files and directories, as shown in Table 9-2.
  Table 9-1: File Types
  Attribute File Type
  - A regular file.
  d A directory.
  l A symbolic link. Notice that with symbolic links, the remaining file attributes are always rwxrwxrwx and are dummy values. The real file attributes are those of the file the symbolic link points to.
  c A character special file. This file type refers to a device that handles data as a stream of bytes, such as a terminal or modem.
  b A block special file. This file type refers to a device that handles data in blocks, such as a hard drive or CD-ROM drive.

  Table 9-2: Permission Attributes
   Attribute
  Files
  Allows a file to be opened and read.
  Allows a file to be written to or trun- cated; however, this attribute does not allow files to be renamed or deleted. The ability to delete or rename files is determined by directory attributes.
  Allows a file to be treated as a pro- gram and executed. Program files writ- ten in scripting languages must also be set as readable to be executed.
  Directories
  Allows a directory’s contents to be listed if the execute attribute is also set.
  Allows files within a directory to be created, deleted, and renamed if the execute attribute is also set.
  Allows a directory to be entered; e.g.,
  cd directory.
  r
  w
  x
  Table 9-3: Permission Attribute Examples
           Table 9-3 shows some examples of file attribute settings.
   File Attributes
  -rwx------
  -rw-------
  Meaning
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.
  T
  able 9-3 (continued )
  File Attributes
  -rw-r--r--
  -rwxr-xr-x
  -rw-rw----
  Lrwxrwxrwx
  drwxrwx---
  drwxr-x---
  Meaning
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  chmod—Change File Mode

  To change the mode (permissions) of a file or directory, the chmod com- mand is used. Be aware that only the file’s owner or the superuser can change the mode of a file or directory. chmod supports two distinct ways of specifying mode changes: octal number representation and symbolic repres- entation. We will cover octal number representation first.

  Symbolic Representation
  chmod also supports a symbolic notation for specifying file modes. Symbolic notation is divided into three parts: whom the change will affect, which opera- tion will be performed, and which permission will be set. To specify who is affected, a combination of the characters u, g, o, and a is used, as shown in Table 9-5.
  Table 9-5: chmod Symbolic Notation

  Symbol
  u g o a
  Meaning
  Short for user but means the file or directory owner. Group owner.
  Short for others but means world.
  Short for all; the combination of u, g, and o.
          If no character is specified, all will be assumed. The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.
  Permissions are specified with the r, w, and x characters. Table 9-6 lists some examples of symbolic notation.
  Table 9-6: chmod Symbolic Notation Examples
  Notation Meaning
  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.
  (continued )

  Permissions 83
  Table 9-6 (continued )
  Notation
  o-rw go=rw
  u+x,go=rx
  Meaning
  Remove the read and write permissions from anyone besides the owner and group owner.
  Set the group owner and anyone besides the owner to have read and write permission. If either the group owner or world previously had execute permissions, remove them.
  Add execute permission for the owner and set the permissions for the group and others to read and execute. Multiple speci- fications may be separated by commas.
        84 Chapter 9

  Some people prefer to use octal notation; some folks really like the sym- bolic. Symbolic notation does offer the advantage of allowing you to set a single attribute without disturbing any of the others.
  Take a look at the chmod man page for more details and a list of options. A word of caution regarding the --recursive option: It acts on both files and directories, so it’s not as useful as one would hope because we rarely want files and directories to have the same permissions.

  chown—Change File Owner and Group

  The chown command is used to change the owner and group owner of a file or directory. Superuser privileges are required to use this command. The syntax of chown looks like this:

  chown [owner][:[group]] file...
  chown can change the file owner and/or the file group owner depending
  on the first argument of the command. Table 9-7 lists some examples.
  Table 9-7: chown Argument Examples
  Argument
  bob
  bob:users
  :admins
  bob:
  Results
  Changes the ownership of the file from its current owner to user bob.
  Changes the ownership of the file from its current owner to user bob and changes the file group owner to group users.
  Changes the group owner to the group admins. The file owner is unchanged.
  Change the file owner from the current owner to user bob and changes the group owner to the login group of user bob.

  Undo with sudo

  e.g. PostgreSQL user
  e.g. shell script


### VO 300w
  *touch/cp/mv/rm
  
  (create day,month,year files & directories)

  we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files

  $ mkdir -p playground/dir-{00{1..9},0{10..99},100}
  $ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  *redirection

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  save the output of a command to a file, instead of displaying it to the screen.

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  { date; who; ls; } > log
  
  < 
  Input from a file
  
  &> ~/tmp/wget.log
  redirect all to file

  &> /dev/null
  ignore all output (redirect all to null device)
  
  *change file attritutes

  -rwx------
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.

  -rw-r--r--
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.

  -rwxr-xr-x
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.

  -rw-rw----
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.

  Lrwxrwxrwx
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.

  drwxrwx---
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.

  drwxr-x---
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  *change file mode

  u Short for user but means the file or directory owner.
  g Group owner.
  o Short for others but means world.
  a Short for all; the combination of u, g, and o.

  If no character is specified, all will be assumed.

  The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.

  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.

  *change file owner

  chown [owner][:[group]]
  chown -R
                          
  SELF DIRECTED:
  * chmod octal
  
  find . -perm -u=x -name "*.*"


## File modification 2m

  CRUD

  $ touch
  $ echo
  $ rm
  $ mkdir
  $ cp *-dt-*-nt-~
  $ cp foo.{txt,md}
  $ ln
  $ chown (permissions)
  $ chmod
  $ touch
  $ tar / gzip

  cat chap1 chap2 chap3 > book

  Redirection

  Function 	csh 	sh
  Send stdout to file 	prog > file 	prog > file
  Send stderr to file 		prog 2> file
  Send stdout and stderr to file 	prog >& file 	prog > file 2>&1
  Take stdin from file 	prog < file 	prog < file
  Send stdout to end of file 	prog >> file 	prog >> file
  Send stderr to end of file 		prog 2>> file
  Send stdout and stderr to end of file 	prog >>& file 	prog >> file 2>&1
  Read stdin from keyboard until c (see article 8.18 ) 	prog << c 	prog << c
  Pipe stdout to prog2 	prog | prog2 	prog | prog2
  Pipe stdout and stderr to prog2 	prog |& prog2 	prog 2>&1 | prog2

  { date; who; ls; } > log

  If you're running a program and you want to send its output to a file - but you want to see the output on your screen, too, so you can stop the program if something goes wrong - you can use tee . The tee program reads its standard input and writes it to one or more files. (The CD-ROM has the GNU version.)

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  There are times when it is useful to save the output of a command to a file, instead of displaying it to the screen. For example, if we want to create a file that lists all of the MP3 files in a directory, we can do something like this, using the ">" redirection character:

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt

  A similar command can be written so that instead of creating a new file called mp3files.txt,
  we can append to the end of the original file:
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  Reading, Writing, and Executing

  Access rights to files and directories are defined in terms of read access, write access, and execution access. If we look at the output of the ls com- mand, we can get some clue as to how this is implemented:
  [me@linuxbox ~]$ > foo.txt
  [me@linuxbox ~]$ ls -l foo.txt
  -rw-rw-r-- 1 me me 0 2012-03-06 14:52 foo.txt
     The first 10 characters of the listing are the file attributes (see Figure 9-1). The first of these characters is the file type. Table 9-1 lists the file types you are most likely to see (there are other, less common types too).
  The remaining nine characters of the file attributes, called the file mode, represent the read, write, and execute permissions for the file’s owner, the file’s group owner, and everybody else.
  Figure 9-1: Breakdow<!--  -->n of file attributes
   Permissions 79
  When set, the r, w, and x mode attributes have certain effects on files and directories, as shown in Table 9-2.
  Table 9-1: File Types
  Attribute File Type
  - A regular file.
  d A directory.
  l A symbolic link. Notice that with symbolic links, the remaining file attributes are always rwxrwxrwx and are dummy values. The real file attributes are those of the file the symbolic link points to.
  c A character special file. This file type refers to a device that handles data as a stream of bytes, such as a terminal or modem.
  b A block special file. This file type refers to a device that handles data in blocks, such as a hard drive or CD-ROM drive.

  Table 9-2: Permission Attributes
   Attribute
  Files
  Allows a file to be opened and read.
  Allows a file to be written to or trun- cated; however, this attribute does not allow files to be renamed or deleted. The ability to delete or rename files is determined by directory attributes.
  Allows a file to be treated as a pro- gram and executed. Program files writ- ten in scripting languages must also be set as readable to be executed.
  Directories
  Allows a directory’s contents to be listed if the execute attribute is also set.
  Allows files within a directory to be created, deleted, and renamed if the execute attribute is also set.
  Allows a directory to be entered; e.g.,
  cd directory.
  r
  w
  x
  Table 9-3: Permission Attribute Examples
           Table 9-3 shows some examples of file attribute settings.
   File Attributes
  -rwx------
  -rw-------
  Meaning
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.
  T
  able 9-3 (continued )
  File Attributes
  -rw-r--r--
  -rwxr-xr-x
  -rw-rw----
  Lrwxrwxrwx
  drwxrwx---
  drwxr-x---
  Meaning
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  chmod—Change File Mode

  To change the mode (permissions) of a file or directory, the chmod com- mand is used. Be aware that only the file’s owner or the superuser can change the mode of a file or directory. chmod supports two distinct ways of specifying mode changes: octal number representation and symbolic repres- entation. We will cover octal number representation first.

  Symbolic Representation
  chmod also supports a symbolic notation for specifying file modes. Symbolic notation is divided into three parts: whom the change will affect, which opera- tion will be performed, and which permission will be set. To specify who is affected, a combination of the characters u, g, o, and a is used, as shown in Table 9-5.
  Table 9-5: chmod Symbolic Notation

  Symbol
  u g o a
  Meaning
  Short for user but means the file or directory owner. Group owner.
  Short for others but means world.
  Short for all; the combination of u, g, and o.
          If no character is specified, all will be assumed. The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.
  Permissions are specified with the r, w, and x characters. Table 9-6 lists some examples of symbolic notation.
  Table 9-6: chmod Symbolic Notation Examples
  Notation Meaning
  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.
  (continued )

  Permissions 83
  Table 9-6 (continued )
  Notation
  o-rw go=rw
  u+x,go=rx
  Meaning
  Remove the read and write permissions from anyone besides the owner and group owner.
  Set the group owner and anyone besides the owner to have read and write permission. If either the group owner or world previously had execute permissions, remove them.
  Add execute permission for the owner and set the permissions for the group and others to read and execute. Multiple speci- fications may be separated by commas.
        84 Chapter 9

  Some people prefer to use octal notation; some folks really like the sym- bolic. Symbolic notation does offer the advantage of allowing you to set a single attribute without disturbing any of the others.
  Take a look at the chmod man page for more details and a list of options. A word of caution regarding the --recursive option: It acts on both files and directories, so it’s not as useful as one would hope because we rarely want files and directories to have the same permissions.

  chown—Change File Owner and Group

  The chown command is used to change the owner and group owner of a file or directory. Superuser privileges are required to use this command. The syntax of chown looks like this:

  chown [owner][:[group]] file...
  chown can change the file owner and/or the file group owner depending
  on the first argument of the command. Table 9-7 lists some examples.
  Table 9-7: chown Argument Examples
  Argument
  bob
  bob:users
  :admins
  bob:
  Results
  Changes the ownership of the file from its current owner to user bob.
  Changes the ownership of the file from its current owner to user bob and changes the file group owner to group users.
  Changes the group owner to the group admins. The file owner is unchanged.
  Change the file owner from the current owner to user bob and changes the group owner to the login group of user bob.

  Undo with sudo

  e.g. PostgreSQL user
  e.g. shell script


### VO 300w
  *touch/cp/mv/rm
  
  (create day,month,year files & directories)

  we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files

  $ mkdir -p playground/dir-{00{1..9},0{10..99},100}
  $ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  *redirection

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  save the output of a command to a file, instead of displaying it to the screen.

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  { date; who; ls; } > log
  
  < 
  Input from a file
  
  &> ~/tmp/wget.log
  redirect all to file

  &> /dev/null
  ignore all output (redirect all to null device)
  
  *change file attritutes

  -rwx------
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.

  -rw-r--r--
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.

  -rwxr-xr-x
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.

  -rw-rw----
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.

  Lrwxrwxrwx
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.

  drwxrwx---
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.

  drwxr-x---
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  *change file mode

  u Short for user but means the file or directory owner.
  g Group owner.
  o Short for others but means world.
  a Short for all; the combination of u, g, and o.

  If no character is specified, all will be assumed.

  The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.

  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.

  *change file owner

  chown [owner][:[group]]
  chown -R
                          
  SELF DIRECTED:
  * chmod octal
  
  find . -perm -u=x -name "*.*"


## File modification 2m

  CRUD

  $ touch
  $ echo
  $ rm
  $ mkdir
  $ cp *-dt-*-nt-~
  $ cp foo.{txt,md}
  $ ln
  $ chown (permissions)
  $ chmod
  $ touch
  $ tar / gzip

  cat chap1 chap2 chap3 > book

  Redirection

  Function 	csh 	sh
  Send stdout to file 	prog > file 	prog > file
  Send stderr to file 		prog 2> file
  Send stdout and stderr to file 	prog >& file 	prog > file 2>&1
  Take stdin from file 	prog < file 	prog < file
  Send stdout to end of file 	prog >> file 	prog >> file
  Send stderr to end of file 		prog 2>> file
  Send stdout and stderr to end of file 	prog >>& file 	prog >> file 2>&1
  Read stdin from keyboard until c (see article 8.18 ) 	prog << c 	prog << c
  Pipe stdout to prog2 	prog | prog2 	prog | prog2
  Pipe stdout and stderr to prog2 	prog |& prog2 	prog 2>&1 | prog2

  { date; who; ls; } > log

  If you're running a program and you want to send its output to a file - but you want to see the output on your screen, too, so you can stop the program if something goes wrong - you can use tee . The tee program reads its standard input and writes it to one or more files. (The CD-ROM has the GNU version.)

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  There are times when it is useful to save the output of a command to a file, instead of displaying it to the screen. For example, if we want to create a file that lists all of the MP3 files in a directory, we can do something like this, using the ">" redirection character:

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt

  A similar command can be written so that instead of creating a new file called mp3files.txt,
  we can append to the end of the original file:
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  Reading, Writing, and Executing

  Access rights to files and directories are defined in terms of read access, write access, and execution access. If we look at the output of the ls com- mand, we can get some clue as to how this is implemented:
  [me@linuxbox ~]$ > foo.txt
  [me@linuxbox ~]$ ls -l foo.txt
  -rw-rw-r-- 1 me me 0 2012-03-06 14:52 foo.txt
     The first 10 characters of the listing are the file attributes (see Figure 9-1). The first of these characters is the file type. Table 9-1 lists the file types you are most likely to see (there are other, less common types too).
  The remaining nine characters of the file attributes, called the file mode, represent the read, write, and execute permissions for the file’s owner, the file’s group owner, and everybody else.
  Figure 9-1: Breakdow<!--  -->n of file attributes
   Permissions 79
  When set, the r, w, and x mode attributes have certain effects on files and directories, as shown in Table 9-2.
  Table 9-1: File Types
  Attribute File Type
  - A regular file.
  d A directory.
  l A symbolic link. Notice that with symbolic links, the remaining file attributes are always rwxrwxrwx and are dummy values. The real file attributes are those of the file the symbolic link points to.
  c A character special file. This file type refers to a device that handles data as a stream of bytes, such as a terminal or modem.
  b A block special file. This file type refers to a device that handles data in blocks, such as a hard drive or CD-ROM drive.

  Table 9-2: Permission Attributes
   Attribute
  Files
  Allows a file to be opened and read.
  Allows a file to be written to or trun- cated; however, this attribute does not allow files to be renamed or deleted. The ability to delete or rename files is determined by directory attributes.
  Allows a file to be treated as a pro- gram and executed. Program files writ- ten in scripting languages must also be set as readable to be executed.
  Directories
  Allows a directory’s contents to be listed if the execute attribute is also set.
  Allows files within a directory to be created, deleted, and renamed if the execute attribute is also set.
  Allows a directory to be entered; e.g.,
  cd directory.
  r
  w
  x
  Table 9-3: Permission Attribute Examples
           Table 9-3 shows some examples of file attribute settings.
   File Attributes
  -rwx------
  -rw-------
  Meaning
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.
  T
  able 9-3 (continued )
  File Attributes
  -rw-r--r--
  -rwxr-xr-x
  -rw-rw----
  Lrwxrwxrwx
  drwxrwx---
  drwxr-x---
  Meaning
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  chmod—Change File Mode

  To change the mode (permissions) of a file or directory, the chmod com- mand is used. Be aware that only the file’s owner or the superuser can change the mode of a file or directory. chmod supports two distinct ways of specifying mode changes: octal number representation and symbolic repres- entation. We will cover octal number representation first.

  Symbolic Representation
  chmod also supports a symbolic notation for specifying file modes. Symbolic notation is divided into three parts: whom the change will affect, which opera- tion will be performed, and which permission will be set. To specify who is affected, a combination of the characters u, g, o, and a is used, as shown in Table 9-5.
  Table 9-5: chmod Symbolic Notation

  Symbol
  u g o a
  Meaning
  Short for user but means the file or directory owner. Group owner.
  Short for others but means world.
  Short for all; the combination of u, g, and o.
          If no character is specified, all will be assumed. The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.
  Permissions are specified with the r, w, and x characters. Table 9-6 lists some examples of symbolic notation.
  Table 9-6: chmod Symbolic Notation Examples
  Notation Meaning
  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.
  (continued )

  Permissions 83
  Table 9-6 (continued )
  Notation
  o-rw go=rw
  u+x,go=rx
  Meaning
  Remove the read and write permissions from anyone besides the owner and group owner.
  Set the group owner and anyone besides the owner to have read and write permission. If either the group owner or world previously had execute permissions, remove them.
  Add execute permission for the owner and set the permissions for the group and others to read and execute. Multiple speci- fications may be separated by commas.
        84 Chapter 9

  Some people prefer to use octal notation; some folks really like the sym- bolic. Symbolic notation does offer the advantage of allowing you to set a single attribute without disturbing any of the others.
  Take a look at the chmod man page for more details and a list of options. A word of caution regarding the --recursive option: It acts on both files and directories, so it’s not as useful as one would hope because we rarely want files and directories to have the same permissions.

  chown—Change File Owner and Group

  The chown command is used to change the owner and group owner of a file or directory. Superuser privileges are required to use this command. The syntax of chown looks like this:

  chown [owner][:[group]] file...
  chown can change the file owner and/or the file group owner depending
  on the first argument of the command. Table 9-7 lists some examples.
  Table 9-7: chown Argument Examples
  Argument
  bob
  bob:users
  :admins
  bob:
  Results
  Changes the ownership of the file from its current owner to user bob.
  Changes the ownership of the file from its current owner to user bob and changes the file group owner to group users.
  Changes the group owner to the group admins. The file owner is unchanged.
  Change the file owner from the current owner to user bob and changes the group owner to the login group of user bob.

  Undo with sudo

  e.g. PostgreSQL user
  e.g. shell script


### VO 300w
  *touch/cp/mv/rm
  
  (create day,month,year files & directories)

  we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files

  $ mkdir -p playground/dir-{00{1..9},0{10..99},100}
  $ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  *redirection

  >
  Redirect output of a command into a new file. If the file already exists, over-write it. Example: ls > myfiles.txt
  
  >>
  Redirect the output of a command onto the end of an existing file. Example: echo "Mary 555-1234" >> phonenumbers.txt

  save the output of a command to a file, instead of displaying it to the screen.

  ls -l /home/vic/MP3/*.mp3 > mp3files.txt
  ls -l /home/vic/extraMP3s/*.mp3 >> mp3files.txt

  { date; who; ls; } > log
  
  < 
  Input from a file
  
  &> ~/tmp/wget.log
  redirect all to file

  &> /dev/null
  ignore all output (redirect all to null device)
  
  *change file attritutes

  -rwx------
  A regular file that is readable, writable, and executable by the file’s owner. No one else has any access.

  -rw-r--r--
  A regular file that is readable and writable by the file’s owner. Members of the file’s owner group may read the file. The file is world readable.

  -rwxr-xr-x
  A regular file that is readable, writable, and executable by the file’s owner. The file may be read and executed by everybody else.

  -rw-rw----
  A regular file that is readable and writable by the file’s owner and members of the file’s owner group only.

  Lrwxrwxrwx
  A symbolic link. All symbolic links have "dummy" permis- sions. The real permissions are kept with the actual file pointed to by the symbolic link.

  drwxrwx---
  A directory. The owner and the members of the owner group may enter the directory and create, rename, and remove files within the directory.

  drwxr-x---
  A directory. The owner may enter the directory and create, rename, and delete files within the directory. Members of the owner group may enter the directory but cannot create, delete, or rename files.

  *change file mode

  u Short for user but means the file or directory owner.
  g Group owner.
  o Short for others but means world.
  a Short for all; the combination of u, g, and o.

  If no character is specified, all will be assumed.

  The operation may be
  a + indicating that a permission is to be added, a - indicating that a permis- sion is to be taken away, or a = indicating that only the specified permissions are to be applied and that all others are to be removed.

  u+x Add execute permission for the owner.
  u-x Remove execute permission from the owner.
  +x Add execute permission for the owner, group, and world. Equivalent to a+x.

  *change file owner

  chown [owner][:[group]]
  chown -R
                          
  SELF DIRECTED:
  * chmod octal
  
  find . -perm -u=x -name "*.*"


