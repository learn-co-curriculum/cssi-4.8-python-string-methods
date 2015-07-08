---
tags: cssi, python, string methods
level: 2
languages: python
---
#Python String Functions

#Objectives:
+ Understand the syntax of strings in Python
+ How to get data from the user
+ How to concatenate strings
+ How to interpolate with str.format()
+ Understand style guide and escape characters

#Motivation
We've seen how to use strings to print words to the command line - just like we printed words to with the javascript console and the python interpreter. But strings have way more power than we've seen so far. We'll look at some of the powerful functions python has for dealing with strings.

#Strings
Let's explore how to use some string methods, and then jump into some challenges. Remember, you can always look back at these pages as a reference, or search for the method that you need. It's good to practice using these methods, but it's always okay to look up the function name and the syntax.In Python, strings can be declared using single or double quotes.

#Printing Strings
```
print 'hello, world!'
```
displays
```
hello, world!
```
in your command prompt. You'll be doing lots of printing, so remember this one!

#User input
In python, if you want to get text from a user, you can use the input() function. Let's try it out!
```
>>> name = raw_input('Enter your name: ')
Enter your name: Joseph
>>> name
'Joseph'
```

#String concatenation
The process of joining two strings is called "concatenation" in programming. This is one of those things that might seem intuitive to a human but needs to be spelled out explicitly for the computer. For instance, when I run this, what will display?
```
new_str = 'one' + 'two'
print new_str
```
Python doesn't add anything extra - if you want a space between your words, you need to put it there!

What happens when you try to concatenate a string with a variable? What if the variable is holding a number?
```
TypeError: cannot concatenate 'str' and 'int' objects
```

#Substrings
A substring is a part of a string. Substrings work exactly as they sound; ‘super’ is a substring of the string ‘superfly’ because ‘super’ is a part of ‘superfly’. To get a substring from a string, use square brackets and specify the range of characters that you want from the string.

Grabbing a specific character:
```
>>> old_str = 'superfly'
>>> print old_str[0]
s

```
Notice here, that old_str[0] gets the first character of the string. Just like in javascript arrays, string characters are indexed starting at 0.

Grabbing a substring of a range of characters in a string looks like this
```
>>> old_str = 'superfly'
>>> print old_str[0:4]
su
```
As you might be able to guess, the selection works like this:
```
<string>[<first character position>: <last character position +1>]
```
Here are a couple handy shortcuts for selecting particular parts of strings:
```
>>> print old_str[3:] # character position 3 to the end
erfluous
>>> print old_str[:5] # From the beginning to character position 4
super
```
#String length
Sometimes, you want to know how long a string is. Imagine you  wanted to insert line breaks into strings so that they displayed nicely - you want to know how long your strings are!

Python gives us the len() function to determine a string's length.
```
>>> short_string = "o"
>>> long_string = "(pumba) When I was a young warthog… (timon) When he was a young waaarthoooooooooooooog!"
>>> len(short_string)
1
>>> len(long_string)
89
```

#Replace Function
Replace() replaces a substring of a string with another substring. Here are some examples
```
>>> old_str = 'superfly'
>>> new_str = old_str.replace('super', 'SUPA')
>>> print new_str
SUPAfly
```
# Lower and Upper Function

lower() and upper() make strings lowercase and uppercase respectively.
```
>>> old_str = 'Seattle Seahawks'
>>> print  old_str.lower()
seattle seahawks
>>> print old_str.upper() + '!!!'
SEATTLE SEAHAWKS!!!
```

#Strip Function

When you prompt a user for some text or grab a string from a database, you will almost certainly want to normalize it using strip(). You want to remove unnecessary variation. For example, if you have a program that prints a greeting based on a name:
```
# greeter.py
user_name = raw_input('Tell me your name: ')

if user_name == 'Collin':
  print 'Oh, I know you!'
elif user_name == 'Shubie':
  print 'You wrote this web page!'
else:
  print 'I\'m sorry, I don\'t know you...'
```
...you will get different output depending on whether the user types in:
```
$ python greeter.py
Tell me your name: Collin
Oh, I know you!
$ python greeter.py
Tell me your name: COLLIN
I'm sorry, I don't know you…
$ python greeter.py
Tell me your name:             Collin
I'm sorry, I don't know you...

'Collin', 'COLLIN', and '                   Collin'
```
To a human, it's all the same name! But the computer gets confused by different capitalization, or by spaces in the input.

#String Formatting
String formatting lets us pass different data into a string, which is faster and more convenient than keeping track of different pieces of string and concatenating them ourselves. Let's take a look at the difference:
```
>>> customer = "Rob"
>>> print "Hello, " + customer + "!"
Hello, Rob!
>>> print "Hello, {name}!".format(name=customer)
Hello, Rob!
```
That looks more complicated than just concatenating. Why would anyone do that? Well, let's look at an example where the customer changes.

Without format:
```
>>> customer = "Georgia"
>>> print "Hello, " + customer + "!"
Hello, Georgia!
>>> customer = "Norah"
>>> print "Hello, " + customer + "!"
Hello, Norah!
>>> customer = "Nicki"
>>> print "Hello, " + customer + "!"
Hello, Nicki!
>>> customer = "Joseph"
>>> print "Hello, " + customer + "!"
Hello, Joseph!
```
With format:
```
>>> greeting = "Hello, {name}!"
>>> customer = "Georgia"
>>> print greeting.format(customer)
Hello, Georgia!
>>> customer = "Norah"
>>> print greeting.format(customer)
Hello, Norah!
>>> customer = "Nicki"
>>> print greeting.format(customer)
Hello, Nicki!
>>> customer = "Joseph"
>>> print greeting.format(customer)
Hello, Joseph!
```
Much better! Instead of typing out all of those quotes and pluses, we just called a function. The code is more DRY, and we all know that we don't like wet code.

Check out python string format() in the python documentation. Remember, you can use dir() to see a strings' available functions, and help() on a function to see a description of how it is used.

#Conclusion
Try these python function labs!
