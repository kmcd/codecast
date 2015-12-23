# Wildcards L 19
## What is it?
  abbreviate filenames or refer to groups of files

  Like a wildcard in a poker game, a wildcard in a filename can have any value.

## Why is it useful?

  Match groups of files so you don't have to specify each file name manually

## You will be able to ...
## Examples
  *zero or more

  cd ~/src/git

  ls *
  ls a*

  *exactly one

  ls at*.c
  ls at?.c

  *any char in brackets

  ls -1 test-[mp]*
  ls -1 test-[dg]*

  *char range [a-z]

  ls -1 test-[a-z]*
  ls -1 test-[d-f]*
  ls -1 test-[d-g]*

  *negation

  ls -1 test-[^d-g]*
  ls -1 test-[!d-g]*

## Points to note

  wildcards do not match files whose names begin with a dot ( . ), like .cshrc . [1] This prevents you from deleting (or otherwise mucking around with) these files by accident.

  To match those files, type the dot literally. For example, .[a-z]* matches anything whose name starts with a dot and a lowercase letter. Watch out for plain .* , though; it matches the directory entries . and .. (see article 15.5 for suggestions on solving that problem)

  wildcards only match names that already exist.

  program never sees wildcards. For example, typing:

  $ lpr *

  is exactly the same as typing:

  $ lpr file1 file2 file3 file4 file5

  Wildcards are simlar to but NOT regular expressions!

## Recap
## Next steps



## Wildcards 4m
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

### VO 600w
  abbreviate filenames or refer to groups of files.

  Like a wildcard in a poker game, a wildcard in a filename can have any value.

  ? matches any single character.

  For example, letter? letterA , letter1, filenames with a non-printing character as their last letter, like letter ^C.

  The * wildcard matches any character or group of zero or more characters.

  For example, \*.txt matches all files whose names end with .txt ,

  For example, you may want to list files whose names end with .txt , mail , or let: use a separate * with each filename ending:

  \*.txt \*mail \*let

  list all filenames that begin with digits, or all filenames that begin with uppercase letters.

  program.[0123456789]

  wildcard [ character-list ] matches any single character that appears in the list. The character list can be any group of ASCII characters;

  if they are consecutive (e.g., A-Z, a-z, 0-9, or 3-5, for that matter), you can use a hyphen as shorthand for the range. For example, [a-zA-Z] means any alphabetic character.

  Wildcards never match / , which is both the name of the filesystem root ( 1.19 ) and the character used to separate directory names in a path.

  Therefore, the equivalent of rm * does virtually nothing on most operating systems. Under UNIX, it is very dangerous: it means "delete all the files in the current directory, regardless of their name."

  If a file's name begins with . , you always have to type the . explicitly.

  For example, .*rc matches all files whose names begin with . and end with rc .

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

  Wildcards can be used at any point or points within a path. Remember, wildcards only match names that already exist.

  You can't use them to create new files ( 9.4 ) - though some shells have curly braces ( {} ) ( 9.5 , 15.3 ) for doing that.

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

  put \*.txt in quotes to prevent the shell from expanding the wildcard


