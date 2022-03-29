# Regex summary

A regular expression is a pattern in input text that the regular expression engine tries to match. One or more character literals, operators, or structures make up a pattern. i will be explaining Grouping Constructs in my own words which is only one type of Regex.

## Grouping Constructs
Subexpressions of a regular expression are delineated by grouping constructs, which typically capture substrings of an input string.
By putting an expression inside matching open and close parentheses, capturing groups generate a sub-expression. Sub-expressions can have quantifiers and optionality. Each set of parenthesis generates a capture number, which ranges from 1 to 9, which is used to identify capturing groups (\1 to \9).

## For example
 select REGEXP_REPLACE('Hello World','(\w+) (?:\w+)','\& -> \1') from sys.const;
    regexp_replace    
----------------------
 Hello World -> Hello
(1 row)

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

### Anchors
The majority of UNIX text editors are line-oriented. It's not easy to find patterns that span multiple lines. The end of line character, for example, is not included in the text block that is searched. It's a divider, after all. The text between the separators is examined by regular expressions. Anchors are used to find a pattern that is at one end or the other of a line.

^: Beginning of string (or line, depending on the mode)
$: End of string (or line, depending on the mode)
\A: Beginning of string
\z: End of string
\Z: Varies a lot depending on the engine, so be careful with it
\b: Word boundary
\B: Not a word boundary

### Quantifiers
For a match to happen, a quantifier defines how many instances of the previous element (which can be a character, a group, or a character class) must be present in the input string.For example:
{ n , m }	Matches the previous element at least n times, but no more than m times.	"\d{3,5}"	"166", "17668"
"19302" in "193024"

### Grouping Constructs
By putting an expression inside matching open and close parentheses, capturing groups generate a sub-expression. Sub-expressions can have quantifiers and optionality. Each set of parenthesis generates a capture number, which ranges from 1 to 9, which is used to identify capturing groups (\1 to \9).

### Bracket Expressions
A bracket expression can be either a matching or a non-matching list expression. Ordinary characters, collating elements, collating symbols, equivalence classes, character classes, or range expressions are all examples of expressions.

### Character Classes
A character class is a set of characters that matches any one of them. for example 
[character_group] ---Matches any single character in character_group. By default, the match is case-sensitive. 
[ first - last ]  ---Character range: Matches any single character in the range from first to last. [A-Z]  

### The OR Operator 
Also called The Alternation Operator ( | or \| ) 
Alternation is the term in regular expression that is actually a simple “OR”.
In a regular expression it is denoted with a vertical line character |.
For instance, we need to find programming languages: HTML, PHP, Java or JavaScript.
The corresponding regexp: html|php|java(script)?.

### Flags

### Character Escapes
In a regular expression, the backslash character () signifies that the character after it is either a special character (like in the example below) or should be understood literally.
\r Matches a carriage return, \u000D. (\r is not equivalent to the newline character, \n.) 
\c X Matches the ASCII control character that is specified by X or x, where X or x is the letter of the control character. 
\    When followed by a character that is not recognized as an escaped character in this and other tables in this topic, matches that character. For example, \* is the same as \x2A, and \. is the same as \x2E. This allows the regular expression engine to disambiguate language elements (such as * or ?) and character literals (represented by \* or \?).

## Author <b>Matt</b>

This is my summary of Regex please contact me if you have any questions...

LinkedIn: <a href="https://www.linkedin.com/in/mathew-osadolor-848b33177/" target="_blank">Mathew Osad</a> | Website: <a href="https://github.com/mathewosad/" target="_blank">Mathew Osad | Portfolio</a> | Email: <a href="mailto:matthewosad@yahoo.com" target="_blank">matthewosad@yahoo.com</a>

<br>
