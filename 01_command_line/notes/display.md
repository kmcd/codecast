## File display 2m

  e.g. Rails source

  cat
  less
  (syntax highlight)
  du/df
  wc?
  head / tail
  open

  Chapter 25: Showing What's in a File
  59 Calculating File Size and Disk Space
  165 Launching GUI Applications
  
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
## Next steps

## File display 2m
  git clone RAILS

  cat README

  less README
  * scroll
  * search

  less \*.rb

  head -n 1

  (rails project)
  tail -n 1
  tail -f log/development.log
  tail -f /var/log/messages
  tail -f log/development.log /var/log/messages

  Calculating File Size and Disk Space

  You can find the size of a file with the du (disk usage) command: $ du Documents/Outline.doc
      300     Documents/Outline.doc
  The size is reported in kilobytes, so Outline.doc is 300 KB in size.
  If you give du the name of a directory, it calculates the sizes of everything inside that
  directory, including any subdirectories and their contents:
  $ du Library
  136 Library/Accounts
  64 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/MacOS
  8 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/bg.lproj 8 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/da.lproj 8 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/de.lproj 16 Library/Address Book Plug-Ins/SkypeABDialer.bundle/Contents/Resources/en.lproj ...
   Calculating File Size and Disk Space | 59
   This means that it’s not a great idea to type du /, unless you want to see a lot of information stream past your screen at a lightning pace!
  If you want the total for the directory, use -s (summarize):

  $ du -s Library
      41075320  Library
  If you’d like separate totals for all directories and files, including hidden ones, use a wildcard pattern that ignores the current (.) and parent (..) directories, as discussed earlier in this chapter:


  $ du -s * .[^.]* 86696 Desktop 73427240 Documents 13330568 Downloads 5508072 Dropbox 269120 Google Drive 41078120 Library
      ...
      8   .nchsoftware
      8   .profile
      8   .ssh
      64  .subversion
      48  .viminfo
      8   .vuescanrc
  To gain information about the size of the standard user applications in OS X, use the pattern /Applications/*.app:
  $ du -s /Applications/*.app
  1784120 /Applications/Aperture.app 3760 /Applications/App Store.app 20872 /Applications/Automator.app 8880 /Applications/Calculator.app 52832 /Applications/Calendar.app 11888 /Applications/Chess.app
  23296 /Applications/Contacts.app
  ...
  17864 /Applications/TextEdit.app
  656
  /Applications/Time Machine.app 1169280 /Applications/VMware Fusion.app 37952 /Applications/VueScan.app 3574832 /Applications/Xcode.app
  855160 /Applications/iMovie.app 382416 /Applications/iPhoto.app 153200 /Applications/iTunes.app
   60 | Chapter 3: Exploring the Filesystem
  Notice that the output is in alphabetical order, but all the uppercase filenames are sorted before the lowercase filenames (that is, TextEdit appears before iMovie in a case- sensitive sort).
  One option that’s worth keeping in mind when using du -s is -h, which produces more human-readable output:

  $ du -sh /Library/*
  3.1G /Library/Application Support 1001M /Library/Audio
       24M   /Library/Automator
      1.6M   /Library/Caches
        0B   /Library/ColorPickers
       92K   /Library/ColorSync
        0B   /Library/Components
        0B   /Library/Compositions
      512K   /Library/Contextual Menu Items
      127M   /Library/Desktop Pictures
      ...
        0B   /Library/Speech
        0B   /Library/Spelling
      1.9M   /Library/Spotlight
        0B   /Library/StartupItems
        0B   /Library/SystemProfiler
      668K   /Library/Updates
       21M   /Library/User Pictures
        0B   /Library/Video
      3.3M   /Library/WebServer
      8.5M   /Library/Widgets
       16K   /Library/iTunes



  While this is a bit more readable, the enormous /Library/Application Support, at 3.1 GB, doesn’t jump out as it would if the -h flag weren’t used and the output of 6507128 blocks were shown instead. It’s probably best to include the -h flag, but remember to scan the suffix letters to see if anything jumps out as being ridiculously large.


  You can also sort the largest directories to the top of the results with a command sequence like du -s /Library/* | sort -rn, or, better, only view the top 10 results with du -s /Library/* | sort -rn | head. I’ll explain com­ mand pipes and the tremendously useful sort command a bit later.

  Launching GUI Applications

  One great feature of OS X’s Unix command line is that you can interact with the graphical applications in Aqua. For example:
  • Drag a file or folder from the Finder onto a Terminal window and watch as its full pathname gets dropped in after the command prompt.
  • Want to use vi to edit a text file that’s on your Desktop? Just type vi on the command line, followed by a space, and then drag the file onto the Terminal window.
  • When viewing a file in the Finder, you’ll see what’s known as a proxy icon in the Finder’s title bar that shows you what directory you’re in. Type cd followed by a space, then drag the proxy icon into the Terminal window and hit Return; you’ll be taken to that same exact location, just in the Terminal.
  If you can have the Finder interact with the Terminal, it should be no surprise to you that you can also have the Terminal interact with other graphical applications on the Mac. For this, OS X offers the open command.
   164 | Chapter 7: Multitasking
  open
  By default, the open command works identically to double-clicking an icon in the Finder. To open up a picture file in your default picture editor, use:
  $ open peanut.jpg $
  If you don’t have a graphics-editing application like Photoshop installed, the image opens in Preview (/Applications). If Preview is already running, the peanut.jpg image file opens in a new window.
  The open command also lets you work at the command line with file matching, since it accepts more than one filename at a time. For example, if you need to open up a bunch of Microsoft Word files in a directory, just use:
  $ open *.doc $
  You can, however, get things a bit confused, because sometimes the system doesn’t know what to do with certain files. For example, try issuing the following command:
  $ open .profile $
  The default application that’s used when there’s no specific binding is TextEdit, which works in this instance, but look what happens when you try to open something it can’t recognize:
  $ open .sample.swp
  No application knows how to open /Users/taylor/Desktop/.sample.swp.
  In this case, open just couldn’t figure out what to do with this temporary scratch file from the vi editor. That’s because open uses a file’s creator and/or type code to determine which application should be used to open a particular file. And since vi’s scratch files don’t have a creator or type code, the command gets confused and ends up doing nothing.
  What Are Creator and Type Codes?
  Unlike in other operating systems, whenever you create and save a file with an application on the Mac, the application you use assigns its creator and type codes to the file. These codes are four characters in length and can contain upper- and lowercase letters, numbers, and even spaces. OS X uses these codes to figure out which icon gets assigned to certain files and, more importantly, to determine the default application for opening that file.
  For example, in the Terminal, you can create a blank file on your Desktop with the fol­ lowing command:
  $ touch ~/Desktop/myFile.txt
      Launching GUI Applications | 165
  As you can see from the file extension (.txt), this is a plain-text file. If you were to double- click on this file, and if you didn’t have another graphical text editor on your system, the file would open in TextEdit.
  However, if you rename that file and give it a .doc extension: $ mv myFile.txt myFile.doc
  you can trick the system into thinking that it’s a Word file. Don’t believe me? Just try double-clicking the file and see which application opens it!
  If you’ve installed the Xcode Tools on your Mac (https://developer.apple.com/technologies/ tools/), you can use a couple of special command-line utilities to peek inside a file to see its creator and type codes. For example, the following displays the output of the GetFi­ leInfo command (located in /usr/bin) when used on a Word file:
  $ GetFileInfo lmut_ch07.doc
  file: "/Users/taylor/Documents/Linux Journal/Column.42.docx" type: "WXBN"
  creator: "MSWD"
  attributes: avbstclinmedz
  created: 03/02/2009 20:45:22
  modified: 03/02/2009 20:45:22
  $
  Here you can see that the creator code is MSWD, short for Microsoft Word. Useful Starting Options for Use with open
  The open command has a lot of power accessible through command options. For ex­ ample, if you want to stream a bunch of input into a text file then open it in an Aqua file, you can do so by using the -f option:
  $ mdfind NIKON | open -f $
  This quick call to Spotlight generates a list of all filenames that reference or include NIKON. It would be easy to generate a printout with TextEdit, too.
  The most useful option for use with open is -a, which is used to specify an application to open. For example, you can launch Messages with the generic open command, but you need to know where it’s located on your system:
  $ open messages
  The file /Users/taylor/Desktop/messages does not exist.
  Add the -a option, though, and open knows that you’re talking about an application, so it’ll search in the /Applications directory to find and launch it:
  $ open -a messages
      166 | Chapter 7: Multitasking
  Notice that open is smart enough to ignore case: the actual application is called Messages. You can also use the open -a command to open applications that are in a subdirectory of /Applications. Want to launch the Console (located in /Applications/Utilities)? Use open -a console. Ready to compare the output of Activity Monitor to the ps command, as discussed earlier in this chapter? Launch Activity Monitor with open -a "activity monitor".
  If you want to open a file with TextEdit, there’s another option to open that’s worth knowing: use open -e, and whatever you specify will be opened with the TextEdit pro­ gram, regardless of its type. For example, if you wanted to open an HTML file in TextEdit instead of with BBEdit, you could use the following:
  $ open -e ~/Sites/someFile.html
  The open command will then look in your Sites folder for the file someFile.html and open
  it in TextEdit.
  Making open More Useful
  open makes it a breeze to launch your favorite applications, but because it requires that you type in the full application name, a few aliases are in order:
      alias word="open -a Microsoft\ Word"
      alias excel="open -a Microsoft\ Excel"
      alias gc="open -a GraphicConverter"
  With these added to your .profile, you can easily launch Graphic Converter by just en­ tering gc, and launch Microsoft Excel with excel.
  A more sophisticated approach would be to use a shell script wrapper that would give its arguments to open and, if they failed, try to figure out what application you were talking about. It’s an advanced topic, but here’s how that script might look:
  #!/bin/sh
      # open2 - a smart wrapper for the cool OS X 'open' command
      #   to make it even more useful. By default, open launches the
      #   appropriate application for a specified file or directory
      #   based on the Aqua bindings, and has a limited ability to
      #   launch applications if they're in the /Applications dir.
      # first off, whatever argument we're given, try it directly:
      open=/usr/bin/open
      if ! $open "$@" >/dev/null 2>&1 ; then
        if ! $open -a "$@" >/dev/null 2>&1 ; then
          # More than one arg?  Don't know how to deal with it: quit
          if [ $# -gt 1 ] ; then
            echo "open: Can't figure out how to open or launch $@" >&2
   Launching GUI Applications
  | 167
  exit 1 else
            case $(echo $1 | tr '[:upper:]' '[:lower:]') in
              acrobat      ) app="Acrobat Reader"             ;;
              address*     ) app="Contacts"                   ;;
              chat         ) app="Messages"                   ;;
              cpu          ) app="Activity Monitor"           ;;
              dvd          ) app="DVD Player"                 ;;
              word         ) app="Microsoft Word"             ;;
              excel        ) app="Microsoft Excel"            ;;
              prefs        ) app="System Preferences"         ;;
              qt|quicktime ) app="QuickTime Player"           ;;
              * ) echo "open: Don't know what to do with $1" >&2
  exit 1 esac
            echo "You asked for $1 but I think you mean $app." >&2
            $open -a "$app"
          fi
  fi fi
  exit 0
  This script has a simple table of nicknames for common applications, allowing you to type open2 qt to launch QuickTime Player, for example.
  This script is based on one in my book, Wicked Cool Shell Scripts (No Starch Press), which explains 101 powerful and interesting shell scripts. You can learn about the book, and download the above script for your­ self, at http://www.intuitive.com/wicked/.

### VO 300w
  less README
  * scroll
  * search

  less \*.rb

  head -n 1

  (rails project)
  tail -n 1
  tail -f log/development.log
  tail -f /var/log/messages
  tail -f log/development.log /var/log/messages

  *open

  • Drag a file or folder from the Finder onto a Terminal window and watch as its full pathname gets dropped in after the command prompt.

  • When viewing a file in the Finder, you’ll see what’s known as a proxy icon in the Finder’s title bar that shows you what directory you’re in. Type cd followed by a space, then drag the proxy icon into the Terminal window and hit Return; you’ll be taken to that same exact location, just in the Terminal.

  $ open *.doc

  $ open .profile

  The default application that’s used when there’s no specific binding is TextEdit,

  $ open .sample.swp

  No application knows how to open /Users/taylor/Desktop/.sample.swp.

  in the Terminal, you can create a blank file on your Desktop

  $ touch ~/Desktop/myFile.txt

  the file would open in TextEdit. However, if you rename that file and give it a .doc extension:

  $ mv myFile.txt myFile.doc

  you can trick the system into thinking that it’s a Word file.

  The open command has a lot of power accessible through command options. For ex­ ample, if you want to stream a bunch of input into a text file then open it in an Aqua file, you can do so by using the -f option:

  $ mdfind NIKON | open -f

  This quick call to Spotlight generates a list of all filenames that reference or include NIKON. It would be easy to generate a printout with TextEdit, too.

  The most useful option for use with open is -a, which is used to specify an application to open.

  search in the /Applications directory to find and launch it:

  $ open -a messages

  Notice that open is smart enough to ignore case:

  You can also use the open -a command to open applications that are in a subdirectory of /Applications.

  $ open -a console.

  open -a 'activity monitor'

  use open -e, and whatever you specify will be opened with the TextEdit program, regardless of its type.

  $ open -e ~/Sites/someFile.html

  a few aliases are in order:

  alias word="open -a Microsoft\ Word"


