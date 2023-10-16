# A beginner's guide to coding

## Table of Contents

- Preface (why code?)
- Why Python
- How to use jupyter notebook
- Comments
- Hello world
- Data types
- Built in functions, reserved words
- Variables
- Arithmetic expressions (modulo)
- Logical operators, boolean expressions
- If statements
- Loops (while, for)
- Nested if statements and loops
- String and List (string slicing, indexing)
- Dictionary, Sets, Tuples
- Immutability
- big O, runtime
- Writing your own function
- Scopes, namespaces/name binding, references
- File Handling

Pythonic tips and tricks
(iterators, fstrings, list and dictionary comprehension)


## Preface

This guide is designed to help anyone learn how to code. There are many that believe coding is arcane or insanely difficult, but it does not need to be that way.

The goal of these tutorial pages is to make coding clear and easy to understand, especially for beginners.

### Why code?
Because it's fun [1], useful [2], and can grow your career [3]!

### Why Python?

Python is one of the most popular programming languages today. It has powerful features and libraries for data analysis, scientific computing, machine learning, web programming, and game development.

Python code has beautiful syntax and is designed to be easy to read and understand.

See more about the most common languages [here].

# Start of Tutorial

## Hello World

The most simple program in Python:
```python
print("hello world")
```

### Functions

Functions in python perform a command. `print` is a built-in function that takes a text string as input, and writes it onto the screen.

The text string is delimited using double quotes `""`, and the print function takes 
this string as input inside the parentheses.

### Interpreter

The Python interpreter takes your code, which is stored as a text
file, and processes each line, from top to bottom, one at a time.

### Comments

Comments are useful for explaining what a line of code does. They are ignored by the intepreter.
```python
# greet the user
print("Hi there!")
```

They can also be inline:
```python
print("I am learning python!")  # this is an inline comment
```

They can also span multiple lines. (see [multi-line strings])

# Part 1: Expressions and Variables

## Math Expressions

Python supports the common mathematical operators:
- addition
- subtraction
- multiplication
- division
- exponentiation

`*` is the  multiplication operator, and `**` is the exponentiation operator.

```python
2 + 3             # 5
2 * 3             # 2 * 3 = 6
2 ** 3            # 2 * 2 * 2 = 8
```

Python follows the order of operations.

```python
2 + 3             # 5
10 - 2 * 20       # -30
(10 - 2) * 20     # 160
```

Division in Python always results in a decimal number.

```python
5 / 2             # 2.5
6 / 2             # 3.0
-4 / 3            # -1.333333
```

### Floor and Modulo operators

`//` is the floor division operator (integer portion of divsion).

```python
8 // 3            # 2
9 // 3            # 3
```

`%` is the modulo operator (remainder after division).

```python
15 % 5            # 0
15 % 4            # 3
```
```python
5 % 10            # 5
5 % 5             # 0
```

## Strings

A string literal in Python is a sequence of characters. Strings can be delimited using either the `'` or `"` characters.

```python
"This is a string"
'This is another string'
```

### String operations

If you want to concatenate (join) two strings, use the `+` operator.

```python
"pine" + "apple"       # pineapple
"hello," + " friend"   # hello, friend
```

The `*` operator can be used to repeat a string.

```python
"echo" * 4              # echoechoechoecho
```

### Multi-line strings

Use `"""` if you want your string literal to span several lines.

```python
"""
Roses are red,
Violets are blue,
sugar is sweet,
and so are you.
"""
```

Multi-line strings can also be used as multi-line comments in Python.

```python
"""This is a description of how my program works.

   The program takes the width and height of a rectangle as input,
   and prints out its area.
"""
```

### Escape characters

Escape characters start with `\` and are used to represent characters that cannot be
typed directly into the string literal.

`\n` is the newline character, which starts text on a new line.

```python
print("I love Python!\n\nMe too!") 
```

`\"` and `\'` are used to escape the double and single quotes inside a string.

```python
print("My middle name is \"Frank\".")   # \" not needed if string delimited with ''
print('Isn\'t it nice outside?')        # \' not needed if string delimited with ""
```

## Data Types

Every value in Python belongs to exactly one data type.

Python has 4 basic data types:
- integers (`int`)
- decimals (`float`)
- string (`str`)
- boolean (`bool`)

```python
5          # integer
5.0        # float
"hello"    # string
True       # boolean
```

Integers are whole numbers (including negatives), floats are floating point (decimal) numbers, strings are text, and booleans are either `True` or `False`.

Types are important because they determine which operations can be performed on the data.

Math operations can be applied on numeric types (`int`, `float`), string operations can be applied on `str`, and [logical operations] can be applied on `bool`.

## Variables

A variable stores the value of an expression. It has a name so the programmer can refer to the value later.

### Assignment operator

Create a new variable and assign it to a value using the `=` operator.

```python
x = 5
print(x)        # 5
```

If you assign to the same variable twice, the original value is lost and replaced with the new value.

```python
x = 5
print(x)        # 5
x = 20
print(x)        # 20
x = 8
print(x)        # 8
print(x)        # 8
```

You can make a copy by assigning a variable to another variable.

```python
x = 10
y = 5
x = y            
print(x, y)      # x and y are both 5
x = y + 2
print(x, y)      # x is 7, y is 5
```

### Incrementing and decrementing

```python
x = 10
x = x + 20      # x + 20 is evaluated first => 30
                # then, x is assigned the value on the right hand side
print(x)        # 30
```

Incrementing is so common, it has its own operator: `+=`

```python
x += 20        # same as x = x + 20
x -= 20        # same as x = x - 20
x *= 20        # same as x = x * 20
```

## Functions

Functions in math take one or more inputs, and give a single output.

In programming, the inputs are referred to as **arguments**, and the output (if any)
is called the **return value**.

If a function does not have output, it returns `None`, meaning "no value".

### Print

The `print` function takes one or more arguments, printing each of them separated by spaces.

```python
print("apple", "version", 2.0)       # apple version 2.0
```

`print` does not have a return value, since it writes to the screen instead.

```python
x = print("hello")                     # hello
print(x)                               # None
```

### Built-in functions

Aside from the `print` function, Python provides a number of built-in functions
to perform common tasks.

#### Math Functions

The `max` and `min` functions return the maximum and minimum values out of 
all their arguments.

```python
x = max(1, 5, 8, -2)       # x has the value 8
y = min(1, 5, 8, -2)       # y has the value -2
```

The `abs` function returns the absolute value of its argument.

```python
x = abs(2)                 # x has the value 2
y = abs(-2.4)              # y has the value 2.4
```

#### Other functions

The `len` function returns the length of a string in characters.

```python
x = len("hello")            # x has value 5
y = len("a")                # y has value 1
z = len("")                 # z has value 0
```

The `type()` function returns the type of the data.

```python
type(3)                     # int
type(3.14)                  # float
type(True)                  # boolean
type("A")                   # string
type(None)                  # NoneType - None has its own special type   
```

## Importing modules

You can import external modules to include additional functions
in your program.

The syntax for calling a module function is `module_name.function_name`.

### Examples

The `math` module has many useful mathematical functions.

```python
import math     # you can now use all functions within the math module

x = math.sqrt(64)  # the square root function always returns a float
                     # x has the value 8.0
```

The `random` module generates random numbers.

```python
import random

x = random.randint(1, 10)     # randint returns a random integer from 1 to 10 inclusive
y = random.uniform(2.5, 4.5)  # uniform returns a random float from 2.5 to 4.5 inclusive
```

The `time` module provides the current system time.

```python
import time

time.ctime()                  # ctime returns the current time in string format
                              # ex. 'Fri Jul  1 12:00:10 2022'
```

## Type conversions

Python also has built-in functions for converting between types (casting).

```python
int("2")             # 2
float("1.2")         # 1.2

int(2.8)             # 2 - only keep integer portion when casting float to int
float(3)             # 3.0

str(3)               # "3"       
str(2.54)            # "2.54"
```

Type casting is useful when a value needs to be converted into the correct type
in order to perform an operation.

### concatenating numbers to strings

```python
age = 10

# error due to type mismatch: does + refer to concatenation or addition?
# print("I am " + age + " years old")

# concatenate strings
print("I am " + str(age) + " years old")
```

This kind of formatting can also be done using [f-strings].

### math operations

Convert the string to a numeric type before performing the operation.

```python
int("2") + 3                  # 5
float("2.5") + 3              # 5.5
```

## Getting user input

You can use the `input` function to ask the user for input and save it to a variable.

```python
name = input("What is your name? ")                 # Jake
print("Hi " + name + ", it's nice to meet you!")    # Hi Jake, it's nice to meet you!
```

The `input` function always returns a string containing the text that the user typed,
up to the newline.

This means that if you want to perform math operations on user input, you must
convert it to a numeric type first.

```python
num1 = int(input("Enter your first number: "))
num2 = int(input("Enter your second number: "))

print(num1 + num2)
```

## f-strings

f-strings stand for formatted strings. They allow you to embed expressions inside a
string.

Simply put `f` before the quotes, and include the expression inside the curly braces.

```python
name = "Derek"
print(f"{name}, it's nice to meet you!")     # Hi Derek, it's nice to meet you!
```

```python
age = 10
print(f"I am {age} years old")                # I am 10 years old
```

```python
num1 = int(input("Enter your first number: "))
num2 = int(input("Enter your second number: "))

print(f"The sum of {num1} and {num2} is {num1 + num2}")
```

f-strings also allow you to set the output precision of a numeric expression.

```python
import math
pi = math.pi          # 3.1415926535...

# syntax: {value:.{precision}f}
print(f"pi rounded to 4 decimal places is {pi:.4f}.") # 3.1416
```

[advanced f-string tricks]

# Part 2: Conditional Statements

All the code that we have seen so far has been executed line by line, from top to bottom.

This section covers structures which allow code to be selectively run depending on the inputs.

## Logical Operators and Boolean Expressions

### Comparison Operators

There are 6 basic comparison operators in python:
`==, !=, <, <=, >, >=`

Comparison operators take two operands and evaluate to a boolean.

```python
# Equality operator
1 == 2           # False
```
```python
# Not equals operator
2 != 2           # True
```

```python
# Less than operator
3 < 5            # True
5 <= 5           # True
```

```python
# Greater than operator
4 > 1            # True
7 >= 8           # False
```

Strings can be compared using the `==` and `!=` operators as well.

```python
"apple" == "apple"    # True
"apple" == 'apple'    # True
```

```python
"apple" != "pear"     # True
"apple" == "pear"     # False
```

Numeric types compare equal to each other, but strings do not.

```python
3 == 3.0      # True - integers automatically convert to float before comparing
3 == '3'      # False - strings do not automatically convert to int before comparing
3.0 == '3.0'  # False - strings do not automatically convert to float before comparing
```

### `=` vs. `==`

`=` is the assignment operator. It assigns a variable a value.

`==` is the equality comparison operator. It tests if two values are equal.

```python
x = 7             # set x to 7
x == 7            # is x equal to 7?
```

`x = 7` evaluates to None, while `x == 7` evaluates to a boolean.

```python
print(x = 7)      # None
print(x == 7)     # True
```

### Logical Operators

There are 3 basic logical operators in Python: `and, or, not`

Each logical operator takes two boolean operands and gives a boolean result.

#### And
The `and` operator evaluates to `True` if and only if both operands evaluate to `True`.

[Truth table]

#### Or
The `or` operator evaluates to `True` if at least one operand evaluates to `True`.

[Truth table]

#### Not
The `not` operator negates a boolean expression.

```python
not True            # False
not False           # True
```

### Operator precedence

From highest priority to lowest priority:

arithmetic operators `**, *, /, //, %, +, -`
comparison operators `==, !=, <, <=, >, >=`
not
and
or
assignment operator `=`

All arithmetic operators have precedence based on math order of operations.
(`**` has highest precedence, then `*, /, //, %`, then `+, -`)

All comparison operators have the same precedence, and are evaluated from left to right.

### Examples

```python
# Simple comparisons
5 + 2 == 7               # True
2 * 3 != 6               # False
4 ** 2 < 20              # True
5 - 3 <= 2               # True
```

```python
# logical operators
12 % 3 == 0 and 12 > 10     # True and True -> True
1 + 1 == 2 or 2 + 2 == 5    # True or False -> True
1 + 1 != 2 or 2 + 2 == 5    # False or False -> False
```

```python
x = not False                 # x has the value True
x = not False or True         # x has the value False - False or True evaluates first
x = False or True and False   # x has the value False - True and False evaluates first
```

It is considered good practice to explicitly indicate order using parentheses
when operator precedence is not obvious, especially for logical operators.

`(not False) or True` vs `not (False or True)`
`(False or True) and False` vs `False or (True and False)`


## If Statements

Most programs require us to perform different actions when given different input.

The if statement allows us to selectively run code depending on whether a condition is met.

**Syntax**
```
if <condition>:
  <code block>
```

Python uses indentation to indicate a block of code.
Each line in the code block has a single indent (whitespace before the code).

The condition is a boolean expression. 

If the condition is True, the interpreter will run all the code inside the code block.

Otherwise, it will skip performing those actions and resume executing code immediately
following the if statement.

```python
# will print all 3 statements - statement 1 and statement 2 are inside the code block
if True:
  print("statement 1")
  print("statement 2")
print("statement 3")
```

```python
# will not print the first two statements inside the if statement,
# but will print 'statement 3'
if False:
  print("statement 1")
  print("statement 2")
print("statement 3")
```

```python
age = 18

if age >= 18:
  print("You can vote")            # You can vote

if not age >= 18:
  print("You cannot vote")         # will not be run, since condition is false
```

### Else

The `else` keyword allows you to specify alternate code to run when the condition is False. 

**Syntax**
```
if <condition>:
  <code block 1>
else:
  <code block 2>
```

Code block 1 runs if the statement is True, and code block 2 runs if the statement is False.

```python
age = 17

if age >= 18:
  print("You can vote")
else:
  print("You cannot vote")          # you cannot vote
```

```python
num = 10

if num % 2 == 0:
  print(num, "is even")            # 10 is even
else:
  print(num, "is odd")
```

### Elif

The `elif` keyword is an abbreviation for `else if`.

**Syntax**
```
if <condition 1>:
  <code block 1>
elif <condition 2>:
  <code block 2>
else:
  <code block 3> 
```

The `elif` statement allows you to specify another condition to test if the
previous condition evaluates to `False`. 

```python
num = 0

if num > 0:
  print(num, "is positive")
elif num == 0:
  print(num, "is neither positive nor negative")   # num is 0
else:
  print(num, "is negative")

# try for different values of num
```

You are allowed to have multiple elif statements in a chain.

```python
money = 600

if money > 500:
  print("You should get an electric bicycle")
elif money > 200:
  print("You should get a smartwatch")
elif money > 30:
  print("You should get a lego set") 
elif money > 10:
  print("You should get a gift card")
else:
  print("A handwritten card is good too") #runs only if money <= 10
```

Note that each condition is checked in the order that they appear, and the else block
runs only if all the above conditions evaluate to false.

## Nested If Statements

You can place an if statement inside an if statement.

This is useful when you need to check a condition if the first statement is true.

```python
hour = 10
weekday = True
status = "closed"

if weekday:
  if hour >= 9 and hour <= 17:
    status = "open"

print(f"The store is {status}")
```

Note that the outer if statement has a single indent, and the inner if statement has two
indents to indicate the nested block.

The above test is equivalent to `if weekday and hour >= 9 and hour <= 17`, but it is considered
better style to keep related tests at the same indentation level.

You are allowed to have as many nested if statements as you like, but nesting more than 3
levels deep is a sign that you should reorganize your logic.


## Leap Year Example

Nearly every 4 years, an extra day is added to the calendar because the earth takes
approximately 365.25 days to orbit the sun. The year in which this happens is called a **leap year**.

A year is a leap year if:
it is divisible by 4, unless
it is divisible by 100, in which case is **NOT** a leap year, unless
it is also divisible by 400, in which case it **is** a leap year.

Ex. 2004 is a leap year, 1900 is not a leap year, and 2000 is a leap year.

```python
# Direct implementation
year = 2004

if year % 4 == 0:
  if year % 100 == 0:
    if year % 400 == 0:
      print("leap year")
    else:
      print("not a leap year")
  else:
    print("leap year")
else:
  print("not a leap year")

   
print(is_leap_year)
```

```python
# improved version
year = 1900

if year % 400 == 0:
  print("leap year")
elif year % 100 == 0:
  print("not a leap year")
elif year % 4 == 0:
  print("leap year")
else:
  print("not a leap year")
```

# Part 3: While loops

## Concept

Loops allow you to repeat a code block.

This is useful because programs often perform repetitive tasks, such as sending
out an email to all of a company's customers.

There are two ways to write a loop in Python: **while loops** and **for loops**.

We will cover while loops in this section, and for loops in part 5.

## While loop 

The while loop repeats the code while the condition is true.

**Syntax**
```
while <condition>:
  <code block>
```

If the condition is always `True`, then the code will run forever. This is called an
**infinite loop**.

```python
while True:
  print("I love coding!")        # press the red square to stop the infinite loop
```

To prevent the loop from running forever, we need a *counter variable* to keep track
of the number of times the loop has run so far.

We then exit the loop when the specified number of iterations have been reached.

```python
i = 1             # counter variable
while i <= 10:
  print(f"Loop has run {i} time(s)")     # loop 10 times
  i += 1
```

Pay attention to the last line in the while loop: `i += 1`.

If that line was omitted from the loop, i would always equal 1 and the code would run forever.

## Examples

Loops can be used to perform a variety of tasks that would be repetitive to code out by hand.

### Print the first 10 perfect squares

```python
i = 1
while i <= 10:
  print(i * i)
  i += 1
```

### Counting down from 10 to 1

```python
i = 10
while i >= 1:   
  print(i)
  i -= 1
```

### Printing all multiples of 7 between 100 and 200

In the following code, the if statement is nested inside the while loop.

```python
i = 100
while i <= 200:
  if i % 7 == 0:
    print(i)
  i += 1
```

## Break and Continue

`break` and `continue` are keywords that allow you to perform special actions
within a loop.

`break` is used to exit a loop immediately.

```python
# output: 1, 2, 3, 4
i = 1
while i <= 10:
  if i == 5:         # when i is equal to 5, exit the loop
    break
    
  print(i)
```

`continue` immediately ends the current iteration of the loop (skipping all code below),
and continues with the next iteration of the loop.

```python
# output: 1, 2, 3, 4, 6, 7, 8, 9, 10
i = 1
while i <= 10:
  if i == 5:          # when i is equal to 5, go to next iteration (i = 6)
    continue

  print(i)
```

### Determine if a number is prime

A number n is prime if it has exactly two factors, 1 and itself.

We can test all factors from 2 to n-1 to see if it divides evenly into n.
If all factors do not divide evenly into n, then n is prime.

```python
n = 97
is_prime = True

factor = 2
while factor < n:
  if num % factor == 0:
    is_prime = False
    break 
    
  factor += 1

print(is_prime)
```

# Part 4: Lists and Strings 

Lists in python are a container data type. They hold multiple values in a single variable.

You specify a list using brackets, and separate the values using commas.

```python
nums = [4, 5, 2, 8, 5]
print(nums)
```

Lists are an ordered collection of items, which may contain duplicates.

These items are usually the same type, but are allowed to be different types.

```python
values = [2, "apples", 3.99, True]
```






concatenation

len

Check if a value is in list using in


check if a substring is in a string using in


lists are mutable


indexing, slicing

some built in methods (examples)




## Shopping List

```python
cart = ["apples", "milk", "bread", "tomatoes"]

cart.append("broccoli")
cart.pop()
```




# Part 5: For loops and Iterators

## For loop

The for loop iterates through every item in a sequence, one at a time.

**Syntax**

```
for <item> in <iterable>:
  <code block>
```

Two examples of iterables are lists of numbers and strings of characters.

```python
# iterate over each number in a list
for x in [1, 3, 5, 8]:
  print(x)
```

```python
# iterate over each character in a string
for c in "elephant":
  print(c)
```

#### Range

The `range` function returns a sequence of numbers.

**Syntax**
```
range(start, stop, step)
```

The first argument specifies the starting value, and the second argument specifies
the ending value.

```python
for i in range(5, 10):
  print(i)                  # 5, 6, 7, 8, 9
```

As you can see, the start value is included in the sequence, but the ending value is not.

If only one argument is provided, it is taken to be the stopping value.

```python
for i in range(5):          # observe that the sequence starts at 0
  print(i)                  # 0, 1, 2, 3, 4
```

There is an optional third argument that can specify the increment size between numbers.

```python
for i in range(1, 10, 2):
  print(i)                  # 1, 3, 5, 7, 9
```

The increment can be negative to loop through numbers in the reverse order.

```python
for i in range(10, 0, -1):
  print(i)                 # 10, 9, 8, 7, 6, 5, 4, 3, 2, 1
```

#### When to use a for loop vs. a while loop

For loops provide a convenient syntax to loop over an iterable, such as a list.

Compare the following programs with the ones written [earlier] using while loops.

#### Print the first 10 perfect squares

```python
for i in range(1, 11):
  print(i * i)
```

#### Print all multiples of 7 between 100 and 200

```python
for i in range(100, 201):
  if i % 7 == 0:
    print(i)
```

While loops are more general than for loops, and are good at representing code
that needs to be repeated while a condition holds.

The authors recommend using whichever loop is more concise.

### Nested loops

Similar to if statements, it is possible to put a loop inside another loop.

The inner loop will run completely for every iteration of the outer loop.

```python
#prints 15 pairs of values
for i in ['a', 'b', 'c']:
  for j in [1, 2, 3, 4, 5]:
    print(i, j)
```

Every letter in the outer loop is paired with every number in the inner loop.

#### Printing a square

```python
N = 3

for i in range(N):
  for j in range(N):
    print('*', end='')              # end argument is used to print on the same line
  print()
```

The code prints one row at a time.

The outer loop prints the first row when i = 0, the second row when i = 1, and so on.

The inner loop prints N `*` characters next to each other. It is equivalent to `'*' * N`.

#### Printing a triangle

```python
N = 3
for i in range(1, N+1):
  for j in range(i):
    print('*', end='')
  print()
```

Now, the number of characters the inner loop prints varies with i.

1 star is printed when i = 1, 2 stars printed when i = 2, and so on.

Nested loops are also useful for iterating over nested lists,
as we will see in the next section.



# Part 5: Data Structures

## Strings

### Indexing

Indexing a string allows you to access individual characters.

```python
word = "elephant"
word[0]              # e
word[1]              # l
word[5]              # a
```

Note that indexing starts from 0, rather than 1. This is due to a programming convention
that the values in the brackets represent the offset from the starting character.

The last character's index is `len(string) - 1`.

```python
word = "elephant"
# get the last character of elephant
word[len(word)-1]     # t
```

#### Negative indices

Negative indices count backwards from the end of the string.

```python
word = "elephant"
word[-1]              # t
word[-2]              # n
word[-8]              # e
```

If the index is out of the valid range of the word, the interpreter will halt
with an `index out of range` error.

### Slicing

We use slicing to get a substring (multiple contiguous characters) from a string.

```python
word = "elephant"
word[0:3]            # ele
word[5:8]            # ant
word[3:7]            # phan
```

The starting index of the substring is to the left of the colon, and the ending index
is to the right.

The starting and ending index can be omitted and is taken to be `0` or `len(word)`,
respectively.

```python
word[:3]            # ele - starts from the beginning of the string
word[5:]            # ant - ends at the end of the string
```

The slice includes the character at the starting index but excludes the one at the ending
index. This is so `word[:3] + word[3:] == word`, as the middle character is not included 
twice.

Out of range indices are handled gracefully by the interpreter.

```python
word = "elephant"
word[3:64]         # phant
word[64:]          # ""
word[7:3]           # ""
```d

#### Reversing a string

The slice can take a third number for the increment size.

```python
# word[start:stop:step]

# skip every other letter
word = "typeracer" 
word[0:9:2]           # tprcr
word[::2]             # same as above (omit indices)
```

We can get a reversed string by specifying `-1` as the step size.

```python
word = "elephant"
word[::-1]           # tnahpele
```

## Lists
 
A string can be viewed as a list of characters. This explains the similarities between
lists and strings in the following sections.

### Indexing

Similar to strings, we can use indexing to access elements in a list.

```python
nums = [4, 12, 7, 9, 10]
x = nums[0]                     # x has the value 4
y = nums[3]                     # y has the value 9
```

The first element has index 0, and the last element has index `len(nums) - 1`.

#### Negative Indexing

Negative indexing counts backwards from the end of the list.

```python
nums = [4, 12, 7, 9, 10]
x = nums[-1]                  # x has value 10
y = nums[-2]                  # y has value 9
```

### Slicing

We use slicing to get a sublist (multiple contiguous elements) from a list.

Recall that the slicing operator will include the starting index, but omit the ending index.

```python
nums = [4, 12, 7, 9, 10]

nums[1:4]                     # [12, 7, 9]
nums[0:3]                     # [4, 12, 7]
```

We can use negative indices to specify the start or ending index in the slice.

```python
nums = [4, 12, 7, 9, 10]

nums[-2:5]                    # [9, 10]
nums[0:-1]                    # [4, 12, 7, 9]
```

We can omit the starting and ending index to refer to the beginning or end of the list.

```python
nums = [4, 12, 7, 9, 10]

nums[:3]                      # [4, 12, 7]
nums[-2:]                     # [9, 10]
```

Out of range indices are handled gracefully.

```python
nums = [4, 12, 7, 9, 10]
nums[2:42]                     # [7, 9, 10]
```

#### Reversing a list

The slicing operator can take a third value for the step size.

Syntax: `[start:stop:step]`

We can get a reversed list by specifying `-1` as the step size.

```python
nums = [4, 12, 7, 9]

# slice starts at end of list and steps backwards up to beginning
reversed_nums = nums[::-1]     # [9, 7, 12, 4]
```

#### Making a copy






Slicing returns a copy of the list without modifying the original.






To copy a list, slice the original but don't omit any of its elements.
```python
myList = [4, 12, 7, 9]
copyList = myList[:] #sets start, stop, and step indices to their default values
```







### Built-in methods

Lists and Strings are objects. We will cover these in more depth later, but
basically this means that they have methods, or functions attached to them that can
process their internal data.

### String methods


- lower (comparison)
The `lower()` function converts a string to all lowercase.
This function can be useful to standardize input.
```python
if user_input.lower() == "yes": #will work for user_input = YES, Yes, etc.
  # continue
```

- count (non-overlapping)
The `count()` function provides the amount of times one string appears in another.
```python
"yarrharhar".count("ar") #3
"ababa".count("aba") # 1
"aaa".count("aa")    # 1
```
- find
The `find()` function finds the first occurrence of one string within another.
If it does not appear in that string, it returns -1.
```python
"bananananana".find("an") #1
"bear".find("eat") #-1
```
- replace
The `replace()` function replaces every occurrence of a given string with another one.

```python
"long-sentence-with-hypens".replace('-', ' ')   # "long sentence with hyphens"
"1010.1001.1010.1111".replace('.', '')          # 1010101110101111
"banana".replace("ana", "ono") #bonona
# example with strings
```

- strip
The `strip()` function removes whitespace at the beginning and end of a string.
```python
myString = "   apple    " 
myString.strip() #"apple"
```

### List methods
- append
The `append()` method allows us to add elements to the end of an existing list.
```python
myList = [4, 12, 7, 9]
myList.append(5) #[4, 12, 7, 9, 5]
```
- pop (including popping at index)
The `pop()` function allows us to remove the element at the given index, which is -1 by default.
```python
myList = [4, 12, 7, 9]
x = myList.pop() #9
print(myList) #[4, 12, 7]
y = myList.pop(1) #12
print(myList) #[4, 7]
```
- insert
The `insert()` function inserts an element at the specified position in the list.
It follows the pattern of `list.insert(position, element)`.
```python
myList = [4, 12, 7, 9]
myList.insert(0, 1) #[1, 4, 12, 7, 9]
```
- sum, max, min of list
The `sum()` function returns the sum of all elements within the list, while
the `max()` and `min()` functions return the maximum and minimum values within the list, respectively.
```python
myList = [4, 12, 7, 9]
x = sum(myList) #32
y = max(myList) #12
z = min(myList) #4
```
Keep in mind that the elements of the list must be comparable to each other for these 3 functions to work.
- sorted
The `sorted()` function returns a sorted list.
```python
myList = [4, 12, 7, 9]
print(sorted(myList)) #[4, 7, 9, 12]
```
As before, elements of the list must be comparable for `sorted()` to work.

### Split, Join

The `split` function splits a string into a list of tokens based on whitespace
or another separating character.
```python
myString = "this is a string"
print(myString.split()) #["this", "is", "a", "string"]
ipAddress = "132.0.12.6"
print(ipAddress.split(".")) #["132", "0", "12", "6"]
```

The `join` function joins a list of tokens into a single string, with a separator
character in between.
```python
myList = ["this", "will", "be", "a", "string"]
print(" ".join(myList)) #"this will be a string"
ipList = ["132", "0", "12", "6"]
print(".".join(ipList))#132.0.12.6
```

### Immutability

Lists are **mutable**: modifying an existing list is allowed:

```python
fruits = ["apple", "orange", "pear", "banana"]
fruits[2] = "watermelon"       # allowed to change the elements inside a list
print(fruits)                  # ["apple", "orange", "watermelon", "banana"]           
```

Strings are **immutable**: modifying an existing string gives an error:

```python
fruit = "watermelon"
fruit[2] = 'w'                  # error: cannot change the characters in a string
```

If you want to change a character in a string, you must make a new string
using slicing.

```python
fruit = "watermelon"
fruit[:2] + 'w' + fruit[3:]     # wawermelon
```

Similar to strings, the other basic types `int`, `float`, `boolean` are immutable.

The primitive types are defined as immutable for programmer convenience, so that
after a string is defined it can no longer be modified.

Complex types such as list, dictionaries, and sets are defined as mutable for
efficiency reasons (do not need to make a copy when modifying object)

However, this means you need to be aware of the following:

```python
x = [1, 2, 3]
y = x

x[2] = 100
print(x)         # [1, 2, 100]
print(y)         # [1, 2, 100]
```

When y is assigned to x, both symbols x and y refer to the same list object, so
modifying one modifies the other.

On the other hand, immutable objects cannot change after assignment. You can reassign
the symbol to a new value, but it does not change the underlying object.

```python
x = "hello"
y = x

x = "bye"
print(x)         # hello
print(y)         # bye
```

Note that in the above example, x is bound to a new object, but y refers to prior
object. This is different from modifying the same object.


Diagram of symbol to object

String reassignment does not change the original version

List reassignment does change original


## Dictionary, Sets, and Tuples

Lists, dictionaries, sets, and tuples are examples of composite data types.

Composite data types are made up of primitive data types, such as integers, strings
and floats. They can also contain nested containers.


### Dictionaries

Dictionaries store data in `key: value` pairs. This is useful for associating
data for every element.

The keys in a dictionary are required to be **unique** and **immutable**.

In other words, the key can either be one of the primitive types, or a tuple.

Accessing a value

```python
fruit_prices = {"apple": 2, "banana": 3, "watermelon": 2.5}
fruit_prices["watermelon"]   # 2.5
```

Updating a value

```python
fruit_prices["banana"] = 1
```

Insert a new value into the dictionary

```python
fruit_prices["pear"] = 1.5
```

Accessing a value that is not in the dictionary gives a `KeyError`.

```python
fruit_prices["cantalope"]      # KeyError
```

If you want to test if a key is in the dictionary, you can use the `in` keyword:

```python
"apple" in fruit_prices        # True
"cantalope" in fruit_prices    # False
```

You can also get the value in the dictionary but specify a default value if the key
does not exist:

```python
fruit_prices.get("apple", 3)       # key exists - 2
fruit_prices.get("cantalope", 5)   # key does not exist - 5
```

Examples of each built in function

```python
myDict.keys() #returns list of keys in the dictionary
myDict.Values() #returns list of values in the dictionary
```




pop (including with default argument)

keys of a dictionary or set must be immutable, because otherwise the value cannot be
accessed again

### Sets
- sets store unordered data without duplicates
- defining a set
```python
mySet = {15, "apple", True, 99}
emptyset = set() #initialize empty set with set() function
```
- adding items to a set
```python
mySet.add("Carl") #set now also contains "Carl"
mySet.add(15) #no effect, sets do not allow duplicates
```
- checking for appearance in set
```python
if 15 in mySet:
  print("15 is in the set")
if 7 not in mySet:
  print("7 is not in the set")
```
- modifying a set
```python
mySet.remove(15) #removes the element given that it is in the set
myList = [1, 2, 3]
mySet.update(myList) #adds all elements from myList to mySet
```

- intersection, union, difference, exclusive difference

### Tuples
- tuples store values like a list, but immutable
- defining a tuple
```python
myTuple = (15, "apple", True, 99, [6, 9])
```
- accessing elements
```python
x = myTuple[0] #x has value 15
```
- slicing
```python
print(myTuple[0:3]) #prints elements 0, 1, 2
```
- resassign values within tuple
```python
myTuple[4][0] = 3 #reassigns the value of index 0 at index 4 of myTuple to 3
myTuple[0] = 3 #invalid because immutable type
```
- checking for appearance in tuple
```python
if "apple" in myTuple: #use "in" keyword
  print("apple is in the tuple")
```

## Looping techniques

```python
num_list = [4, 8, 16, 20]

for i, num in enumerate(my_list):
  print(i, num)
```

```python
word = "apple"
for i, c in enumerate(word):
  print(i, c)
```

```python
for key in myDict:
  print(key)
```


```python
fruit_prices = {"apple": 2, "banana": 3, "watermelon": 2.5}

for key, value in fruit_prices.items():
  print(key, value)
```

## Nested lists and dictionaries

## Runtime
- must consider efficiency of your program
- algorithms and data structures have different efficiencies


- Why use big O instead of runtime?


#### Determine if a number is prime

A number n is prime if it has exactly two factors, 1 and itself.

We can test all factors from 2 to n-1 to see if it divides evenly into n.
If all factors do not divide evenly into n, then n is prime.

```python
n = 97
is_prime = True

for i in range(2, n):
  if num % i == 0:
    is_prime = False
    break 

print(is_prime)
```

#### Prime Factorization

Every number can be written as a product of its prime factors.

```python
n = 280
factor = 2

while factor <= n:
    if n % factor == 0:
        n = n // factor
        print(factor)
    else:
        factor += 1
```

#### How it works

The code tests the smallest possible factors first, and divides them out of n.

This ensures that if a factor divides into n, it must be prime. All the smaller
factors of n are already removed, so composite numbers no longer divide into n. 

[see optimization]

# Part 4: Functions and Objects

## Custom Functions

Previously, we seen examples of how to use functions to perform a task.

In this section, we explain how you can make your own function. This is useful,
since it allows you to reuse and modularize your code.

- functions are useful for breaking down a complex task into smaller pieces

- modularizing code, refactoring
- reuse code


### def

You define your own function using the `def` keyword.

Notice that the code for the function is indented in its own block. 

```python
def greet():
  print("hello!")
  print("Weclonme to our home!")

greet()
```

The above function has no return statement, so it returns `None`. We can specify
a return value using the return statement.

```python
def magic_number():
  return 42

print(magic_number + 18)          # 50
```

If a function takes than argument, you specify the variable in the definition
within the parentheses. This variable is called a `parameter`, and it is assigned
the value specified in the function call before the code is run.

```python
def increment_by_2(x):
  return x + 2

increment_by_2(5)   # 7
increment_by_2(8)   # 10
```

```python
def absolute_value(x):
  if x < 0:
    return -x
  return x

absolute_value(-4)       # 4
absolute_value(0)        # 0
absolute_value(10)       # 10
```

```python
def three_sum(a, b, c):
  return a + b + c

three_sum(3, 4, 5)       # 12
```



- fibonacci


- Arguments vs. Parameters

- 


immutable vs. mutable


- contains code that runs when called
- can simplify a problem by breaking it into parts


## Exceptions

Exceptions are useful for error handling:

```python
while True:
  answer = input("Do you want to continue?")
  if answer == "yes" or answer == 'y':
    break
```

```python
while True:
  try:
    num = int(input("Enter a number from 1 to 10"))
    if 1 <= num <= 10:
      break
  catch ValueError:
    print("That is not a valid number")
```

try-catch for operations that might fail (database operations, web api requests)


## File Handling

- with ... open statement
Before you can read or write from a file, you must
specify a file to operate upon.
```python
input = open("inputFile.txt")
#you can now read the contents of the file.
output = open("outputFile.txt", "w")
#the second argument specifies that you will write in the opened file.
output.write("hi!")
input.close() #closes files once input or output is finished
output.close()
```
Using the `with` keyword, opening files is much cleaner looking.
```python
with open("input.txt") as f:
  #read input
with open("output.txt", 'w') as f:
  #write to file 
#handles closing of files automatically
```
- read each line of a file
Using a `for` loop, we can loop over an opened file and read each line as input.
```python
with open("inputFile.txt") as f:
  for line in f:
    print(line) #prints each line of input from the file
```

f.read()
With the `f.read()` function, we can read an entire file into a single string. Only use this for small files.
```python
with open("inputFile.txt") as f:
  input = f.read()
```
By default,  `open()` uses the `'r'` mode, opening a file to read.
- write to the end of a file
With the `f.write()` function, we can write into an existing file.
```python
with open("outputFile.txt") as f:
  f.write("hi!") #clears outputFile.txt, then writes "hi!"
```
By default, `write()` uses the `'w'` mode, clearing the file and then writing.

Using the `'a'` argument, we can specify that we want to append to the end of a file, rather than overwrite it.
```python
with open("outputFile.txt", 'a') as f:
  f.write("hi!") #appends to end of outputFile.txt
```

- reads the entire file into a single string
- only for small files

specifying the path for open
When using the `open()` function to open files, you may sometimes need to specify a file path if the desired file isn't in the current working directory.
```python
with open("/Users/Desktop/inputFile.txt") as f:
  #do stuff
```

specifying file mode 'r', 'a', 'w', 

rstrip to remove the ending whitespace
Combine `strip()` with `split()` to process multiple lines of input from a file.
```python
# process a 2d, n by m grid 
```


## Scopes, namespaces/name binding, references

## Introduction to object-oriented programming

An **object** is a collection of data and functions that operate on that data.

The data of an object are called **attributes**, and the functions of an object are called **methods**.

Objects are used to model real-world objects. For example, a video game may have a player object, which keeps track of the player's coordinates.


```python
rob = Player()
rob.position = (40, 50)
```

To define an object, we use the **class** keyword. A class defines the structure of an object, similar to how a blueprint defines the structure of a house.

```python
class Player:
  def __init__(self, health, position):
    self.health = health
    self.position = position

  def move_right(self, amount):
    self.position[0] += 5
```


