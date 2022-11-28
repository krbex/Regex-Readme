# Matching a URL Gist

Regular expressions, also known as regex, allows for users to search information more easily. The regex that allows for URL matching primarily uses four grouped constructs, three bracket expressions, and a few quantifiers to accurately find and match a user requested url.

## Summary

This README covers the functions and components utilized in the URL matching regex, as well as breaking down the quantifiers, grouping constructs, bracket expressions, character classes, and character escapes.
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]_)_\/?$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

The '^' at the start and $ are both anchors. These are representative of position of a certain character rather than a specific character.

'^' signifies the start of a string with the remaining characters coming after that point.

'$' signifies the end of a string with the preceeding characters coming before that point.

### Quantifiers

Since quantifiers will match as many occurances as possible, they contain very specific controllers that will measure how often they will try to match the pattern.

'?' will match the pattern 0 or 1 time. Without the https, and there being exactly one, preceeding it, the regex can determine if it will continue. At the end it will ensure that the full url is the exact match.

'+' will match the pattern one or more time. This refers to the domain name, which must be matched at least once.

{2, 6} will look to match the top level domain. This section looks for any group of characters that have a length of 2-6.

### Grouping Constructs

() is a grouping construct. Expressions that are placed within each () allow users to run multiple sections of a string against the url pattern.

([a-z\.]{2,6}) - will for example look for any group of characters that have a length of 2-6.

### Bracket Expressions

[] allows for input characters to be matched, it indicates what counts as user input and what will be checked against the given pattern.

[\da-z\.-] - will look for the given domain name against the url matchers pattern

### Character Classes

'\d' from the below code will match one digit and an alphabetic string input, allowing for inputs like www2.test.com

[\da-z\.-]

'\w' from the below code will match a word character like com, org, or net

[\/\w \.-]

### Flags

### Character Escapes

This regex contains multiple character excapes, '\', which act as a toggle for whether the character in front of it should be treated as a metacharacter or a literal character. Anchors like '^', and '$' need to be escaped to be used as a literal. When using those anchors at the start or end of the regex respectively, additional escaping is not necessary but best practice says to escape them anyway.

/^(https?:\/\/)

Character escapes also allow for special characters like '/', and '.' to be used within the regex as literals, which would allow for something like 'www2.' to be accepted.

([\da-z\.-]+)\.

## Author

My name is Aidan Krbec, thanks for reading my Gist. I am currently an inside sales professional in the B2B advertising space and have been learning to code through UT Austin's Coding Bootcamp. I'm a fantasy enthusiast and hope to finish writing a book in the next few years. I can be found on GitHub here- https://github.com/krbex
