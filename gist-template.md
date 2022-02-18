# Title (replace with your title)
Ever wonder how when you search for something, the computer sometimes knows how to find the data you're looking for? What about validating data format when searching? Or how you would find things in varying degrees of literalness or specificity? The answer is using search patterns through regular expressions, or regex.

A regex, which is short for regular expression, is a sequence of characters that defines a specific search pattern. When included in code or search algorithms, regular expressions can be used to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. They are also frequently used to validate input.
## Summary

For example, the following regular expression can be used to verify that user input is a valid email address:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

This translates to:
- The string can contain any lowercase letter between a–z
- The string can contain any number between 0-9
- The string can contain underscores, periods and dashes
- The string must include one or more charachers before the "@" symbol 
- The string must include an "@" symbol
- The string may contain any of the above characters after the "@" symbol
- The string must contain a period after one or more characters after the "@" symbol 
- The string may contain a character from "a" to "z"
- The string may contain another "."
- The string must match between 2 and 6 of the preceding token  


Each component of this regex has a unique responsibility to make sure that a user enters an email address that begins with an unspecified number of characters preceding the @ symbol, followed by a domain.
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
A regex is literal, so the pattern must be wrapped in slash characters (/) and will contain different components. Below is an overview of the different regex components.

### Anchors
The characters `^` and `$` in our example above are both anchors.

The `^` anchor means that a string begins with the exact character that follows the `^` sign in the expression. And matches will be case sensitive.

The `$` anchor is the opposite, meaning that the string should end with the character that precedes the `$` sign in the expression. 

### Quantifiers
Quantifiers set the limits of the string that your regex matches (or an individual section of the string). They frequently include the minimum and maximum number of characters that your regex is looking for.

In our example, `{2,6}` is a quantifier.
### Grouping Constructs
 Grouping constructs allow you to check multiple parts of a string to determine that different sections fulfill different requirements by breaking them up inside `()` symbols.

These are called subexpressions. Our example above had 3 of them.

Grouping constructs can be capturing (saving matched sequences for future use) and non-capturing.

### Bracket Expressions
Anything inside a set of square brackets like this `[]` represents a range of characters that we want to match. They are also known as a positive character or group.

In our example, we saw:
`[a-z]`—The string can contain any lowercase letter between a–z. Keep in mind that this looks for lowercase characters only. If we wanted to include uppercase characters, we would need to change the expression to [a-zA-Z].

`[0-9]`—The string can contain any number between 0–9

`[_\.-]`—The string can contain an underscore, slash, period or hyphen. These are special characters since they are not letters or numbers.
### Character Classes
A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. We've actually already discussed some character classes. The bracket expressions outlined previously, including positive and negative character groups, are considered character classes.

Other common character classes are:

`.`—Matches any character except the newline character (\n)

`\d`—Matches any Arabic numeral digit. This class is equivalent to the bracket expression `[0-9]`.

`\w`—Matches any alphanumeric character from the basic Latin alphabet, including the `_` symbol. This class is equivalent to the bracket expression `[A-Za-z0-9_]`

`\s`—Matches a single whitespace character, including tabs and line break

Each of the last three character classes can be changed to perform an inverse match by capitalizing the letter character. For example, `\D` matches a non-digit character.


### The OR Operator
You can use the OR operator with the `|` symbol in grouping constructs `()` symbols to seaparate options.
### Flags
 Flags are placed at the end of a regex, after the second slash, and they define additional functionality or limits for the regex.

 Here are some of the most common:

`g`—Global search: the regex should be tested against all possible matches in a string

`i`—Case-insensitive search: case should be ignored while attempting a match in a string

`m`—Multi-line search: a multi-line input string should be treated as multiple lines
### Character Escapes
The backslash `\` in a regex escapes a character that otherwise would be interpreted literally. For example, the open curly brace `{` is used to begin a quantifier, but adding a backslash before the open curly brace `\{` means that the regex should look for the open curly brace character instead of beginning to define a quantifier.
## Author

Nicole is a web development student through the UCSD Extension Coding Bootcamp. Follow her on Github: https://github.com/nmbeilke
