# Title Matching an Email - Regex

In this tutorial, we will go over how to match an email using Regex, otherwise known as Regular Expression. These expressions are used to to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. Below, we will break down the sequences of characters that are placed together as paramaters that help search and validate data.  

## Summary

The regex described in this tutorial is matching an email. We will explain the various components that make up the regex that help it return the correct data. 
Snippet: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

### Anchors
`^` matches the beginning of a target string, while `$` matches the end of the target string or input--these are called `Anchors`. For example, if we were to put in the email addresses `uni-corn_1@yahoo.com` and `unicorn@hotmail.govvvvv`, with `^` and the front of the input and `$` and the end (ex: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`), only `uni-corn_1@yhaoo.com` would be selected since it contains `a-z` letters and `0-9` numbers. `unicorn@hotmail.govvvvv` is not selected since it does not adhere to the limits "anchored" at the end of the expression that `$` is anchoring. Basically, it goes outside of the `quantifiers`. `Quantifiers` are explained in the next section.

### Quantifiers
As the exmple above, `unicorn@hotmail.govvvvv` was not found in our regular expression. While it fulfils all the front parts of the expression, there are certain `quantifiers` in order that must match. The section, `{2,6}` is the `quantifier` stating that the back part of the email address string must be between two and six characters. If you notice, `.govvvvv` is seven characters which disqualifies it from being returned since it exceeds the six character limit. 

### Character Classes
This email match example uses the `character class` `\d` which is the `digit` `character class`. Ex: `[\da-z\.-]`. When using `\d` this `class` finds any single digit. 

### Grouping and Capturing
`Groups` are used to return certain sets of data. For example, this regex calls three parts: the username, the domain, and extension. 
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/' Let's break down the parts:

- Username: `([a-z0-9_\.-]+)`
- Domain: `([\da-z\.-]+)`
    *Notice that this includes `@` and `\.` around it to caputure the full part of the domain. Ex: `@yhaoo.`
- Extension: `([a-z\.]{2,6})`

Therefore, each part is `grouped` together and the strings are `captured` to make the full string.

### Bracket Expressions
`Bracket Expressions` exist in a group. Take for example the `username` part of the regex: `([a-z0-9_\.-]+)`. this contains the bracket expression: `[a-z0-9_\.-]`.

These `bracket expressions` are used to find matching or non-matching sets of data such as letters, numbers, or special characters in this case. 

Let's break it down:

`a-z`: is looking for lowercase letters, a-z
`0-9`: looks for digits
`_`: is looking for underscores
`\.`: this part is looking for periods. However, the period requires a backslash `\` so that the period `.` can be found and included, or `captured.` This is called `escaping` a character and making it `literal.` In other words, for that `character` to literally be found. 

### Greedy and Lazy Match
This expression uses `greedy matching` in its `groups.` How do we know this? By the use of the `+.` By making a match `greedy,` using the `+` allows it to find the logest match possible. Think of it as another quantifier. If you notice on the `exenstion group,` there is no `+,` but there is `{2,6}.` The `{2,6}` is fixed, but `+` is not. 

## Author

Nancy holds expertise in Human Resources, but is expanding her skills into the world of Tech. Checkout her GitHub at: https://github.com/nancyrosas0.
