2022-07-14

Sometimes it's just good to know how to make the most portable types of filenames.
Then it's good to know about the POSIX standard, seen below. In this modern day
and age you could assume for normal cases that max string length could be 255 chars,
but for backwards compatibility stick to 14 as noted below.
PS. The max length includes the file extension.

Allowed Chars: ```A–Z a–z 0–9 . _ -```
Reserved Chars: ```/ null```
Max length: ```14```

Hyphen must not be first character. A command line utility checking for conformance,
"pathchk", is part of the IEEE 1003.1 standard and of The Open Group Base Specifications.

Here's some easy to copy code of all allowed characters in the above standard:

## List

```
allowed_chars = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F', 'G', 'H', 'I', 'J', 'K', 'L', 'M', 'N', 'O', 'P', 'Q', 'R', 'S', 'T', 'U', 'V', 'W', 'X', 'Y', 'Z', 'a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z', '.', '_', '-']
```
## String

```
allowed_chars = "0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz._-"
```

### References:
* Original source for this article: [https://gist.github.com/VictorieeMan/de0ba221e1c694da4bdd038cd68fd184](https://gist.github.com/VictorieeMan/de0ba221e1c694da4bdd038cd68fd184)
* [https://en.wikipedia.org/wiki/POSIX](https://en.wikipedia.org/wiki/POSIX)
* [https://en.wikipedia.org/wiki/Filename#Comparison_of_filename_limitations](https://en.wikipedia.org/wiki/Filename#Comparison_of_filename_limitations)
* [https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_280](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_280)
* [https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap06.html#tag_06_01](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap06.html#tag_06_01)

This webpage might be helpful for you: https://regex101.com/
