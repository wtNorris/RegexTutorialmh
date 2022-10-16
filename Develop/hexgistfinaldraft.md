# Hexadecimal Regex Explained

## Summary

Regular expressions, regex for short, are sequences of characters that create a search pattern for text. Most often used in search engines, word processors, and text editors. Here you will find a detailed explanation of a particular regex, one that finds hexadecimals. Hexadecimals use a letter- and whole number- value system. Hex can be tricky to search as they can often begin with a # and vary in the amount of characters. For example to use the color white you can use #ffffff, or for a seafoam green you'd use something like #9fe2bf. 

The hex matching regex looks like this: ` /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ ` . Seemingly gibberish, each charactercomponent in this string performs a different function and will be explained in this tutorial. Please use links provided in the ToC to navigate the page, contact information is available at the bottom for further questions.


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

## Hex Matching Regex Components Breakdown

` /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ ` =

- ^                 [Anchors](#anchors)
- `#`
- ?
- (                 [Grouping and Capturing](#grouping-and-capturing) (this includes everything inside the parenthesis)
- ` [a-f0-9] `      [Bracket Expressions](#bracket-expressions) / [Character Classes](#character-classes)
- {6}               [Quantifiers](#quantifiers)
- |                 [OR Operator](#or-operator)
- ` [a-f0-9] `      [Bracket Expressions](#bracket-expressions) / [Character Classes](#character-classes)
- {3}               [Quantifiers](#quantifiers)
- )                 [Grouping and Capturing](#grouping-and-capturing)
- $                 [Anchors](#anchors)

![hexregexvisual](/Docs/img/exampleimg.png)

### Anchors

Our anchors in this expressions are the `^` and the `&` symbols. The `^` character signifies the string must begin with the letters following. For example if the expression has `^f56`, the string found by the regex must start with `f56`. The & character is the same except it applies to the preceding letters. If the expression ends in 98g$, the regex will search for strings ending in `98g`.

### Quantifiers

The quantifiers in our expression are `?` and `{6}`, `{3}`. The `?` in this case signifies that our string matched may or may not have a pound sign `#`. Remember hexadecimals don't always have the `#` in front. The `?` also only applies to preceding characters. The `{3}` and `{6}` are quantifiers (inherently greedy) and provide an exact match to what's inside the curly brackets. So this expression will return matches with either 3 or 6 characters, as these are both possible hexademical lengths.

### OR Operator

The hex matching regex contains an OR operator, | , right in the middle of the main group. As its name implies, matches found can either fit into the [a-f0-9]{6} expression OR the [a-f0-9]{3} expression. If you notice, the only thing different between these two are the numbers in each [qauntifier](#quantifiers). Our returned matches can be either 3 or 6 characters, aligning with hexadecimal codes.

### Character Classes

Character classes are any defined set of characters to find matches. Our [Bracket Expressions](#bracket-expressions) contain our chracter classes in this expression. [a-f0-9] includes alphanumerics from a-z and 0-9.  

### Flags (the hex matching regex does not include flags so a brief definition is provided)

Since regex's are literals, they must be wrapped in slashes. The only thing you'll use outside of your slashes are flags, and they come at the end after the second slash. The most common flags used are `m` which is a multi-line search, and `i` which will make your search case-insensitive. 

### Grouping and Capturing

Capturing groups in () is the regex can treat multiple characters as one unit. Our group here ` ([a-f0-9]{6}|[a-f0-9]{3}) ` combines two patterns that can be used by the regex to match hex strings. This is where you find our bracket expressions (that include our character classes) and the OR operater that again allows both to be searched and returned.

### Bracket Expressions

There are two indetical bracket expression in this regex, [a-f0-9]. This represents the character range that the expression is trying to match. The [a-f] represents the range of possible hex letters, as they only go from A to F. The [0-9] represents the whole integers found in hex codes. Grouped together the way they are, it will match any string with any combination of the letters and integers in their respective ranges. Also note this does not require the string to match all requirements, as long as it meets one.

### Greedy and Lazy Match (the hex matching regex does not include flags so a brief definition is provided)

In very short terms, a greedy match will match the longest possible string. A lazy will return the shortest. This [resource](https://www.regular-expressions.info/repeat.html)<sup>1</sup> goes further into depth on this topic.

### Boundaries (the hex matching regex does not include flags so a brief definition is provided)

" A word boundary, in most regex dialects, is a position between \w and \W (non-word char), or at the beginning or end of a string if it begins or ends (respectively) with a word character ([0-9A-Za-z_]). " -Excerp taken from [stackoverflow](https://stackoverflow.com/users/54323/brianary)<sup>2</sup>, [user brianary](https://stackoverflow.com/users/54323/brianary)

### Back-references (the hex matching regex does not include flags so a brief definition is provided)



### Look-ahead and Look-behind (the hex matching regex does not include flags so a brief definition is provided)



## Author & Resources Cited

Molly Hesse is a student of web development, with passions in the arts. Her github can be found here: [Github](https://github.com/wtNorris).

1. https://www.regular-expressions.info/repeat.html Copyright © 2003-2022 Jan Goyvaerts.