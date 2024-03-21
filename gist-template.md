# RegEx Broken Down

Explained below is an in depth breakdown of RegEx and some it's components and how it's used to easier understand.

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
-  `**^**` 
- This is our string anchor. It matches the start of the string the regex pattern is applied to.
- Anchors are used to specify the position in the input text where the match should occur. For example:
    `^` matches the start of a line.
    `$` matches the end of a line.

### Quantifiers
- Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found.  Here we have '*' to show each type of character needs to be used at least once. In the case of '**{8,}**', it shows we need at least 8 characters.
    `+` matches one or more occurrences.
    `*` matches zero or more occurrences.
    `{n}` matches exactly n occurrences.
- Quantifiers in regular expressions are used to specify how many times a character or a group of characters should occur in the input text. They allow you to define repetition patterns, such as matching zero or more occurrences, one or more occurrences, or a specific number of occurrences.

- Here are some common quantifiers and their meanings:
    `*`: Matches zero or more occurrences of the preceding character or group. For example, 'a*' will match "", "a", "aa", "aaa", and so on.
    `+`: Matches one or more occurrences of the preceding character or group. For example, a+ will match "a", "aa", "aaa", and so on, but not "".
    `?`: Matches zero or one occurrence of the preceding character or group. It makes the preceding character or group optional. For example, 'colou?r' will match both "color" and "colour".
    `{n}`: Matches exactly n occurrences of the preceding character or group. For example, 'a{3}' will match "aaa" but not "aa" or "aaaa".
    `{n,}`: Matches n or more occurrences of the preceding character or group. For example, 'a{2,}' will match "aa", "aaa", "aaaa", and so on.
    `{n,m}`: Matches between n and m occurrences of the preceding character or group, inclusive. For example, 'a{2,4}' will match "aa", "aaa", or "aaaa", but not "a" or "aaaaa".

- Quantifiers can be applied to individual characters, groups of characters, or even to other quantifiers. They provide a powerful way to specify repetition patterns in regular expressions, allowing you to match complex patterns in text efficiently.

### OR Operator
- The OR operator allows you to match one of several patterns. 
- For example:
    `a|b` matches either "a" or "b".
    `[aeiou]` matches any vowel.
- The OR operator in regular expressions allows you to specify multiple alternatives for a pattern to match. It's denoted by the | character and is used to match any of the alternatives provided.

- Here are some examples of using the OR operator:
    Matching colors:
    Pattern: `red|green|blue`
    Description: This pattern matches either "red", "green", or "blue".
    
    Matching different spellings of a word:
    Pattern: `color|colour`
    Description: This pattern matches either "color" or "colour".
    
    Matching different file extensions:
    Pattern: `\.txt|\.csv|\.json`
    Description: This pattern matches file extensions ".txt", ".csv", or ".json".
    
    Matching variations of a word:
    Pattern: `dog|dogs|doggo`
    Description: This pattern matches either "dog", "dogs", or "doggo".
    
    Matching email domains:
    Pattern: `gmail\.com|yahoo\.com|outlook\.com`
    Description: This pattern matches email domains "gmail.com", "yahoo.com", or "outlook.com".
    The OR operator allows you to specify multiple options for a single part of your regular expression, providing flexibility in matching different variations or alternatives in the input text.

### Character Classes
- Character classes allow you to match a single character from a set of characters. 
- For example:
    `\d` matches any digit.
    `\w` matches any word character.
- Character classes in regular expressions allow you to specify a set of characters that you want to match. They are denoted by square brackets [ ] and can match any single character within the defined set.

- Here are some examples of using character classes:

    Matching digits:
    Pattern: `[0-9]`
    Description: This pattern matches any single digit from 0 to 9.

    Matching lowercase letters:
    Pattern: `[a-z]`
    Description: This pattern matches any single lowercase letter from "a" to "z".

    Matching uppercase letters:
    Pattern: `[A-Z]`
    Description: This pattern matches any single uppercase letter from "A" to "Z".

    Matching alphanumeric characters:
    Pattern: `[a-zA-Z0-9]`
    Description: This pattern matches any single alphanumeric character, either a lowercase letter, uppercase letter, or digit.

    Matching a specific set of characters:
    Pattern: `[aeiou]`
    Description: This pattern matches any single lowercase vowel ("a", "e", "i", "o", "u").

    Matching special characters:
    Pattern: `[\^$.|?*+()]`
    Description: This pattern matches any single character that is a metacharacter (^, $, ., |, ?, *, +, (, )).

    Matching a specific range of characters:
    Pattern: `[abcde]`
    Description: This pattern matches any single character that is either "a", "b", "c", "d", or "e".

- Character classes are very versatile and allow you to specify which characters you want to match in your regular expression. They are commonly used to define specific sets of characters that are expected to occur in the input text.

### Flags
- Flags modify the behavior of a regex pattern. 
- For example:
    `g` enables global matching.
    `i` enables case-insensitive matching.
- Flags in regular expressions (regex) are optional parameters that modify how the pattern matching behavior works. They are usually appended to the end of the regex pattern and are denoted by letters. 
- Here are some common flags in JavaScript regex:

i (case-insensitive):
This flag makes the regex match case-insensitively, meaning it will ignore the difference between uppercase and lowercase letters.
Example: /hello/i matches "hello", "Hello", "HELLO", etc.

    `g` (global match):
    This flag enables global matching, meaning the regex will match all occurrences in the input string, rather than just the first one.
    Example: `/a/g` matches all occurrences of "a" in the input string.

    `m` (multiline match):
    This flag changes the behavior of the ^ and $ anchors, allowing them to match the start and end of each line within a multiline input string, rather than just the start and end of the entire string.
    Example: `/^hello/m` matches "hello" at the start of any line in a multiline input string.

    `u` (unicode):
    This flag enables full Unicode matching support for the regex pattern, including Unicode escape sequences and Unicode character classes.
    Example: `/[\u{1F600}-\u{1F64F}]/u` matches any emoji character in the input string.

    'y' (sticky):
    This flag enables sticky matching, meaning the regex will search for matches starting at the lastIndex property of the regex object.
    Example: `/a/y` matches "a" only if it is found right after the lastIndex position.

    `s` (dotAll):
    This flag enables the "dotAll" mode, which makes the dot (.) character match all characters, including line terminators like newline (\n).
    Example: `/hello.world/s` matches "hello\nworld".

    `d` (unicode default):
    This flag changes the default source character set to Unicode.
    Example: `/\d/d` matches any Unicode digit.

- These flags can be combined together, such as '/pattern/gi', which performs a global, case-insensitive search. Understanding and using flags appropriately can enhance the flexibility and power of your regular expressions.

### Grouping and Capturing
- Grouping and capturing allow you to extract parts of a match. 
- For example:
    `(abc)` captures "abc" as a group.
    `(?:abc)` groups "abc" without capturing.
- Grouping and capturing in regular expressions allow you to capture parts of a matched string for further processing or reference. Here are some examples to illustrate how grouping and capturing work:
    
    Capturing Groups:
    Parentheses `()` are used to create capturing groups.
    Example: `/(foo)(bar)/` captures "foo" and "bar" as separate groups.

    Nested Capturing Groups:
    You can nest capturing groups within each other.
    Example: `/(\d{3})-(\d{3}-\d{4})/` captures both the area code and the phone number separately.

    Named Capturing Groups:
    You can give capturing groups meaningful names for easier reference.
    Example: `/(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/` captures the year, month, and day parts of a date.

    Non-Capturing Groups:
    If you don't need to capture the matched substring, you can use non-capturing groups `(?:)`.
    Example: `/Mr(?:s|)\. (\w+)/` matches both "Mr. John" and "Mrs. Smith" but only captures "John" and "Smith".
    
    Group Referencing:
    You can reference captured groups within the same regex pattern.
    Example: `/(\w+)\s+\1/` matches repeated words.

- Grouping and capturing are powerful features of regular expressions that allow you to extract specific parts of a matched string or to define complex patterns with ease.

### Bracket Expressions
- Bracket expressions define a set of characters enclosed in square brackets. 
- For example:
    '[aeiou]' matches any vowel.
    '[0-9]' matches any digit.
- Bracket expressions, also known as character classes, allow you to match a single character out of several possible characters. They are enclosed within square brackets []. Here are some examples to illustrate the usage of bracket expressions:

    Matching a Single Character:
    `[aeiou]` matches any vowel character.
    Example: `/[aeiou]/` matches any vowel in a string.

    Negating a Character Class:
    `[^0-9]` matches any character that is not a digit.
    Example: `/[^0-9]/` matches any non-digit character.

    Ranges:
    `[a-z]` matches any lowercase letter.
    `[A-Z]` matches any uppercase letter.
    `[0-9]` matches any digit.
    Example: `/[a-zA-Z]/` matches any alphabetical character.

    Combining Character Classes:
    `[a-zA-Z0-9]` matches any alphanumeric character.
    Example: `/[a-zA-Z0-9]/` matches any alphanumeric character.

- Bracket expressions provide a concise and powerful way to match specific characters or ranges of characters within a string. They are commonly used in regular expressions to define patterns for validation or extraction tasks.

### Greedy and Lazy Match
- Greedy and lazy matching control how much text is matched by a quantifier.
- For example:
    `*` is greedy, matching as much text as possible.
    `*?` is lazy, matching as little text as possible.

- Greedy Matching:
In greedy matching, the regex engine tries to match as much of the string as possible while still allowing the overall pattern to match. It matches the longest possible string that satisfies the pattern.

    Example:
    Consider the regex pattern `/a.+b/` applied to the string `"aabab"`.
    Greedy Match: The regex engine matches the longest substring that starts with `a` and ends with `b`. So, it matches the entire string `"aabab"`.

- Lazy Matching:
In lazy matching, the regex engine matches the shortest possible string that satisfies the pattern. It matches as little as possible while still allowing the overall pattern to match.

    Example:
    Consider the regex pattern `/a.+?b/` applied to the string `"aabab"`.
    Lazy Match: The regex engine matches the shortest substring that starts with 'a' and ends with 'b'. So, it matches the substring `"aab"`.

- Comparison:
Greedy: Matches the longest possible substring that satisfies the pattern.
Lazy: Matches the shortest possible substring that satisfies the pattern.
Both greedy and lazy matching have their use cases, depending on the specific requirements of the pattern being matched. Greedy matching is the default behavior in most regex engines, while lazy matching is indicated by appending a `?` after quantifiers such as `+` or `*`.

### Boundaries
- Boundaries assert that a match occurs at a certain position in the input text.
- For example:
    `\b` matches a word boundary.
    `\B` matches a non-word boundary.

- Boundaries in regular expressions specify positions within the text where a match must occur. Here are more examples of different types of boundaries:

    Word Boundary (\b):
    The word boundary `\b` matches the position between a word character (alphanumeric or underscore) and a non-word character (or the start/end of the string).
    Example:
    Consider the regex pattern `/cat\b/` applied to the string `"catch cat cathedral"`.
    Matches: The word boundary before the word "cat" in "catch" and "cathedral".

- Start of String (^):
- The start of string anchor `^` matches the position at the start of the string.

    Example:
    Consider the regex pattern `/^cat/` applied to the string `"cat catch cathedral`".
    Matches: The word "cat" at the start of the string.

- End of String ($):
- The end of string anchor '$' matches the position at the end of the string.

    Example:
    Consider the regex pattern `/cat$/` applied to the string `"catch cathedral cat"`.
    Matches: The word "cat" at the end of the string.

- Word Boundary (\B):
- The non-word boundary \B matches any position that is not a word boundary.

    Example:
    Consider the regex pattern `/cat\B/` applied to the string `"catch cat cathedral"`.
    Matches: The non-word boundary after the word "cat" in "catch" and "cathedral".

- These examples demonstrate how boundaries can be used to precisely define where a match should occur within the text.

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