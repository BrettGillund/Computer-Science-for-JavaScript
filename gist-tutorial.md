# Regex Tutorial by Brett Gillund

Introductory paragraph (replace this with your text)

## Summary

This tutorial is to be used as a reference regarding the components of a simple **REGular EXpression**, or as they are more commonly refered to REGEX. Regular expressions are paterns that can be used to connect character combinations in strings. These expressions are used to locate and modify specific characters within a string, as well as confirming input of a specific string. 
What is a regular expression?

This is possibly one of the most cryptic strings of characters that you can look at, but is extreamly useful in practice.

Ex:
Hello, look at that rainbow! 

example of a regex - "Rainbow" looking for an uppercase R lowercase a lowercase i lowercase n lowercase b lowercase o lowercase w.

In order to enable regular expressions in VS code you need to press CTRL f or Command f then click the .* button third from the left of the search bar to enable the search of regular expressions.



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Anchors - ^ $

Anchors matche the position of a character within the string itself.
- ^ = beginning of a line.
    - ex: ^\w looks for the first WORD char in each line.
- $ = end of a line.
    - ex: \w+$ looks for the last WORD char in each line.
- \b = word boundry. 
    - ex: \b\w{4}\b looks for each four letter word within a string.

### Quantifiers * + ? { }

quantifiers are meta characters that modify the previous character in the regular expression.
- "*" = 0 or more.
- "+" = 1 or more.
- "?" = 0 or 1.
    -   ex: colou?rs? - find all text that includes either color, colour, or colours - the u and s are both optional as they were preceded by a ? optional.
- "{min,max}"
- "{n}"
    - ex: \w{6} find all six letter words in the text.

### Grouping Constructs ( )

Grouping Constructs means using parentheses to seperate different groups within a regular expression. This data can be modified to the users parameters.
ex: Lets say that we want to change 612-888-8888 to 612-XXX-XXXX. We can use a regex with grouping constructs to group and modify those sections. (\d{3})-\d{3}-\d{4} looks for a group of three digets, a dash, three digets, a dash, and then four digets. We can the use the Replace bar found underneath the REGEX bar to replace the digets we want with Xs using the following code: $1-XXX-XXXX. The $1 targets the group within the parentheses.

Note that the character $ represents GROUP, and that $0 is everything.


### Bracket Expressions [ ]

Bracket Expressions are characters that appear between square brackets [ ].
- Note that any character found within a character class becomes a literal character.
ex: [.] the period that normally is equal to all characters is now a literal character equal to ".".

- When using a character class put a character between two square brackets and the system will look for any character within those brackets.
ex: searching for: l[iy]nk : within the body of text "The lynk is quate a link don't you think?". This will retrun both link as well as lynk as both of the characters i and y are found within the square brackets.

- Note that using a dash between two characters changes the meaning from a literal character to a through character.
ex: searching for [-] searches for a literal dash. Searching for [a-z] searches for characters from a through z.

- Note that using a carrot between two characters changes the meaning from a literal character to a NOT character.
ex: Searching for [a-z] searches for characters from a through z. Seaching for [^a-z] searches for any character that is NOT a through z.

### Character Classes

Literal character - match this exact character.

META character - does not indicate a single character, but instead a generalized pattern to search for. 
ex: 
- \d = any DIGET 0 - 9. 
- \D = any NOT DIGET.
- \w = any WORD char A-Z, a-z, 0-9.
- \W = any NOT WORD char.
- \s = any whiteSPACE char - space or tab.
- \S = any NOT whiteSPACE char.
- . = any character. 



### The OR Operator ( | )

The OR Operator also known as alternation uses parentheses and a pipe symbol to look for one of several potential characters.
- ex: when searching for com or net or gov you can use (com|net|gov) which will search for any instance of these characters.

### Flags

Flags are used in regular expresssions to affect search paramters. There are six different flags in JavaScript.
- i with this flag the search is case sensitive. 
- g with this flag the search looks for all matches. Without it only the first match is returned.
- m with this flag the searches through multiple lines of code. 
- s with this flag the search enables a "dotall" mode. This allows a . to match a newline character \n.
- u enables full Unicode support. This flag enables correct processing of surrogate pairs. 
- y enables "sticky" mode. This serches at for an exact position within the text. 

### Character Escapes

Character Esacapes are used to yse any of the special characters literally. To use a character escape use a backslash \ .
ex: if a user needs to search for a * they wi;; need to use put a backslash in front of it \ *.

## Author

My name is Brett Gillund, and I am currenty studying to fulfull my dream of becoming a full-stack web developer. I have created this template as a reference, as REGEX expressions will be something that I frequently use when searching for and intending to modify data. Please see the below link to my github account:

https://github.com/BrettGillund



