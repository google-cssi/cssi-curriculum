---
  layout: post
  title: Python Functions
  language: python
---

# What You Will Learn:
+ What functions are, and how we use them in python
+ N.I.C.O (Name, Input, Code, Output)
+ How to declare functions with and without parameters
+ Call functions with and without passing arguments
+ Output vs. Return Values
+ Local and global variable scope

# Why This is Important:
Functions let us package code into blocks that we can reuse. We've been using a handful functions already and this lesson will explain how and why we've been doing that.

In programming, a function holds a set of actions that will run when we call that function. This helps us control the flow of our program and allows us to easily repeat a set of actions multiple times.

## Polly the Parrot
![parrot](http://1.bp.blogspot.com/-HDI-XiLird8/ToaJsehSY0I/AAAAAAAABso/XHXOU_qDK3k/s1600/Parrot+Funny+Pictures_1.jpg)

As you learn about functions, you'll be training some parrots with special talents.

# Function Declaration
A python function is essentially a set of instructions that we write out and can reuse over and over again.

The syntax for writing python functions is very specific. Let’s write a function in python to go get dinner. To define a function in python, you use the `def` keyword, followed by the name of the function, parentheses, and a colon. Like this:

```python
def go_get_dinner():
```

Then, you write the block of code defining what the function does. The block of code, called the 'function body', is indented - that's what tells python which statements are part of your function, and when your function declaration is over.

```python
def go_get_dinner():
  print "Stop what you're doing. "
  print "Wash your hands. "
  print "Get a plate of food."
  print "EAT!"

print "finished declaring the function"
```
Copy this code in a file dinner.py, and run it from the command line.

Python only printed the last line. Why is that? We declared our function, but didn't call it. Declaring the function is like writing down a set of instructions on a piece of paper. We wrote down the instructions, but we never told python to follow them.

# Calling a Function
When we want a function to run, we type its name and include parentheses. This is called 'calling' the function. Python will run the function whenever it sees `go_get_dinner()`.

```python
def go_get_dinner():
  print "Stop what you're doing. "
  print "Wash your hands. "
  print "Get a plate of food."
  print "EAT!"

go_get_dinner()
go_get_dinner()
go_get_dinner()
```

When you write go_get_dinner(), you are telling the computer - do the steps in the `go_get_dinner` function. Test it out.

What’s up with those parentheses? Those are a placeholder for something called an argument.

Our instructions are pretty generic right now. What if we wanted to direct them towards a specific student? Like adding a step that says “hey, Joe”.

## Introducing Polly
Create a file named polly.py and write a function `hello` that prints out "Polly Wanna Cracker!"

Call your function below the definition. Save polly.py and run it from the terminal. You should see your message!

# Using Parameters (Inputs)
It's awesome to be able to reuse all of our print statements with a single command, but functions have even more power. We can modify our function to do slightly different things based on a parameter.

Let's rewrite our function so we can tell different students to get dinner.

```python
def go_get_dinner(student):
	print 'Hey, ' + student + '! '
  print "Stop what you're doing. "
  print "Wash your hands. "
  print "Get a plate of food."
  print "EAT!"
```

We can reuse this function and change the name of the student we address when we call it. To address different students, we pass their name as an argument - we put the name in the parentheses.

```python
go_get_dinner("Joe");
go_get_dinner("Jill");
go_get_dinner("Josie");
```
The `student` in our function gets assigned to the name that we pass in.
Arguments extend the power of functions, making them far more reusable.

# Arguments vs Parameters
* A parameter is a variable in the function definition: "student". It's available inside the block of code in the function body.
* An argument is the data you pass into the function's parameters when you call it: "Joe", "Jill", "Josie". It comes from outside the function.

# Happy Parrot, Sad Parrot
**Happy Parrot** - This parrot is so happy. It accepts a 'thing' as its argument and then returns a string where it says how happy it is about the thing!
```python
def happy_parrot(thing):
  print "I am so happy about " + thing + "!"

happy_parrot('carrots')
```

Now, write functions to let the parrot express a wider range of emotions. `sad_parrot` should print out a message about how sad the parrot is about the parameter passed in.

`angry_parrot` should express the parrots anger - except if the argument was "cracker" - Polly is never angry about a cracker.

Be sure to call your functions after defining them, and run your code!

# Return Values vs. Printing Output
Often, we want to do something with the result of a function - not just print the output. If we want our function to have some result, we tell it to 'return' a value. The syntax for a return statement is:
```python
def myFunction():
  #... the rest of the function
  return value_to_return
```

Functions can have only one return statement, and no statements after the return statement get evaluated. Usually, return statements come at the end of the function body.

Instead of printing our instructions to the student, let's return a string with the instructions, so that we can do other things with the string before printing it out.

```python
def go_get_dinner(student):
	instructions = 'Hey, ' + student + '! '
  instructions += "Stop what you're doing. "
  instructions += "Wash your hands. "
  instructions += "Get a plate of food. "
  instructions += "EAT!"
  return instructions
```

Now, `go_get_dinner()` will not print anything. Try adding this line to your python file and running it:
```python
go_get_dinner("Jemma")
```

To see the result, we need to print it:
```python
print go_get_dinner("Jemma")
```

When python sees that line, it:
1. Runs the function
2. Replaces `go_get_dinner("Jemma")` with the value returned by the function call - the string "Hey, Jemma! Stop what you're doing. Wash your hands. Get a plate of food. EAT!"
3. prints that string.

If we don't have `print` before the statement, python does the replacement, but doesn't do anything with the string.

Return values let us do more with the results of our functions:
```python
print go_get_dinner("Jimmy").upper()
print go_get_dinner("Jessica").lower()
tell_them = go_get_dinner("CSSI Students")
tell_them += "!!!!!!"
tell_them.upper()
print tell_them
```

## Polly Returns Values
Polly likes to repeat the words you say, with a little noise. Write a function `repeat()` that takes a single parameter and returns the parameter with the word "Squawk!" before and after it. So, you should be able to call it:
```python
print repeat("Good Bird!")
```
and get as output:

```python
Squawk! Good Bird! Squawk!
```
#  N.I.C.O
We can break down the creation of functions into four things that every function has:

 * **Name** - Decide an appropriate name for the function
 * **Input** - Figure out what inputs, if any, are needed to accomplish what the name describes
 * **Code** - Put the code inside the function to be run when it is called
 * **Output** - A value that the function can return (though it can be `undefined`)

#  Variable Scope
"Scope" tells when in our program different variables exist.

When you declare a variable outside of a function it will also be available inside of the function. This is called a 'global' variable - it exists everywhere! For example:

```python
milk_type = "skim milk" # global variable
def is_whole_milk():
  if (milkType == "whole milk"):
 	  return true
  else:
    return false

print milk_type
```

If I run `is_whole_milk()`, I'll  get back false. The function `is_whole_milk` has access to the variable milk_type that was declared outside of the function.

If you declare a variable inside of a function it will only be available inside of the function. This is called a local variable.

Here is an example:

```python
def milk_the_cow():
  bessy_cow = 'milked'  #  local var
  return bessy_cow;

print bessy_cow  #  Throws an error, since the variable is local to the function 'milkTheCow'

print milk_the_cow()  #  Prints correctly since we are printing the returned value
```

If we type `bessy_cow` we’ll get an error. We are trying to access `bessy_cow` from outside of the function and she only exists inside of the function.

The only time `bessy_cow` exists is while the function is executing.

# More to know about functions
Functions can accept any datatype as input. Lists, for instance:

```python
def get_max_length(list_of_strings):
  lengths = []
  for string in list_of_strings:
    lengths.append(len(string))
  return max(lengths)

print get_max_length(['hello', 'from', 'cssi', 'at', 'google'])
```

Functions can return any datatype, too:

```python
def get_digits(my_string):
  digits = []
  for letter in my_string:
    if letter.isdigit():
      digits.append(letter)
    return digits

print get_digits('It is 71 degrees today')
```

Functions can modify their arguments:

```python
def swap_ends(some_list):
  some_list[0] = some_list[-1]

a_list = [1, 2, 3, 4]
print a_list
swap_ends(a_list)
print a_list
```

And functions can call each other:

```python
def mess_with_list(my_list):
  swap_ends(my_list)
  my_list.append(5)

a_list = [1, 2, 3, 4]
print a_list
MessWithList(a_list)
print a_list
```

Parameters can be optional. In the function definition, set a default value for the parameter, then the function can call it with or without that argument:

```python
def count_up(end,start=0):
  for i in range(start,end):
    print i

# These two are equivalent
count_up(10,0)
count_up(10)

# Sometimes this is helpful - it does the same thing
count_up(end=10,start=0)
# If you specify the parameters, you can mix up the order
count_up(start=0,end=10)
```

## Super Parrot
Write a function `like()` that takes a list as a parameter and **prints out** "I like ______ " for each of the items in the list.

You should be able to call it like this:

```python
like(["crackers","pizza","pirates","treasure"])
```

and get out:

```python
I like crackers
I like pizza
I like pirates
I like treasure
```

Write a function `greet()` that takes a name parameter and an age parameter, and **returns** a greeting string like "Hi (name)! You're (age) years old." You should be able to call it like this:

```python
print greet("One-Eyed Paul",67)
```
Which would print

```python
Hi One-Eyed Paul! You are 67 years old.
```

Now, modify the `greet()` function so that the age parameter is optional. The example with One-Eyed Paul should still work, but so should this one:

```python
print greet("Peg-Leg Zeke")
```
Which should return:

```python
Hi Peg-Leg Zeke! You can keep your age a secret.
```

Write a function multi_greet() that takes a list of names as the only parameter, and **returns** a list of greeting strings:

```python
multi_greet(["Hook-hand Ramona","One-Eyed Paul","Peg-Leg Zeke","Patchy"])
```

Which would return:

```python
["Hi Hook-hand Ramona! I'm Polly.", "Hi One-Eyed Paul! I'm Polly.","Hi Peg-Leg Zeke! I'm Polly.","Hi Patchy! I'm Polly."]
```

# Conclusion:
Functions are the building block of programs. They let you create reusable machines that perform the tasks you need. This will make life a lot easier and save a ton of typing!
