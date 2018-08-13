# Regex

[Good resource for learning](https://regexone.com)

## Basics

* `abc` will match all strings containing `abc` anywhere in the string, like `123abc123`
* Patterns are case-sensitive
* `[]` represents a single character in the string and the character must match a character in the brackets
  * `[abc]` would match with the `a` in `abc` and not all three characters
* It's best two write as specific of a RegExp as possible
  * Use `^`, `$`, `{}`, etc

## Special Characters/Expressions

* `\`: escape character
* `\d`: shorthand for any digit, 0-9
* `\D`: any non-digit
* `\w`: Any alphanumeric character
* `\W` Any NON-alphanumeric character
* `.`: wildcard. Match any character. If you want to match a period, use `\.` to escape it
* `^`: exclude characters within brackets. "Do not match"
* `-`: Match a range of characters. Like `[0-5]` is the same as `[012345]`
* `{m}`: Match exactly m repetitions of preceding expression. `[abc]{3}` would match all characters in `abc` but not `ab`
* `{m,n}`: Match m to n repetitions. `[abc]{2,3}` matches both `abc` and `ab`
* `*`: Match zero or more repetitions of preceding expression. Must always follow a character or digit. `\d*` matches any number of digits
* `+`: Match at least one or more repetition. Must always follow a character or digit. `\d+` matches at least 1 digit
* `?`: Preceding character/expression is optional. `ab?c` matches both `abc` and `ac`
* `\s`: Any whitespace
* `\S`: Any non-whitespace character
* `^`: Line start. `^success` will match `success` but not `unsuccessful`
* `$` Line end. `success$` will match `success` but not `successful`
* `(...)`: Capture group. Returns the text that matches expression within `()`. `(abc)\d*` would match `abc123` and return `abc`
  * You can nest groups to return multiple strings. `(ab(c))\d*` would match `abc123` and return `abc, c`
  * You can also capture mutliple groups. `(abc)(123)` would match `abc123` and return `abc, 123`
* `|`: OR. Match the expression on either side of the `|`
  * Group the expression with `()`. `(abc|123)` matches both `abc` and `123` but won't return anything
* `\b`: Matches the boundary between a word and non-word character. `\w+\b` is useful for matching whole words
* `\n`: Where `n` is a number, it allows you to back-reference captured groups
  * `\0` is for the whole matched text, `\1` is matched group 1, etc...
    * Useful for find+replace. If you wanted to swap two things, you might search `(\d+)-(\d+)` and replace with `\2-\1`