# Title Matching an Email - Regex

In this tutorial, we will go over how to match an email using Regex, otherwise known as Regular Expression. These expressions are used to to find certain patterns of characters within a string, or to find and replace a character or sequence of characters within a string. Below, we will break down the sequences of characters that are placed together as paramaters that help search and validate data.  

## Summary

The regex described in this tutorial is matching an email. We will explain the various components that make up the regex that help it return the correct data. 
Snippet: /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
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
`^` matches the beginning of a target string, while `$` matches the end of the target string or input--these are called `Anchors`. For example, if we were to put in the email addresses `uni-corn_1@yahoo.com` and `unicorn@hotmail.govvvvv`, with `^` and the front of the input and `$` and the end (ex: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`), only `uni-corn_1@yhaoo.com` would be selected since it contains `a-z` letters and `0-9` numbers. `unicorn@hotmail.govvvvv` is not selected since it does not adhere to the limits "anchored" at the end of the expression that `$` is anchoring. Basically, it goes outside of the `quantifiers`. `Quantifiers` are explained in the next section.

### Quantifiers
As the exmple above, `unicorn@hotmail.govvvvv` was not found in our regular expression. While it fulfils all the front parts of the expression, there are certain `quantifiers` in order that must match. The section, `{2,6}` is the `quantifier` stating that the back part of the email address string must be between two and six characters. If you notice, `.govvvvv` is seven characters which disqualifies it from being returned. 

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
