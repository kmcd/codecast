## Intro 1m
  Every woodworker needs a good, solid, reliable workbench, somewhere to hold work pieces at a convenient height while he or she works them. The workbench becomes the center of the wood shop, the craftsman returning to it time and time again as a piece takes shape.

  For a programmer manipulating files of text, that workbench is the command shell. From the shell prompt, you can invoke your full repertoire of tools, using pipes to combine them in ways never dreamt of by their original developers. 
  
  From the shell, you can launch applications, debuggers, browsers, editors, and utilities. You can search for files, query the status of the system, and filter output. 
  
  And by programming the shell, you can build complex macro commands for activities you perform often.
  
  For programmers raised on GUI interfaces and integrated development environments (IDEs), this might seem an extreme position. After all, can't you do everything equally well by pointing and clicking?
  
  The simple answer is "no." GUI interfaces are wonderful, and they can be faster and more convenient for some simple operations. Moving files, reading MIME-encoded e-mail, and typing letters are all things that you might want to do in a graphical environment. But if you do all your work using GUIs, you are missing out on the full capabilities of your environment.
  
  You won't be able to automate common tasks, or use the full power of the tools available to you. And you won't be able to combine your tools to create customized macro tools. 
  
  A benefit of GUIs is WYSIWYG—what you see is what you get. The disadvantage is WYSIAYG—what you see is all you get.
  GUI environments are normally limited to the capabilities that their designers intended.
  
  If you need to go beyond the model the designer provided, you are usually out of luck—and more often than not, you do need to go beyond the model. Pragmatic Programmers don't just cut code, or develop object models, or write documentation, or automate the build process—we do all of these things.
  
  The scope of any one tool is usually limited to the tasks that the tool is expected to perform. For instance, suppose you need to integrate a code preprocessor (to implement design-by-contract, or multi-processing ,mas, or some such) into your IDE. Unless the designer of the IDE explicitly provided hooks for this capability, you can't do it.
  
  
  You may already be comfortable working from the command prompt, in which case you can safely skip this section. Otherwise, you may need to be convinced that the shell is your friend.
  
  As a Pragmatic Programmer, you will constantly want to perform ad hoc operations—things that the GUI may not support. The command line is better suited when you want to quickly combine a couple of commands to perform a query or some other task. Here are a few examples.

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


