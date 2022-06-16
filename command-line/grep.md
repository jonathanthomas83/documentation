# grep

## grep to search for strings, recursively, in directories.

Outside of the directory:

```
grep -r "some text" /etc/apache2/
```

Inside of the directory:

```
grep -r "some text"
```

Ignore case:

```
grep -i "SoME tExT"
```

Ignore case and inside of the directory:

```
grep -ir "SoME tExT"
```

## grep - Search recursively within all files in a folder to find all lines that include a word[A] but not if they include another word[B].

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
