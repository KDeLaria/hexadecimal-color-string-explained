# Hexadecimal Color Regex Explained

Hexadecimal color strings are used many times in web applications. There are 3 different types of hexadecimal color strings. There are simplified RGB strings which have 4 characters \(3 that are hexadeciaml\). The most common hexadecimal string is the 7 character RGB string \(which has 6 hexadecimal characters\). The final hexadecimal color string is the RGB string with transparency which has 9 characters \(and 8 hexadeciaml characters\).

## Summary

A hexadecimal character is a base 16 numeric value.  The hexadecimal characters are `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `a`, `b`, `c`, and `f`. All hexadecimal color strings begin with the `#` character. The regex for a hexadecimal color string is `/^#([a-f0-9]{8}|[a-f0-9]{6}|[a-f0-9]{3})$/i`. 

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

Since all regular expression \(or regex\) are considered to be a literal, regex strings written in JavaScript \(ECMA script\) are surrounded by `/` to enclose the pattern. The `/` will not be read in as part of the string that will be matched. However, everything inside of the `/` will be used for matching a string.

### Anchors

The `^` character indicates the start position of the string, and any characters before the `^` will be ignored.  The `$` character indicates the end of a string. The string that will be matched is between the `^` and `$` characters. Any characters outside of the `^` and `$` will be ignored when comparing to a string.

### Quantifiers

The hexadecimal color strings have either 3 or 6 characters after the literal `#` character. The `{` `}` characters enclose the number of times the pattern to the left of the brackets will be matched.

### Grouping Constructs 

The `(` `)` enclose the `[a-f0-9]{8}|[a-f0-9]{6}|[a-f0-9]{3}` group.  The group is seperated from the `#` character, and any comparison that is made to the characters inside the group will not impact the comparison of the `#` character.

### Bracket Expressions

The characters inside of the `[` `]` bracket expression define a group of characters that the string will match.  The group `[a-f0-9]` defines two ranges of character sets.  The `a-f` defines the upper range of possible characters, and the `0-9` defines the lower range of possible characters.

### Character Classes

The `[0-9]` group can be replaced by `\d`. Since `\d` represents the numeric values `0` through `9` the regex string would look a `/^#([a-f\d]{8}|[a-f\d]{6}|[a-f\d]{3})$/i` when replacing the `[0-9]`.  Both `/^#([a-f\d]{8}|[a-f\d]{6}|[a-f\d]{3})$/i` and `/^#([a-f0-9]{8}|[a-f0-9]{6}|[a-f0-9]{3})$/i` represent the exact same string match.

### The OR Operator

The `|` character signifies an "or" operator between `[a-f0-9]{8}|` and `[a-f0-9]{6}`, and between `[a-f0-9]{6}` and `[a-f0-9]{3}`.  In this case, if a string of hexadecimal characters has either 8, 6, or 3 characters the match result for that character group will be true. If the number of hexadecimal characters is not 8, 6, or 3 the match result for the string will be false.

### Flags

The `i` after the outer right `/` is a flag that ignores the case of a string that being matched. This flag causes the case of matching characters in `[a-f]` to be ignored. In other words, any character between `[A-F]` will still match. 

### Character Escapes

The `\` character in the regex string `/^#([a-f\d]{8}|[a-f\d]{6}|[a-f\d]{3})$/i` is not read in for comparison.  The character after the `\` escape character will be used in matching a string. In this example the `\d` represents numeric characters.

## Author

[KDeLaria](https://github.com/KDeLaria)
A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)




## Additional Resources

*"Hexadecimal color code for transparency" lopspower, GitHub, *[gist.github.com/lopspower/03fb1cc0ac9f32ef38f4](https://gist.github.com/lopspower/03fb1cc0ac9f32ef38f4)

*Regular Expressions 101, *[regex101.com/](https://regex101.com/)

*"What’s the difference between PMS, CMYK, RGB and HEX?" Neglia Design, *[negliadesign.com/ask-a-designer/whats-the-difference-between-pms-cmyk-rgb-and-hex/](https://negliadesign.com/ask-a-designer/whats-the-difference-between-pms-cmyk-rgb-and-hex/)