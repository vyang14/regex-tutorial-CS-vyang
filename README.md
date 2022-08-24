# Regex Tutorial - By Vincent Yang

Regular Expression, or Regex for short, are methods or rules for helping developers search for and/or match text. These Regex methods can be used in a variety of ways to perform operations that can match text, validate formats such as email addresses or phone numbers, ensure a user's password matches minimum security criteria and more!

## Summary

This brief tutorial will cover a number of basic and advanced Regular Expressions and how to implement them in JavaScript.

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
To start, the contents within our expression must have a '/' at the start AND end of the string. For example, if we were to searching for the specific string of 'ort,' our expression should look like:
> Example: /ort/

### Anchors

* <code>^</code> - **Beginning** - Matches the beginning of the string, or the beginning of a line if the multiline flag <code>m</code> is also enabled. This only matches the position, NOT characters.

* <code>$</code> - **End** - Matches the end of the string, or the end of a line if the multiline flag <code>m</code> is also enabled. This only matches the position, NOT characters.

* <code>\b</code> - **Word Boundary** - Matches any position that is at the end of a word. This matches the position of the given character, not the character itself.

* <code>\B</code> - **Not Work Boundary** - Matches any position that is not at the end of a word. This matches the position of the given character, not the character itself.

### Quantifiers

* <code>+</code> - Must follow a character, but will match one or more of the same consecutive character.

>Example: /a+/ will search for instances of the letter 'a' AND any instance where there are multiple consecutive a's.
        
        Additionally, the <code>+</code> quantifer can be used between multiple letters to create

* <code>?</code> - The character preceeding this quantifer is optional. The character returns a match between zero to one.

* <code>*</code> - Is similar to the <code>?</code> that the character preceding this is optional, but this quantifer returns matches in quantities from zero or more.

* <code>{}</code> - Matches the quantity of the character preceding this quantifer.
>Example: /a\w{3,}/ will search for words that begin with the letter 'a' that are longer than 3 characters.

### Grouping Constructs

* <code>()</code> - **Capture Group** - This grouping construct collects the characters inside and creates a capture group for extracting a substring or using a backreference.

* <code>(?:)</code> **Non-Capturing Group** - This construct groups multiple characters together without creating a capture group.


### Bracket Expressions

* <code>(?=)</code> - **Positive Lookahead** - Matches groups of text to the main expression without including the main expression in the result.

* <code>(?!)</code> - **Negative Lookahead** - Specifies a group that cannot match after the main expression. Any matches will be discarded.

* <code>(?!)</code> - **Positive Lookbehind** - Matches a group before the main expression wtithout including it in the result.

* <code>(?!)</code> - **Negative Lookbehind** - Specifies a group that cannot match before the main expression. Any matches will be discarded.

### Character Classes

* <code>[]</code> - **Character Set** - Match any characters inside of the brackets.

* <code>[^]</code> - **Negated Set** - Match any characters not inside of the brackets.

* <code>[a-e</code> - **Range** - Matches any characters that contains a character code between the two specified characters included between the brackets.

        In this case, this would search for all letters from 'a' to 'e'

### The OR Operator

* <code>|</code> - **The OR Operator** acts just like a boolean statement. Matches the expression before or after the operator.

### Flags

* <code>g</code> - **Global** -  Match anywhere in the string, allowing subsequent searches to start from the end of the previous match.

* <code>i</code> - **Ignore Case** - Makes the expression case-insensitive.

* <code>m</code> - **Multiline** - When enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.

* <code>s</code> - **dotall** - Matches any character, including newline.

### Character Escapes

* <code>\+</code> - **Reserved Characters** - The following characters has special meaning and should be preceded by a \ to represent a literal character.

* <code>\t</code> - **Tab** - Matches a TAB character. (character code of 9)

* <code>\v</code> - **Vertical Tab** - Matches a VERTICAL TAB character (character code of 11)

* <code>\0</code> - **null** - Matches any NULL characters. (character code of 0)

## Author

Thank you for taking the time to read through this tutorial. Please reach out to me at vyang1014888@gmail.com with any questions or issues.

You can find more of my work on my GitHub page at https://github.com/vyang14/.