# grep

Further information and practical examples found here:
[https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)

## grep to search for strings, recursively, in directories.

Search recursively within a directory using the `-r option`.

Outside of the directory:

```
grep -r "some text" /etc/apache2/
```

Inside of the directory:

```
grep -r "some text"
```

## grep to perform a case-insensitive search for a word

Search for a word but ignore the case using the `-i option`.

```
grep -i "SoME tExT"
```

Ignore case and inside of the directory:

```
grep -i -r "SoME tExT"
```

## grep to search recursively but don't show filenames

List all instances of a string found within files in a directory but don't show the filenames using the `-h option`.

```
grep -r -h "Some text"
```

## grep to search recursively within all files in a folder to find all lines that include a word[A] but not if they include another word[B].

To find all lines in a file.

```
grep 'wordA' filename.txt | grep -v 'word-b'
```

Using '-r' to recursively search all files within the folder and not specifying a file at the end.

```
grep -r 'wordA' | grep -v 'word-b'
```

Works if you add more words to exclude, too.
```
grep -r 'wordA' | grep -v 'word-b' | grep -v 'word-c'
```

## grep save output to a file

Search for a keyword and output to a `.txt` file.

```
grep -w 'keyword' squid.conf > new-filename.txt
```

View the contents of the created file.

```
cat new-filename.tx
```

## grep to search words only

When you search for 'boo', grep will match fooboo, boo123, barfoo35 and more. You can force the grep command to select only those lines containing matches that form whole words i.e. match only 'boo' word.

Using the `-w option`.

```
grep -w "boo" file
```

## grep to display lines before and after the match

Want to see the lines before your matches? Try passing the -B to the grep:

```
grep -B NUM "word" file
grep -B 3 "foo" file1
```

Similarly, display the lines after your matches by passing the -A to the grep:

```
grep -A NUM "string" /path/to/file
# Display 4 lines after dropped word matched in firewall log file #
grep -A 4 "dropped" /var/log/ufw.log
```

We can combine those two options to get most meaningful outputs:

```
grep -C 4 -B 5 -A 6 --color 'error-code' /var/log/httpd/access_log
```

## grep to display the total number of times that a string appears

Use the `-c option`

Searches directory recursively, is case-insensitive and shows a number count next to each file for number of appearances of the string in each file.

```
grep -c -i -r "some text"
```

## grep my most used commands

View all to-do notes that aren't related to daily chores and watch list items:

```
grep -i -h -r '_todo' | grep -v -i '#daily' | grep -v -i -w '#watch'
```

View all car notes:

```
grep -i -h -r -w '#car'
```

View watch list:

```
grep -i -h -r '_todo' | grep '#watch'
```
