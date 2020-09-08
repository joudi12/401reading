# Python Regular Expression 
- Regular Expressions, often shortened as regex, are a sequence of characters used to check whether a pattern exists in a given text (string) or not. If you've ever used search engines, search and replace tools of word processors and text editors - you've already seen regular expressions in use. They are used at the server side to validate the format of email addresses or passwords during registration, used for parsing text data files to find, replace, or delete certain string, etc. They help in manipulating textual data, which is often a prerequisite for data science projects involving text mining.

#### Regular Expressions in Python
- In Python, regular expressions are supported by the re module. That means that if you want to start using them in your Python scripts, you have to import this module with the help of import:
> import re
- The re library in Python provides several functions that make it a skill worth mastering. You will see some of them closely in this tutorial.


## Basic Patterns: Ordinary Characters
- You can easily tackle many basic patterns in Python using ordinary characters. Ordinary characters are the simplest regular expressions. They match themselves exactly and do not have a special meaning in their regular expression syntax.

> Examples are 'A', 'a', 'X', '5'.

- Ordinary characters can be used to perform simple exact matches:

```
pattern = r"Cookie"
sequence = "Cookie"
if re.match(pattern, sequence):
    print("Match!")
else: print("Not a match!") 
```
> Match! 
- Most alphabets and characters will match themselves, as you saw in the example.

- The match() function returns a match object if the text matches the pattern. Otherwise, it returns None. The re module also contains several other functions, and you will learn some of them later on in the tutorial.
>\t - Lowercase t. Matches tab.
> \n - Lowercase n. Matches newline.

> \r - Lowercase r. Matches return.

> \A - Uppercase a. Matches only at the start of the string. Works across multiple lines as well.

> \Z - Uppercase z. Matches only at the end of the string
* '*' - Checks if the preceding character appears zero or more times starting from that position.
> ? - Checks if the preceding character appears exactly zero or one time starting from that position.

> {x} - Repeat exactly x number of times.
> {x,} - Repeat at least x times or more.
> {x, y} - Repeat at least x times but no more than y times.
> The + and * qualifiers are said to be greedy. You will see what this means later on.



