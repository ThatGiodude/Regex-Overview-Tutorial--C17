# RegExBroken Down

Introductory paragraph (replace this with your text)

## Summary

In this tutorial, we will dive into various aspects of regular expressions, including anchors, quantifiers, the OR operator, character classes, flags, grouping and capturing, bracket expressions, greedy and lazy matching, boundaries, back-references, and look-ahead and look-behind assertions. Each section will include explanations and examples to help you understand how these components work.

Let's start by examining a simple regex pattern: 

## ^hello$

This regex pattern matches the exact word "hello" at the beginning and end of a line.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
- Anchors are used to specify the position in the input text where the match should occur. 
- For example:
-  **^** 
- This is our string anchor. It matches the start of the string the regex pattern is applied to.
- Anchors are used to specify the position in the input text where the match should occur. For example:
    ^ matches the start of a line.
    $ matches the end of a line.

### Quantifiers
- Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.  Here we have '*' to show each type of character needs to be used at least once. In the case of '**{8,}**', it shows we need at least 8 characters.
    '+' matches one or more occurrences.
    '*' matches zero or more occurrences.
    '{n}' matches exactly n occurrences.

### OR Operator
- The OR operator allows you to match one of several patterns. 
- For example:
    'a|b' matches either "a" or "b".
    '[aeiou]' matches any vowel.

### Character Classes
- Character classes allow you to match a single character from a set of characters. 
- For example:
    '\d' matches any digit.
    '\w' matches any word character.

### Flags
- Flags modify the behavior of a regex pattern. 
- For example:
    'g' enables global matching.
    'i' enables case-insensitive matching.

### Grouping and Capturing
- Grouping and capturing allow you to extract parts of a match. 
- For example:
    '(abc)' captures "abc" as a group.
    '(?:abc)' groups "abc" without capturing.

### Bracket Expressions
- Bracket expressions define a set of characters enclosed in square brackets. 
- For example:
    '[aeiou]' matches any vowel.
    '[0-9]' matches any digit.

### Greedy and Lazy Match
- Greedy and lazy matching control how much text is matched by a quantifier.
- For example:
    '*' is greedy, matching as much text as possible.
    '*?' is lazy, matching as little text as possible.

### Boundaries
- Boundaries assert that a match occurs at a certain position in the input text.
- For example:
    '\b' matches a word boundary.
    '\B' matches a non-word boundary.

### Back-references
- Back-references allow you to match the same text that was captured by a capturing group. 
- For example:
    '\1' matches the same text as the first capturing group.

### Look-ahead and Look-behind
- Look-ahead and look-behind assertions assert that a match is followed or preceded by certain text. 
- For example:
    '(?=abc)' asserts that the text is followed by "abc".
    '(?<=abc)' asserts that the text is preceded by "abc".
## Author
- Giovanni (ThatGiodude) Strangio
- Github Profile: [https://github.com/ThatGiodude]