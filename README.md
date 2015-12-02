
#Python String Functions

#Objectives:
+ Understand the syntax of strings in Python
+ How to get data from the user
+ How to concatenate strings
+ How to interpolate with str.format()
+ Understand style guide and escape characters

#Motivation
Python has lots of prebuilt string methods that help us use and modify strings. 

#Strings
Let's explore how to use some string methods, and then jump into some challenges. Remember, you can always look back at these pages as a reference, or search for the method that you need. It's good to practice using these methods, but it's always okay to look up the function name and the syntax.

#Printing Strings
```
print 'hello, world!'
```
displays
```
hello, world!
```
in your command prompt. You'll be doing lots of printing, so remember this one!

#User Input
In python, if you want to get text from a user, you can use the raw_input() function. Let's try it out!
```
>>> name = raw_input('Enter your name: ')
Enter your name: Joseph
>>> name
'Joseph'
```

You can also use the input() function, but the user would have to enter their name as a string, otherwise the console will throw back an error.

#String Concatenation
The process of joining two strings is called "concatenation" in programming. This is one of those things that might seem intuitive to a human but needs to be spelled out explicitly for the computer. For instance, when I run this, what will display?
```
new_str = 'one' + 'two'
print new_str
```
Python doesn't add anything extra - if you want a space between your words, you need to put it there!

When you try to concatenate a string with a datatype other than another string you will get an error.
```
TypeError: cannot concatenate 'str' and 'int' objects
```


#Substrings
A substring is a part of a string.  To get a substring from a string, use square brackets and specify the range of characters that you want from the string. Just like in javascript arrays and python lists, string characters are indexed starting at 0.

Grabbing a specific character:
```
>>> old_str = 'superfly'
>>> print old_str[0]
s
```

Grabbing a substring of a range of characters:
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
#String Length

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
Replace() replaces a substring of a string with another substring. 
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
The strip() function removes leading and trailing white space.
```
>>>print '     spaces everywhere     '.strip()
spaces everywhere
```

#String Formatting and Interpolation
String interpolation lets us pass different data into a string, which is faster and more convenient than keeping track of different pieces of string and concatenating them ourselves. There are two ways to do string interpolation. With the .format method and with the %s. Let's take a look at the difference:


***.format***
This is the newer version of using variables within string in Python.

The string is in quotes. The placeholder for the variable is surrounded by curly brackets.  The entire string is followed by .format(). Inside the parenthesis, declare what the substituted variable will be. 

The Spongebob example uses a keyword argument, 'character', which is assigned to a global variable, 'name'.
```
name = "Spongebob Squarepants"
print "Who lives in a Pineapple under the sea? {character}".format(character=name)
>> Who lives in a Pineapple under the sea? Spongebob Squarepants.
```
The hobby example uses two keyword arguments: 'name' and 'hobby', which are assigned to strings within .format()
```
print "{name} is the best at {hobby}".format(name='Charlie', hobby='playing piano')
>>Charlie is the best at playing piano
```

This final example uses positional arguments:
```
print "There are {0} students at CSSI in {1}!".format(30, "Chicago")
>>There are 30 students at CSSI in Chicago!
```
***%s***
The older way to use variables in strings and uses the % operator.

Again the whole string is in quotes. The placeholder for the variable is a percent sign and the first letter of the datatype. (%d int, %s string, %f/%g float). The entire string is followed by a percent sign and the name of the variable

```
print "The %s have %d %s championships in %d years" %("Chicago",3, "NHL", 3)
>>The Chicago have 3 NHL championships in 3 years
```

# Conclusion
There are a lot of string methods that we can access in python. Whenever you don't remember if one exists, or the syntax, you can always look up the documentation.

# References
[Python String Interpolation Guide] (https://mkaz.com/2012/10/10/python-string-format/)

<a href='https://learn.co/lessons/cssi-4.9-python-string-methods' data-visibility='hidden'>View this lesson on Learn.co</a>
