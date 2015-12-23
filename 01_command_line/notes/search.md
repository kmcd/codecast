
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
  
# File search L 25
## What is it?
  find is one of UNIX's most useful and important utilities. It finds files that match a given set of parameters, ranging from the file's name to its modification date.

## Why is it useful?
## You will be able to ...
## Examples
  *find by name

  find path operators

  find .

  find . -name "active*"
  find . -name "active*rb"
  find . -name "Active*rb"
  find . -iname "Active*rb"

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
  
  find -name "*.o" -exec rm -f {} \;
  
  tells find to delete any files whose names end in .o .
  
  -ok
  
  Same as -exec , except that find prompts you for permission before executing command . This is a useful way to test find commands. See article 17.10 .
  
  MP3 audio files scattered all over your filesystem; move them where you want. For example:
  
  find . -name '*.mp3' -print -exec mv '{}' ~/songs \;
  find . -name '*.mp3' -print -exec rm '{}' ~/songs \;
  
  -delete

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
  ack -C 2 -n --with-filename validates_length_of activemodel/test/cases/validations_test.rb

  j activemodel/test/cases/validations_test.rb

  ack validate guides --pager='less -r'

  ack -ch '%r{'

## Points to note
## Recap
## Next steps
  mdfind, mdls, mdutil

## File search 4m

  15.7 Getting a List of Matching Files with grep -l

  Normally when you run grep ( 27.1 ) on a group of files, the output lists the filename along with the line containing the search pattern. Sometimes you want to know only the names of the files, and you don't care to know the line (or lines) that match. In this case, use the -l (lowercase letter "l") option to list only filenames where matches occur. For example, the command:

      %

      grep -l R5



      file1 file2 ...



      > r5.filelist

  searches the files for a line containing the string R5 , produces a list of those filenames, and stores the list in r5.filelist . (This list might represent the files containing Release 5 documentation of a particular product.) Because these Release 5 files can now be referenced by one list, you can treat them as a single entity and run various commands on them all at once:

  `...`

  %

  print `cat r5.filelist`

  Print only the Release 5 files

  %

  grep UNIX `cat r5.filelist`


  Search limited to the Release 5 files

  You don't have to create a file list, though. You can insert the output of a grep directly into a command line with command substitution. For example, to edit only the subset of files containing R5 , you would type:

      %

      vi `grep -l R5

      files

      `

  grep -l is also good for shell programs that need to check whether a file contains a particular string. The traditional way to do that test is by throwing away grep 's output and checking its exit status:

      if grep

      something somefile

       >/dev/null
      then ...

  If somefile is huge, though, grep has to search all of it. Adding the grep -l option saves time because grep can stop searching after it finds the first matching line.

  15.8 Getting a List of Non-Matching Files with grep -c

  You can use the grep ( 27.2 ) option -c to tell you how many occurrences of a pattern appear in a given file, so you can also use it to find files that don't contain a pattern (i.e., zero occurrences of the pattern). Let's say you're indexing a troff ( 43.13 ) document and you want to make a list of files that don't yet contain indexing macros. What you need to find are files with zero occurrences of the string .XX . The command:

      %

      grep -c "\.XX" chapter*

  might produce the following output:

      chapter1:10
      chapter2:27
      chapter3:19
      chapter4:0
      chapter5:39
         ...

  This is all well and good, but suppose you need to check index entries in hundreds of reference pages? Well, just filter grep 's output by piping it through another grep . The above command can be modified as follows:

      %

      grep -c "\.XX" chapter* | grep :0

  This results in the following output:

      chapter4:0

  Using sed ( 34.24 ) to truncate the :0 , you can save the output as a list of files. For example, here's a trick for creating a list of files that don't contain index macros:

      %

      grep -c "\.XX" * | sed -n s/:0//p > ../not_indexed.list

  The sed -n command prints only the lines that contain :0 ; it also strips the :0 from the output so that ../not_indexed.list contains a list of files, one per line. The .. pathname ( 1.21 ) puts the not_indexed.list file into the parent directory - this is one easy way to keep grep from searching that file, but may not be worth the bother.

  [To edit all files that need index macros added, you could type:

      %

      vi `grep -c "\.XX" * | sed -n s/:0//p`

  which is more obvious once you start using backquotes a lot. You can put this into a little script named vgrep with a couple of safety features added:

  "$@"

  #!/bin/sh
  case $# in
  0|1) echo "Usage: `basename $0` pattern file [files...]" 1>&2 ;;
  *)  pat="$1"; shift
      grep -c "$pat" "$@" | sed -n 's/:0$//p'
     ;;
  esac

  Then you can type, for example, vi `vgrep "\.XX" *` . -JP  ]

   15.2 Filename Wildcards in a Nutshell

  This section summarizes the wildcards that are used for filename expansion. The shells use the same basic wildcards, though csh , tcsh , ksh , and bash have some extensions. Unless otherwise noted, assume that wildcards are valid for all shells.

  *

      Match zero or more characters. For example, a* matches the files a , ab , abc , abc.d , and so on.
  ?

      Match exactly one character. For example, a? matches aa , ab , ac , etc.
  [12..a..z]

      Match any character listed in the brackets. For example, a[ab] matches aa or ab .
  [a-z]

      Match all characters between a and z. For example, a[0-9] matches a0 , a1 , and so on, up to a9 .
  [!ab..z]

      Match any character that does not appear within the brackets. For example, a[!0-9] doesn't match a0 , but does match aa . bash , Korn, and newer Bourne shells only.
  [^ab..z]

      Match any character that does not appear within the brackets. For example, a[^0-9] doesn't match a0 , but does match aa . tcsh only.
  {word1,word2...}

      Match word1 , word2 , etc. E.g., a_{dog,cat,horse} matches the filenames a_dog , a_cat , and a_horse . bash and C shells only. These ( 9.5 ) actually aren't filename-matching wildcards. They expand any string, including filenames that don't exist yet, email addresses, and more.
  ?(abc)

      Match zero or one instance of abc . For example, x?(abc)x matches xx or xabcx . Korn shell only.
  *(abc)

      Match zero or more instances of abc . For example, x*(abc)x matches xx , xabcx , xabcabcx , etc. Korn shell only.
  +(abc)

      Match one or more instances of abc . For example, x+(abc)x matches xabcx , xabcabcx , etc. Korn shell only.
  !(abc)

      Match anything that doesn't contain abc . For example, x!(abc)x doesn't match xabcx or xabcabcx , but does match practically anything else that begins or ends with x . Korn shell only.
  ^ pat

      Match any name that doesn't match pat . pat must include at least one of the wildcards * , ? and [] . To match all except a single name, here's a trick: put brackets around one character. For instance, you can match all except abc with ^ab[c] . tcsh only. (For other shells, see nom ( 15.9 ) .)

  Note: wildcards do not match files whose names begin with a dot ( . ), like .cshrc . [1] This prevents you from deleting (or otherwise mucking around with) these files by accident. To match those files, type the dot literally. For example, .[a-z]* matches anything whose name starts with a dot and a lowercase letter. Watch out for plain .* , though; it matches the directory entries . and .. (see article 15.5 for suggestions on solving that problem).

      [1] Setting the bash variable glob_dot_filenames includes these names in wildcard expansion.

  And a final note: many operating systems (VAX/VMS and DOS included) consider a file's name and extension to be different entities; therefore, you can't use a single wildcard to match both. What do I mean? Consider the file abc.def . Under DOS or VMS, to match this filename you'd need the wildcard expression *.* . The first * matches the name (the part before the period), and the second matches the extension (the part after the period). Although UNIX uses extensions, they aren't considered a separate part of the filename, so a single * will match the entire name.

   17.1 The find Command Is Great; The Problem Is Finding How to Use It

  find is one of UNIX's most useful and important utilities. It finds files that match a given set of parameters, ranging from the file's name to its modification date. In this chapter, we'll be looking at many of the things it can do. As an introduction, here's a quick summary of its features and operators:

      %

      find



      path operators

  where path is the directory in which find will begin to search and operators (or, in more customary jargon, options ) tell find which files you're interested in. The operators are:

  -name   filename

      Find files with the given filename . This is the most commonly used operator. filename may include wildcards ( 15.2 ) , but if it does, it must be quoted to prevent the shell from interpreting the wildcards. See article 17.4 .
  -perm   mode

      Find files with the given access mode ( 22.2 ) . You must give the access mode in octal ( 1.23 ) . See articles 17.10 and 17.15 .
  -type   c

      The files of the given type, specified by c . c is a one-digit code; for example, f for a plain file, b for a block special file, l for a symbolic link, etc. See article 17.13 .
  -user   name

      Find files belonging to user name . name may also be a user ID number ( 38.3 ) . See article 17.16 .
  -group   name

      Find files belonging to group name . name may also be a group ID number ( 38.3 ) . See article 17.16 .
  -size   n

      Find files that are n blocks long. A block equals 512 bytes. The notation + n says "find files that are over n  blocks long." The notation n c says "find files that are n  characters long." Can you guess what + n c means? See article 17.14 .
  -inum   n

      Find files with the inode number ( 1.22 ) n . See article 17.10 .
  -atime   n

      Find files that were accessed n days ago. + n means "find files that were accessed over n days ago" (i.e., not accessed in the last n days). - n means "find files that were accessed less than n days ago" (i.e., accessed in the last n days). See articles 17.5 and 17.7 .
  -mtime   n

      Similar to atime , except that it checks the time the file's contents were modified. See articles 17.5 and 17.7 .
  -ctime   n

      Similar to atime , except that it checks the time the inode ( 1.22 ) was last changed. "Changed" means that the file was modified or that one of its attributes (for example, its owner) was changed. See articles 17.5 and 17.7 .
  -newer   file

      Find files that have been modified more recently than the given file . See articles 17.8 and 17.9 .

  Of course, you often want to take some action on files that match several criteria. So we need some way to combine several operators:

  operator1   -a   operator2

      Find files that match both operator1 and operator2 . The -a isn't necessary; when two search parameters are juxtaposed, find assumes you want files that match both of them. See article 17.12 .
  operator1   -o   operator2

      Find files that match either operator1 or operator2 . See article 17.6 .
  !   operator

      Find all files that do not match the given operator . The ! performs a logical NOT operation. See article 17.6 .
  \(  expression  \)

      Logical precedence; in a complex expression, evaluate this part of the expression before the rest. See article 17.6 .

  Another group of operators tells find what action to take when it locates a file:

  -print

      Print the file's name on standard output. See articles 17.2 and 17.3 .
  -exec   command

      Execute command . To include the pathname of the file that's just been found in command , use the special symbol {} . command must end with a backslash followed by a semicolon ( \; ). For example:

          %

          find -name "*.o" -exec rm -f {} \;

      tells find to delete any files whose names end in .o . See article 17.10 .
  -ok   command

      Same as -exec , except that find prompts you for permission before executing command . This is a useful way to test find commands. See article 17.10 .

  A last word: find is one of the tools that vendors frequently fiddle with, adding (or deleting) a few operators that they like (or dislike). The operators listed above should be valid on virtually any system. If you check your system's manual page, you may find a few others.

   In general, most commands do not understand directory structures, and rely on the shell to expand wildcards ( 15.2 ) to directory names. That is, to delete all files whose names end with a .o in a group of directories, you could type:

  %

  rm *.o */*.o */*/*.o

  find . -print

   The first arguments to find are directory and file pathnames - in that example, a dot ( . ) is one name for the current directory ( 1.21 ) . The arguments after the pathnames always start with a minus sign ( - ) and tell find what to do once it finds a file. These are the search operators. In this case, the filename is printed. You can use the tilde ( ~ ) ( 14.11 ) supported by the C shell, as well as particular paths. For example:

   ls -l `find . -print`

    17.5 Searching for Old Files

  If you want to find a file that is seven days old, use the -mtime operator:

      %

      find . -mtime 7 -print

  An alternate way is to specify a range of times:

      %

      find . -mtime +6 -mtime -8 -print

  mtime is the last modified time of a file. If you want to look for files that have not been used, check the access time with the -atime argument. A command to list all files that have not been read in 30 days or more is:

      %

      find . -type f -atime +30 -print

  It is difficult to find directories that have not been accessed because the find command modifies the directory's access time.

  There is another time associated with each file, called the ctime , the inode ( 1.22 ) change time. Access it with the -ctime operator. The ctime will have a more recent value if the owner, group, permission, or number of links has changed, while the file itself does not. If you want to search for files with a specific number of links, use the -links operator.

  Article 16.5 has more information about these three times. Article 17.7 explains how find checks them.

  Self-directed: find out how to use the -exec option to execute commands

   There are many well-known benefits provided by grep to the user who doesn't remember what his or her files contain. Even users of non-UNIX systems who make fun of its obscure name wish they had a utility with its power to search through a set of files for an arbitrary text pattern, known as a regular expression ( 26.4 ) .

  The main function of grep is to look for strings matching a regular expression and print only the lines found. Use grep when you want to look at how a particular word is used in one or more files. For example, here's how to list the lines in the file ch04 that contain either run-time or run time :

  $

  grep "run[- ]time" ch04

  Finding Text That Doesn't Match

  find. | grep -v

  19.15 Confusing Shell Wildcards and Regular Expressions
  Problem
  Sometimes you see .* sometimes just *, and sometimes you see [a-z]* but it means something other than what you thought. You use regular expressions for grep and sed but not in some places in bash. You can’t keep it all straight.
  Solution
  Relax; take a deep breath. You’re probably confused because you’re learning so much (or just using it too infrequently to remember it). Practice makes perfect, so keep trying.
  The rules aren’t that hard to remember for bash itself. After all, regular expression syntax is only used with the =~ comparison operator in bash. All of the other expres- sions in bash use shell pattern matching.
  Discussion
  The pattern matching used by bash uses some of the same symbols as regular expres- sions, but with different meanings. But it is also the case that you often have calls in your shell scripts to commands that use regular expressions—commands like grep and sed.
  We asked Chet Ramey, the current keeper of the bash source and all-around bash guru, if it was really the case that the =~ was the only use of regular expressions in bash. He concurred. He also was kind enough to supply a list of the various parts of bash syntax that use shell pattern matching. We’ve covered most, but not all of these topics in various recipes in this book. We offer the list here for completeness.
  Shell pattern matching is performed by:
  • Filename globbing (pathname expansion)
  • == and != operators for [[
  • case statements
  • $GLOBIGNORE handling
  • $HISTIGNORE handling
  • ${parameter#[#]word}
  • ${parameter%[%]word}
  • ${parameter/pattern/string}
  • Several bindable readline commands (glob-expand-word, glob-complete-word, etc.)
   480 | Chapter 19: Tips and Traps: Common Goofs for Novices
  • complete -G and compgen -G
  • complete -X and compgen -X
  • The help built-in’s `pattern` argument
  Thanks, Chet!

  Shining a Light on Spotlight

  A key feature included in OS X since Mac OS X Tiger is Spotlight, which indexes and stores metadata for all of the files on your system. This means that if you’re looking for a file by name, you can use locate or find, but if you’re looking for all images taken with a Nikon camera, or all PDF files that are more than 10 pages long, then Spotlight and its command-line tools are for you.
  Spotlight builds what Apple calls a metadata database that has a lot of information about the files on the system, in addition to their filenames. Whenever you conduct a Spotlight search—either through the graphical interface or on the command line—this metadata is searched to reveal information about the files on your system and offer up results. The two Spotlight commands that are analogous to the regular Unix commands ls and find are logically called mdls and mdfind.
  Let’s start with the mdls command—you’re going to be quite impressed!
  What’s Metadata?
  If you’ve been using computers for even a short time, you’re used to certain data being associated with each file you create. The filename, file size, date of creation—that’s all file- related data that’s familiar to you. But many files have additional, supplemental information.
  For example, Microsoft Word records the name and address of the file creator; Adobe Photoshop remembers what version of Photoshop you last used to edit an image file; and even digital cameras write out additional information for each image saved, including the camera name, the date and time the shot was taken, and often the film speed and lens focal length, all in EXIF format. This supplemental information is what OS X refers to as metadata, and it’s at the heart of Spotlight.
  Listing Spotlight Metadata with mdls
  Some of the most interesting types of files to explore with mdls are the pictures you take with a digital camera. Here’s what the ls command has to say about the JPEG file Peanut.jpg:
  $ ls -l IMG_1912.JPG
  -rw------- 1 taylor staff 8600047 May 7 12:17 IMG_1912.JPG
  Not particularly useful in terms of what’s actually inside the file. By comparison, here’s what the mdls command reports:
  $ mdls IMG_1912.JPG kMDItemAcquisitionMake kMDItemAcquisitionModel kMDItemAperture
  = "Canon"
  = "Canon EOS 50D"
  = 7
   128 | Chapter 5: Finding Files and Information
  kMDItemAuthors
      "
  = (
  )
  kMDItemBitsPerSample
  kMDItemColorSpace
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2012-05-07 18:17:06 +0000
  kMDItemContentType
  kMDItemContentTypeTree
      "public.jpeg",
      "public.image",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemCopyright
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEXIFVersion
  kMDItemExposureMode
  kMDItemExposureProgram
  kMDItemExposureTimeSeconds
  kMDItemFlashOnOff
  kMDItemFNumber
  kMDItemFocalLength
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemHasAlphaChannel
  kMDItemISOSpeed
  kMDItemKind
  kMDItemLogicalSize
  kMDItemOrientation
  kMDItemPhysicalSize
  kMDItemPixelCount
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemProfileName
  = "public.jpeg"
  = (
  ="
  = 2012-05-07 18:17:06 +0000 = "IMG_1912.JPG"
  = "2.2.1"
  =0
  = 4
  = 0.005555555555555556
  = 0
  = 11
  = 110
  = 2012-05-07 18:17:06 +0000 = 2012-05-07 18:17:06 +0000 ="
  =0
  =0
  =0
  =0
  =0
  =0
  = "IMG_1912.JPG"
  = 8600047
  = 20
  = 501
  = 8600047
  = "
  = 0
  = 400
  = "JPEG document"
  = 8600047
  =1
  = 8601600
  = 15054336
  = 4752
  = 3168
  = "sRGB IEC61966-2.1"
  = 32
  = "RGB"
  = 2012-05-07 18:17:06 +0000
   Shining a Light on Spotlight
  | 129
  kMDItemRedEyeOnOff
  kMDItemResolutionHeightDPI
  kMDItemResolutionWidthDPI
  kMDItemWhiteBalance
  = 0 = 72 = 72 = 1
  Quite a bit more useful information, thanks to Spotlight and its smart file parsing mod­ ules! Note that mdls offers the following details:
  • The camera used (Canon EOS 50D), as noted by kMDItemAcquisitionModel
  • The dimensions of the image (3168 x 4752), as noted by the kMDItem-PixelWidth
  and kMDItemPixelHeight items, respectively
  • The resolution of the image (72 DPI), as noted by kMDItemResolutionHeightDPI
  and kMDItemResolutionWidthDPI
  • Various other digital photo data, including exposure time (kMDItemExposureTime
  Seconds), focal length of the lens (kMDItemFocalLength), etc. Here’s another example of mdls output, this time with a PDF file:
  $ mdls ADT\ Writers\ Guide.pdf kMDItemAlternateNames
      "ADT Writers Guide.pdf"
  )
  kMDItemAuthors
      "Dave Taylor"
  = (
  = (
  = 2010-03-11 23:36:28 +0000
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2010-03-22 21:55:54 +0000
  kMDItemContentType             = "com.adobe.pdf"
  kMDItemContentTypeTree         = (
  "com.adobe.pdf",
  "public.data",
  "public.item",
  "public.composite-content",
  "public.content"
  )
  kMDItemCreator
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEncodingApplications
  = "Pages"
  = 2011-08-11 23:32:26 +0000 = "ADT Writers Guide"
  =(
      "Mac OS X 10.6.2 Quartz PDFContext"
  )
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  = 2010-03-22 21:55:54 +0000 = 2010-03-11 23:36:28 +0000 ="
  = 16
  =0 =0 =1 =0
   130
  | Chapter 5: Finding Files and Information
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemNumberOfPages
  kMDItemPageHeight
  kMDItemPageWidth
  kMDItemPhysicalSize
  kMDItemSecurityMethod
  kMDItemTitle
  kMDItemVersion
  = 0
  = "ADT Writers Guide.pdf"
  = 212658
  = 20
  = 501
  = 212658
  ="
  = "Portable Document Format (PDF)" = 212658
  = 5
  = 792
  = 612
  = 212992
  = "None"
  = "ADT Writers Guide"
  = "1.4"
  On a PDF document, the information includes the number of pages (as noted with kMDItemNumberOfPages; this document has 5), the application used to encode the PDF (Mac OS X 10.6.2 Quartz PDFContext, as noted by kMDItemEncodingApplications), and the date and time that the PDF file was created (March 11, 2010 at 23:36:28, as noted by kMDItemFSCreationDate).
  Let’s peek at one more file type before we explore what you can actually do with the Spotlight data, shall we? This time, it’s an MP3 file from my iTunes library:
  $ mdls 06\ Elise\ affair.mp3 kMDItemAlbum kMDItemAudioBitRate kMDItemAudioChannelCount kMDItemAudioSampleRate kMDItemAudioTrackNumber kMDItemAuthors
      "Thievery Corporation"
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2011-12-19 00:04:16 +0000
  kMDItemContentType             = "public.mp3"
  kMDItemContentTypeTree         = (
      "public.mp3",
      "public.audio",
      "public.audiovisual-content",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemDurationSeconds
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  = 2011-08-12 01:24:05 +0000
  = "06 Elise affair_.mp3"
  = 280.9774
  = 2011-12-19 00:04:16 +0000
  = 2010-10-05 05:22:24 +0000
  = "
  = "Lebanese Blonde"
  = 160000
  = 2
  = 44100
  = 6 = (
  = 2010-10-05 05:22:24 +0000
   Shining a Light on Spotlight
  | 131
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemMediaTypes
  Sound )
  kMDItemMusicalGenre
  kMDItemPhysicalSize
  kMDItemRecordingYear
  kMDItemTitle
  kMDItemTotalBitRate
  = 64
  =0
  =0
  =0
  =0
  =0
  = "06 Elise affair_.mp3" = 5723052
  = 20
  = 501
  = 5723052
  = "
  = "MP3 audio"
  = 5723052
  = (
  = "Electronic"
  = 5726208
  = 1998
  = "Elise affair"
  = 160000
  Encoded in each audio file is the artist (kMDItemAuthors), album (kMDItemAlbum), song name (kMDItemTitle), genre (kMDItemMusicalGenre), length of track (kMDItemDura tionSeconds), and much more, all accessible thanks to Spotlight and mdls.
  Finding Files with mdfind
  Knowing that there’s so much valuable and interesting information available through Spotlight, how do you actually do something useful with it? The answer is by using the mdfind command. However, while find has weird syntax, mdfind’s is even weirder and more unfriendly.
  The mdfind command matches files in the filesystem that meet a specific criterion or set of criteria, specified as:
  "metadata_field_name == 'pattern'"
  For example, to find all photographs taken with a Nikon camera, you’d use the following:
  $ mdfind "kMDItemAcquisitionModel == 'NIKON*'" /Users/taylor/Library/Mail/V2/Mailboxes/Film.mbox/
          965F1F99-FAB0-4EFE-9635-E04F1D6A4D84/Data/2/9/2/
          Attachments/292738/2/DLO_0887.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0006.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0008.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0001.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0010.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0013.jpg
   132
  | Chapter 5: Finding Files and Information
  Want to constrain the search to a specific subdirectory? You might be tempted to specify this directly as you would in find, but that’s not how it’s done. Instead, you need to use a flag called -onlyin, followed by a directory name. To find all the songs in your Jazz collection, use:
  $ mdfind -onlyin ~/Music "kMDItemMusicalGenre == 'Jazz'"
  You can also specify that you want a specific word anywhere in the metadata info by
  specifying just that word:
  $ mdfind -onlyin ~ Jazz /Users/taylor/Library/Safari/ReadingListArchives/
          381D47A1-2B73-4D2D-A388-6CAE189C92B4/Page.webarchive
      /Users/taylor/Desktop/LearnUnixOSX/ch05.asc
      /Users/taylor/Library/Calendars/74F70952-82D1-4222-BD5A-D4F03A465D55.caldav/
          015FBACF-C1E6-42AF-A3B0-37328DBC10A9.calendar/Events/
          M2CD-3-1-F2BEC546-28D9-4671-8E3D-F1E5114615E8.ics
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          20 Harlem Strut (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          19 Alice Blue Gown (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          18 Maple Leaf Rag (Bonus Track).mp3
      ...
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch04.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch01.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/app-a.doc
      /Users/taylor/Documents/BlogWorld Expo/jazz-performances.doc
      /Users/taylor/Documents/Blog Backups/Nov-1-2007/art_dolls.txt
  This output is quite interesting because it matches not only files where the word "Jazz" is part of the Spotlight metadata (as in the iTunes files), but also files that have "Jazz" in their name (the BlogWorld Expo document jazz-performances.doc), and even a plain- text file where the word "Jazz" appears in the text itself (art_dolls.txt). Pretty nifty, eh?
  Making Spotlight Useful
  Before leaving Spotlight, and certainly before we give up and assume that it’s only useful on the command line, let’s have a look at a couple of simple Unix commands that can extract useful information from the mdls information stream.
  Curious about the size in pixels of your JPEG files? You can quickly ascertain their height and width by using grep:
  $ mdls IMG_1912.JPG | grep -E '(PixelHeight|PixelWidth)' kMDItemPixelHeight = 4752
  kMDItemPixelWidth = 3168
  You can identify the duration of an audio file without loading it into iTunes or any other audio player by using:
   Shining a Light on Spotlight | 133
  $ mdls "06 Elise affair.mp3" | grep Duration kMDItemDurationSeconds = 280.9774
  You can also use find and xargs to identify files by name and then extract specific char­ acteristics:
  $ find . -name "*jpg" -print0 | xargs -0 mdls | grep FocalLength
  Or, you can actually use mdfind in the same manner (it does have a -0 option that makes
  it possible to match filenames that have spaces without things breaking):
  $ mdfind -0 "kMDItemFocalLength == '35'" | xargs -0 mdls | grep -E '(PixelHeight|PixelWidth|DisplayName)'
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  = "Little-Hand.jpg"
  = 532
  = 800
  = "Peanut.jpg"
  = 531 = 800
  This last search matches all pictures on the entire system with a focal length of 35 (meaning, they were taken with a 35mm lens), and then displays the name, height, and width of each of the images it finds.
  These commands really beg for a simple shell script or two, where you could actually parse the output and reformat it as desired. We’ll talk about writing shell scripts a bit later in the book, but here’s a sneak preview of what such a script could do:
  $ photosize Peanut.jpg 800x531 at 300DPI
  The Spotlight commands accessible from the command line still haven’t been refined quite yet. You can get started with the information shown here, but don’t be surprised if a revision or two down the road turns the Spotlight commands into really powerful tools you can use for all sorts of tasks.

  Shining a Light on Spotlight
  A key feature included in OS X since Mac OS X Tiger is Spotlight, which indexes and stores metadata for all of the files on your system. This means that if you’re looking for a file by name, you can use locate or find, but if you’re looking for all images taken with a Nikon camera, or all PDF files that are more than 10 pages long, then Spotlight and its command-line tools are for you.
  Spotlight builds what Apple calls a metadata database that has a lot of information about the files on the system, in addition to their filenames. Whenever you conduct a Spotlight search—either through the graphical interface or on the command line—this metadata is searched to reveal information about the files on your system and offer up results. The two Spotlight commands that are analogous to the regular Unix commands ls and find are logically called mdls and mdfind.
  Let’s start with the mdls command—you’re going to be quite impressed!
  What’s Metadata?
  If you’ve been using computers for even a short time, you’re used to certain data being associated with each file you create. The filename, file size, date of creation—that’s all file- related data that’s familiar to you. But many files have additional, supplemental information.
  For example, Microsoft Word records the name and address of the file creator; Adobe Photoshop remembers what version of Photoshop you last used to edit an image file; and even digital cameras write out additional information for each image saved, including the camera name, the date and time the shot was taken, and often the film speed and lens focal length, all in EXIF format. This supplemental information is what OS X refers to as metadata, and it’s at the heart of Spotlight.
  Listing Spotlight Metadata with mdls
  Some of the most interesting types of files to explore with mdls are the pictures you take with a digital camera. Here’s what the ls command has to say about the JPEG file Peanut.jpg:
  $ ls -l IMG_1912.JPG
  -rw------- 1 taylor staff 8600047 May 7 12:17 IMG_1912.JPG
  Not particularly useful in terms of what’s actually inside the file. By comparison, here’s what the mdls command reports:
  $ mdls IMG_1912.JPG kMDItemAcquisitionMake kMDItemAcquisitionModel kMDItemAperture
  = "Canon"
  = "Canon EOS 50D"
  = 7
   128 | Chapter 5: Finding Files and Information
  kMDItemAuthors
      "
  = (
  )
  kMDItemBitsPerSample
  kMDItemColorSpace
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2012-05-07 18:17:06 +0000
  kMDItemContentType
  kMDItemContentTypeTree
      "public.jpeg",
      "public.image",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemCopyright
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEXIFVersion
  kMDItemExposureMode
  kMDItemExposureProgram
  kMDItemExposureTimeSeconds
  kMDItemFlashOnOff
  kMDItemFNumber
  kMDItemFocalLength
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemHasAlphaChannel
  kMDItemISOSpeed
  kMDItemKind
  kMDItemLogicalSize
  kMDItemOrientation
  kMDItemPhysicalSize
  kMDItemPixelCount
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemProfileName
  = "public.jpeg"
  = (
  ="
  = 2012-05-07 18:17:06 +0000 = "IMG_1912.JPG"
  = "2.2.1"
  =0
  = 4
  = 0.005555555555555556
  = 0
  = 11
  = 110
  = 2012-05-07 18:17:06 +0000 = 2012-05-07 18:17:06 +0000 ="
  =0
  =0
  =0
  =0
  =0
  =0
  = "IMG_1912.JPG"
  = 8600047
  = 20
  = 501
  = 8600047
  = "
  = 0
  = 400
  = "JPEG document"
  = 8600047
  =1
  = 8601600
  = 15054336
  = 4752
  = 3168
  = "sRGB IEC61966-2.1"
  = 32
  = "RGB"
  = 2012-05-07 18:17:06 +0000
   Shining a Light on Spotlight
  | 129
  kMDItemRedEyeOnOff
  kMDItemResolutionHeightDPI
  kMDItemResolutionWidthDPI
  kMDItemWhiteBalance
  = 0 = 72 = 72 = 1
  Quite a bit more useful information, thanks to Spotlight and its smart file parsing mod­ ules! Note that mdls offers the following details:
  • The camera used (Canon EOS 50D), as noted by kMDItemAcquisitionModel
  • The dimensions of the image (3168 x 4752), as noted by the kMDItem-PixelWidth
  and kMDItemPixelHeight items, respectively
  • The resolution of the image (72 DPI), as noted by kMDItemResolutionHeightDPI
  and kMDItemResolutionWidthDPI
  • Various other digital photo data, including exposure time (kMDItemExposureTime
  Seconds), focal length of the lens (kMDItemFocalLength), etc. Here’s another example of mdls output, this time with a PDF file:
  $ mdls ADT\ Writers\ Guide.pdf kMDItemAlternateNames
      "ADT Writers Guide.pdf"
  )
  kMDItemAuthors
      "Dave Taylor"
  = (
  = (
  = 2010-03-11 23:36:28 +0000
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2010-03-22 21:55:54 +0000
  kMDItemContentType             = "com.adobe.pdf"
  kMDItemContentTypeTree         = (
  "com.adobe.pdf",
  "public.data",
  "public.item",
  "public.composite-content",
  "public.content"
  )
  kMDItemCreator
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemEncodingApplications
  = "Pages"
  = 2011-08-11 23:32:26 +0000 = "ADT Writers Guide"
  =(
      "Mac OS X 10.6.2 Quartz PDFContext"
  )
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  = 2010-03-22 21:55:54 +0000 = 2010-03-11 23:36:28 +0000 ="
  = 16
  =0 =0 =1 =0
   130
  | Chapter 5: Finding Files and Information
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemNumberOfPages
  kMDItemPageHeight
  kMDItemPageWidth
  kMDItemPhysicalSize
  kMDItemSecurityMethod
  kMDItemTitle
  kMDItemVersion
  = 0
  = "ADT Writers Guide.pdf"
  = 212658
  = 20
  = 501
  = 212658
  ="
  = "Portable Document Format (PDF)" = 212658
  = 5
  = 792
  = 612
  = 212992
  = "None"
  = "ADT Writers Guide"
  = "1.4"
  On a PDF document, the information includes the number of pages (as noted with kMDItemNumberOfPages; this document has 5), the application used to encode the PDF (Mac OS X 10.6.2 Quartz PDFContext, as noted by kMDItemEncodingApplications), and the date and time that the PDF file was created (March 11, 2010 at 23:36:28, as noted by kMDItemFSCreationDate).
  Let’s peek at one more file type before we explore what you can actually do with the Spotlight data, shall we? This time, it’s an MP3 file from my iTunes library:
  $ mdls 06\ Elise\ affair.mp3 kMDItemAlbum kMDItemAudioBitRate kMDItemAudioChannelCount kMDItemAudioSampleRate kMDItemAudioTrackNumber kMDItemAuthors
      "Thievery Corporation"
  )
  kMDItemContentCreationDate
  kMDItemContentModificationDate = 2011-12-19 00:04:16 +0000
  kMDItemContentType             = "public.mp3"
  kMDItemContentTypeTree         = (
      "public.mp3",
      "public.audio",
      "public.audiovisual-content",
      "public.data",
      "public.item",
      "public.content"
  )
  kMDItemDateAdded
  kMDItemDisplayName
  kMDItemDurationSeconds
  kMDItemFSContentChangeDate
  kMDItemFSCreationDate
  kMDItemFSCreatorCode
  = 2011-08-12 01:24:05 +0000
  = "06 Elise affair_.mp3"
  = 280.9774
  = 2011-12-19 00:04:16 +0000
  = 2010-10-05 05:22:24 +0000
  = "
  = "Lebanese Blonde"
  = 160000
  = 2
  = 44100
  = 6 = (
  = 2010-10-05 05:22:24 +0000
   Shining a Light on Spotlight
  | 131
  kMDItemFSFinderFlags
  kMDItemFSHasCustomIcon
  kMDItemFSInvisible
  kMDItemFSIsExtensionHidden
  kMDItemFSIsStationery
  kMDItemFSLabel
  kMDItemFSName
  kMDItemFSNodeCount
  kMDItemFSOwnerGroupID
  kMDItemFSOwnerUserID
  kMDItemFSSize
  kMDItemFSTypeCode
  kMDItemKind
  kMDItemLogicalSize
  kMDItemMediaTypes
  Sound )
  kMDItemMusicalGenre
  kMDItemPhysicalSize
  kMDItemRecordingYear
  kMDItemTitle
  kMDItemTotalBitRate
  = 64
  =0
  =0
  =0
  =0
  =0
  = "06 Elise affair_.mp3" = 5723052
  = 20
  = 501
  = 5723052
  = "
  = "MP3 audio"
  = 5723052
  = (
  = "Electronic"
  = 5726208
  = 1998
  = "Elise affair"
  = 160000
  Encoded in each audio file is the artist (kMDItemAuthors), album (kMDItemAlbum), song name (kMDItemTitle), genre (kMDItemMusicalGenre), length of track (kMDItemDura tionSeconds), and much more, all accessible thanks to Spotlight and mdls.
  Finding Files with mdfind
  Knowing that there’s so much valuable and interesting information available through Spotlight, how do you actually do something useful with it? The answer is by using the mdfind command. However, while find has weird syntax, mdfind’s is even weirder and more unfriendly.
  The mdfind command matches files in the filesystem that meet a specific criterion or set of criteria, specified as:
  "metadata_field_name == 'pattern'"
  For example, to find all photographs taken with a Nikon camera, you’d use the following:
  $ mdfind "kMDItemAcquisitionModel == 'NIKON*'" /Users/taylor/Library/Mail/V2/Mailboxes/Film.mbox/
          965F1F99-FAB0-4EFE-9635-E04F1D6A4D84/Data/2/9/2/
          Attachments/292738/2/DLO_0887.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0006.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0008.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0001.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0010.jpg
      /Users/taylor/Dropbox/Photos/Lily in New Jersey/DSC_0013.jpg
   132
  | Chapter 5: Finding Files and Information
  Want to constrain the search to a specific subdirectory? You might be tempted to specify this directly as you would in find, but that’s not how it’s done. Instead, you need to use a flag called -onlyin, followed by a directory name. To find all the songs in your Jazz collection, use:
  $ mdfind -onlyin ~/Music "kMDItemMusicalGenre == 'Jazz'"
  You can also specify that you want a specific word anywhere in the metadata info by
  specifying just that word:
  $ mdfind -onlyin ~ Jazz /Users/taylor/Library/Safari/ReadingListArchives/
          381D47A1-2B73-4D2D-A388-6CAE189C92B4/Page.webarchive
      /Users/taylor/Desktop/LearnUnixOSX/ch05.asc
      /Users/taylor/Library/Calendars/74F70952-82D1-4222-BD5A-D4F03A465D55.caldav/
          015FBACF-C1E6-42AF-A3B0-37328DBC10A9.calendar/Events/
          M2CD-3-1-F2BEC546-28D9-4671-8E3D-F1E5114615E8.ics
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          20 Harlem Strut (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          19 Alice Blue Gown (Bonus Track).mp3
      /Users/taylor/Music/iTunes/iTunes Media/Music/Various Artists/Boardwalk Empire/
          18 Maple Leaf Rag (Bonus Track).mp3
      ...
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch04.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/Ch01.doc
      /Users/taylor/Documents/Books/Cool Web Sites/As Submitted/app-a.doc
      /Users/taylor/Documents/BlogWorld Expo/jazz-performances.doc
      /Users/taylor/Documents/Blog Backups/Nov-1-2007/art_dolls.txt
  This output is quite interesting because it matches not only files where the word "Jazz" is part of the Spotlight metadata (as in the iTunes files), but also files that have "Jazz" in their name (the BlogWorld Expo document jazz-performances.doc), and even a plain- text file where the word "Jazz" appears in the text itself (art_dolls.txt). Pretty nifty, eh?
  Making Spotlight Useful
  Before leaving Spotlight, and certainly before we give up and assume that it’s only useful on the command line, let’s have a look at a couple of simple Unix commands that can extract useful information from the mdls information stream.
  Curious about the size in pixels of your JPEG files? You can quickly ascertain their height and width by using grep:
  $ mdls IMG_1912.JPG | grep -E '(PixelHeight|PixelWidth)' kMDItemPixelHeight = 4752
  kMDItemPixelWidth = 3168
  You can identify the duration of an audio file without loading it into iTunes or any other audio player by using:
   Shining a Light on Spotlight | 133
  $ mdls "06 Elise affair.mp3" | grep Duration kMDItemDurationSeconds = 280.9774
  You can also use find and xargs to identify files by name and then extract specific char­ acteristics:
  $ find . -name "*jpg" -print0 | xargs -0 mdls | grep FocalLength
  Or, you can actually use mdfind in the same manner (it does have a -0 option that makes
  it possible to match filenames that have spaces without things breaking):
  $ mdfind -0 "kMDItemFocalLength == '35'" | xargs -0 mdls | grep -E '(PixelHeight|PixelWidth|DisplayName)'
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  kMDItemDisplayName
  kMDItemPixelHeight
  kMDItemPixelWidth
  = "Little-Hand.jpg"
  = 532
  = 800
  = "Peanut.jpg"
  = 531 = 800
  This last search matches all pictures on the entire system with a focal length of 35 (meaning, they were taken with a 35mm lens), and then displays the name, height, and width of each of the images it finds.
  These commands really beg for a simple shell script or two, where you could actually parse the output and reformat it as desired. We’ll talk about writing shell scripts a bit later in the book, but here’s a sneak preview of what such a script could do:
  $ photosize Peanut.jpg 800x531 at 300DPI
  The Spotlight commands accessible from the command line still haven’t been refined quite yet. You can get started with the information shown here, but don’t be surprised if a revision or two down the road turns the Spotlight commands into really powerful tools you can use for all sorts of tasks.

  9.1 Finding All Your MP3 Files Problem

  You have MP3 audio files scattered all over your filesystem. You’d like to move them all into a single location so that you can organize them and then copy them onto a music player.
   184
   Solution
  The find utility can locate all of those files and then execute a command to move them where you want. For example:
       $ find . -name '*.mp3' -print -exec mv '{}' ~/songs \;

  Discussion

  The syntax for the find utility is unlike other Unix tools. It doesn’t use options in the typical way, with dash and single-letter collections up front followed by several words of arguments. Rather, the options look like short words, and are ordered in a logical sequence describing the logic of which files are to be found, and what to do with them, if anything, when they are found. These word-like options are often called predicates.

  A find command’s first arguments are the directory or directories in which to search. A typical use is simply (.) for the current directory. But you can provide a whole list of directories, or even search the entire filesystem (permissions allowing) by specify- ing the root of the filesystem (/) as the starting point.

  In our example the first option (the -name predicate) specifies the pattern we will search for. Its syntax is like the bash pattern matching syntax, so *.mp3 will match all filenames that end in the characters ".mp3". Any file that matches this pattern is con- sidered to return true and will thus continue to the next predicate of the command.

  Think of it this way: find will climb around on the filesystem and each filename that it finds it will present to this gauntlet of conditions that must be run. Any condition that is true is passed. Encounter a false and that filename’s turn is immediately over, and the next filename is processed.

  Now the -print condition is easy. It is always true and it has the side effect of print- ing the name to standard output. So any file that has made it this far in the sequence of conditions will have its name printed.

  The -exec is a bit odd. Any filename making it this far will become part of a com- mand that is executed. The remainder of the lineup to the \; is the command to be executed. The {} is replaced by the name of the file that was found. So in our exam- ple, if find encounters a file named mhsr.mp3 in the ./music/jazz subdirectory, then the command that will be executed will be:
       mv ./music/jazz/mhsr.mp3 ~/songs
  The command will be issued for each file that matches the pattern. If lots and lots of matching files are found, lots and lots of commands will be issued. Sometimes this is too demanding of system resources and it can be a better idea to use find just to find the files and print the filenames into a datafile and issue fewer commands by
   Finding All Your MP3 Files | 185
  consolidating arguments several to a line. (But with machines getting faster all the time, this is less and less of an issue. It might even be something worthwhile for your dual core or quad core processor to do.)

  9.2 Handling Filenames Containing Odd Characters Problem
  You used a find command like the one in Recipe 9.1, "Finding All Your MP3 Files" but the results were not what you intended because many of your filenames contain odd characters.
  Solution
  First, understand that to Unix folks, odd means "anything not a lowercase letter, or maybe a number." So uppercase, spaces, punctuation, and character accents are all odd. But you’ll find all of those and more in the names of many songs and bands.
  Depending on the oddness of the characters, your system, tools, and goal, it might be enough to simply quote the replacement string (i.e., put single quotes around the {}, as in '{}') . You did test your command first, right?
  If that’s no good, try using the -print0 argument to find and the -0 argument to xargs. -print0 tells find to use the null character (\0) instead of whitespace as the output delimiter between pathnames found. -0 then tells xargs the input delimiter. These will always work, but they are not supported on every system.
  The xargs command takes whitespace delimited (except when using -0) pathnames from standard input and executes a specified command on as many of them as possi- ble (up to a bit less than the system’s ARG_MAX value; see Recipe 15.13, "Working Around "argument list too long" Errors"). Since there is a lot of overhead associated with calling other commands, using xargs can drastically speed up operations because you are calling the other command as few times as possible, rather than each time a pathname is found.
   186 | Chapter 9: Finding Files: find, locate, slocate
   So, to rewrite the solution from Recipe 9.1, "Finding All Your MP3 Files" to handle odd characters:
       $ find . -name '*.mp3' -print0 | xargs -i -0 mv '{}' ~/songs
  Here is a similar example demonstrating how to use xargs to work around spaces in a path or filename when locating and then coping files:
       $ locate P1100087.JPG PC220010.JPG PA310075.JPG PA310076.JPG | xargs -i cp '{}' .
  Discussion
  There are two problems with this approach. One is that not all versions of xargs sup- port the -i option, and the other is that the -i option eliminates argument grouping, thus negating the speed increase we were hoping for. The problem is that the mv command needs the destination directory as the final argument, but traditional xargs will simply take its input and tack it onto the end of the given command until it runs out of space or input. The results of that behavior applied to an mv command would be very, very ugly. So some versions of xargs provide a -i switch that defaults to using {} (like find), but using -i requires that the command be run one at a time. So the only benefit over using find’s -exec is the odd character handling.
  However, the xargs utility is most effective when used in conjunction with find and a command like chmod that just wants a list of arguments to process. You can really see a vast speed improvement when handling large numbers of pathnames. For example:
       $ find some_directory -type f -print0 | xargs -0 chmod 0644
  See Also
  • man find
  • man xargs
  • Recipe 9.1, "Finding All Your MP3 Files"
  • Recipe 15.13, "Working Around "argument list too long" Errors"
  9.3 Speeding Up Operations on Found Files Problem
  You used a find command like the one in Recipe 9.1, "Finding All Your MP3 Files" and the resulting operations take a long time because you found a lot of files, so you want to speed it up.
   Speeding Up Operations on Found Files | 187
   Solution
  See the discussion on xargs Recipe 9.2, "Handling Filenames Containing Odd Characters."
  See Also
  • Recipe 9.1, "Finding All Your MP3 Files"
  • Recipe 9.2, "Handling Filenames Containing Odd Characters"
  9.4 Finding Files Across Symbolic Links Problem
  You issued a find command to find your .mp3 files but it didn’t find all of them—it missed all those that were part of your filesystem but were mounted via a symbolic link. Is find unable to cross that kind of boundary?
  Solution
  Use the -follow predicate. The example we used before becomes:
  $ find . -follow -name '*.mp3' -print0 | xargs -i -0 mv '{}' ~/songs
  Discussion
  Sometimes you don’t want find to cross over onto other filesystems, which is where symbolic links originated. So the default for find is not to follow a symbolic link. If you do want it to do so, then use the -follow option as the first option in the list on your find command.
  See Also
  • man find
  9.5 Finding Files Irrespective of Case Problem
  Some of your MP3 files end with .MP3 rather than .mp3. How do you find those?
   188 | Chapter 9: Finding Files: find, locate, slocate
   Solution
  Use the -iname predicate (if your version of find supports it) to run a case-insensitive search, rather than just -name. For example:
       $ find . -follow -iname '*.mp3' -print0 | xargs -i -0 mv '{}' ~/songs
  Discussion
  Sometimes you care about the case of the filename and sometimes you don’t. Use the -iname option when you don’t care, in situations like this, where .mp3 or .MP3 both indicate that the file is probably an MP3 file. (We say probably because on Unix-like systems you can name a file anything that you want. It isn’t forced to have a particu- lar extension.)
  One of the most common places where you’ll see the upper- and lowercase issue is when dealing with Microsoft Windows-compatible filesystems, especially older or "lowest common denominator" filesystems. A digital camera that we use stores its files with filenames like PICT001.JPG, incrementing the number with each picture. If you were to try:
       $ find . -name '*.jpg' -print
  you wouldn’t find many pictures. In this case you could also try:
       $ find . -name '*.[Jj][Pp][Gg]' -print
  since that regular expression will match either letter in brackets, but that isn’t as easy to type, especially if the pattern that you want to match is much longer. In prac- tice, -iname is an easier choice. The catch is that not every version of find supports the -iname predicate. If your system doesn’t support it, you could try tricky regular expressions as shown above, use multiple -name options with the case variations you expect, or install the GNU version of find.
  See Also
  • man find
  9.6 Finding Files by Date Problem
  Suppose someone sent you a JPEG image file that you saved on your filesystem a few months ago. Now you don’t remember where you put it. How can you find it?
   Finding Files by Date | 189
   Solution
  Use a find command with the -mtime predicate, which checks the date of last modifi- cation. For example:
       find . -name '*.jpg' -mtime +90 -print
  Discussion
  The -mtime predicate takes an argument to specify the timeframe for the search. The 90 stands for 90 days. By using a plus sign on the number (+90) we indicate that we’re looking for a file modified more than 90 days ago. Write -90 (using a minus sign) for less than 90 days. Use neither a plus nor minus to mean exactly 90 days.
  There are several predicates for searching based on file modification times and each take a quantity argument. Using a plus, minus, or no sign indicates greater than, less than, or equals, respectively, for all of those predicates.
  The find utility also has logical AND, OR, and NOT constructs so if you know that the file was at least one week old (7 days) but not more than 14 days old, you can combine the predicates like this:
       $ find . -mtime +7 -a -mtime -14 -print
  YoucangetevenmorecomplicatedusingORaswellasANDandevenNOTto combine conditions, as in:
  $ find . -mtime +14 -name '*.text' -o \( -mtime -14 -name '*.txt' \) -print
  This will print out the names of files ending in .text that are older than 14 days, as
  well as those that are newer than 14 days but have .txt as their last 4 characters.
  You will likely need parentheses to get the precedence right. Two predicates in sequencearelikealogicalAND,whichbindstighterthananOR(infindasinmost languages). Use parentheses as much as you need to make it unambiguous.
  Parentheses have a special meaning to bash, so we need to escape that meaning, and write them as \( and \) or inside of single quotes as '(' and ')'. You cannot use sin- gle quotes around the entire expression though, as that will confuse the find com- mand. It wants each predicate as its own word.
  See Also
  • man find
   190 | Chapter 9: Finding Files: find, locate, slocate
   9.7 Finding Files by Type
  Problem
  You are looking for a directory with the word "java" in it. When you tried:
       $ find . -name '*java*' -print
  you got way too many files—including all the Java source files in your part of the filesystem.
  Solution
  Use the -type predicate to select only directories: $ find . -type d -name '*java*' -print
  Discussion
  We put the -type d first followed by the -name *java*. Either order would have found the same set of files. By putting the -type d first in the list of options, though, the search will be slightly more efficient: as each file is encountered, the test will be made to see if it is a directory and then only directories will have their names checked against the pattern. All files have names; relatively few are directories. So this ordering eliminates most files from further consideration before we ever do the string comparison. Is it a big deal? With processors getting faster all the time, it mat- ters less so. With disk sizes getting bigger all the time, it matters more so. There are several types of files for which you can check, not just directories. Table 9-1 lists the single characters used to find these types of files.
  Table 9-1. Characters used by find’s -type predicate
  Key Meaning
  b block special file
  c character special file
  d directory
  p pipe (or "fifo")
  f plain ol’ file
  l symbolic link
  s socket
  D (Solaris only) "door"
     Finding Files by Type
  | 191
   See Also
  • man find
  9.8 Finding Files by Size Problem
  You want to do a little housecleaning, and to get the most out of your effort you are going to start by finding your largest files and deciding if you need to keep them around. But how do you find your largest files?
  Solution
  Use the -size predicate in the find command to select files above, below, or exactly a certain size. For example:
       find . -size +3000k -print
  Discussion
  Like the numeric argument to -mtime, the -size predicate’s numeric argument can be preceded by a minus sign, plus sign, or no sign at all to indicate less than, greater than, or exactly equal to the numeric argument. So we’ve indicated, in our example, that we’re looking for files that are greater than the size indicated.
  The size indicated includes a unit of k for kilobytes. If you use c for the unit, that means just bytes (or characters). If you use b, or don’t put any unit, that indicates a size in blocks. (The block is a 512-byte block, historically a common unit in Unix systems.) So we’re looking for files that are greater than 3 MB in size.
  See Also
  • man find • man du
  9.9 Finding Files by Content Problem
  How do you find a file of some known content? Let’s say that you had written an important letter and saved it as a text file, putting .txt on the end of the filename. Beyond that, the only thing you remember about the content of the letter is that you had used the word "portend."
   192 | Chapter 9: Finding Files: find, locate, slocate
   Solution
  If you are in the vicinity of that file, say within the current directory, you can start with a simple grep:
       grep -i portend *.txt
  With the -i option, grep will ignore upper- and lowercase difference. This command may not be sufficient to find what you’re looking for, but start simply. Of course, if you think the file might be in one of your many subdirectories, you can try to reach all the files that are in subdirectories of the current directory with this command:
       grep -i portend */*.txt
  Let’s face it, though, that’s not a very thorough search.
  If that doesn’t do it, let’s use a more complete solution: the find command. Use the -exec option on find so that if the predicates are true up to that point, it will exe- cute a command for each file it finds. You can invoke grep or other utilities like this:
       find . -name '*.txt' -exec grep -Hi portend '{}' \;
  Discussion
  We use the -name '*.txt' construct to help narrow down the search. Any such test will help, since having to run a separate executable for each file that it finds is costly in time and CPU horsepower. Maybe you have a rough idea of how old the file is (e.g., -mdate -5 or some such).
  The '{}' is where the filename is put when executing the command. The \; indi- cates the end of the command, in case you want to continue with more predicates. Both the braces and the semicolon need to be escaped, so we quote one and use the backslash for the other. It doesn’t matter which way we escape them, only that we do escape them, so that bash doesn’t misinterpret them.
  On some systems, the -H option will print the name of the file if grep finds some- thing. Normally, with only one filename on the command, grep won’t bother to name the file, it just prints out the matching line that it finds. Since we’re searching through many files, we need to know which file was grepped.
  If you’re running a version of grep that doesn’t have the -H option, then just put /dev/ null as one of the filenames on the grep command. The grep command will then have more than one file to open, and will print out the filename if it finds the text.
  See Also
  • man find

   Finding Files by Content | 193
  9.10 Finding Existing Files and Content Fast Problem
  You’d like to be able to find files without having to wait for a long find command to complete, or you need to find a file with some specific content.
  Solution
  If your system has locate, slocate, Beagle, Spotlight or some other indexer, you are already set. If not, look into them.
  As we discussed in Recipe 1.3, "Finding and Running Commands", locate and slocate consult database files about the system (usually compiled and updated by a cron job) to find file or command names almost instantly. The location of the actual database files, what is indexed therein, and how often, may vary from system to sys- tem. Consult your system’s manpages for details.
       $ locate apropos
       /usr/bin/apropos
       /usr/share/man/de/man1/apropos.1.gz
       /usr/share/man/es/man1/apropos.1.gz
       /usr/share/man/it/man1/apropos.1.gz
       /usr/share/man/ja/man1/apropos.1.gz
       /usr/share/man/man1/apropos.1.gz
  locate and slocate don’t index content though, so see Recipe 9.9, "Finding Files by Content" for that.
  Beagle and Spotlight are examples of a fairly recent technology known as desktop search engines or indexers. Google Desktop Search and Copernic Desktop Search are two examples from the Microsoft Windows world. Desktop search tools use some kind of indexer to crawl, parse, and index the names and contents of all of the files (and usually email messages) in your personal file space; i.e., your home directory on a Unix or Linux system. This information is then almost instantly available to you when you look for it. These tools are usually very configurable, graphical, operate on a per-user basis, and index the contents of your files.
  Discussion
  slocate stores permission information (in addition to filenames and paths) so that it will not list programs to which the user does not have access. On most Linux sys- tems locate is a symbolic link to slocate; other systems may have separate programs, or may not have slocate at all. Both of these are command-line tools that crawl and index the entire filesystem, more or less, but they only contain filenames and locations.

  Find all .c files modified more recently than your Makefile.
  Shell...
  find . -name ' *.c' -newer Makefile -print


    GUI.....
  Open the Explorer, navigate to the correct directory, click on the Makefile, and note the modification time. Then bring up Tools/Find, and enter *.c for the file specification. Select the date tab, and enter the date you noted for the Makefile in the first date field. Then hit OK.

  Shell...
  zip archive.zip *.h *.c -or- tar cvf archive.tar *.h *.c
  GUI.....
  Bring up a ZIP utility (such as the shareware WinZip [URL41], select "Create New Archive," enter its name, select the source directory in the add dialog, set the filter to "* .c", click "Add," set the filter to "* .h", click "Add," then close the archive. ̈

  Shell...
  find . -name '*.java' -mtime +7 -print
  GUI.....
  Click and navigate to "Find files," click the "Named" field and type in "*.java", select the "Date Modified" tab. Then select "Between." Click on the starting date and type in the starting date of the beginning of the project. Click on the ending date and type in the date of a week ago today (be sure to have a calendar handy). Click on "Find Now."
  Shell...
  find . -name '*.java' -mtime +7 -print |
       xargs grep 'java.awt'
  GUI.....
  Load each file in the list from the previous example into an editor and search for the string "java.awt". Write down the name of each file containing a match.
   Construct a zip/tar archive of my source.
  Which Java files have not been changed in the last week?
  Of those files, which use the awt libraries?
  Clearly the list could go on. The shell commands may be obscure or terse, but they are powerful and concise. And, because shell commands can be combined into script files (or command files under Windows systems), you can build sequences of commands to automate things you do often.

  SEARCHING FOR FILES

  As we have wandered around our Linux system, one thing has become abundantly clear: A typical Linux system has a lot of files! This raises the question "How
  do we find things?" We already know that the Linux filesystem is well organized according to conventions that have been passed down from one generation of Unix-like systems to the next, but the sheer number of files can present a daunting problem.
  In this chapter, we will look at two tools that are used to find files on a system:
    locate—Find files by name.
    find—Search for files in a directory hierarchy.
  We will also look at a command that is often used with file-search com- mands to process the resulting list of files:
    xargs—Build and execute command lines from standard input.
  In addition, we will introduce a couple of commands to assist us in our explorations:
    touch—Change file times.
    stat—Display file or filesystem status.
  locate—Find Files the Easy Way
  The locate program performs a rapid database search of pathnames and then outputs every name that matches a given substring. Say, for example, we want to find all the programs with names that begin with zip. Since we are looking for programs, we can assume that the name of the directory containing the programs would end with bin/. Therefore, we could try to use locate this way to find our files:
  [me@linuxbox ~]$ locate bin/zip
  locate will search its database of pathnames and output any that contain
  the string bin/zip:
               /usr/bin/zip
               /usr/bin/zipcloak
               /usr/bin/zipgrep
               /usr/bin/zipinfo
               /usr/bin/zipnote
               /usr/bin/zipsplit
  If the search requirement is not so simple, locate can be combined with other tools, such as grep, to design more interesting searches:
  [me@linuxbox ~]$ locate zip | grep bin /bin/bunzip2
  /bin/bzip2
  /bin/bzip2recover
               /bin/gunzip
               /bin/gzip
               /usr/bin/funzip
               /usr/bin/gpg-zip
               /usr/bin/preunzip
               /usr/bin/prezip
               /usr/bin/prezip-bin
               /usr/bin/unzip
               /usr/bin/unzipsfx
               /usr/bin/zip
               /usr/bin/zipcloak
               /usr/bin/zipgrep
               /usr/bin/zipinfo
               /usr/bin/zipnote
               /usr/bin/zipsplit
  The locate program has been around for a number of years, and several different variants are in common use. The two most common ones found in modern Linux distributions are slocate and mlocate, though they are usually
        188
  Chapter 17
  accessed by a symbolic link named locate. The different versions of locate have overlapping options sets. Some versions include regular-expression matching (which we’ll cover in Chapter 19) and wildcard support. Check the man page for locate to determine which version of locate is installed.
      WHERE DOES THE LOCATE DATABASE COME FROM?
  You may notice that, on some distributions, locate fails to work just after the system is installed, but if you try again the next day, it works fine. What gives? The locate database is created by another program named updatedb. Usually, it is run periodically as a cron job; that is, a task performed at regular intervals by the cron daemon. Most systems equipped with locate run updatedb once a day. Since the database is not updated continuously, you will notice that very recent files do not show up when using locate. To overcome this, it’s possible to run the updatedb program manually by becoming the superuser and running updatedb
  at the prompt.
     find—Find Files the Hard Way
  While the locate program can find a file based solely on its name, the find program searches a given directory (and its subdirectories) for files based on a variety of attributes. We’re going to spend a lot of time with find because it has a bunch of interesting features that we will see again and again when we start to cover programming concepts in later chapters.
  In its simplest use, find is given one or more names of directories to search. For example, it can produce a list of our home directory:
  [me@linuxbox ~]$ find ~
  On most active user accounts, this will produce a large list. Since the
  list is sent to standard output, we can pipe the list into other programs. Let’s use wc to count the number of files:
  [me@linuxbox ~]$ find ~ | wc -l 47068
  Wow, we’ve been busy! The beauty of find is that it can be used to identify files that meet specific criteria. It does this through the (slightly strange) application of tests, actions, and options. We’ll look at the tests first.
  Tests
  Let’s say that we want a list of directories from our search. To do this, we could add the following test:
  [me@linuxbox ~]$ find ~ -type d | wc -l 1695
        Searching for Files 189
  Adding the test -type d limited the search to directories. Conversely, we could have limited the search to regular files with this test:
  [me@linuxbox ~]$ find ~ -type f | wc -l 38737
  Table 17-1 lists the common file-type tests supported by find. Table 17-1: find File Types
     File Type
  b c d f l
  Description
  Block special device file Character special device file Directory
  Regular file
  Symbolic link
            We can also search by file size and filename by adding some additional tests. Let’s look for all the regular files that match the wildcard pattern *.JPG and are larger than 1 megabyte:
  [me@linuxbox ~]$ find ~ -type f -name "*.JPG" -size +1M | wc -l 840
  In this example, we add the -name test followed by the wildcard pattern. Notice that we enclose it in quotes to prevent pathname expansion by the shell. Next, we add the -size test followed by the string +1M. The leading plus sign indicates that we are looking for files larger than the specified number. A leading minus sign would change the string to mean "smaller than the specified number." Using no sign means "match the value exactly." The trailing letter M indicates that the unit of measurement is megabytes. The characters shown in Table 17-2 may be used to specify units.
  Table 17-2: find Size Units
  Character Unit
  b 512-byte blocks (the default if no unit is specified)
  c Bytes
  w 2-byte words
  k Kilobytes (units of 1024 bytes)
  M Megabytes (units of 1,048,576 bytes)
  G Gigabytes (units of 1,073,741,824 bytes)
                 190 Chapter 17
  find supports a large number of different tests. Table 17-3 provides a rundown of the common ones. Note that in cases where a numeric argu- ment is required, the same + and - notation discussed above can be applied.
  Table 17-3: find Tests
   Test
  -cmin n
  -cnewer file -ctime n
  -empty -group name
  -iname pattern -inum n
  -mmin n -mtime n -name pattern -newer file
  -nouser
  -nogroup
  Description
  Match files or directories whose content or attributes were last modified exactly n minutes ago. To specify fewer than n minutes ago, use -n; to specify more than n minutes ago, use +n.
  Match files or directories whose contents or attributes were last modified more recently than those of file.
  Match files or directories whose contents or attributes (i.e., permissions) were last modified n*24 hours ago.
  Match empty files and directories.
  Match file or directories belonging to group name. name may be expressed as either a group name or as a numeric group ID.
  Like the -name test but case insensitive.
  Match files with inode number n. This is helpful for finding
  all the hard links to a particular inode.
  Match files or directories whose contents were modified n minutes ago.
  Match files or directories whose contents only were last modified n*24 hours ago.
  Match files and directories with the specified wildcard pattern.
  Match files and directories whose contents were modified more recently than the specified file. This is very useful when writing shell scripts that perform file backups. Each time you make a backup, update a file (such as a log) and then use find to determine which files have changed since the last update.
  Match file and directories that do not belong to a valid user. This can be used to find files belonging to deleted accounts or to detect activity by attackers.
  Match files and directories that do not belong to a valid group.
  (continued ) Searching for Files 191

  Table 17-3 (continued )
   Test
  -perm mode
  -samefile name
  -size n -type c -user name
  Description
  Match files or directories that have permissions set to the specified mode. mode may be expressed by either octal or symbolic notation.
  Similar to the -inum test. Matches files that share the same inode number as file name.
  Match files of size n. Match files of type c.
  Match files or directories belonging to name. name may be expressed by a username or by a numeric user ID.
            This is not a complete list. The find man page has all the details. Operators
  Even with all the tests that find provides, we may still need a better way to describe the logical relationships between the tests. For example, what if we needed to determine if all the files and subdirectories in a directory had secure permissions? We would look for all the files with permissions that are not 0600 and the directories with permissions that are not 0700. Fortunately, find provides a way to combine tests using logical operators to create more complex logical relationships. To express the aforementioned test, we could do this:
  [me@linuxbox ~]$ find ~ \( -type f -not -perm 0600 \) -or \( -type d -not -perm 0700 \)
  Yikes! That sure looks weird. What is all this stuff? Actually, the opera- tors are not that complicated once you get to know them (see Table 17-4).
  Table 17-4: find Logical Operators
  Operator Description
  -and Match if the tests on both sides of the operator are true. May be shortened to -a. Note that when no operator is present, -and is
  implied by default.
  -or Match if a test on either side of the operator is true. May be
  shortened to -o.
  -not Match if the test following the operator is false. May be shortened to -!.
           192 Chapter 17
  Table 17-4 (continued )
   Operator
  ( )
  Description
  Groups tests and operators together to form larger expressions. This is used to control the precedence of the logical evaluations. By default, find evaluates from left to right. It is often necessary to override the default evaluation order to obtain the desired result. Even if not needed, it is helpful sometimes to include the grouping characters to improve readability of the command. Note that since the parentheses characters have special meaning to the shell, they must be quoted when using them on the command line to allow them to be passed as arguments to find. Usually the backslash character is used to escape them.
    With this list of operators in hand, let’s deconstruct our find command. When viewed from the uppermost level, we see that our tests are arranged as two groupings separated by an -or operator:
  (expression 1) -or (expression 2)
  This makes sense, since we are searching for files with a certain set of permissions and for directories with a different set. If we are looking for both files and directories, why do we use -or instead of -and? Because as find scans through the files and directories, each one is evaluated to see if it matches the specified tests. We want to know if it is either a file with bad permissions or a directory with bad permissions. It can’t be both at the same time. So if we expand the grouped expressions, we can see it this way:
          (file with bad perms) -or (directory with bad perms)
  Our next challenge is how to test for "bad permissions." How do we do that? Actually we don’t. What we will test for is "not good permissions," since we know what "good permissions" are. In the case of files, we define good as 0600; for directories, 0700. The expression that will test files for "not good" permissions is:
          -type f -and -not -perms 0600
  and the expression for directories is:
          -type d -and -not -perms 0700
  As noted in Table 17-4, the -and operator can be safely removed, since it is implied by default. So if we put this all back together, we get our final command:
          find ~ (-type f -not -perms 0600) -or (-type d -not -perms 0700)
  However, since the parentheses have special meaning to the shell, we must escape them to prevent the shell from trying to interpret them. Pre- ceding each one with a backslash character does the trick.
  Searching for Files 193
  There is another feature of logical operators that is important to under- stand. Let’s say that we have two expressions separated by a logical operator:
  expr1 -operator expr2
  In all cases, expr1 will always be performed; however, the operator will
  determine if expr2 is performed. Table 17-5 shows how it works. Table 17-5: find AND/OR Logic
   Results of expr1 Operator True -and
  False -and
  True -or
  False -or
  expr2 is... Always performed Never performed Never performed Always performed
              Why does this happen? It’s done to improve performance. Take -and, for example. We know that the expression expr1 -and expr2 cannot be true if the result of expr1 is false, so there is no point in performing expr2. Likewise, if we have the expression expr1 -or expr2 and the result of expr1 is true, there is no point in performing expr2, as we already know that the expression expr1 -or expr2 is true.
  Okay, so this helps things go faster. Why is this important? Because we can rely on this behavior to control how actions are performed, as we shall soon see.
  Actions
  Let’s get some work done! Having a list of results from our find command is useful, but what we really want to do is act on the items on the list. Fortu- nately, find allows actions to be performed based on the search results.
  Predefined Actions
  There are a set of predefined actions and several ways to apply user-defined actions. First let’s look at a few of the predefined actions in Table 17-6.
  Table 17-6: Predefined find Actions
  Action Description
  -delete Delete the currently matching file.
  -ls Perform the equivalent of ls -dils on the matching file.
  Output is sent to standard output.
  -print Output the full pathname of the matching file to standard output. This is the default action if no other action is specified.
         194 Chapter 17
  Table 17-6 (continued ) Action Description
  -quit Quit once a match has been made.
  As with the tests, there are many more actions. See the find man page for full details.
  In our very first example, we did this:
  find ~
  This command produced a list of every file and subdirectory contained within our home directory. It produced a list because the -print action is implied if no other action is specified. Thus, our command could also be expressed as
  find ~ -print
  We can use find to delete files that meet certain criteria. For example, to delete files that have the file extension .BAK (which is often used to desig- nate backup files), we could use this command:
            find ~ -type f -name '*.BAK' -delete
  In this example, every file in the user’s home directory (and its sub- directories) is searched for filenames ending in .BAK. When they are found, they are deleted.
  Warning: It should go without saying that you should use extreme caution when using
  the -delete action. Always test the command first by substituting the -print action for -delete to confirm the search results.
  Before we go on, let’s take another look at how the logical operators affect actions. Consider the following command:
            find ~ -type f -name '*.BAK' -print
  As we have seen, this command will look for every regular file (-type f) whose name ends with .BAK (-name '*.BAK') and will output the relative path- name of each matching file to standard output (-print). However, the reason the command performs the way it does is determined by the logical relation- ships between each of the tests and actions. Remember, there is, by default, an implied -and relationship between each test and action. We could also express the command this way to make the logical relationships easier to see:
            find ~ -type f -and -name '*.BAK' -and -print
  With our command fully expressed, let’s look at Table 17-7 to see how the logical operators affect its execution.
                 Searching for Files 195
  Table 17-7: Effect of Logical Operators
   Test/Action
  -print
  -name '*.BAK'
  -type f
  Is performed when...
  -type f and -name '*.BAK' are true. -type f is true.
  Is always performed, since it is the first test/action in an -and relationship.
        Since the logical relationship between the tests and actions determines which of them are performed, we can see that the order of the tests and actions is important. For instance, if we were to reorder the tests and actions so that the -print action was the first one, the command would behave much differently:
  find ~ -print -and -type f -and -name '*.BAK'
  This version of the command will print each file (the -print action always evaluates to true) and then test for file type and the specified file extension.
  User-Defined Actions
  In addition to the predefined actions, we can also invoke arbitrary com- mands. The traditional way of doing this is with the -exec action, like this:
  -exec command {} ;
  where command is the name of a command, {} is a symbolic representation
  of the current pathname, and the semicolon is a required delimiter indicat- ing the end of the command. Here’s an example of using -exec to act like the -delete action discussed earlier:
  -exec rm '{}' ';'
  Again, since the brace and semicolon characters have special meaning to the shell, they must be quoted or escaped.
  It’s also possible to execute a user-defined action interactively. By using the -ok action in place of -exec, the user is prompted before execution of each specified command:
  find ~ -type f -name 'foo*' -ok ls -l '{}' ';'
  < ls ... /home/me/bin/foo > ? y
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo < ls ... /home/me/foo.txt > ? y
  -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  In this example, we search for files with names starting with the string foo and execute the command ls -l each time one is found. Using the -ok action prompts the user before the ls command is executed.
        196 Chapter 17
  Improving Efficiency
  When the -exec action is used, it launches a new instance of the specified command each time a matching file is found. There are times when we might prefer to combine all of the search results and launch a single instance of the command. For example, rather than executing the commands like this,
  ls -l file1 ls -l file2
  we may prefer to execute them this way:
  ls -l file1 file2
  Here we cause the command to be executed only one time rather than multiple times. There are two ways we can do this: the traditional way, using the external command xargs, and the alternative way, using a new feature in find itself. We’ll talk about the alternative way first.
  By changing the trailing semicolon character to a plus sign, we activate the ability of find to combine the results of the search into an argument list for a single execution of the desired command. Going back to our example,
        find ~ -type f -name 'foo*' -exec ls -l '{}' ';'
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  will execute ls each time a matching file is found. By changing the com- mand to
        find ~ -type f -name 'foo*' -exec ls -l '{}' +
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  we get the same results, but the system has to execute the ls command only once.
  We can also use the xargs command to get the same result. xargs accepts input from standard input and converts it into an argument list for a speci- fied command. With our example, we would use it like this:
        find ~ -type f -name 'foo*' -print | xargs ls -l
  -rwxr-xr-x 1 me me 224 2011-10-29 18:44 /home/me/bin/foo -rw-r--r-- 1 me me 0 2012-09-19 12:53 /home/me/foo.txt
  Here we see the output of the find command piped into xargs, which, in turn, constructs an argument list for the ls command and then executes it.
  Note: While the number of arguments that can be placed into a command line is quite large, it’s not unlimited. It is possible to create commands that are too long for the shell to accept. When a command line exceeds the maximum length supported by the system, xargs executes the specified command with the maximum number of arguments pos- sible and then repeats this process until standard input is exhausted. To see the max- imum size of the command line, execute xargs with the --show-limits option.
        Searching for Files 197
     DEALING WITH FUNNY FILENAMES
  Unix-like systems allow embedded spaces (and even newlines!) in filenames. This causes problems for programs like xargs that construct argument lists for other programs. An embedded space will be treated as a delimiter, and the resulting command will interpret each space-separated word as a separate argument. To overcome this, find and xarg allow the optional use of a null char- acter as argument separator. A null character is defined in ASCII as the charac- ter represented by the number zero (as opposed to, for example, the space character, which is defined in ASCII as the character represented by the num- ber 32). The find command provides the action -print0, which produces null- separated output, and the xargs command has the --null option, which accepts null separated input. Here’s an example:
     find ~ -iname '*.jpg' -print0 | xargs --null ls -l
     Using this technique, we can ensure that all files, even those containing embedded spaces in their names, are handled correctly.
    A Return to the Playground
  It’s time to put find to some (almost) practical use. First, let’s create a play- ground with lots of subdirectories and files:

  [me@linuxbox ~]$ mkdir -p playground/dir-{00{1..9},0{10..99},100} [me@linuxbox ~]$ touch playground/dir-{00{1..9},0{10..99},100}/file-{A..Z}

  Marvel in the power of the command line! With these two lines, we cre- ated a playground directory containing 100 subdirectories, each containing 26 empty files. Try that with the GUI!

  The method we employed to accomplish this magic involved a familiar command (mkdir); an exotic shell expansion (braces); and a new command, touch. By combining mkdir with the -p option (which causes mkdir to create the parent directories of the specified paths) with brace expansion, we were able to create 100 directories.
  The touch command is usually used to set or update the modification times of files. However, if a filename argument is that of a non-existent file, an empty file is created.
  In our playground, we created 100 instances of a file named file-A. Let’s find them:
  [me@linuxbox ~]$ find playground -type f -name 'file-A'
  Note that unlike ls, find does not produce results in sorted order. Its order is determined by the layout of the storage device. We can confirm that we actually have 100 instances of the file this way:
  [me@linuxbox ~]$ find playground -type f -name 'file-A' | wc -l 100
        198 Chapter 17
  Next, let’s look at finding files based on their modification times. This will be helpful when creating backups or organizing files in chronological order. To do this, we will first create a reference file against which we will compare modification time:
  [me@linuxbox ~]$ touch playground/timestamp
  This creates an empty file named timestamp and sets its modification time to the current time. We can verify this by using another handy com- mand, stat, which is a kind of souped-up version of ls. The stat command reveals all that the system understands about a file and its attributes:
  [me@linuxbox ~]$ stat playground/timestamp
  File: `playground/timestamp'
  Size: 0 Blocks: 0 IO Block: 4096 regular empty file
  Device: 803h/2051d Inode: 14265061 Links: 1
  Access: (0644/-rw-r--r--)  Uid: ( 1001/ me)   Gid: ( 1001/ me)
  Access: 2012-10-08 15:15:39.000000000 -0400
  Modify: 2012-10-08 15:15:39.000000000 -0400
  Change: 2012-10-08 15:15:39.000000000 -0400
  If we touch the file again and then examine it with stat, we will see that the file’s times have been updated:
  [me@linuxbox ~]$ touch playground/timestamp [me@linuxbox ~]$ stat playground/timestamp
    File: `playground/timestamp'
  Size: 0 Blocks: 0 IO Block: 4096 regular empty file Device: 803h/2051d Inode: 14265061 Links: 1
  Access: (0644/-rw-r--r--) Uid: ( 1001/ me) Gid: ( 1001/ me) Access: 2012-10-08 15:23:33.000000000 -0400
  Modify: 2012-10-08 15:23:33.000000000 -0400
  Change: 2012-10-08 15:23:33.000000000 -0400
  Next, let’s use find to update some of our playground files: [me@linuxbox ~]$ find playground -type f -name 'file-B' -exec touch '{}' ';'
  This updates all files in the playground that are named file-B. Next we’ll use find to identify the updated files by comparing all the files to the refer- ence file timestamp:
  [me@linuxbox ~]$ find playground -type f -newer playground/timestamp
  The results contain all 100 instances of file-B. Since we performed
  a touch on all the files in the playground that are named file-B after we updated timestamp, they are now "newer" than timestamp and thus can be identified with the -newer test.
  Finally, let’s go back to the bad permissions test we performed earlier and apply it to playground:
  [me@linuxbox ~]$ find playground \( -type f -not -perm 0600 \) -or \( -type d -not -perm 0700 \)
              Searching for Files 199
  This command lists all 100 directories and 2,600 files in playground (as well as timestamp and playground itself, for a total of 2,702) because none of them meets our definition of "good permissions." With our knowledge of operators and actions, we can add actions to this command to apply new permissions to the files and directories in our playground:
  [me@linuxbox ~]$ find playground \( -type f -not -perm 0600 -exec chmod 0600 '{}' ';' \) -or \( -type d -not -perm 0700 -exec chmod 0700 '{}' ';' \)
  On a day-to-day basis, we might find it easier to issue two commands, one for the directories and one for the files, rather than this one large compound command, but it’s nice to know that we can do it this way. The important point here is to understand how operators and actions can be used together to perform useful tasks.
  Options
  Finally, we have the options. The options are used to control the scope of a find search. They may be included with other tests and actions when con- structing find expressions. Table 17-8 lists the most commonly used options.
  Table 17-8: find Options

  Option
  -depth
  -maxdepth levels -mindepth levels -mount
  -noleaf
  Description
  Direct find to process a directory’s files before the directory itself. This option is automatically applied when the -delete action is specified.
  Set the maximum number of levels that find will descend into a directory tree when performing tests and actions.
  Set the minimum number of levels that find will descend into a directory tree before applying tests and actions.
  Direct find not to traverse directories that are mounted on other filesystems.
  Direct find not to optimize its search based on the assumption that it is searching a Unix-like filesystem. This is needed when scanning DOS/Windows file- systems and CD-ROMs.

### VO 600w
  find is one of UNIX's most useful and important utilities. It finds files that match a given set of parameters, ranging from the file's name to its modification date.

  $ find path operators

  where path is the directory in which find will begin to search and operators (or, in more customary jargon, options ) tell find which files you're interested in. The operators are:

  -name   filename

  Find files with the given filename . This is the most commonly used operator. filename may include wildcards ( 15.2 ) , but if it does, it must be quoted to prevent the shell from interpreting the wildcards. See article 17.4 .

  -type   d

  *attibutes

  -perm   mode
  -user   name
  -group   name
  -size   n

  *time range
  -atime   n

  Find files that were accessed n days ago. + n means "find files that were accessed over n days ago" (i.e., not accessed in the last n days). - n means "find files that were accessed less than n days ago" (i.e., accessed in the last n days). See articles 17.5 and 17.7 .

  -mtime   n

  Similar to atime , except that it checks the time the file's contents were modified. See articles 17.5 and 17.7 .

  -ctime   n

  Similar to atime , except that it checks the time the inode ( 1.22 ) was last changed. "Changed" means that the file was modified or that one of its attributes (for example, its owner) was changed. See articles 17.5 and 17.7 .
  -newer   file

  Find files that have been modified more recently than the given file . See articles 17.8 and 17.9 .

  If you want to find a file that is seven days old, use the -mtime operator:

  $ find . -mtime 7 -print

  An alternate way is to specify a range of times:

  % find . -mtime +6 -mtime -8 -print

  mtime is the last modified time of a file. If you want to look for files that have not been used, check the access time with the -atime argument. A command to list all files that have not been read in 30 days or more is:

  $ find . -type f -atime +30 -print

  It is difficult to find directories that have not been accessed because the find command modifies the directory's access time.

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

  The -exec is a bit odd. Any filename making it this far will become part of a com- mand that is executed. The remainder of the lineup to the \; is the command to be executed. The {} is replaced by the name of the file that was found.

  *logical operators

  find -and -not -perms 0700

  find ~ (-type f -not -perms 0600) -or (-type d -not -perms 0700)
  -and
  -or
  -not

  *text search

  grep global regular expression print

  regular expressions describes patterns in text. similar to wildcards

  grep searches text files for the occurrence of a specified regular expression and outputs any line containing a match to standard output.
  [me@linuxbox ~]$ ls /usr/bin | grep zip

  This will list all the files in the /usr/bin directory whose names contain the substring zip.

  Option Description

  -i Ignore case. --ignore-case.

  -v Invert match.

  -c Print the number of matches instead of the lines themselves.

  -l
  Print the name of each file that contains a match instead of the lines

  -L
  Like the -l option, but print only the names of files that do not contain matches. May also be specified --files-without-match.

  -n Prefix each matching line with the number of the line within the file.

  -h For multifile searches, suppress the output of filenames.

  FURTHER EXPLORATION: mdfind, mdls, mdutil

