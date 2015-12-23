
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

  Command line substitution : ` ` or $() (in pipe section)

## Examples
  (in notes)

  *sed
  *tr
  *cut
  (history 50 | grep find | cut -c 8-99 | pbcopy)

  *sort

  head data/train.csv | sort -t ',' -k 1
  head data/train.csv | sort -t ',' -k 3,4 -n
  head data/train.csv | sort -t ',' -k 4 -n

  *uniq
  *wc

  man sort
  man uniq
  man wc

  history | cut -d ' ' -f 3-99
  history | cut -d ' ' -f 3-99 | sort
  history | cut -d ' ' -f 3-99 | sort | uniq
  history | cut -d ' ' -f 3-99 | sort | uniq | wc -l

  history | cut -d ' ' -f 3-99 | sort | uniq -d | wc -l
  history | cut -d ' ' -f 3-99 | sort | uniq -d
  history | cut -d ' ' -f 3-99 | sort | uniq -d -c

  history | cut -d ' ' -f 3-99 | sort | uniq -c
  history | cut -d ' ' -f 3-99 | sort | uniq -c | sort -n

## Text processing 4m

  34.24 Quick Reference: sed

  How sed operates:

      Each line of input is copied into a pattern space.

      Editing commands may be given on the command line (if more than one, use a -e option before each command) and/or in script files named after -f options. All editing commands are applied in order to each line of input.

      Editing commands are applied to all lines (globally) unless line addressing restricts the lines affected.

      If a command changes the input, subsequent command-addresses will be applied to the current line in the pattern space, not the original input line.

      The original input file is unchanged; editing commands modify a copy of the original input line. The copy is sent to standard output ( 13.1 ) unless the -n option was used; standard output can be redirected to a file ( 13.1 , 34.3 ) .

  34.24.1 Syntax of sed Commands

  sed commands have the general form:

      [ address ][ , address ][ ! ] command [ arguments ]

  sed commands consist of addresses and editing commands . commands consist of a single letter or symbol; they are described later, alphabetically and by group. arguments include the label supplied to b or t , the filename supplied to r or w , and the substitution flags for s . addresses are described below. Elements in [ brackets ] are optional; don't type the brackets.

  Braces ( {} ) are used in sed to nest one address inside another or to apply multiple commands at the same address:

      [

      address

      ][
      ,


      address

      ]{


      command1
         command2


      }

  The left curly brace ( { ) is a command that starts a group of other sed commands. The group ends with a right curly brace ( } ). Commands within the braces may be spread across multiple lines, as shown above. Or commands may be on the same line, with a semicolon ( ; ) after each command (including the last command on a line) - as in:

      [ address ][ , address ] { command1 ; ... commandN ; }

  34.24.2 Pattern Addressing

  A sed command can specify zero, one, or two addresses. An address can be a line number, the symbol $ (for last line), or a regular expression enclosed in slashes ( / pattern / ). Regular expressions are described in Chapter 26, Regular Expressions (Pattern Matching) . Additionally, \n can be used to match any newline in the pattern space (resulting from the N command), but not the newline at the end of the pattern space. See article 34.4 .
  If the command specifies: 	Then it is applied to:
  No address

  Each input line.
  One address

  Any line matching the address. Some commands accept only one address: a , i , r , q , and = .
  Two comma-separated addresses

  First matching line and all succeeding lines up to and including a line matching the second address. Repeat for each matching range in the text.
  An address followed by !

  All lines that do not match the address.
  34.24.2.1 Examples

  Substitute on all lines (all occurrences):

      s/xx/yy/g

  Delete lines containing BSD :

      /BSD/d

  Print the lines between each pair of BEGIN and END , inclusive:

      /^BEGIN/,/^END/p

  Delete any line that doesn't contain SAVE :

      /SAVE/!d

  Substitute on all lines, except between BEGIN and END :

      /BEGIN/,/END/!s/xx/yy/g

  34.24.3 Alphabetical Summary of sed Commands

  #

      Begin a comment in a sed script. If the first such line is exactly #n , sed sets its -n command-line option.
  :

      : label

      Label a line in the script for the transfer of control by b or t . label may contain up to seven characters.
  =

      [ address ] =

      Write to standard output the line number of each line addressed.
  a

          [ address ]a\
          text

      Append text following each line matched by address . If there is more than one line of text , all newlines except the last must be "hidden" by preceding them with a backslash. text will be terminated by the first newline that is not hidden in this way. text is not available in the pattern space, and subsequent commands cannot be applied to it. The results of this command are sent to standard output when the list of editing commands is finished, regardless of what happens to the current line in the pattern space. (There's an example in article 43.22 , among others.)

      Example

          $a\
          This goes after the last line in the file\
          (marked by $). This text is escaped at the\
          end of each line, except for the last one.

  b

      [ address1 ][, address2 ] b[ label ]

      Transfer control unconditionally to : label elsewhere in script. That is, the command following the label is the next command applied to the current line. If no label is specified, control falls through to the end of the script, so no more commands are applied to the current line. See articles 34.19 and 34.17 .

      Example

          # Ignore tbl tables; resume script after TE:
          /^\.TS/,/^\.TE/b

  c

          [ address1 ][ , address2 ]c\
          text

      Replace the lines selected by the address with text . When a range of lines is specified, all lines as a group are replaced by a single copy of text . The newline following each line of text must be escaped by a backslash, except the last line. The contents of the pattern space are, in effect, deleted and no subsequent editing commands can be applied to it (or text ).

      Example

          # Replace first 100 lines in a file:
          1,100c\

          ...first replacement line
          \

          ...second replacement line
          \

          ...
          \

          ...last replacement line

  d

      [ address1 ][, address2 ]d

      Delete the addressed line (or lines) from the pattern space. Thus, the line is not passed to standard output. A new line of input is read, and editing resumes with the first command in the script. See articles 34.4 and 34.18 .

      Example

          # delete all blank lines:
          /^$/d

  D

      [ address1 ][ , address2 ] D

      Delete first part (up to embedded newline) of multiline pattern space created by N command and resume editing with first command in script. If this command empties the pattern space, then a new line of input is read, as if d had been executed. See article 34.18 .

      Example

          # Strip multiple blank lines, leaving only one:
          /^$/{
              N
              /^\n$/D
          }

  g

      [ address1 ][, address2 ]g

      Paste the contents of the hold space (see h or H ) back into the pattern space, wiping out the previous contents of the pattern space. See articles 34.13 and 34.16 . The example shows a simple way to copy lines.

      Example

      This script collects all lines containing the word Item: and copies them to a place marker later in the file. The place marker is overwritten.

          /Item:/H
          /<Replace this line with the item list>/g

  G

      [ address1 ][ , address2 ] G

      Same as g , except that the hold space is pasted below the address instead of overwriting it. The example shows a simple way to "cut and paste" lines. See articles 34.13 and 34.16 .

      Example

      This script collects all lines containing the word Item: and moves them after a place marker later in the file. The original Item: lines are deleted.

          /Item:/{
              H
              d
          }
          /Summary of items:/G

  h

      [ address1 ][ , address2 ] h Copy the pattern space into the hold space, a special temporary buffer. The previous contents of the hold space are obliterated. You can use h to save a line before editing it. See articles 34.13 and 34.16 .

      Example

          # Edit a line; print the change; replay the original
          /UNIX/{
              h
              s/.* UNIX \(.*\) .*/\1:/
              p
              x
          }

      Sample input:

          This describes the UNIX ls command.
          This describes the UNIX cp command.

      Sample output:

          ls:
          This describes the UNIX ls command.
          cp:
          This describes the UNIX cp command.

  H

      [ address1 ][ , address2 ] H

      Append the contents of the pattern space (preceded by a newline) to the contents of the hold space. Even if the hold space is empty, H still appends a newline. H is like an incremental copy. See examples under g and G , also articles 34.13 and 34.16 .
  i

          [ address ]i\
          text

      Insert text before each line matched by address . (See a for details on text .) Article 43.20 shows a script that uses i .

      Example

          /Item 1/i\
          The five items are listed below:

  l

      [ address1 ][ , address2 ] l

      List the contents of the pattern space, showing non-printing characters as ASCII codes ( 51.3 , 25.7 ) . Long lines are wrapped.
  n

      [ address1 ][ , address2 ] n

      Read next line of input into pattern space. The current line is sent to standard output, and the next line becomes the current line. Control passes to the command following n instead of resuming at the top of the script.

      Example

      In the ms macros ( 43.14 ) , a section header occurs on the line below an .NH macro. To print all lines of header text, invoke this script with sed -n :

          /^\.NH/{
              n
              p
          }

  N

      [ address1 ][ , address2 ] N

      Append next input line to contents of pattern space; the two lines are separated by an embedded newline. (This command is designed to allow pattern matches across two lines.) Using \n to match the embedded newline, you can match patterns across multiple lines. See example under D , also article 34.15 .

      Examples

      Like previous example, but print .NH line as well as header title:

          /^\.NH/{
              N
              p
          }

      Join two lines (replace newline with space):

          /^\.NH/{
              N
              s/\n/ /
              p
          }

  p

      [ address1 ][ , address2 ] p

      Print the addressed line(s). Unless the -n command-line option is used, this command will cause duplicate lines to be output. Also, it is typically used before commands that change flow control ( d , N , b ) and that might prevent the current line from being output. See examples under h , n , and N .
  P

      [ address1 ][ , address2 ] P

      Print first part (up to embedded newline) of multiline pattern created by N command. Same as p if N has not been applied to a line.

      Example

      The following script prints each line containing word and also the line before it:

          N
          /

          word

          /P
          D

  q

      [ address ] q

      Quit when address is encountered. The addressed line is first written to output (if default output is not suppressed), along with any text appended to it by previous a or r commands. See articles 34.21 and 34.22 .

      Example

      Delete everything after the addressed line:

          /Garbled text follows:/q

      Print only the first 50 lines of a file:

          50q

  r

      [ address ] r file

      Read contents of file and append after the contents of the pattern space. Exactly one space must be put between the r and file .

      Example

          /The list of items follows:/r item_file

  s

      [ address1 ][ , address2 ] s/ pattern / replacement / [ flags ]

      Substitute replacement for pattern on each addressed line. If pattern addresses are used, the pattern // represents the last pattern address specified. The following flags can be specified:

      n

          Replace n th instance of / pattern / on each addressed line. n is any number in the range 1 to 512 (default is 1). See article 34.11 .
      g

          Replace all instances of / pattern / on each addressed line, not just the first instance.
      p

          Print the line if a successful substitution is done. If several successful substitutions are done, multiple copies of the line will be printed. Often used in scripts with the -n command-line option ( 34.2 ) .
      w  file

          Write the line to a file if a replacement was done. A maximum of ten different files can be opened in a script. See articles 34.7 through 34.10 .

          Examples

          Here are some short, commented scripts:

              # Change third and fourth quote to ( and ):
              /function/{
                  s/"/)/4
                  s/"/(/3
              }

              # Remove all quotes on a given line:
              /Title/s/"//g

              # Remove first colon or all quotes; print resulting lines:
              s/://p
              s/"//gp

              # Change first "if" but leave "ifdef" alone:
              /ifdef/!s/if/   if/

  t

      [ address1 ][ , address2 ] t [ label ]

      Test if any substitutions have been made on addressed lines, and if so, branch to line marked by : label . (See b and : .) If label is not specified, control falls through to bottom of script. See article 34.20 .

      The t command can be used like a case statement ( 44.5 ) in the Bourne shell. You test each case: when it's true, you exit the construct.

      Example

      Suppose you want to fill empty fields of a database. You have this:

          ID: 1   Name: greg   Rate: 45
          ID: 2   Name: dale
          ID: 3

      You want this:

          ID: 1   Name: greg   Rate: 45   Phone: ??
          ID: 2   Name: dale   Rate: ??   Phone: ??
          ID: 3   Name: ????   Rate: ??   Phone: ??

      You need to test the number of fields already there. Here's the script (fields are tab-separated):

          /ID/{
              s/ID: .* Name: .* Rate: .*/&   Phone: ??/p
              t
              s/ID: .* Name: .*/&   Rate: ??   Phone: ??/p
              t
              s/ID: .*/&   Name: ??     Rate: ??   Phone: ??/p
          }

  w

      [ address1 ][ , address2 ] w file

      Append, contents of pattern space to file . This action occurs when the command is encountered rather than when the pattern space is output. Exactly one space must separate the w and file . A maximum of ten different files can be opened in a script. This command will create the file if it does not exist; if the file exists, its contents will be overwritten each time the script is executed. Multiple write commands that direct output to the same file append to the end of the file.

      Example

          # Store tbl and eqn blocks in a file:
          /^\.TS/,/^\.TE/w troff_stuff
          /^\.EQ/,/^\.EN/w troff_stuff

  x

      [ address1 ][ , address2 ] x

      Exchange contents of the pattern space with the contents of the hold space. For examples, see h and articles 34.13 and 34.16 .
  y

      [ address1 ][ , address2 ] y/ abc / xyz /

      Translate characters. Change every instance of a to x , b to y , c to z , etc. See articles 34.12 and 34.14 .

      Example

          # Change item 1, 2, 3 to Item A, B, C ...
          /^item [1-9]/y/i123456789/IABCDEFGHI/


  Pipes and Filters

  We’ve seen how to redirect input from a file and output to a file. You can also connect two programs together so the output from one program becomes the input of the next, without ever being written to disk. Two or more programs connected in this way form a pipe. To make a pipe, place a vertical bar (|) on the command line between the two commands.
  When a pipe is set up between two commands, the standard output of the command to the left of the pipe symbol becomes the standard input of the command to the right of the pipe symbol. Any two commands can form a pipe, as long as the first program writes to standard output and the second program reads from standard input. For example:
  $ ls -l $HOME | colrm 1 30 714 Jul 29 23:16 Desktop
      1020 Jul 19 23:39 Documents
       238 Jul 30 07:22 Downloads
       408 Jul 28 07:14 Dropbox
       714 Jul 24 08:47 Google Drive
      1768 Jul 29 23:00 Library
       340 Jul 26 14:54 Movies
       204 Jul 19 22:53 Music
       408 Jul 24 11:59 Pictures
      1938 Jul  9 16:52 Presentations
       170 Jul 19 10:04 Public
       408 Jul 20 07:20 bin
   Pipes and Filters
  | 141
  This example combines ls -l with the colrm (column remove) command to give you a listing that just includes file size, modification date, and name.
  You could take this example one step further and redirect its output to a file; for example:
  $ ls -l | colrm 1 30 > homedirlist.txt
  That command line starts by listing the files, uses colrm to strip out the extraneous information that ls -l returns, and then redirects the re­ maining information into a new file, named homedirlist.txt.
  You just can’t do that in the Finder.
  When a program takes its input from another program, performs some operation on that input, and writes the result to the standard output (or pipes it to yet another pro­ gram), it is referred to as a filter. A common use of filters is to modify output. Just as a common filter culls unwanted items, Unix filters can restructure output so you get just what you need.
  Most Unix programs can be used to form pipes. Some programs that are commonly used as filters are described in the next sections. (Note that these programs aren’t used only as filters or parts of pipes, though; they’re also useful in their own right.)
  wc
  The wc program is one of the most useful pipe programs, believe it or not. By default, the program counts characters, words, and lines in the input file or standard input, but you can constrain the output to just characters (-c), words (-w), or lines (-l). Counting lines turns out to be wonderfully useful.
  A classic example is identifying how many "core" files are in the filesystem.
  Core files are identified with the suffix .core; they’re crashed program debugging datafiles and can be deleted to free up disk space as needed.
  This is done with a call to find with the output piped to wc:
  $ sudo find / -name "*.core" -print | wc -l 13
  $
  sudo helps sidestep any permissions problems here.
     142 | Chapter 6: Redirecting I/O
  A more common use of find and wc together is to count larger output streams. For example, wondering how many directories you have within your Documents directory? You might be surprised:
  $ find ~/Documents -type d -print | wc -l 1064
  You can see how having a single number displayed is far superior to having all 1,064 directory names stream past!
  tr
  Another simple and helpful program for command pipes is tr, the translator utility. The most common use for this command is to replace all occurrences of one character with another character. Here’s how you would replace all occurrences of x with y:
  tr "x" "y"
  More usefully, tr can also work with sets of characters (you can either list them all in a range or specify a named range like lower or alpha), so it’s an easy way to turn all low­ ercase text into uppercase:
      tr "[:lower:]" "[:upper:]" < file1
  For example:
  $ tr "[:lower:]" "[:upper:]" < todo 1. WAKE UP
  2. LOOK IN MIRROR
  3. SIGH
      4. GO BACK TO BED.
      $
  The tr command has a number of different options for power users, including -c to invert the specified pattern (that is, if you specify tr -c "abc", the program matches anything other than a, b, or c), and -d deletes any characters from the first pattern specified.
  To remove all vowels from the input, you could use:
  $ tr -d "[aeiou]" < todo 1. Wk p
  2. Lk n mrrr
  3. Sgh
  4. G bck t bd.
  The tr command can be quite useful in other situations, too. Wondering how many words appear in a large text file? tr can figure this out with a little help from the -s flag, which tells it to output only one occurrence of a character if more than one is found:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | wc -l 29061
   Pipes and Filters | 143
  Here, we can see that Lewis Carroll’s Alice’s Adventures in Wonderland contains just over 29,000 words.
  You can download this text for yourself at http://www.intuitive.com/ wicked/scripts/alice.txt.gz.
  As with the wc command, tr may not seem too useful by itself, but when you start building up more complex pipes you’ll be surprised by how frequently it’s useful to translate case and fix similar problems.
  grep
  As you learned in the previous chapter, grep searches the contents of files for lines that contain a certain pattern. The syntax is:
  grep "pattern" file(s)
  Most of the earlier discussion, however, focused on how grep can help you search through files to find lines that match a specified pattern. In fact, grep is a tremendously useful command for pipes, too, because it can help you easily weed out the few lines you care about from hundreds or thousands of lines of information.
  As an example, let’s use the mdfind command to identify files on the system that reference the word "ipod" (mdfind, a part of Spotlight, is discussed in Chapter 5). The default command reveals that there are 1,030 matches, by using wc:
  $ mdfind ipod | wc -l 1030
  It turns out that many of these are actually related to the scripting Automator utility and other library files. They’re easily identified by their Library directory location, however, so grep, with its useful -v option (which returns everything but lines that match this pattern) helps us identify how many files aren’t in the Library subdirectory:
  $ mdfind ipod | grep -v "Library" | wc -l 150
  Of those 150, how many are within my home directory?
  $ mdfind ipod | grep -v "Library" | grep "/taylor/" | wc -l 82
  Notice here that you can build pipes that are 2, 3, 4, or even 10 or 20 commands long. Unix has no limit on how complex your pipes can be, and I commonly work with pipes that are six or seven commands long.
    144 | Chapter 6: Redirecting I/O
  head and tail
  When you have output of hundreds or thousands of lines, being able to peek in and see the first few or last few lines is critically important. Those two tasks are enabled by the helpful head and tail commands. With both commands, the default action is to show 10 lines (the first 10 for head, and the last 10 for tail). You can change this by specifying n, where n is the desired number of lines. To see just the first three lines, use head -3, and to see the last 15, use tail -15.
  For example, we can see that the last 15 words of Alice’s Adventures in Wonderland are:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | tail -15
      in
      all
      their
      simple
      joys
      remembering
      her
      own
      child
      life
      and
      the
      happy
      summer
      days
      $
  In addition to using head and tail to view the beginning or end of files, with a little bit of fancy footwork, you can use them to view any range of lines in a file. Want to see lines 131−134? You could use:
  $ head -134 alice.txt | tail -4
  Alice opened the door and found that it led into a small passage, not much larger than a rat-hole: she knelt down and looked along the passage into the loveliest garden you ever saw. How she longed to get out of that dark hall, and wander about among those beds of $
  This could also be accomplished by using other Unix commands, and that’s part of the power of Unix: there’s usually more than one way to solve a problem at the command line.
  sort
  The sort program arranges lines of text alphabetically or numerically. The following example alphabetically sorts the lines in the food file. sort doesn’t modify the file itself; it just reads the file and displays the result on standard output (in this case, the Terminal):
   Pipes and Filters | 145
  $ sort food Afghani Cuisine Bangkok Wok Big Apple Deli Isle of Java Mandalay
      Sushi and Sashimi
      Sweet Tooth
      Tio Pepe's Peppers
  By default, sort arranges lines of text alphabetically. Many options control the sorting, and Table 6-1 lists some of them.
  Table 6-1. Some sort options
  Option Description
  -n Sort numerically (for example, 10 sorts after 2); ignore blanks and tabs. -r Reverse the sorting order.
  -f Sort upper- and lowercase together.
  -kx Ignore firstxfields when sorting.
  Don’t forget that more than two commands may be linked together with a pipe. Taking a previous pipe example using grep, you can further sort the files modified in January by order of size. The following pipe uses the commands ls, grep, and sort:
  $ ls -l | grep "Jan" | sort -n -k 5
  drwx------ 2 taylor taylor 264 Jan 13 10:02 Music/ drwx------ 4 taylor taylor 264 Jan 29 22:33 Movies/ drwxr-xr-x 3 taylor taylor 264 Jan 24 21:24 Public/ drwx------ 95 taylor taylor 3186 Jan 29 22:44 Pictures/ $
  Both grep and sort are used here as filters to modify the output of the ls -l command. This pipe sorts all files in your working directory modified in January by order of size, and prints them to the Terminal screen. The sort option -n forces a numeric (rather than alphabetic) sort, and -k 5 uses the fifth field as the sort key. So, the output of ls, filtered by grep, is sorted by the file size (this is the fifth column, starting with 264).
  sort is also a powerful tool for identifying the extremes of a list. A common use is to identify the largest files on the system, which can be done by using find and xargs to generate a list of all files, one per line, including their size in 512-byte blocks, then feeding that to sort -rn (reverse, numeric) and looking at the top few:
  $ find . -type f -print0 | xargs -0 ls -s1 | sort -rn | head 14082048 ./Documents/Parallels/Ubuntu Linux 11.04 Desktop.pvm/
          ubuntu-linux-11.04-desktop-amd64-0.hdd/ubuntu-linux-11.04-desktop-amd...
      9474040 ./Music/iTunes/iTunes Media/Movies/Lawrence of Arabia/Lawrence of Ara...
      6316920 ./Music/iTunes/iTunes Media/Movies/Who Framed Roger Rabbit/Who Framed...
      6129352 ./Music/iTunes/iTunes Media/Movies/Dial 'M' For Murder/Dial 'M' For M...
      5774616 ./Music/iTunes/iTunes Media/Movies/Casablanca/Casablanca.mp4
      146
  | Chapter 6: Redirecting I/O
      5766976 ./Music/iTunes/iTunes Media/Movies/Tomb Raider - The Cradle of Life/T...
      5764848 ./Music/iTunes/iTunes Media/Movies/In The Shadow of the Moon/In The S...
      5559592 ./Documents/Entourage Mail Data/Database
      5559592 ./Documents/Microsoft User Data/Office 2008 Identities/
          Main Identity/Database
      5409584 ./Music/iTunes/iTunes Media/Movies/Tomb Raider/Tomb Raider.mp4
  Coupled with the power of find, you should be able to see how you can identify not only the largest files, but also the largest files owned by a particular user (hint: use find - user XX to match all files owned by that user).
  uniq
  Another command that’s quite useful in pipes is the oddly named uniq (which would be easier to remember if it were spelled correctly: unique). Give uniq a stream of input, and it silently eliminates duplicate lines. Add the -c flag, and uniq not only removes duplicate lines but lists a count of how frequently each line occurs.
  If you’re thinking that sort and uniq are a good pair, you’re absolutely correct! For ex­ ample, figuring out how many unique words occur in the book Alice’s Adventures in Wonderland is a simple task:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | uniq | wc -l 27313
  Or is it? That’s not correct, because in this situation, uniq needs to have the input sorted. Add that step and the number changes dramatically:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | sort | uniq | wc -l 2868
  Further, we should also ensure that all the letters are lowercase, so that "Hello" and "hello," for example, are counted as one word, not two. This can be done by using the - f (ignore case) flag to sort:
  $ tr -cs "[:alpha:]" "\n" < alice.txt | sort -f | uniq | wc -l 2577
  So now you know—the entire novel is written using only 2,577 different words.
  Piping Output to a Pager
  The less program, which you saw in Chapter 4, can also be used as a filter. A long output normally zips by you on the screen, but if you run text through less, the display stops after each page or screen of text (that’s why such programs are called pagers: they let you see the output page by page).
   Pipes and Filters | 147
  Let’s assume that you have a long directory listing. (If you want to try this example and need a directory with lots of files, use cd first to change to a system directory such as /bin or /usr/bin.) To make it easier to read the sorted listing, pipe the output through less:
  $ cd /bin
  $ ls -l | sort -nk 5 | less
  total 5976
  -rwxr-xr-x 1 root wheel
  -rwxr-xr-x 1 root wheel
  -r-xr-xr-x 1 root wheel
  -rwxr-xr-x 1 root wheel
  -r-xr-xr-x 1 root wheel
  -rwxr-xr-x 1 root wheel
  ...
  -rwxr-xr-x 1 root wheel 566144 May 5 18:54 zsh -r-xr-xr-x 1 root wheel 1333792 May 5 21:18 bash -r-xr-xr-x 1 root wheel 1333872 May 5 21:18 sh -r-xr-xr-x 1 root wheel 1380176 May 5 21:18 ksh
  less reads a screen of text from the pipe (consisting of lines sorted by order of file size), then prints a colon (:) prompt. At the prompt, you can type a less command to move through the sorted text. less reads more text from the pipe, shows it to you, and saves a copy of what it has read, so you can go backward to reread previous text if you want. When you’re done viewing the sorted text, type the q command at the colon prompt to quit less. Table 6-2 contains a list of useful commands to use along with less.
  Table 6-2. Useful less commands to remember
  Command Meaning
  d
  u
  b
  f /pat ?pat n
  :n v q
  Scroll down (forward) one half of the screen size. Scroll up (backward) one half the screen size. Scroll back one screen.
  Scroll forward one screen.
  Scroll forward until a line containing the specified pattern is found. Scroll back until a line containing the specified pattern is found.
  Repeat previous search.
  Move to the next file in the file list (if more than one file was specified). Open up the file in the vi editor.
  Quit.
  13984 May  5 18:54 sleep
  14048 May  5 18:54 echo
  14064 May  5 21:18 wait4path
  14096 May  5 21:18 rmdir
  14192 May  5 18:54 domainname
  14192 May  5 18:54 pwd

  sort—Sort Lines of Text Files
  The sort program sorts the contents of standard input, or one or more files specified on the command line, and sends the results to standard output. Using the same technique that we used with cat, we can demonstrate pro- cessing of standard input directly from the keyboard.
  [me@linuxbox ~]$ sort > foo.txt c
  b
  a
  [me@linuxbox ~]$ cat foo.txt a
  b
  c
      236 Chapter 20
  After entering the command, we type the letters c, b, and a, followed once again by CTRL-D to indicate end-of-file. We then view the resulting file and see that the lines now appear in sorted order.
  Since sort can accept multiple files on the command line as arguments, it is possible to merge multiple files into a single sorted whole. For example, if we had three text files and wanted to combine them into a single sorted file, we could do something like this:
  sort file1.txt file2.txt file3.txt > final_sorted_list.txt
  sort has several interesting options. Table 20-1 shows a partial list.
  Table 20-1: Common sort Options
  Option Long Option
   -b         --ignore-leading-blanks
  -f --ignore-case -n --numeric-sort
  -r --reverse
  -k --key=field1[,field2]
  -m --merge
  -o --output=file
  -t --field-separator=char
  Description
  By default, sorting is performed on the entire line, starting with the first char- acter in the line. This option causes sort to ignore leading spaces in lines and calculates sorting based on the first non-whitespace character on the line.
  Makes sorting case insensitive.
  Performs sorting based on the numeric evaluation of a string. Using this option allows sorting to be performed on numeric values rather than alphabetic values.
  Sort in reverse order. Results are in descending rather than ascending order.
  Sort based on a key field located from field1 to field2 rather than the entire line.
  Treat each argument as the name of a presorted file. Merge multiple files into a single sorted result without perform- ing any additional sorting.
  Send sorted output to file rather than to standard output.
  Define the field-separator character. By default, fields are separated by spaces or tabs.
                             Text Processing 237
  Although most of the options above are pretty self-explanatory, some are not. First, let’s look at the -n option, used for numeric sorting. With this option, it is possible to sort values based on numeric values. We can demon- strate this by sorting the results of the du command to determine the largest users of disk space. Normally, the du command lists the results of a summary in pathname order:
  [me@linuxbox ~]$ du -s /usr/share/* | head 252 /usr/share/aclocal
  96 /usr/share/acpi-support
  8 /usr/share/adduser
  196 /usr/share/alacarte 344 /usr/share/alsa
  8 /usr/share/alsa-base 12488 /usr/share/anthy
  8 /usr/share/apmd
  21440 /usr/share/app-install
   48
  /usr/share/application-registry
   In this example, we pipe the results into head to limit the results to the first 10 lines. We can produce a numerically sorted list to show the 10 largest consumers of space this way:
  [me@linuxbox ~]$ du -s /usr/share/* | sort -nr | head 509940 /usr/share/locale-langpack
  242660 /usr/share/doc
  197560 /usr/share/fonts
  179144 /usr/share/gnome 146764 /usr/share/myspell 144304 /usr/share/gimp 135880 /usr/share/dict 76508 /usr/share/icons 68072 /usr/share/apps 62844 /usr/share/foomatic
  By using the -nr options, we produce a reverse numerical sort, with the largest values appearing first in the results. This sort works because the numerical values occur at the beginning of each line. But what if we want to sort a list based on some value found within the line? For example, the result of ls -l looks like this:
  [me@linuxbox ~]$ ls -l /usr/bin | head total 152948
     -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
   34824 2012-04-04 02:42 [
  101556 2011-11-27 06:08 a2p
   13036 2012-02-27 08:22 aconnect
   10552 2011-08-15 10:34 acpi
    3800 2012-04-14 03:51 acpi_fakekey
    7536 2012-04-19 00:19 acpi_listen
    3576 2012-04-29 07:57 addpart
   20808 2012-01-03 18:02 addr2line
  489704 2012-10-09 17:02 adept_batch
   238 Chapter 20
  Ignoring, for the moment, that ls can sort its results by size, we could use sort to sort this list by file size, as well.
   [me@linuxbox ~]$ ls -l /usr/bin | sort -nr -k 5 | head
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  -rwxr-xr-x 1 root   root
  8234216 2012-04-07 17:42 inkscape
  8222692 2012-04-07 17:42 inkview
  3746508 2012-03-07 23:45 gimp-2.4
  3654020 2012-08-26 16:16 quanta
  2928760 2012-09-10 14:31 gdbtui
  2928756 2012-09-10 14:31 gdb
  2602236 2012-10-10 12:56 net
  2304684 2012-10-10 12:56 rpcclient
  2241832 2012-04-04 05:56 aptitude
  2202476 2012-10-10 12:56 smbcacls
   Many uses of sort involve the processing of tabular data, such as the results of the ls command above. If we apply database terminology to the table above, we would say that each row is a record and that each record con- sists of multiple fields, such as the file attributes, link count, filename, file size and so on. sort is able to process individual fields. In database terms,
  we are able to specify one or more key fields to use as sort keys. In the example above, we specify the n and r options to perform a reverse numerical sort and specify -k 5 to make sort use the fifth field as the key for sorting.
  The k option is very interesting and has many features, but first we need to talk about how sort defines fields. Let’s consider a very simple text file consisting of a single line containing the author’s name:
  William    Shotts
  By default, sort sees this line as having two fields. The first field contains the characters William and the second field contains the characters Shotts, meaning that whitespace characters (spaces and tabs) are used as delimiters between fields and that the delimiters are included in the field when sorting is performed.
  Looking again at a line from our ls output, we can see that a line con- tains eight fields and that the fifth field is the file size:
  -rwxr-xr-x 1 root   root    8234216 2012-04-07 17:42 inkscape
  For our next series of experiments, let’s consider the following file con- taining the history of three popular Linux distributions released from 2006 to 2008. Each line in the file has three fields: the distribution name, the ver- sion number, and the date of release in MM/DD/YYYY format:
       SUSE
  Fedora
  SUSE
  Ubuntu
  Fedora
  SUSE
  Ubuntu
  Fedora
  Ubuntu
  Ubuntu
  SUSE
  Fedora
  10.2 12/07/2006 10 11/25/2008 11.0 06/19/2008 8.04 04/24/2008 8 11/08/2007 10.3 10/04/2007 6.10 10/26/2006 7 05/31/2007 7.10 10/18/2007 7.04 04/19/2007 10.1 05/11/2006 6 10/24/2006
  Text Processing 239
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  9 05/13/2008 6.06 06/01/2006 8.10 10/30/2008 5 03/20/2006
   Using a text editor (perhaps vim), we’ll enter this data and name the resulting file distros.txt.
  Next, we’ll try sorting the file and observe the results:
  [me@linuxbox ~]$ sort distros.txt
   Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  SUSE
  SUSE
  SUSE
  SUSE
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  10 11/25/2008 5 03/20/2006 6 10/24/2006 7 05/31/2007 8 11/08/2007 9 05/13/2008 10.1 05/11/2006 10.2 12/07/2006 10.3 10/04/2007 11.0 06/19/2008 6.06 06/01/2006 6.10 10/26/2006 7.04 04/19/2007 7.10 10/18/2007 8.04 04/24/2008 8.10 10/30/2008
   Well, it mostly worked. The problem occurs in the sorting of the Fedora version numbers. Since a 1 comes before a 5 in the character set, version 10 ends up at the top while version 9 falls to the bottom.
  To fix this problem, we have to sort on multiple keys. We want to per- form an alphabetic sort on the first field and then a numeric sort on the third field. sort allows multiple instances of the -k option so that multiple sort keys can be specified. In fact, a key may include a range of fields. If no range is specified (as has been the case with our previous examples), sort uses a key that begins with the specified field and extends to the end of the line.
  Here is the syntax for our multikey sort:
  [me@linuxbox ~]$ sort --key=1,1 --key=2n distros.txt
   Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  Fedora
  SUSE
  SUSE
  SUSE
  SUSE
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  Ubuntu
  5 03/20/2006 6 10/24/2006 7 05/31/2007 8 11/08/2007 9 05/13/2008 10 11/25/2008 10.1 05/11/2006 10.2 12/07/2006 10.3 10/04/2007 11.0 06/19/2008 6.06 06/01/2006 6.10 10/26/2006 7.04 04/19/2007 7.10 10/18/2007 8.04 04/24/2008 8.10 10/30/2008
   240 Chapter 20
  Though we used the long form of the option for clarity, -k 1,1 -k 2n would be exactly equivalent. In the first instance of the key option, we spe- cified a range of fields to include in the first key. Since we wanted to limit the sort to just the first field, we specified 1,1, which means "start at field 1 and end at field 1." In the second instance, we specified 2n, which means that field 2 is the sort key and that the sort should be numeric. An option letter may be included at the end of a key specifier to indicate the type of sort to be performed. These option letters are the same as the global options for the sort program: b (ignore leading blanks), n (numeric sort), r (reverse sort), and so on.
  The third field in our list contains a date in an inconvenient format for sorting. On computers, dates are usually formatted in YYYY-MM-DD order to make chronological sorting easy, but ours are in the American format of MM/DD/YYYY. How can we sort this list in chronological order?
  Fortunately, sort provides a way. The key option allows specification of offsets within fields, so we can define keys within fields:
  [me@linuxbox ~]$ sort -k 3.7nbr -k 3.1nbr -k 3.4nbr distros.txt
   Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
  Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
  SUSE
  Ubuntu
  Fedora
  Ubuntu
  SUSE
  Fedora
  10 11/25/2008 8.10 10/30/2008 11.0 06/19/2008 9 05/13/2008 8.04 04/24/2008 8 11/08/2007 7.10 10/18/2007 10.3 10/04/2007 7 05/31/2007 7.04 04/19/2007 10.2 12/07/2006 6.10 10/26/2006 6 10/24/2006 6.06 06/01/2006 10.1 05/11/2006 5 03/20/2006
   By specifying -k 3.7, we instruct sort to use a sort key that begins at the seventh character within the third field, which corresponds to the start of the year. Likewise, we specify -k 3.1 and -k 3.4 to isolate the month and day portions of the date. We also add the n and r options to achieve a reverse numeric sort. The b option is included to suppress the leading spaces (whose numbers vary from line to line, thereby affecting the outcome of the sort) in the date field.
  Some files don’t use tabs and spaces as field delimiters; take, for example, the /etc/passwd file:
  [me@linuxbox ~]$ head /etc/passwd root:x:0:0:root:/root:/bin/bash daemon:x:1:1:daemon:/usr/sbin:/bin/sh bin:x:2:2:bin:/bin:/bin/sh sys:x:3:3:sys:/dev:/bin/sh sync:x:4:65534:sync:/bin:/bin/sync games:x:5:60:games:/usr/games:/bin/sh man:x:6:12:man:/var/cache/man:/bin/sh
   Text Processing 241
        lp:x:7:7:lp:/var/spool/lpd:/bin/sh
        mail:x:8:8:mail:/var/mail:/bin/sh
        news:x:9:9:news:/var/spool/news:/bin/sh
  The fields in this file are delimited with colons (:), so how would we sort this file using a key field? sort provides the -t option to define the field separator character. To sort the passwd file on the seventh field (the account’s default shell), we could do this:
  [me@linuxbox ~]$ sort -t ':' -k 7 /etc/passwd | head me:x:1001:1001:Myself,,,:/home/me:/bin/bash root:x:0:0:root:/root:/bin/bash dhcp:x:101:102::/nonexistent:/bin/false
  gdm:x:106:114:Gnome Display Manager:/var/lib/gdm:/bin/false hplip:x:104:7:HPLIP system user,,,:/var/run/hplip:/bin/false klog:x:103:104::/home/klog:/bin/false messagebus:x:108:119::/var/run/dbus:/bin/false polkituser:x:110:122:PolicyKit,,,:/var/run/PolicyKit:/bin/false pulse:x:107:116:PulseAudio daemon,,,:/var/run/pulse:/bin/false
  By specifying the colon character as the field separator, we can sort on the seventh field.
  uniq—Report or Omit Repeated Lines
  Compared to sort, the uniq program is a lightweight. uniq performs a seem- ingly trivial task. When given a sorted file (including standard input), it removes any duplicate lines and sends the results to standard output. It is often used in conjunction with sort to clean the output of duplicates.
  Note: While uniq is a traditional Unix tool often used with sort, the GNU version of sort supports a -u option, which removes duplicates from the sorted output.
  Let’s make a text file to try this out:
  [me@linuxbox ~]$ cat > foo.txt a
  b
  c
  a b c
  Remember to type CTRL-D to terminate standard input. Now, if we run uniq on our text file, the results are no different from our original file; the duplicates were not removed:
  [me@linuxbox ~]$ uniq foo.txt a
  b
  c
  a b c
         242 Chapter 20
  For uniq to actually do its job, the input must be sorted first:
  [me@linuxbox ~]$ sort foo.txt | uniq a
  b
  c
  This is because uniq only removes duplicate lines that are adjacent to each other.
  uniq has several options. Table 20-2 lists the common ones. Table 20-2: Common uniq Options
     Option
  -c -d
  -f n
  -i -s n -u
  Description
  Output a list of duplicate lines preceded by the number of times the line occurs.
  Output only repeated lines, rather than unique lines.
  Ignore n leading fields in each line. Fields are separated by whitespace as they are in sort; however, unlike sort, uniq has no option for setting an alternative field separator.
  Ignore case during the line comparisons.
  Skip (ignore) the leading n characters of each line. Output only unique lines. This is the default.
              Here we see uniq used to report the number of duplicates found in our text file, using the -c option:
  [me@linuxbox ~]$ sort foo.txt | uniq -c 2a
  2b 2c
  Slicing and Dicing
  The next three programs we will discuss are used to peel columns of text out of files and recombine them in useful ways.
  cut—Remove Sections from Each Line of Files
  The cut program is used to extract a section of text from a line and output the extracted section to standard output. It can accept multiple file argu- ments or input from standard input.
  Specifying the section of the line to be extracted is somewhat awkward and is specified using the options shown in Table 20-3.
    Text Processing 243
  Table 20-3: cut Selection Options
   Option
  -c char_list
  -f field_list
  -d delim_char
  --complement
  Description
  Extract the portion of the line defined by char_list. The list may consist of one or more comma-separated numerical ranges.
  Extract one or more fields from the line as defined by field_list. The list may contain one or more fields or field ranges separated by commas.
  When -f is specified, use delim_char as the field delimit- ing character. By default, fields must be separated by a single tab character.
  Extract the entire line of text, except for those portions specified by -c and/or -f.
          As we can see, the way cut extracts text is rather inflexible. cut is best used to extract text from files that are produced by other programs, rather than text directly typed by humans. We’ll take a look at our distros.txt file to see if it is "clean" enough to be a good specimen for our cut examples. If we use cat with the -A option, we can see if the file meets our requirements of tab-separated fields.
  [me@linuxbox ~]$ cat -A distros.txt SUSE^I10.2^I12/07/2006$ Fedora^I10^I11/25/2008$ SUSE^I11.0^I06/19/2008$ Ubuntu^I8.04^I04/24/2008$ Fedora^I8^I11/08/2007$ SUSE^I10.3^I10/04/2007$ Ubuntu^I6.10^I10/26/2006$ Fedora^I7^I05/31/2007$ Ubuntu^I7.10^I10/18/2007$ Ubuntu^I7.04^I04/19/2007$ SUSE^I10.1^I05/11/2006$ Fedora^I6^I10/24/2006$ Fedora^I9^I05/13/2008$ Ubuntu^I6.06^I06/01/2006$ Ubuntu^I8.10^I10/30/2008$ Fedora^I5^I03/20/2006$
  It looks good—no embedded spaces, just single tab characters between the fields. Since the file uses tabs rather than spaces, we’ll use the -f option to extract a field:
  [me@linuxbox ~]$ cut -f 3 distros.txt 12/07/2006
  11/25/2008
  06/19/2008
  04/24/2008
  11/08/2007
     244 Chapter 20
  10/04/2007
  10/26/2006
  05/31/2007
  10/18/2007
  04/19/2007
  05/11/2006
  10/24/2006
  05/13/2008
  06/01/2006
  10/30/2008
  03/20/2006
  Because our distros file is tab delimited, it is best to use cut to extract fields rather than characters. This is because when a file is tab delimited, it is unlikely that each line will contain the same number of characters, which makes calculating character positions within the line difficult or impossible. In our example above, however, we now have extracted a field that luckily contains data of identical length, so we can show how character extraction works by extracting the year from each line:
  [me@linuxbox ~]$ cut -f 3 distros.txt | cut -c 7-10 2006
  2008
  2008
  2008
  2007
  2007
  2006
  2007
  2007
  2007
  2006
  2006
  2008
  2006
  2008
  2006
  By running cut a second time on our list, we are able to extract charac- ter positions 7 through 10, which corresponds to the year in our date field. The 7-10 notation is an example of a range. The cut man page contains a complete description of how ranges can be specified.
  When working with fields, it is possible to specify a different field delim- iter rather than the tab character. Here we will extract the first field from the /etc/passwd file:
  [me@linuxbox ~]$ cut -d ':' -f 1 /etc/passwd | head root
  daemon
  bin
  sys
  sync
  games
  man
      Text Processing 245
  lp mail news
  Using the -d option, we are able to specify the colon character as the field delimiter.
      EXPANDING TABS
  Our distros.txt file is ideally formatted for extracting fields using cut. But what if we wanted a file that could be fully manipulated with cut by characters, rather than fields? This would require us to replace the tab characters within the file with the corresponding number of spaces. Fortunately, the GNU coreutils pack- age includes a tool for that. Named expand, this program accepts either one or more file arguments or standard input, and it outputs the modified text to standard output.
  If we process our distros.txt file with expand, we can use the cut -c to extract any range of characters from the file. For example, we could use the follow- ing command to extract the year of release from our list by expanding the file and using cut to extract every character from the 23rd position to the end of the line:
       [me@linuxbox ~]$ expand distros.txt | cut -c 23-
     coreutils also provides the unexpand program to substitute tabs for spaces.
    paste—Merge Lines of Files
  The paste command does the opposite of cut. Rather than extracting a column of text from a file, it adds one or more columns of text to a file.
  It does this by reading multiple files and combining the fields found in each file into a single stream of standard output. Like cut, paste accepts multiple file arguments and/or standard input. To demonstrate how paste operates, we will perform some surgery on our distros.txt file to produce a chronological list of releases.
  From our earlier work with sort, we will first produce a list of distros sorted by date and store the result in a file called distros-by-date.txt:
  [me@linuxbox ~]$ sort -k 3.7nbr -k 3.1nbr -k 3.4nbr distros.txt > distros-by- date.txt
  Next, we will use cut to extract the first two fields from the file (the dis- tro name and version) and store that result in a file named distro-versions.txt:
  [me@linuxbox ~]$ cut -f 1,2 distros-by-date.txt > distros-versions.txt [me@linuxbox ~]$ head distros-versions.txt
     246 Chapter 20
  Fedora 10 Ubuntu 8.10 SUSE 11.0 Fedora 9 Ubuntu 8.04 Fedora 8 Ubuntu 7.10 SUSE 10.3 Fedora 7 Ubuntu 7.04
  The final piece of preparation is to extract the release dates and store them a file named distro-dates.txt:
  [me@linuxbox ~]$ cut -f 3 distros-by-date.txt > distros-dates.txt [me@linuxbox ~]$ head distros-dates.txt
  11/25/2008
  10/30/2008
  06/19/2008
  05/13/2008
  04/24/2008
  11/08/2007
  10/18/2007
  10/04/2007
  05/31/2007
  04/19/2007
  We now have the parts we need. To complete the process, use paste to put the column of dates ahead of the distro names and versions, thus creat- ing a chronological list. This is done simply by using paste and ordering its arguments in the desired arrangement.
  [me@linuxbox ~]$ paste distros-dates.txt distros-versions.txt
      11/25/2008
  10/30/2008
  06/19/2008
  05/13/2008
  04/24/2008
  11/08/2007
  10/18/2007
  10/04/2007
  05/31/2007
  04/19/2007
  12/07/2006
  10/26/2006
  10/24/2006
  06/01/2006
  05/11/2006
  03/20/2006
  Fedora 10 Ubuntu 8.10 SUSE 11.0 Fedora 9 Ubuntu 8.04 Fedora 8 Ubuntu 7.10 SUSE 10.3 Fedora 7 Ubuntu 7.04 SUSE 10.2 Ubuntu 6.10 Fedora 6 Ubuntu 6.06 SUSE 10.1 Fedora 5
   join—Join Lines of Two Files on a Common Field
  In some ways, join is like paste in that it adds columns to a file, but it does so in a unique way. A join is an operation usually associated with relational data- bases where data from multiple tables with a shared key field is combined to
  Text Processing 247
  form a desired result. The join program performs the same operation. It joins data from multiple files based on a shared key field.
  To see how a join operation is used in a relational database, let’s ima- gine a very small database consisting of two tables, each containing a single record. The first table, called CUSTOMERS, has three fields: a customer number (CUSTNUM), the customer’s first name (FNAME), and the cus- tomer’s last name (LNAME):
   CUSTNUM
  =========
  4681934
  FNAME LNAME ====== ====== John Smith
   The second table is called ORDERS and contains four fields: an order number (ORDERNUM), the customer number (CUSTNUM), the quantity (QUAN), and the item ordered (ITEM):
   ORDERNUM
  ==========
  3014953305
  CUSTNUM
  =========
  4681934
  QUAN ITEM
  ===== ====
  1 Blue Widget
   Note that both tables share the field CUSTNUM. This is important, as it allows a relationship between the tables.
  Performing a join operation would allow us to combine the fields in the two tables to achieve a useful result, such as preparing an invoice. Using the matching values in the CUSTNUM fields of both tables, a join operation could produce the following:
  FNAME LNAME QUAN ITEM
  ====== ====== ===== ====
  John Smith 1 Blue Widget
  To demonstrate the join program, we’ll need to make a couple of files with a shared key. To do this, we will use our distros-by-date.txt file. From this file, we will construct two additional files. One contains the release dates (which will be our shared key field for this demonstration) and the release names:
  [me@linuxbox ~]$ cut -f 1,1 distros-by-date.txt > distros-names.txt [me@linuxbox ~]$ paste distros-dates.txt distros-names.txt > distros-key-names .txt
  [me@linuxbox ~]$ head distros-key-names.txt
     11/25/2008
  10/30/2008
  06/19/2008
  05/13/2008
  04/24/2008
  11/08/2007
  10/18/2007
  10/04/2007
  05/31/2007
  04/19/2007
  Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
  Fedora
  Ubuntu
  SUSE
  Fedora
  Ubuntu
   248 Chapter 20
  The second file contains the release dates and the version numbers:
  [me@linuxbox ~]$ cut -f 2,2 distros-by-date.txt > distros-vernums.txt [me@linuxbox ~]$ paste distros-dates.txt distros-vernums.txt > distros-key- vernums.txt
  [me@linuxbox ~]$ head distros-key-vernums.txt
  11/25/2008 10 10/30/2008 8.10 06/19/2008 11.0 05/13/2008 9 04/24/2008 8.04 11/08/2007 8 10/18/2007 7.10 10/04/2007 10.3 05/31/2007 7 04/19/2007 7.04
  We now have two files with a shared key (the "release date" field). It is important to point out that the files must be sorted on the key field for join to work properly.
  [me@linuxbox ~]$ join distros-key-names.txt distros-key-vernums.txt | head 11/25/2008 Fedora 10
  10/30/2008 Ubuntu 8.10
  06/19/2008 SUSE 11.0
               05/13/2008 Fedora 9
               04/24/2008 Ubuntu 8.04
               11/08/2007 Fedora 8
               10/18/2007 Ubuntu 7.10
               10/04/2007 SUSE 10.3
               05/31/2007 Fedora 7
               04/19/2007 Ubuntu 7.04
  Note also that, by default, join uses whitespace as the input field delim- iter and a single space as the output field delimiter. This behavior can be modified by specifying options. See the join man page for details.

  tr—Transliterate or Delete Characters

  The tr program is used to transliterate characters. We can think of this as a sort of character-based search-and-replace operation. Transliteration is the process of changing characters from one alphabet to another. For example, converting characters from lowercase to uppercase is transliteration. We can perform such a conversion with tr as follows:
  [me@linuxbox ~]$ echo "lowercase letters" | tr a-z A-Z LOWERCASE LETTERS
  As we can see, tr operates on standard input and outputs its results on standard output. tr accepts two arguments: a set of characters to convert from and a corresponding set of characters to convert to. Character sets may be expressed in one of three ways:
    An enumerated list; for example, ABCDEFGHIJKLMNOPQRSTUVWXYZ.
    A character range; for example, A-Z. Note that this method is sometimes subject to the same issues as other commands (due to the locale colla- tion order) and thus should be used with caution.
    POSIX character classes; for example, [:upper:].
  In most cases, the character sets should be of equal length; however, it is possible for the first set to be larger than the second, particularly if we wish to convert multiple characters to a single character:
  [me@linuxbox ~]$ echo "lowercase letters" | tr [:lower:] A AAAAAAAAA AAAAAAA
  In addition to transliteration, tr allows characters to simply be deleted from the input stream. Earlier in this chapter, we discussed the problem of converting MS-DOS text files to Unix-style text. To perform this conversion, carriage return characters need to be removed from the end of each line. This can be performed with tr as follows:
  tr -d '\r' < dos_file > unix_file
      254
  Chapter 20
  where dos_file is the file to be converted and unix_file is the result. This form of the command uses the escape sequence \r to represent the carriage return character. To see a complete list of the sequences and character classes tr supports, try
  [me@linuxbox ~]$ tr –help
       ROT13: THE NOT-SO-SECRET DECODER RING
  One amusing use of tr is to perform ROT13 encoding of text. ROT13 is a trivial type of encryption based on a simple substitution cipher. Calling ROT13 encryp- tion is being generous; text obfuscation is more accurate. It is used sometimes on text to obscure potentially offensive content. The method simply moves each character 13 places up the alphabet. Since this is halfway up the possible 26 characters, performing the algorithm a second time on the text restores it to
  its original form. To perform this encoding with tr:
     echo "secret text" | tr a-zA-Z n-za-mN-ZA-M
  frperg grkg
     Performing the same procedure a second time results in the translation:
   echo "frperg grkg" | tr a-zA-Z n-za-mN-ZA-M
  secret text
     A number of email programs and Usenet news readers support ROT13 encoding. Wikipedia contains a good article on the subject: http://en.wikipedia .org/wiki/ROT13.
    tr can perform another trick, too. Using the -s option, tr can "squeeze" (delete) repeated instances of a character:
  [me@linuxbox ~]$ echo "aaabbbccc" | tr -s ab abccc
  Here we have a string containing repeated characters. By specifying
  the set ab to tr, we eliminate the repeated instances of the letters in the set, while leaving the character that is missing from the set (c) unchanged. Note that the repeating characters must be adjoining. If they are not, the squeez- ing will have no effect:
  [me@linuxbox ~]$ echo "abcabcabc" | tr -s ab abcabcabc
      Text Processing 255
  sed—Stream Editor for Filtering and Transforming Text
  The name sed is short for stream editor. It performs text editing on a stream of text, either a set of specified files or standard input. sed is a powerful and somewhat complex program (there are entire books about it), so we will not cover it completely here.
  In general, the way sed works is that it is given either a single editing command (on the command line) or the name of a script file containing multiple commands, and it then performs these commands upon each line in the stream of text. Here is a very simple example of sed in action:
  [me@linuxbox ~]$ echo "front" | sed 's/front/back/' back
  In this example, we produce a one-word stream of text using echo and pipe it into sed. sed, in turn, carries out the instruction s/front/back/ upon the text in the stream and produces the output back as a result. We can also recognize this command as resembling the substitution (search and replace) command in vi.
  Commands in sed begin with a single letter. In the example above, the substitution command is represented by the letter s and is followed by the search and replace strings, separated by the slash character as a delimiter. The choice of the delimiter character is arbitrary. By convention, the slash character is often used, but sed will accept any character that immediately follows the command as the delimiter. We could perform the same com- mand this way:
  [me@linuxbox ~]$ echo "front" | sed 's_front_back_' back
  When the underscore character is used immediately after the command, it becomes the delimiter. The ability to set the delimiter can be used to make commands more readable, as we shall see.
  Most commands in sed may be preceded by an address, which specifies which line(s) of the input stream will be edited. If the address is omitted, then the editing command is carried out on every line in the input stream. The simplest form of address is a line number. We can add one to our example:
  [me@linuxbox ~]$ echo "front" | sed '1s/front/back/' back
  Adding the address 1 to our command causes our substitution to be performed on the first line of our one-line input stream. We can specify another number:
  [me@linuxbox ~]$ echo "front" | sed '2s/front/back/' front
          256 Chapter 20
  Now we see that the editing is not carried out, because our input stream does not have a line 2.
  Addresses may be expressed in many ways. Table 20-7 lists the most common ones.
  Table 20-7: sed Address Notation
   Address
  n
  $ /regexp/
  addr1,addr2 first~step
  addr1,+n addr!
  Description
  A line number where n is a positive integer
  The last line
  Lines matching a POSIX basic regular expression. Note that the regular expression is delimited by slash characters. Optionally, the regular expression may be delimited by an alternate char- acter, by specifying the expression with \cregexpc, where c is the alternate character.
  A range of lines from addr1 to addr2, inclusive. Addresses may be any of the single address forms above.
  Match the line represented by the number first and then each subsequent line at step intervals. For example, 1~2 refers to each odd-numbered line, and 5~5 refers to the fifth line and every fifth line thereafter.
  Match addr1 and the following n lines.
  Match all lines except addr, which may be any of the forms above.
                We’ll demonstrate different kinds of addresses using the distros.txt file from earlier in this chapter. First, a range of line numbers:
  [me@linuxbox ~]$ sed -n '1,5p' distros.txt
   SUSE
  Fedora
  SUSE
  Ubuntu
  Fedora
  10.2
  10
  11.0
  8.04
  8
  12/07/2006
  11/25/2008
  06/19/2008
  04/24/2008
  11/08/2007
   we print a range of lines, starting with line 1 and con- do this, we use the p command, which simply causes
  In this example,
  tinuing to line 5. To
  a matched line to be printed. For this to be effective, however, we must include the option -n (the no autoprint option) to cause sed not to print every line by default.
  Text Processing 257
  Next, we’ll try a regular expression:
  [me@linuxbox ~]$ sed -n '/SUSE/p' distros.txt
   SUSE 10.2 SUSE 11.0 SUSE 10.3 SUSE 10.1
  12/07/2006
  06/19/2008
  10/04/2007
  05/11/2006
   By including the slash-delimited regular expression /SUSE/, we are able to isolate the lines containing it in much the same manner as grep.
  Finally, we’ll try negation by adding an exclamation point (!) to the address:
  [me@linuxbox ~]$ sed -n '/SUSE/!p' distros.txt
   Fedora
  Ubuntu
  Fedora
  Ubuntu
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  10 11/25/2008 8.04 04/24/2008 8 11/08/2007 6.10 10/26/2006 7 05/31/2007 7.10 10/18/2007 7.04 04/19/2007 6 10/24/2006 9 05/13/2008 6.06 06/01/2006 8.10 10/30/2008 5 03/20/2006
   Here we see the expected result: all of the lines in the file except the ones matched by the regular expression.
  So far, we’ve looked at two of the sed editing commands, s and p. Table 20-8 is a more complete list of the basic editing commands.
  Table 20-8: sed Basic Editing Commands
  Command Description
  = Output current line number.
  a Append text after the current line.
  d Delete the current line.
  i Insert text in front of the current line.
  p Print the current line. By default, sed prints every line and edits only lines that match a specified address
  within the file. The default behavior can be over- ridden by specifying the -n option.
  q Exit sed without processing any more lines. If the -n option is not specified, output the current line.
               258 Chapter 20
  Table 20-8 (continued )
  Command
  Q s/regexp/replacement/
  Description
  Exit sed without processing any more lines.
  Substitute the contents of replacement wherever regexp is found. replacement may include the special character &, which is equivalent to the text matched by regexp. In addition, replacement may include the sequences \1 through \9, which are the contents of the corresponding subexpressions in regexp. For more about this, see the following discussion on back references. After the trailing slash following replacement, an optional flag may be specified to modify the s command’s behavior.
  Perform transliteration by converting characters from set1 to the corresponding characters in set2. Note that unlike tr, sed requires that both sets be of the same length.
       y/set1/set2
    The s command is by far the most commonly used editing command. We will demonstrate just some of its power by performing an edit on our distros.txt file. We discussed before how the date field in distros.txt was not in a "computer-friendly" format. While the date is formatted MM/DD/YYYY,
  it would be better (for ease of sorting) if the format were YYYY-MM-DD. To perform this change on the file by hand would be both time consuming and error prone, but with sed, this change can be performed in one step:
  [me@linuxbox ~]$ sed 's/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1
   -\2/' distros.txt
  SUSE 10.2
  2006-12-07
  2008-11-25
  2008-06-19
  2008-04-24
  2007-11-08
  2007-10-04
  2006-10-26
  2007-05-31
  2007-10-18
  2007-04-19
  2006-05-11
  2006-10-24
  2008-05-13
  2006-06-01
  2008-10-30
  2006-03-20
  Fedora
  SUSE
  Ubuntu
  Fedora
  SUSE
  Ubuntu
  Fedora
  Ubuntu
  Ubuntu
  SUSE
  Fedora
  Fedora
  Ubuntu
  Ubuntu
  Fedora
  10
  11.0
  8.04
  8
  10.3
  6.10
  7
  7.10
  7.04
  10.1
  6
  9 6.06 8.10 5
   Wow! Now that is an ugly-looking command. But it works. In just one step, we have changed the date format in our file. It is also a perfect example of why regular expressions are sometimes jokingly referred to as a "write-only"
  Text Processing 259
  260 Chapter 20
  medium. We can write them, but we sometimes cannot read them. Before we are tempted to run away in terror from this command, let’s look at how it was constructed. First, we know that the command will have this basic structure:
  sed 's/regexp/replacement/' distros.txt
  Our next step is to figure out a regular expression that will isolate the date. Since it is in MM/DD/YYYY format and appears at the end of the line, we can use an expression like this:
          [0-9]{2}/[0-9]{2}/[0-9]{4}$
  which matches two digits, a slash, two digits, a slash, four digits, and the end of line. So that takes care of regexp, but what about replacement? To handle that, we must introduce a new regular expression feature that appears in some applications that use BRE. This feature is called back references and works like this: If the sequence \n appears in replacement where n is a number from one to nine, the sequence will refer to the corresponding subexpression in the preceding regular expression. To create the subexpressions, we simply enclose them in parentheses like so:
          ([0-9]{2})/([0-9]{2})/([0-9]{4})$
  We now have three subexpressions. The first contains the month, the second contains the day of the month, and the third contains the year. Now we can construct replacement as follows:
  \3-\1-\2
  which gives us the year, a dash, the month, a dash, and the day. Now, our command looks like this:
  sed 's/([0-9]{2})/([0-9]{2})/([0-9]{4})$/\3-\1-\2/' distros.txt
  We have two remaining problems. The first is that the extra slashes in our regular expression will confuse sed when it tries to interpret the s com- mand. The second is that since sed, by default, accepts only basic regular expressions, several of the characters in our regular expression will be taken as literals, rather than as metacharacters. We can solve both these problems with a liberal application of backslashes to escape the offending characters:
  sed 's/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1-\2/' dis tros.txt
  And there you have it!
  Another feature of the s command is the use of optional flags that may follow the replacement string. The most important of these is the g flag, which instructs sed to apply the search and replace globally to a line, not just to the first instance, which is the default.
  Here is an example:
  [me@linuxbox ~]$ echo "aaabbbccc" | sed 's/b/B/' aaaBbbccc
  We see that the replacement was performed but only to the first instance of the letter b, while the remaining instances were left unchanged. By adding the g flag, we are able to change all the instances:
  [me@linuxbox ~]$ echo "aaabbbccc" | sed 's/b/B/g' aaaBBBccc
  So far, we have given sed single commands only via the command line. It is also possible to construct more complex commands in a script file using the -f option. To demonstrate, we will use sed with our distros.txt file to build a report. Our report will feature a title at the top, our modified dates, and all the distribution names converted to uppercase. To do this, we will need to write a script, so we’ll fire up our text editor and enter the following:
  # sed script to produce Linux distributions report
  1 i\
  \
  Linux Distributions Report\
  s/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1-\2/ y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/
  We will save our sed script as distros.sed and run it like this: [me@linuxbox ~]$ sed -f distros.sed distros.txt
  Linux Distributions Report
         SUSE
  FEDORA
  SUSE
  UBUNTU
  FEDORA
  SUSE
  UBUNTU
  FEDORA
  UBUNTU
  UBUNTU
  SUSE
  FEDORA
  FEDORA
  UBUNTU
  UBUNTU
  FEDORA
  10.2 2006-12-07 10 2008-11-25 11.0 2008-06-19 8.04 2008-04-24 8 2007-11-08 10.3 2007-10-04 6.10 2006-10-26 7 2007-05-31 7.10 2007-10-18 7.04 2007-04-19 10.1 2006-05-11 6 2006-10-24 9 2008-05-13 6.06 2006-06-01 8.10 2008-10-30 5 2006-03-20
   Text Processing 261
  As we can see, our script produces the desired results, but how does it do it? Let’s take another look at our script. We’ll use cat to number the lines.
  [me@linuxbox ~]$ cat -n distros.sed
  1 # sed script to produce Linux distributions report 2
  3 1i\
  4\
  5 Linux Distributions Report\
  6
  7 s/\([0-9]\{2\}\)\/\([0-9]\{2\}\)\/\([0-9]\{4\}\)$/\3-\1-\2/
  8 y/abcdefghijklmnopqrstuvwxyz/ABCDEFGHIJKLMNOPQRSTUVWXYZ/
  Line 1 of our script is a comment. As in many configuration files and programming languages on Linux systems, comments begin with the # char- acter and are followed by human-readable text. Comments can be placed anywhere in the script (though not within commands themselves) and are helpful to any humans who might need to identify and/or maintain the script.
  Line 2 is a blank line. Like comments, blank lines may be added to improve readability.
  Many sed commands support line addresses. These are used to specify which lines of the input are to be acted upon. Line addresses may be expressed as single line numbers, line-number ranges, and the special line number $, which indicates the last line of input.
  Lines 3 through 6 contain text to be inserted at the address 1, the first line of the input. The i command is followed by the sequence backslash– carriage return to produce an escaped carriage return, or what is called a line-continuation character. This sequence, which can be used in many circum- stances including shell scripts, allows a carriage return to be embedded in
  a stream of text without signaling the interpreter (in this case sed) that the end of the line has been reached. The i command and the commands a (which appends text) and c (which replaces text) allow multiple lines of text, providing that each line, except the last, ends with a line-continuation character. The sixth line of our script is actually the end of our inserted text and ends with a plain carriage return rather than a line-continuation char- acter, signaling the end of the i command.
  Note: A line-continuation character is formed by a backslash followed immediately by a car- riage return. No intermediary spaces are permitted.
  Line 7 is our search-and-replace command. Since it is not preceded by an address, each line in the input stream is subject to its action.
  Line 8 performs transliteration of the lowercase letters into uppercase letters. Note that unlike tr, the y command in sed does not support charac- ter ranges (for example, [a-z]), nor does it support POSIX character classes. Again, since the y command is not preceded by an address, it applies to every line in the input stream.
    262 Chapter 20
  PEOPLE WHO LIKE SED ALSO LIKE...
  sed is a very capable program, able to perform fairly complex editing tasks to streams of text. It is most often used for simple, one-line tasks rather than long scripts. Many users prefer other tools for larger tasks. The most popular of these are awk and perl. These go beyond mere tools like the programs covered here and extend into the realm of complete programming languages. perl, in particular, is often used in place of shell scripts for many system-management and administration tasks, as well as being a very popular medium for web devel- opment. awk is a little more specialized. Its specific strength is its ability to manipu- late tabular data. It resembles sed in that awk programs normally process text files line by line, using a scheme similar to the sed concept of an address fol- lowed by an action. While both awk and perl are outside the scope of this book, they are very good tools for the Linux command line user.

  The Command Line

  They wanted a powerful set of tools that you could mix and match to form powerful composites.

  To that end, they built everything around a simple concept: streams of plain text.

  Virtually all the Unix command- line tools produce and consume plain text.

  Even text files can be converted into a stream of plain text (via the cat command) and put back into a file with the redirection command, the >.
  For a simple example, you can take regular text with the echo command and pipe it through something that converts it from lowercase to uppercase (using the tr, or translate, command). This understands character classes (like :lower: and :upper:) like this (note that the $ isn’t part of the command, the command-line prompt, left there so you can tell input from output):
       $ echo "productively lazy" | tr "[:lower:]" "[:upper:]"
       PRODUCTIVELY LAZY
  The concept worth noticing here is the pipe command (the | character). It takes the output of the echo command and passes it into the tr command, which dutifully translates lowercase characters into uppercase ones. All Unix commands are wired this way, where the output of one becomes the input of the next. You can also create a file with that content by redirecting the output of this command into a file:
       $ echo "productively lazy" | tr "[:lower:]" "[:upper:]" >pl.txt
       $ cat pl.txt
       PRODUCTIVELY LAZY
  And, of course, you can take text from one file, do something to it, and put it into another file:
       $ cat pl.txt | tr "[:upper:]" "[:lower:]" | tr "z" "Z" > plz.txt
       productively laZy
  Here is a more practical example. Suppose I have a large Java project with a bunch of classes that are "helpers" for other classes, and follow a naming convention of Class Helper, for the class it is helping. I want to find them all, even though they are scattered all over my project:
  $ find . -name *Helper.java
  And my army of trained minions dutifully responds:
         ./src/java/org/sample/domain/DomainHelper.java
         ./src/java/org/sample/gui/WindowHelper.java
         ./src/java/org/sample/logic/DocumentHelper.java
         ./src/java/org/sample/logic/GenericHelper.java
  194 APPENDIX: BUILDING BLOCKS
         ./src/java/org/sample/logic/LoginHelper.java
         ./src/java/org/sample/logic/PersistenceHelper.java
  OK, fine, you can get the same result in the search dialog of an IDE. But the interesting thing about the command line is what you can do after you get these results. In an IDE, the results of that search are going to be in a window, and if you are lucky, you might be able to copy them out and paste them someplace. But from the command line, you can pipe that output into another tool. In this case, that tool is wc. wc is a tool that counts things; it can count words, characters, lines, and files:
       $ find . -name *Helper.java | wc -l
       6
  The wc -l line simply counts the number of lines passed into it:
    WHO NAMES THESE THINGS?
  The Unix commands are very terse. After all, they were designed to work on teletype terminals and reward those who learn their way through their terseness. Once you learn them, it takes very little typing to get cool stuff to happen. But what about grep? Where did that come from?
  Rumor has it that the grep command comes to us because of the search command in the ex editor. The ex editor was the line-based precursor to VI, the legendary Unix editor with the steepest imaginable learning curve. In ex, to perform a search, you entered command mode and typed g for global search, started a regular expression with the / character, typed your regular expression, terminated it with another /, and then told ex to print the result with a p. In other words, g/re/p. That was so common amongst Unix types that it became a verb. So, when it came time to write a search utility for the command line, they already had the perfect name: grep.
   I know some of the helpers are actually subclasses of other helpers. I can already use find to find all of the helpers; now I want to look inside those files and find just those that happen to extend other helpers. For that, we use grep. We’ll look at three differently nuanced versions of using the combination of find and grep. The first uses find’s extensive options:
       $ find . -name *Helper.java -exec grep -l "extends .*Helper" {} \;
       ./src/java/org/sample/logic/DocumentHelper.java
       ./src/java/org/sample/logic/LoginHelper.java
  What’s going on in this incantation? See Table A-1 for a breakdown.
  TABLE A-1. Decoding command-line magic
     Character(s)
    What it’s doing
     find
    Execute the find command.
     .
    From the current directory.
     -name
     Matching name of "*Helper.java".
   The Command Line 195
     Character(s)
    What it’s doing
     -exec
    Execute the following command on each found file.
     grep
    grep command.
     -l
     Show the files with matching lines.
     "extends .*Helper"
   Match the regular expression for lines matching "extends" + a single space + zero or more characters + "Helper".
     {}
     The placeholder for the filename found by find.
     \;
    Terminate the command after -exec. Because this is a Unix command, you might want to pipe the results of this into another command, and the find command has to know when the "exec" is done.
   Wow, that’s a lot of bang for the buck in a compact syntax. Which is, of course, the point. Just to prove that many ways exist to do everything on a Unix command line, here is an alternative version that produces the same results, using the xargs command:
       $ find . -name *Helper.java | xargs grep -l "extends .*Helper"
       ./src/java/org/sample/logic/DocumentHelper.java
       ./src/java/org/sample/logic/LoginHelper.java
  Most of this one is the same, except that we’re piping the output of the find command through xargs, which is a helper utility that will take the input from a pipe and place it at the end of its argument. Like the {} placeholder above, xargs will take the filenames produced by the find command and put them as the last parameter of the grep command. You can also use options for the xargs command to put the parameters that come through the pipe at different locations within the argument string. For example, the following command copies all the filenames that start with a capital letter to the dest directory:
       $ ls -1d [A-Z]* | xargs -J % cp -rp % destdir
  The -J flag tells xargs to use the % as the placeholder for the input coming through the pipe. This allows you to specify any replacement character you like, to ensure it doesn’t conflict with some other character required by the target command.
  Here’s one last version of our find command:
       $ grep -l "extends .*Helper" `find . -name *Helper.java`
       ./src/java/org/sample/logic/DocumentHelper.java
       ./src/java/org/sample/logic/LoginHelper.java
  Notice those little backtick characters (`). We aren’t using the pipe to send the output of one command to another—if we did that, grep would simply look through the list of filenames, not the content of the files themselves. Wrapping the find command in the backtick character (typically found at the upper left of U.S. keyboards) will make find execute first, and pass the output to grep as the list of files to search instead of the actual text to search.
  Now, I glue together all of the stuff seen so far:
  196
  $ grep -l "extends .*Helper" `find . -name *Helper.java` | wc -l
  2
  APPENDIX: BUILDING BLOCKS
  While the individual commands were pretty trivial, with the pipe and the backtick, I can combine them in ways their original authors might not have anticipated (and that is a major philosophical point behind Unix). With the knowledge of a dozen commands or so, you too can look like a Unix power user. More importantly, you can slice and dice your projects in ways that just are not available from the menus inside of IDEs.

### VO 600w
  *sed

  Substitute on all lines (all occurrences):

      s/xx/yy/g

  Delete lines containing BSD :

      /BSD/d

  Print the lines between each pair of BEGIN and END , inclusive:

      /^BEGIN/,/^END/p

  Delete any line that doesn't contain SAVE :

      /SAVE/!d

  Substitute on all lines, except between BEGIN and END :

      /BEGIN/,/END/!s/xx/yy/g

  Example

      # Replace first 100 lines in a file:
      1,100c\

      ...first replacement line
      \

      ...second replacement line
      \

      ...
      \

      ...last replacement line

  d

      [ address1 ][, address2 ]d

      Delete the addressed line (or lines) from the pattern space. Thus, the line is not passed to standard output. A new line of input is read, and editing resumes with the first command in the script. See articles 34.4 and 34.18 .

      Example

          # delete all blank lines:
          /^$/d

  i

          [ address ]i\
          text

      Insert text before each line matched by address . (See a for details on text .) Article 43.20 shows a script that uses i .

      Example

          /Item 1/i\
          The five items are listed below:

  s

      [ address1 ][ , address2 ] s/ pattern / replacement / [ flags ]

      Substitute replacement for pattern on each addressed line. If pattern addresses are used, the pattern // represents the last pattern address specified. The following flags can be specified:

    g

        Replace all instances of / pattern / on each addressed line, not just the first instance.

  *tr

  tr "[:lower:]" "[:upper:]" < file1
  For example:
  $ tr "[:lower:]" "[:upper:]" < todo 1. WAKE UP
  2. LOOK IN MIRROR
  3. SIGH
      4. GO BACK TO BED.
      $
  The tr command has a number of different options for power users, including -c to invert the specified pattern (that is, if you specify tr -c "abc", the program matches anything other than a, b, or c), and -d deletes any characters from the first pattern specified.

  To remove all vowels from the input, you could use:

  $ tr -d "[aeiou]" < todo 1. Wk p

  *cut

  The cut program is used to extract a section of text from a line and output the extracted section to standard output. It can accept multiple file argu- ments or input from standard input.
  Specifying the section of the line to be extracted is somewhat awkward and is specified using the options shown in Table 20-3.

  Option
  -c char_list
  -f field_list
  -d delim_char
  --complement
  Description
  Extract the portion of the line defined by char_list. The list may consist of one or more comma-separated numerical ranges.
  Extract one or more fields from the line as defined by field_list. The list may contain one or more fields or field ranges separated by commas.
  When -f is specified, use delim_char as the field delimit- ing character. By default, fields must be separated by a single tab character.
  Extract the entire line of text, except for those portions specified by -c and/or -f.

  *sort

  $ ls -l | sort -nk 5 | less

  -b --ignore-leading-blanks
  -f --ignore-case -n --numeric-sort
  -r --reverse
  -k --key=field1[,field2]
  -m --merge
  -o --output=file
  -t --field-separator=cha

  *uniq

  Compared to sort, the uniq program is a lightweight. uniq performs a seem- ingly trivial task. When given a sorted file (including standard input), it removes any duplicate lines and sends the results to standard output. It is often used in conjunction with sort to clean the output of duplicates.

  Note: While uniq is a traditional Unix tool often used with sort, the GNU version of sort supports a -u option, which removes duplicates from the sorted output.

  -c -d

  Output a list of duplicate lines preceded by the number of times the line occurs.

  -f n

  Output only repeated lines, rather than unique lines.

  -i -s n -u

  Ignore n leading fields in each line. Fields are separated by whitespace as they are in sort; however, unlike sort, uniq has no option for setting an alternative field separator.

  Ignore case during the line comparisons.

  Skip (ignore) the leading n characters of each line. Output only unique lines. This is the default.

  Here we see uniq used to report the number of duplicates found in our text file, using the -c option:

  [me@linuxbox ~]$ sort foo.txt | uniq -c 2a

  *wc

  $ find . -name *.rb | wc -l

  find . -name "*.rb" | grep -v test | xargs wc -l | sort
  j ./actionpack/lib/action_dispatch/routing/mapper.rb


