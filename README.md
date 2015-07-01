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
Let's explore how to use some string methods, and then jump into some challenges. Remember, you can always look back at these pages as a reference, or search for the method that you need. It's good to practice using these methods, but it's always okay to look up the function name and the syntax.

In python, strings are identified with single or double quotes ''. This is important because it distinguishes string literals from the names of variables and functions. Take a look:
```
despicable_me = 'gru'
gru = "minion"
print despicable_me
print gru
```
In this example, ‘gru’ and gru are two different things  - one is a string and the other is a variable.
``'despicable_me' = gru``
makes sense.
``despicable_me = 'gru'``
would be nonsense. Try them both out, and see what errors you get!

In Python, strings can be declared using single or double quotes, but our style guide prefers that you use single quotes, as in 'hello', rather than "hello".

You can use either way, but you can't mix and match in the same string - python will still be waiting for the matching partner to the opening mark.

#Printing Strings
As you have seen, printing a string sends the string to the standard output of the command prompt, so:
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
Pretty easy. You pass a string to the raw_input function to be the prompt for the user. The program stops and waits for the input, and then treats it like a string. Give it a quick try now - you can make little quizzes and forms when you have more time.

#Special characters
How would you print the following strings? Give it a try!

I really wonder about this so called 'cheese' in the cafeteria…
I love to use "scare quotes" because I'm "sarcastic"
I am 8'3" tall. I bump my head a lot.

Try them with double quotes and with single quotes - they don't work!

Remember, quotes are used to show where a string begins and ends. So, we need a way to let python know when we want the quotes to actually show up! We need to “escape” the characters.

Python (and lots of other languages) use the backslash character to indicate that we want the actual character, not the symbolic meaning - ending the string, in the case of single or double quote marks.

print 'I really wonder about this so called \'cheese\' in...'
print "I love to use \"scare quotes\" because I\'m \"sarcastic\"'
print 'I am 8\'3\" tall. I bump my head a lot.'

#String concatenation
The process of joining two strings is called "concatenation" in programming. This is one of those things that might seem intuitive to a human but needs to be spelled out explicitly for the computer. For instance, when I run this, what will display?
```
new_str = 'one' + 'two'
print new_str
```
Try it!

Instead of getting 'one two' like one would expect,  python prints 'onetwo’. Python didn't put a space in between, it just stuck 'two' right onto the end of 'one'!

In python, concatenating two strings is as simple as using the '+' sign. 'hi' + ' ' + 'there' equals 'hi there'. Python doesn't add anything extra - if you want a space between your words, you need to put it there!

What happens when you try to concatenate a string with a variable? What if the variable is holding a number?
```
>>> name = 'albert'
>>> greeting = 'hi' + ' ' + 'there' + ' ' + name + '!'
>>> print greeting
hi there albert!
>>> number = 5
>>> print greeting + number
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: cannot concatenate 'str' and 'int' objects
```
Python actually has more than one way of joining strings together. Check it out!
```
>>> print 'one', 'two', 'three'
one two three
>>> print 'did you see that?'
did you see that?
>>> print 'commas','join','strings','with','spaces'
commas join strings with spaces
```
Neat!
```
>>> print " ".join(['we','can','use','other','separators','too,','if','we','like!'])
we can use other separators too, if we like!
>>> print "+".join(['we','can','use','other','separators','too,','if','we','like!'])
we+can+use+other+separators+too,+if+we+like!
>>> print "_".join(['we','can','use','other','separators','too,','if','we','like!'])
we_can_use_other_separators_too,_if_we_like!
>>> print " any ".join(['string','can','be','used','as','a','separator!'])
```
string any can any be any used any as any a any separator!

We haven't looked at lists yet, but if you follow the syntax, you'll be a-ok. If not, you'll get an error - no big deal!

#Student Activity:
enter a set of assignments, so that:
```
print apple, 'apple', banana
print college, 'college', major
```
will result in the output
```
( apple )
( college )
```
Tricky, huh?

Now try to make
```
print apple, 'apple', apple
```
show the output
```
' apple '  
```

You'll have to be clever with your single and double quotes or, better yet, escape the quotes with \

#Substrings
A substring is a part of a string. For instance, 'he' is a substring of the string 'hello' (the first 2 characters). Substrings work exactly as they sound; ‘super’ is a substring of the string ‘superfly’ because ‘super’ is a part of ‘superfly’. To get a substring from a string, use square brackets and specify the range of characters that you want from the string.

Grabbing a specific character:
```
>>> old_str = 'superfluous'
>>> print old_str[0]
s
>>> new_str = old_str[3]
>>> print new_str
e
```
Notice here, that old_str[0] gets the first character of the string. Just like in javascript arrays, string characters are indexed starting at 0. When I say old_str[3]I am asking for the fourth character of new_str.

Grabbing a substring of a range of characters in a string looks like this
```
>>> old_str = 'superfluous'
>>> print old_str[0:2]
su
>>> new_str = old_str[2:6]
>>> print new_str
perf
```
As you might be able to guess, the selection works like this:
```
<string>[<first character position>: <last character position +1>]
```
Try it out in your interpreter - slice and dice some strings you create. What happens when you don't store the string in a variable before you take the substring?

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
Pretty convenient!


#Replace Function
Replace() replaces a substring of a string with another substring. Here are some examples
```
>>> old_str = 'superfluous'
>>> new_str = old_str.replace('super', 'SUPA')
>>> print new_str
SUPAfluous
```
This works on any character or set of characters - including punctuation.
```
>>> old_str = 'superfluidity!'
>>> new_str1 = old_str.replace('u', 't')
>>> new_str2 = old_str.replace('!', '?')
>>> print old_str
superfluous!
>>> print new_str1
stperfltidity
>>> print new_str2
superfluidity?
```
# Lower and Upper Function

lower() and upper() make strings lowercase and uppercase respectively.
```
>>> old_str = 'Seattle Seahawks'
>>> print 'i'm like: ' + old_str.lower() + '?'
i'm like: seattle seahawks?
>>> print 'and he's like: ' + old_str.upper() + '!!!'
and he's like: SEATTLE SEAHAWKS!!!
```
Pretty cool.

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

#Student Activity
You can solve the first problem by using the upper() and lower() functions described above. What about the spaces?  Well, strip() removes all spaces from the beginning and end of the string, leaving you with just the interesting content.
```
user_name = raw_input('Tell me your name: ')

# Normalize the user's name.
user_name = user_name.lower()
user_name = user_name.strip()

if user_name == 'michelle':
    print 'Oh, I know you!'
elif user_name == 'collin':
    print 'You wrote this web page!'
else:
    print 'I\'m sorry, I don\'t know you...'
```
Strip won't help with spaces in the middle of strings - what else could you do to normalize those?
Converting between strings and integers
Programs you write are the interface between people, who use words, and computers, which use numbers. It's often useful to be able to switch back and forth. Try running the following:
```
>>> str1 = 'I have'
>>> int1 = 99
>>> str2 = 'bottles of beer on the wall'
>>> print str1 + ' ' + int1 + ' ' + str2
```
We want this to print "I have 99 bottles of beer on the wall", but what goes wrong?
```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: cannot concatenate 'str' and 'int' objects
```
What we have here is a type error. While it might make sense to us to add 99 and “bottles of beer” to get “99 bottles of beer”, Python doesn't want to mix different types of data - integers and strings. It’s not sure if you want it to convert the string “bottles of beer” into a numeric representation and then add it to the integer 99 or to convert 99 into a string and concatenate it with “bottles of beer” to get a new phrase.

To fix this, we have to convert from one to the other. The str() and  int() functions will let you switch to the str (string) or int (integer) datatypes.

```
>>> str(3) # This will return '3'
'3'
>>> int('3') # This will return 3
3
>>> print 'I have ' + str(99) + 'bottles of beer on the wall'
```
How can we fix this little script? When it runs in the console, it throws an error!
```
boast.py
number = raw_input('how many eggs do you eat each morning? ')
my_eggs = number + 99
print 'Ha! I eat ' + my_eggs + '! Way more!'
```
```
$ python boast.py
how many eggs do you eat each morning? 100
Traceback (most recent call last):
  File "boast.py", line 2, in <module>
    my_eggs = number + 99
TypeError: cannot concatenate 'str' and 'int' objects
```

#String Formatting
There's one more powerful string method that gets used allllll the time. It lets us pass different data into a string, which is faster and more convenient than keeping track of different pieces of string and concatenating them ourselves. Let's take a look at the difference:
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
