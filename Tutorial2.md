
---
title: CSC1002 Tutorial 2 (Guochao Xie)
author: Guochao Xie
date: 2020-02-06

---

# CSC1002 Tutorial 2 (Guochao Xie)

**_I would prefer a coding-based teaching style. Please have your Visual Studio Code or Jupyter Notebook ready._**

## Table of Contents

- [CSC1002 Tutorial 2 (Guochao Xie)](#csc1002-tutorial-2-guochao-xie)
  - [Table of Contents](#table-of-contents)
- [Main Contents](#main-contents)
  - [Part 1](#part-1)
    - [Variables and Values](#variables-and-values)
    - [Types of Values](#types-of-values)
    - [Operations and Operators](#operations-and-operators)
      - [Arithmetic Operators](#arithmetic-operators)
      - [Assignment Operators](#assignment-operators)
        - [Multiple Assignment](#multiple-assignment)
      - [Comparison Operators](#comparison-operators)
        - [Optional (Self-Study Part)](#optional-self-study-part)
    - [Type Conversions](#type-conversions)
      - [Input and Output](#input-and-output)
    - [Exercise 1](#exercise-1)
  - [Part 2](#part-2)
    - [Conditional Statement](#conditional-statement)
        - [Oneline If Statement](#oneline-if-statement)
    - [Exercise 2](#exercise-2)
  - [Part 3](#part-3)
    - [String](#string)
    - [List](#list)
    - [Range](#range)
    - [For Loop](#for-loop)
    - [Exercise 3](#exercise-3)
- [Extra Exercises](#extra-exercises)
  - [Extra Exercise 1.](#extra-exercise-1)
  - [Extra Exercise 2.](#extra-exercise-2)
- [Supplemental Contents](#supplemental-contents)
- [References](#references)

# Main Contents

## Part 1

### Variables and Values

What is variables and values? Let me use an example to illustrate.

Suppose David and Jasmine both have a bank account respectively.

Initially, both accounts have 0 balance.

```python
David = 0
Jasmine = 0
```

On the first day, David deposits 1000 and Jasmine deposits 10.

```python
David = 1000
Jasmine = 10
```

Now, David has more money than Jasmine since `1000 > 10`.

```python
David > Jasmine
1000 > 10
```

On the second day, David transfers 520 to Jasmine.

```python
David -= 520
Jasmine += 520
```

So, how many money do David and Jasmine own? David now owns 480 and Jasmine owns 530.

```python
David == 480
Jasmine == 530
```

Which one is greater, David's balance or Jasmine's? Because `530 > 480`, we will have Jasmine owning more money.

```python
David < Jasmine
480 < 530
```

From the example above, which ones of the following are _variables_ or _values_?

1. _David_
2. _Jasmine_
3. _10_
4. _1000_
5. _520_
6. _480_
7. _530_

The solution is that only _David_ and _Jasmine_ are _variables_, and all remainings are _values_.

Do you see the difference?

_Variables_ resemble _containers_ and _values_ resemble the items put in _containers_. We use _variables_ to store values (in memory) and do operations. We can assign a _value_ to a _variable_ like filling a bottle with water, but we cannot assign a _variable_ to a _value_ because the water itself cannot have an ego of a bottle.

(-3 mins)

### Types of Values

Values have different types. There are 5 standard data types:

- Numbers
- String
- List
- Tuple
- Dictionary

Within each types, there are several subtypes. For example, types belonging to _Numbers_ include _int_ (integer 整数), _float_ (floating point value 小数), _complex_ (complex number 复数), etc. It is not required to remember all types of Python, but more importantly, we need to know how to manipulate variables containing different types.

Now, let's do an experiment: check the type!

`type` is a built-in function (or you can think it is a _keyword_ now). It can present the type of a value to you. The usage is simple:

```python
type( VALUE )
```

where you replace **VALUE** as the value you would like to check.

Try to guess what is the output of the following code, then type and execute it. Compare your guess with the execution result.


```python
print(type(1))
print(type(0))
print(type(0.0))
print(type("Hello"))

David = 100
print(type(David))

David = [1, 2, 3]
print(type(David))

David = tuple(David)
print(David)
print(type(David))

David = {"name": "David"}
print(David)
print(type(David))

David["age"] = 20
print(David)
```

So far, you have seen some examples of every standard data type. You should have known how to get the type of a value so far.


For more information about variable types, you can go through this website: [Python3 Variable Types](https://www.tutorialspoint.com/python3/python_variable_types.htm). Moreover, an official complete manual is [Python3.8 Built-in Types](https://docs.python.org/3/library/stdtypes.html).

(-6 mins)

### Operations and Operators

Python3 supports the following basic operators:

- Arithmetic Operators
- Assignment Operators
- Comparison (Relational) Operators
- Logical Operators
- Bitwise Operators
- Membership Operators
- Identity Operators

Let's use the following code to try different operators.

Reference link: [Python 3 -Basic Operators](https://www.tutorialspoint.com/python3/python_basic_operators.htm).

#### Arithmetic Operators


```python
# Arithmetic Operators: + - * ** / // %
print(2 + 3)
print(2 - 3)
print(2 * 3)
print(2 ** 3)
print(2 ** 4)
print(2 ** 5) # Guess what is ** using the 3 examples above
print(2 / 3)
print(3 // 2)
print(4 // 2)
print(5 // 2)
print(6 // 2) # Guess what is the difference between / and //
print(3 % 2)
print(4 % 2)
print(5 % 2) # Guess what is %
```

Not only can arithmetic operators apply to numbers, but also other types.

For example, we can add two strings or multiply a string by a scalar. Use the following two examples to understand the special feature.

For more special usage of arithmetic operators, you may go through the referencing links or search online.


```python
print("Hello" + " " + "World")
print("Hello " * 3)
```

(-10mins)

#### Assignment Operators

Assignment operators are used to assign values to variables. It is probably the most frequently used operators in Python, because our codes usually manipulate variables. There are several assignment operators.

The most basic one is `=`, for example `David = 100` means we assign the value `100` to the variable `David`. There are 2 cases for the variable `David`. On the one hand, `David` may be previously defined. In this case, `David` will _forget_ what it previously contains and now contain the new value `100`. On the other hand, if `David` never appears before, then Python will initiate a new variable called `David` and set its value to `100`.

Besides the basic `=`, Python also provides several operators that _update_ the variable's value. Here is a list of such operators:

- `+=`
- `-=`
- `*=`
- `/=`
- `%=`
- `**=`
- `//=`

I would like to briefly introduce the machanism of `+=`. The operator `+=` will **increase** the variable on the **left** hand side by the value on the **right**. For example, 

```python
(1)
David = 10
(2)
David += 20
(3)
```

At point 1, `David` has not been initiated and it does not have a value. At point 2, `David` is 10 now. And at point 3, `David` becomes `10 + 20` which equals to `30`. If you can understand this, then you can extend the idea to other operators as well.

##### Multiple Assignment

Multiple assignment is a special feature supported by Python. It allows you to have multiple variables and values on both side of `=`. For example,

```python
a, b = 10, 20
```

In this example, we have 2 variables on the left side adn 2 values on the right side. As a consequence, `a`, `b` will be set as `10` and `20` respectively. To help you better understand this feature, you may run and think about the following codes.


```python
# Multiple Assignment Examples

a = 10
b = 1

a, b = a * 2, b * 3
# What is a, b now?
print(a, b)

a, b = a * 2, b * 3
# What is a, b now?
print(a, b)

# Question: can b be greater than a after some iterations?
```

Now, think about the following question by filling in some **codes** in the middle:

We have variables `a` and `b`. How to exchange the values of `a` and `b`? Think as many solutions as you can! (Do not modify any provided codes!)


```python
x, y = 10, 20 # Constants. Do not use them in your part of codes!

a, b = x, y # Initialize variables a and b

# Your Codes Here: How to exchange a and b? (You can have multiple lines of codes.) ---------------





# End of Your Codes -------------------------------------------------------------------------------

print("Supposed: \ta: {}\tb: {}".format(y, x))
print("Actual: \ta: {}\tb: {}".format(a, b))
if a == y and b == x:
    print("Success!")
else:
    print("Failure!")
```

(-20mins)

#### Comparison Operators

Use the following examples to understand different comparison operators.


```python
# Comparison Operators: == != > < >= <=
# Note: Comparison Operations usually return Boolean (True / False) Value, 
# except for some operator overload examples, like comparing 2 vectors in numpy.

print(1 == 1)
print(1 != 1)
print(2.5 < 3)
print(2.5 <= 2.5) # <= represents no more than (smaller than or equal to)
```

Is it valid to compare two lists or two strings? Yes!

Can you guess what would happen for the following statements? What is the comparison based on? Please have a try on the following statements. Note that the last one will have TypeError. Think about the philosophy behind the comparisons.


```python
# Comparison between 2 strings

print("abc" < "bcd")
print("abc" < "ab")

# Comparison between 2 lists

print([1, 2, 3] < [2, 3, 4])
print([1, 2] < ["A", "B"]) # Note: this will have TypeError.
```

You may wonder if there is a way to give element-wise comparison for two lists with the same length. One way is to use _list comprehension_ which we will discuss in the future tutorials. You can use the following example to have an impression of it. You may also go through this link for more information: [When to Use a List Comprehension in Python](https://realpython.com/list-comprehension-python/).


```python
# List comprehension example for "a < b"
a = [1, 2, 3]
b = [2, 1, 3]
result = [a[i] < b[i] for i in range(len(a))]
print(result)
```

(-23mins)

##### Optional (Self-Study Part)
Is there a simplier way that we can explictly use the operator "<"? Sure, but you need to install the package _numpy_ before hand. To install _numpy_,

for Windows user:

1. Open Terminal (Command Line)
2. Type "_pip install numpy_" and wait.

for Mac user:

1. Open Terminal
2. Type "_pip3 install numpy_" and wait.

Then, you can try the following codes.


```python
import numpy as np # Here you import the library numpy as the name np
a = [1, 2, 3]
b = [2, 1, 3]
a_np = np.array(a) # Transfer the built-in list into a numpy array type.
b_np = np.array(b)
print(a_np < b_np)
```

### Type Conversions

So far, we have learnt several types in Python. Different types support different operations. Sometimes, we may want to convert a variable into another type. Fortunately, Python provides powerful and handy type conversion functions.

I would like to briefly introduce the conversions for numbers and strings. For other type conversions, you may search for them when you need.


```python
text1 = "100"
number2 = 20.0

# What is the type of text1 and number 2?
print(type(text1))
print(type(number2))
print("-"*30)

# Convert into an integer: use int( )
number1 = int(text1)
print(number1)
print(type(number1))
print("-"*30)

# Convert into a string: use str( )
text2 = str(number2)
print(text2)
print(type(text2))
print("-"*30)

# Question: If I want to have a string "20", how to get it from number2? 
# Store the result in text3.

text3 = ""

# Your Codes Here ------------------------------------------------------




# End of your codes ----------------------------------------------------

print("Supposed:\t text3: 20\t type: <class 'str'>")
print("Actual:\t\t text3: {}\t type: {}".format(text3, type(text3)))
if text3 == "20":
    print("Success!")
else:
    print("Failure!")
```

(-26mins)

#### Input and Output

Input and output is essential for a Python program. Input means we have our data from the keyboard or files and output means we output our data to the screen or files. I/O makes our program _reusable_!

The standard input for Python is the function `input( )`. This function gets some inputs from the keyboard and it returns the value as a **string**. It also provides an optional prompt, which is printed before the input.

Besides, Python provides the function `print( )` to print some values. You can put as many arguments as you like inside and Python will print all of them to the screen. By default, Python will print a new line at the end. Interestingly, you can control the formats such as seperators and end.

Go through the following examples to have a better understanding.


```python
# Example of input a string
name = input("Give me your name: ")
print(type(name))
print("Your name is " + name)
```


```python
# Wrong Example of input 2 numbers a, b and add them
a = input("The first number a: ")
b = input("The second number b: ")
print(type(a), type(b))
print("a + b =", a + b)
```


```python
# The above is a wrong example! How to solve it?
a = input("The first number a: ")
b = input("The second number b: ")
a = int(a)
b = int(b)
print(type(a), type(b))
print("a + b =", a + b)
```


```python
# It seems the problem has been solved
# But what if we input two real numbers like 1.0 and 2.0?
# The following one is a better version!
a = input("The first number a: ")
b = input("The second number b: ")
a = float(a)
b = float(b)
print(type(a), type(b))
print("a + b =", a + b)
```


```python
# Moreover, we can have a better look by refactoring the codes as follows
a = float(input("The first number a: ")) # It transfers the input to float as soon we get the input.
b = float(input("The second number b: "))

print(type(a), type(b))
print("a + b =", a + b)
```

Let's have a look at what we have learnt so far:

- [Variables and Values](#variables-and-values)
- [Types of Values](#types-of-values)
- [Operations and Operators](#operations-and-operators)
- [Type Conversions](#type-conversions)
- [Input and Output](#input-and-output)

Now, we would have an exercise for 10 mins. Please try your best to write the codes. If you have any questions, feel free to ask now.

### Exercise 1

This exercise consists of 3 tasks:

1. Create a program that asks users to enter their names and ages. Print out a message that tells them the year when they turn 100 years old.
2. Ask the user for a number of times that they wish to repeat that message. Then print out that many copies of the previous message.
3. Print out every message on a new line. (Hint: the string "\n" is the same as pressing the ENTER button).

(-40mins)

## Part 2

### Conditional Statement

Conditional statements make you possible to _jump through_ code segments with conditions. One of the conditional statement is **if - else - elif**.

```python
if condition1: # Don't forget :
    # If condition1 is True, execute the following -------------
    Some codes here
    
    # Then, exit the whole "if" statement ----------------------
    
elif condition2:
    # If condition1 fails and condition2 is True ---------------
    Some codes here
    
    # Then, exit the whole "if" statement ----------------------
else:
    # If all conditions above fail -----------------------------
    Some codes here
    
    # Finally, exit the whole "if" statement -------------------
```

Note that, the first `if` is **required**. However, the `elif` and `else` are optional and may have multiple `elif` or `else`.

Use the following example to understand the usage of conditional statements.


```python
age = int(input("Your age:"))
if age > 17:
    print("You can see rated R movies.")
elif age <= 17 and age > 12: 
    # elif = else + if
    print("You can see rated PG‐13 movies.")
else:
    print("You can only see rated PG movies.")
```

Question: is _age < 17_ in the 4th line redundant? That is, can we modify our codes as follows?


```python
age = int(input("Your age:"))
if age > 17:
    print("You can see rated R movies.")
elif age > 12: 
    # elif = else + if
    print("You can see rated PG‐13 movies.")
else:
    print("You can only see rated PG movies.")
```

You may test your codes with some selected examples. Think about some sample values that you can use to test the correctness of the codes above.

Here are some possible test cases. Because our if statement separates the domain of age into 3 parts: >17, between 12 and 17, and below 12, we may have a sample for each part as well as the breaking points. For example, you may test with age equal to:

- 18
- 17
- 16
- 12
- 11

If all these 5 samples pass, then your program should be correct.

Testing is an essential part for software development. If you are interested, you can go through [Python3 unittest](https://docs.python.org/3/library/unittest.html) to see how to do unit test in Python.

(-45mins)

##### Oneline If Statement

Moreover, Python supports a kind of _oneline_ if statement. It is very convenient to write the code if your condition is short and you would like to assign a value based on the condition. For example, the codes above may be modified as the following:


```python
age = int(input("Your age:"))
result = ""
result = "You can see a rated R movie" if age > 17 else result
result = "You can see a rated PG‐13 movie" if age <= 17 and age > 12 else result
result = "You can only see rated PG movies" if age <= 12 else result
print(result)
```

It can be simplified as the following:


```python
age = int(input("Your age:"))
result = "You can see a rated R movie" if age > 17 else ("You can see a rated PG‐13 movie" if age > 12 else ("You can only see rated PG movies"))
print(result)
```

Furthermore, it can be more beautiful:


```python
age = int(input("Your age:"))
result = "You can see a rated R movie" if age > 17 \
    else ("You can see a rated PG‐13 movie" if age > 12 \
    else ("You can only see rated PG movies"))
print(result)
```

The oneline if statement must be written in one line. However, the symbol \ in Python is used to connect 2 lines into a single line. Actually, what Python sees is exactly the **same** as the oneline one. The symbol \ connecting 2 lines help the programmers to see more **clearly**.

### Exercise 2

Now, use 10 minutes to complete the following tasks:

- Ask the user for a number. Print out a message to tell the user whether the number is even or odd. (Hint: what is different when an even / odd number is divided by 2?)
- If the number is a multiple of 4, print a different message.
- Ask the user for two numbers: one is the numerator (call it _num_) and the other is the denominator (call it _check_). If _check_ divides evenly into _num_, tell the user; if not, print a different message.

If you have any questions, you can ask now.

(-65mins)

## Part 3

### String

String is an immutable type. We use `' ... '` or `" ... "` to quote a string. If we want to have a string of multiple lines, we can use `""" ... """`. For example,


```python
prompt = """
Hello!
Welcome to CSC1002!
"""

print(prompt)
```

You are allowed to add two strings to connect them. However, you cannot subtract a string.

You can have formatted string using a built-in method `format`. The usage is `string.format( variables )`. I would like to give you some examples.


```python
# Example 1: Ask for a name and greet
name = input("Hello. What's your name please: ")
print("""
Oh, {}!
Have a nice day!
""".format(name))
```

In the above example, we get a `name` from the input. Then, inside the `print` function we have a string 

`"""
Oh, {}!
Have a nice day!
"""`

Note that, in the format function, we use `{}` (braces) to represent a variable. By calling `format`, the string will replace `{}` with the variable provided in the `format( variables )`. In this example, the `{}` matches with the variable `name`.

If you have more variables, then your multiple `{}` will match with the variables one by one. For example,


```python
# Example 2: Ask for a name and age
name = input("Hello. What's your name please: ")
print("""
Oh, {}!
""".format(name))

age = int(input("May I ask your age: "))
result = "You can see a rated R movie." if age > 17 \
    else ("You can see a rated PG‐13 movie." if age > 12 \
    else ("You can only see rated PG movies."))
print("""
Since you are {} years old,
{}""".format(age, result))
```

Moreover, you can control the format of floating numbers as well!


```python
# Example 3: padding numbers
dividend = float(input("Dividend: "))
divider = float(input("Divider: "))
quotient, remainder = dividend // divider, dividend % divider
result = dividend / divider

print("""Normal Result:
{} ÷ {} = {} ... {}
{} ÷ {} = {}""".format(dividend, divider, quotient, remainder, dividend, divider, result))

print("""Formatted Result:
{:.2f} ÷ {:.2f} = {:.0f} ... {:.0f}
{:.2f} ÷ {:.2f} = {:.2f}""".format(dividend, divider, quotient, remainder, dividend, divider, result))
```

For more fancy formats, you can go through this link: [PyFormat](https://pyformat.info/).

(-70mins)

### List

List is a type containing a sequence of elements. The elements in a list can have different types. We can `append` or `remove` elements to / from a list.

To declare a list, we use the syntax: `[...]`. For example, `[1, 2, 3]` represents a list with 3 elements `1, 2, 3`. We can also append or remove elements from a list.


```python
li = [1, 2, 3]
print(li)

li.append(4)
print(li)

li.remove(3)
print(li)

li.append(1)
print(li)

li.remove(1)
print(li)

li.remove(3)
```

Interestingly, the remove method will only remove the first matched one, but not all. If element is not in the list, then `remove` will give an Error.

To check if an element is in a list, use `in`.


```python
li = [1, 2, 3]
print(li)

if 3 in li:
    li.remove(3)
    print(li)
else:
    print("3 is not in li")
    
if 3 in li:
    li.remove(3)
    print(li)
else:
    print("3 is not in li")
```

To get the length of a list, we can use the function `len`. For example, `len(li)` will return the length of `li`.

We can get an element using the index. In Python, the index starts from **0**. For example, if you want to get the first element, you should use `li[0]`. More interestingly, we can have negative indeces in Python. It means we count from the end. For example, the last element is `li[-1]`. Therefore, the index range is from `-len(li)` to `len(li)-1`!


```python
li = [1, 2, 3]

print(li)
print("Length: {}".format(len(li)))
print("li[{}] = {}  li[{}] = {}".format(0, li[0], -3, li[-3]))
print("li[{}] = {}  li[{}] = {}".format(1, li[1], -3, li[-2]))
print("li[{}] = {}  li[{}] = {}".format(2, li[2], -3, li[-1]))
```

(-75mins)

### Range

`Range` function is useful to generate a "list" of integers. You can easily convert a `range` result into a list using `list`. The usage of `range( ... )` have 3 cases:

1. `range(end)`: generate 0, 1, 2, ..., up to but **exclude** end
2. `range(start, end)`: generate start, start+1, ..., up to but **exclude** end
3. `range(start, end, step)`: generate start, start+step, start+2\*step, ..., up to but **exclude** end number **smaller** than end

Let's see the examples.


```python
r = range(10)
li = list(r)
print("r: {} \t\t\ttype: {}".format(r, type(r)))
print("li: {} \ttype: {}".format(li, type(li)))
print("length of r: {}  \nlength of li: {}".format(len(r), len(li)))

print()

r = range(1, -10, -2)
li = list(r)
print(li)
```

(-80mins)

### For Loop

For loop is an important statement in Python. It helps you to iterate a string, list, range, or other iterators.

The syntax of `for` loop is `for VARIABLE in ITERATOR:`. When using `for` loop, Python will iterate along all elements in the `ITERATOR` and assign the value to `VARIABLE`. For example,


```python
# Print 0, 1, 2, ..., 9
for i in [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]:
    print(i)
```

Moreover, we can take advantage of `range` to simplify our code:


```python
# Print 0, 1, 2, ..., 9
for i in range(10):
    print(i)
```

We can also iterate along a string:


```python
for i in "Hello":
    print(i)
```

Sometimes, we want to get both the index and the element. Here I provide 2 ways to do this.

The first one is using `range` and `len` to iterate through all indices. The second one is using `enumerate` function, which is similar to a _double assignment_. It will return 2 values. The first one is the index and the second one is the element. Either way is good!


```python
li = "abcde"
# Way 1
for i in range(len(li)):
    print("Index: {}  Element: {}".format(i, li[i]))

print()

# Way 2
for i, element in enumerate(li):
    print("Index: {}  Element: {}".format(i, element))
```

### Exercise 3

Ask the user for a string . Print out whether it is a palindrome or not. A palindrome is a string that reads the same forwards and backwards. For example, `"abcde"` is not but `"abcba"` and `"abccba"` are palindrome.

# Extra Exercises

## Extra Exercise 1. 

Input a list of numbers `li` and a number `x`; output all numbers within the list except `x`. You may have different solutions.

## Extra Exercise 2.

Write a program to solve the following tasks. The previous tasks should help solve the latter ones.

- Input a number `n`.
- Check if `n` is a positive integer. If not, print out an error message and abort; otherwise, continue.
- Input `n` numbers and store them inside a list `data`.
- Initialize a new list `sorted_data`.
- Find out the minimum value in `data`, copy it to `sorted_data`, and remove it from `data`.
- Do the above operation for totally `n` times.
- Print out the sorted result using the following format (change the actual number as what you get in `sorted_data`). 

```
Sorted Result:
- 1
- 2
- 3

In total 3 numbers.
```

You are welcome to share your solutions with each other. I will give a sample solution in the next tutorial.

# Supplemental Contents

Try to learn these contents yourself. You should be able to understand the following program if you fully understand them.

- [More String Funtions](https://www.tutorialspoint.com/python3/python_strings.htm)
- [List Slicing](https://stackoverflow.com/questions/509211/understanding-slice-notation)


```python
# For a given string, split the words by " ". Count the number of words. Lowercase all letters.
# Then count the number of distinct words.

string = """
Dear students:

 

Subject to the current situation regarding the novel coronavirus, the following decisions have been made in line with the requirements of Guangdong and Shenzhen governments:

 

1. The spring semester 2019-2020 will start no earlier than February 24th. Please wait for further notice of the specific starting date. 

 

2. Students who are currently away from the campus, including undergraduate and postgraduate students, are strictly prohibited from returning to the campus before the semester begins. Under special circumstances in need, application must be submitted to the college at least one day in advance, and entrance is permitted only after approval by the university.

 

3. Students currently residing on campus must submit written application to the college office and wait for approval if they need to leave the campus for a short period (within 12 hours) due to compelling reasons. Anyone leaving the campus for more than 12 hours or without proper application and approval will not be allowed to enter the campus until the semester begins.

Under the current unusually difficult circumstances, your understanding and support will be much needed and highly appreciated.

 

The Chinese University of Hong Kong, Shenzhen

January 29, 2020"""

words = string.split()

num_words = len(words)

lower_words = []
for word in words:
    lower_words.append(word.lower())

distinct_words = []
for word in lower_words:
    if word not in distinct_words:
        distinct_words.append(word)
        
num_distinct_words = len(distinct_words)

print("""
Total number of words: {}
Total number of distinct words: {}""".format(num_words, num_distinct_words))
```

If you are interested, you can also go through the following contents by searching online:

- **Jupyter Notebook**: Jupyter notebook is an IDE that you can integrate the codes and markdown notes. It is very convenient to write tutorials and share codes. It is frequently used in Data Science applications.
- **Markdown**: Markdown is a formating language that is easy to use. It can be exported as HTML (Website), PDF, and etc.

# References

1. [Python3.8 Built-in Types](https://docs.python.org/3/library/stdtypes.html)
2. [Python 3 - Variable Types](https://www.tutorialspoint.com/python3/python_variable_types.htm)
3. [Python 3 -Basic Operators](https://www.tutorialspoint.com/python3/python_basic_operators.htm)
4. [When to Use a List Comprehension in Python](https://realpython.com/list-comprehension-python/)
5. [Python3 unittest](https://docs.python.org/3/library/unittest.html)
6. [PyFormat](https://pyformat.info/)
