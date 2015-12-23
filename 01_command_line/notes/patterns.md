## Pattern expansion 2m

  9.5 Build Strings with { }
  
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
  *directory listing

  tree  action{mailer,view}/lib/action*/

  *create new file

  touch test_{1,2,3}

  for n in {0,1}{0,1,2}{0,1,2,3} ; do echo $n ;done

  *create sub directory

  mkdir logs/{2014,2015}/{01,02}/{1,2,3,4,5,6,7,8,9}

  *fix typo

  touch april_1.txt
  mv april_{1,2}.txt

  *quick ext rename

  touch README.txt
  cp README{,.bak}

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
## Next steps



## Pattern expansion 2m
  9.5 Build Strings with { }

  I've been finding more and more uses for the {} pattern-expansion characters in csh , tcsh , and bash . (Other shells can use {} , too; see article 15.3 .)

  They're similar to * , ? , and [] ( 15.2 ) , but they don't match filenames the way that * , ? , and [] do.

  You can give them arbitrary text (not just filenames) to expand - that "expand-anything" ability is what makes them so useful.

  Here are some examples to get you thinking:

  To fix a typo in a filename (change fixbold5.c to fixbold6.c ):

      %

      mv fixbold{5,6}.c

  An easy way to see what the shell does with {} is by adding echo ( 8.6 ) before the mv :

      %

      echo mv fixbold{5,6}.c


      mv fixbold5.c fixbold6.c

  To copy filename to filename.bak in one easy step:

      %

      cp filename{,.bak}

  To print files from other directory(s) without retyping the whole pathname:

      %

      lpr /usr3/hannah/training/{ed,vi,mail}/lab.{ms,out}

  That would give lpr ( 43.2 ) all of these files:

      /usr3/hannah/training/ed/lab.ms
      /usr3/hannah/training/ed/lab.out
      /usr3/hannah/training/vi/lab.ms
      /usr3/hannah/training/vi/lab.out
      /usr3/hannah/training/mail/lab.ms
      /usr3/hannah/training/mail/lab.out

  ...in one fell swoop!

  To edit ten new files that don't exist yet:

      %

      vi /usr/foo/file{a,b,c,d,e,f,g,h,i,j}

  That would make /usr/foo/filea , /usr/foo/fileb , ... /usr/foo/filej . Because the files don't exist before the command starts, the wildcard vi   /usr/foo/file[a-j] would not work ( 9.4 ) .

  An easy way to step through three-digit numbers 000, 001, ..., 009, 010, 011, ..., 099, 100, 101, ... 299 is:



  foreach





  foreach n ({0,1,2}{0,1,2,3,4,5,6,7,8,9}{0,1,2,3,4,5,6,7,8,9})
     ...
  Do whatever with the number $n
  ...
  end


  Yes, csh also has built-in arithmetic, but its @ operator ( 47.4 ) can't make numbers with leading zeros. This nice trick shows that the {} operators are good for more than just filenames.

  To create sets of subdirectories:

      %

      mkdir man


      %

      mkdir man/{man,cat}{1,2,3,4,5,6,7,8}


      %

      ls -F man


      cat1/   cat3/   cat5/   cat7/   man1/   man3/   man5/   man7/
      cat2/   cat4/   cat6/   cat8/   man2/   man4/   man6/   man8/

  To print ten copies of the file project_report (if your lpr ( 43.2 ) command doesn't have a -#10 option):

      %

      lpr project_repor{t,t,t,t,t,t,t,t,t,t}
### VO 300w
  Build Strings with pattern-expansion characters: {}

  You can give them arbitrary text (not just filenames) to expand which is very handy.

  To fix a typo in a filename (change fixbold5.c to fixbold6.c ):

  $ mv typo{5,6}.rb

  An easy way to see what the shell does with {} is by adding echo ( 8.6 ) before the mv :

  $ echo mv fixbold{5,6}.c

  mv fixbold5.c fixbold6.c

  To copy filename to filename.bak in one easy step:

  $ cp filename{,.bak}

  To print files from other directory(s) without retyping the whole pathname:

  $ lpr /usr3/hannah/training/{ed,vi,mail}/lab.{ms,out}


  /usr3/hannah/training/ed/lab.ms
  /usr3/hannah/training/ed/lab.out
  /usr3/hannah/training/vi/lab.ms
  /usr3/hannah/training/vi/lab.out
  /usr3/hannah/training/mail/lab.ms
  /usr3/hannah/training/mail/lab.out

  ...in one fell swoop!

  To edit ten new files that don't exist yet:

  $ vi /usr/foo/file{a,b,c,d,e,f,g,h,i,j}

  That would make /usr/foo/filea , /usr/foo/fileb , ... /usr/foo/filej . Because the files don't exist before the command starts, the wildcard vi   /usr/foo/file[a-j] would not work ( 9.4 ) .

  An easy way to step through three-digit numbers 000, 001, ..., 009, 010, 011, ..., 099, 100, 101, ... 299 is:

  for n in ({0,1,2}{0,1,2,3,4,5,6,7,8,9}{0,1,2,3,4,5,6,7,8,9})
  end

  Yes, csh also has built-in arithmetic, but its @ operator ( 47.4 ) can't make numbers with leading zeros. This nice trick shows that the {} operators are good for more than just filenames.

  To create sets of subdirectories:

  $ mkdir man
  $ mkdir man/{man,cat}{1,2,3,4,5,6,7,8}
  $ ls -F man

  cat1/   cat3/   cat5/   cat7/   man1/   man3/   man5/   man7/
  cat2/   cat4/   cat6/   cat8/   man2/   man4/   man6/   man8/

  To print ten copies of the file project_report command doesn't have a -#10 option):

  $ lpr project_repor{t,t,t,t,t,t,t,t,t,t}


