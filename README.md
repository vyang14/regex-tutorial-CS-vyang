# Regex Tutorial - By Vincent Yang

Regular Expression, or Regex for short, are methods or rules for helping developers search for and/or match text. These Regex methods can be used in a variety of ways to perform operations that can match text, validate formats such as email addresses or phone numbers, ensure a user's password matches minimum security criteria and more!

## Summary

This brief tutorial will cover a number of basic and advanced Regular Expressions. Let's look at the regular expression in the box below:

    /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
    
At first glance, this might just look like a series of random characters, but this is actually a regular expression sequence of Anchors, Quantifiers, Grouping Constructs, Bracket Expressions, Character Classes, Flags, and other operators that verifies whether or not a given string is a valid email address. The following tutorial will describe how each of the components in this expression works.


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Let's put it all together!](#lets-put-it-all-together)

## Regex Components
To start, the contents within our expression must have a '/' at the start AND end of the string. For example, if we were to searching for the specific string of 'ort,' our expression should look like:

     /ort/

This is a basic match regex query which will specifically search for any case-sensitive instances of the characters 'ort'. Let's apply the previous expression to the following string:
        
> Our associates here at WebTech sincerely thank you for your supp***ort***! We would not have been able to accomplish such a monumental task without your f***ort***itude and expertise.

Notice that in the string above, we saw two instances of 'ort'. Applying the regex /ort/ to the previous string would give you the previous result.
### Anchors

* <code>^</code> - **Beginning** - Matches the beginning of the string, or the beginning of a line if the multiline flag <code>m</code> is also enabled. This only matches the position, NOT characters.

* <code>$</code> - **End** - Matches the end of the string, or the end of a line if the multiline flag <code>m</code> is also enabled. This only matches the position, NOT characters.

* <code>\b</code> - **Word Boundary** - Matches any position that is at the end of a word. This matches the position of the given character, not the character itself.

* <code>\B</code> - **Not Work Boundary** - Matches any position that is not at the end of a word. This matches the position of the given character, not the character itself.

### Quantifiers

Quantifiers are used to find instances of a specific character, group, or character classes.

* <code>+</code> - Must follow a character, but will match one or more of the same consecutive character.

>Example: /a+/ will search for instances of the letter 'a' AND any instance where there are multiple consecutive a's.

* <code>?</code> - The character preceeding this quantifer is optional. The character returns a match between zero to one.

* <code>*</code> - Is similar to the <code>?</code> that the character preceding this is optional, but this quantifer returns matches in quantities from zero or more.

* <code>{}</code> - Matches the quantity of the character preceding this quantifer.
>Example: /a\w{3,}/ will search for words that begin with the letter 'a' that are longer than 3 characters. Let's apply this expression to the string below: <br><br> We tried our h***ardest*** to find ***anything*** that could give us more inform***ation*** ***about*** the subject m***atter***.

### Grouping Constructs

Grouping Constructs help 

* <code>()</code> - **Capture Group** - This grouping construct collects the characters inside and matches the group in that exact order.

* <code>(?:)</code> **Non-Capturing Group** - This construct groups multiple characters together without creating a capture group.


### Bracket Expressions

* <code>(?=)</code> - **Positive Lookahead** - Matches groups of text to the main expression without including the main expression in the result.

* <code>(?!)</code> - **Negative Lookahead** - Specifies a group that cannot match after the main expression. Any matches will be discarded.

* <code>(?!)</code> - **Positive Lookbehind** - Matches a group before the main expression wtithout including it in the result.

* <code>(?!)</code> - **Negative Lookbehind** - Specifies a group that cannot match before the main expression. Any matches will be discarded.

### Character Classes

* <code>.</code> - **Character Set** - This matches any single character however, it does not match return or newline characters. 
> Example expression /.at/ will result in = T***hat*** shipment you sent was a much needed up***dat***e to our equipment.

* <code>[]</code> - **Character Set** - Match any characters inside of the brackets.

* <code>[^]</code> - **Negated Set** - Match any characters not inside of the brackets.

> Example expression /[^p]an/ will search for any character that is NOT 'p' followed by characters 'an'. This gives us  = Chelsea likes burgers more t***han*** pizza.

* <code>[a-e]</code> - **Range** - Matches any characters that contains a character code between the two specified characters included between the brackets.

> In this case, this would search for all letters from 'a' to 'e'.

### The OR Operator

* <code>|</code> - **The OR Operator** acts just like a boolean statement. Matches the expression before or after the operator.

### Flags

* <code>g</code> - **Global** -  Match anywhere in the string, allowing subsequent searches to start from the end of the previous match.

* <code>i</code> - **Ignore Case** - Makes the expression case-insensitive.

* <code>m</code> - **Multiline** - When enabled, beginning and end anchors (^ and $) will match the start and end of a line, instead of the start and end of the whole string.

* <code>s</code> - **dotall** - Matches any character, including newline.

### Character Escapes

* <code>`\+`</code> - **Reserved Characters** - The following characters has special meaning and should be preceded by a \ to represent a literal character.

> Example: the expression <code>\\.</code> will search for the character '.'

* <code>\t</code> - **Tab** - Matches a TAB character. (character code of 9)

* <code>\v</code> - **Vertical Tab** - Matches a VERTICAL TAB character (character code of 11)

* <code>\0</code> - **null** - Matches any NULL characters. (character code of 0)

### Let's put it all together!

Now that we have a better understanding of regex and how it functions, let's revisit the email validation regex that we saw that the beginning of this excercise:

        /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/


Our expression begins with the meta escape <code>^</code> which indicates the start of our input.

Next, we have the capture group <code>([a-z0-9_\.-]+)</code> which searches for a string containing a range from letters a through z, numbers zero through nine, special characters '_', '-', and '.' in a non-specific order. The quantifier <code>+</code> at the end of the capture group allows this to occur any number of times until the next rule:

This carries on to our next group when a specific character '@' is matched. (for email addresses)

Our next expression <code>([\da-z\.-]+)</code> is also a capture group searching for numbers zero through nine, letters ranging from a through z, and then special characters '-', and '.' in a non-specific order. Much like the first expression, this one also contains the <code>+</code> quantifier.

This moves to the last group when the <code>\\.</code> character escape finds a '.' character in the string.

Lastly, the <code>([a-z\.]{2,6})</code> expression is another capture group searching for matches with a range for letters a through z plus including special character '.' with a quantifier matching the charcters between two to six times, as many times as possible.

For more regex practice, <a>https://regex101.com/</a> is a great resource to test expressions. This site also gives the user an explanation of what the expression does, which is a great tool for learning some deeper combinations.

## Author: ***Vincent Yang***

Thank you for taking the time to read through this tutorial! I am a fullstack web developer with an open-minded philosophy who is always looking for challgenges. Please reach out to me at vyang1014888@gmail.com with any questions.

You can find more of my work on my GitHub page at https://github.com/vyang14/.