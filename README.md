# CS For JS: Regex Tutorial- Hex Value

The purpose of this tutorial is to introduce you to regular expressions and demonstrate how they work. A regular expression, or _regex_, is a sequence of characters that illustrate or define a search pattern. They are used to find, match, replace, or validate input in strings. 
Regular expressions are used in many programming languages, my tutorial will focus on their use in JavaScript.

## Summary

The following is the regular expression for matching a hexadecimal color value that we will be examining in this tutorial:
```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```
Hexadecimal color values are alphanumeric codes that define sRGB colors in computer and digital applications. Hex values, as they are commonly called, represent the three primary RGB colors (red, green, blue) using values ranging from 00 to ff, indicating the intensity of the color. There is plenty to learn about color theory and the hex color model, but for this tutorial, all you need to keep in mind is:  

* Hex color values generally, but not always, start with the '#' symbol  
* Hex color values contain a combination of numbers (0-9) and/or letters ( a-f )  
* Hex color values are either three or six digits long, not including the '#'  

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Conclusion](#conclusion)

## Regex Components

### Anchors

Our regex is enclosed by anchors on both ends, indicating that the match will span the entire string
* The `^` symbol marks the beginning of the string
* The `$` symbol marks the end of the string

```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/  

In our example, you can see that the text we are matching will begin after the `^` and end at `$`
```

### Quantifiers

Quantifiers specify the number of characters to match. They are located to the right of the expression or characters in question.
 * The `+` indicates that the element may be repeated 1 or more times
 * The `*` indicates that the element may be repeated 1 or more times, as well as 0 times
 * The `?` indicates that the element is optional, matching 0 or 1 occurrences
 * The `{n}` indicates a quantity, either a single number or a range of numbers
 
Here, the quantifier `?` indicates that the '#' symbol in the hex value is optional.  
```
#?  

Example: Hex values of 000AAA and #000AAA are both matches
```
The `{n}` quantifiers in our regex tell us that hex values are exactly 6 digits or exactly 3 digits long
```
{6}, {3}

Example: #123456 and #123 are both valid hex values
```

### OR Operator

The OR Operator is exactly what is sounds like, it means "or". Denoted with a vertical line `|`, the OR Operator tells the regex to match the pattern either before it or after it.

In our regex, the OR Operator indicates that a matching pattern `[a-f0-9]` can have 3 or 6 characters
```
[a-f0-9]{6}|[a-f0-9]{3}  

Example: A hex value of #001122 or #012 will match
```

### Grouping and Capturing
A regex captures characters by using parenthesis `()` to group them.  
We can see in our example, the multiple characters within the `()` are treated as a unit, a single hexadecimal value with either 6 or 3 characters.  
```
([a-f0-9]{6}|[a-f0-9]{3})
```

### Bracket Expressions

Brackets are used in this regex to define the character sets.  
* The bracket expression `[a-z]` matches all alphabet letters from a to z 
* The bracket expression `[0-9]` matches all whole numbers from 0 to 9  

As we see below, our regex has one bracket expression with both alphabetical and numerical values. Therefore, a matching hex code can contain any combination of letters from a-f, as well as any combination of numbers from 0-9.
```
[a-f0-9]  

Example: Hex values of #abc123, #ff0000, #c63939, #123cd4, and #2a2a2a are all matches
```

### Conclusion

Let's put it all together now and walk through our regex step-by-step.
```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```
* Our anchors indicate that we are starting at `^` and ending at `$`, matching the entire string
* The `?` quantifier tells us that the '#' symbol is optional
* The regex will match the string of characters grouped within the `()`
* Within `[]`, we see that the characters will include the range of letters `a-f` and numbers `0-9`
* According to the quantifiers and the OR Operator `{3} | {6}`, the group will be 3 or 6 characters long

So, in conclusion, if your hex value in question is a single group of characters that may or may not begin with '#', contains 3 or 6 characters from the range of letters a-f and/or whole numbers 0-9, it will match with the regex and be confirmed as a valid hexadecimal color value.

## Author

My name is Arionna Nielson & I'm a current student at the UofU Coding Bootcamp. 

[GitHub](https://github.com/arinielson)