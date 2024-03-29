- [Introduction To Python](#introduction-to-python)
  - [Python key features :](#python-key-features-)
  - [Python background :](#python-background-)
  - [Variables :](#variables-)
  - [Garbage collection :](#garbage-collection-)
  - [Data Types :](#data-types-)
    - [Setting the data type :](#setting-the-data-type-)
    - [Setting the specific data type :](#setting-the-specific-data-type-)
  - [Operators :](#operators-)
    - [Arithmetic operators :](#arithmetic-operators-)
    - [Assignment operators :](#assignment-operators-)
    - [Comparison operators :](#comparison-operators-)
    - [Logical operators :](#logical-operators-)
    - [Identity operators :](#identity-operators-)
    - [Membership operators :](#membership-operators-)
    - [Bitwise operators :](#bitwise-operators-)
- [Strings](#strings)
  - [Slicing Strings :](#slicing-strings-)
  - [Python - Modify Strings :](#python---modify-strings-)
  - [String Concatenation :](#string-concatenation-)
  - [Format - Strings](#format---strings)
  - [Escape Characters](#escape-characters)
  - [String Methods](#string-methods)
- [Lists](#lists)
  - [Access List Items](#access-list-items)
  - [Change List Items](#change-list-items)
  - [Add List Items](#add-list-items)
  - [Remove List Items](#remove-list-items)
  - [Loop Lists](#loop-lists)
  - [List Comprehension](#list-comprehension)
  - [Sort Lists](#sort-lists)
  - [Copy Lists](#copy-lists)
  - [Join Lists](#join-lists)
  - [List Methods](#list-methods)
- [Tuples](#tuples)
  - [Access Tuple Items](#access-tuple-items)
  - [Update Tuples](#update-tuples)
  - [Unpack Tuples](#unpack-tuples)
  - [Loop Tuples](#loop-tuples)
  - [Join Tuples](#join-tuples)
  - [Tuple Methods](#tuple-methods)
- [Sets](#sets)
  - [Access Set Items](#access-set-items)
  - [Add Set Items](#add-set-items)
  - [Remove Set Items](#remove-set-items)
  - [Loop Sets](#loop-sets)
  - [Join Sets](#join-sets)
  - [Set Methods](#set-methods)
- [Dictionaries](#dictionaries)
  - [Access Dictionary Items](#access-dictionary-items)
  - [Change Dictionary Items](#change-dictionary-items)
  - [Add Dictionary Items](#add-dictionary-items)
  - [Remove Dictionary Items](#remove-dictionary-items)
  - [Loop Dictionaries](#loop-dictionaries)
  - [Copy Dictionaries](#copy-dictionaries)
  - [Dictionary Methods](#dictionary-methods)
- [Conditional Execution & Loops](#conditional-execution--loops)
- [Comprehensions](#comprehensions)
  - [List Comprehensions:](#list-comprehensions)
  - [Dictionary Comprehensions](#dictionary-comprehensions)
  - [Set Comprehensions](#set-comprehensions)
  - [Generator Comprehensions](#generator-comprehensions)
- [Functions](#functions)
  - [Recursion](#recursion)
- [Modules](#modules)
- [Namespaces and Scope](#namespaces-and-scope)
- [File handling](#file-handling)
  - [Read Files](#read-files)
  - [Write/Create Files](#writecreate-files)
  - [Delete File](#delete-file)
- [OOPs bullet points](#oops-bullet-points)
- [Iterators](#iterators)
  - [Iterating through an iterator](#iterating-through-an-iterator)
  - [Itearting through an iterator using a for loop](#itearting-through-an-iterator-using-a-for-loop)
  - [Building custom iterators](#building-custom-iterators)
  - [Infinite Iterators](#infinite-iterators)
- [Generators](#generators)
  - [Create Python Generator](#create-python-generator)
  - [Generator Expression](#generator-expression)
  - [Use of Python Generators](#use-of-python-generators)
- [Closures](#closures)
  - [When to use closures?](#when-to-use-closures)
  - [Python closures vs classes](#python-closures-vs-classes)
- [Decorators](#decorators)
  - [@ Symbol With Decorator](#-symbol-with-decorator)
  - [Decorating Functions with Parameters](#decorating-functions-with-parameters)
  - [Chaining Decorators in Python](#chaining-decorators-in-python)
- [Property](#property)
  - [Class Without Getters and Setters](#class-without-getters-and-setters)
  - [Using Getters and Setters](#using-getters-and-setters)
  - [The property Class](#the-property-class)
  - [The @property Decorator](#the-property-decorator)
- [Regular Expressions](#regular-expressions)
- [Lambda/Anonymous Function](#lambdaanonymous-function)
  - [Lambda Function Declaration without arguments](#lambda-function-declaration-without-arguments)
  - [Lambda Function with an Argument](#lambda-function-with-an-argument)
  - [How to use the lambda function with filter()?](#how-to-use-the-lambda-function-with-filter)
  - [How to use the lambda function with map()?](#how-to-use-the-lambda-function-with-map)

---

<br /><br />

# Introduction To Python

## Python key features :
- General purpose language
- Interpreted
- Supports both object oriented and procedure oriented programming
- High level (easy for humans to understand)
- Memory efficient (variables with same value will point to the same memory location instead of having two copies)

--- 

1) `General purpose languge` - Becoz it can be used for machine learning, GUI, web development, software development etc.
   
2) `Interpreted` - Running code line by line => the instruction is executed line by line and not compiling the whole program earlier into machine language. **Python is both compiled and interpreted**. Compilation happens internally i.e. byte code is generated internally and converted to give output using python virtual machine (p.v.m). To prove that, run a .py where another .py file is imported, a pycache folder will be generated which will contain a .pyc file, which is the byte code generated after after compilation of the imported file. So next time when i run the same file, it will not be compiling the imported file
   
3) `Advantages of interpreted language` - Python generates output till the point the code is correct, so **debugging becomes easy**. An interpreter directly translates the code written in a high-level language to machine-level language. Hence, the **size and memory of the program are smaller**. In a compiled language, an executable file is created, which takes up additional space. It is **portable** and need not be recompiled for different platforms. The code can be downloaded as such and used if there is an interpreter in the machine. It is **platform independent** as Python generates byte code before interpretation, this byte code can be used by any other platform to generate output.

4) `Disadvantages of interpreted language` - An **interpreted language is slower** compared to a compiled language. The language analyzes and executes every part of the code, making it process the code every time. An interpreter is needed in the local machine to run the program. An interpreted language is **less secure**. Unlike compiled languages, the interpreter does not have an executable file. So, while sharing the code, we need to share the entire source code

5) `Object oriented programming` - OOP is a computer programming model that organizes software design around data, or **objects**, rather than functions and logic. An object can be defined as a data field that has unique attributes and behavior.

6) `Procedure oriented programming` - This programming language makes use of a **step by step approach** for breaking down a task into a collection of routines (or subroutines) and variables by following a sequence of instructions.

<br /><br />

## Python background :
- Python was first released on **Feb 20, 1991**.
- It was created by **Guido Van Rossum**
- Author of Python was a big fan of British comedy movie called *Monty python's flying circus* and thats where the language got its name.

<br /><br />

## Variables :
- "_" variable refers to the prvious output
- You can get the data type of a variable with the `type()` function.
- Variable names are case-sensitive
- If you want to specify the data type of a variable, this can be done with casting.

> Type `help()` in CLI to get documentation on any topic. Then just type `quit` when you are done. Help function also takes string inputs if u have specific topic in mind, for example, `help('List')`

> To get address of any variable use the `id()` function. Pass the variable name in the curve braces.

<br /><br />

## Garbage collection :
- Garbage collection is implemented in Python in two ways: reference counting and generational. 
- When the reference count of an object reaches 0, reference counting garbage collection algorithm cleans up the object immediately. 
- If you have a cycle, reference count doesn’t reach zero, you wait for the generational garbage collection algorithm to run and clean the object.
  
![Garbage collection](./Utils/garbage_collection.png)

<br /><br />

## Data Types :
<table border="0">
    <tbody>
        <tr>
            <th>Data Types</th>
            <th>Classes</th>
            <th>Description</th>
		</tr>
        <tr>
            <td>Numeric</td>
			<td>int, float, complex</td>
			<td>holds numeric values</td>
		</tr>
        <tr>
            <td>String</td>
			<td>str</td>
			<td>holds sequence of characters</td>
		</tr>
        <tr>
        <td>Sequence</td>
			<td>list, tuple, range</td>
			<td>holds collection of items</td>
		</tr>
        <tr>
            <td>Mapping</td>
			<td>dict</td>
			<td>holds data in key-value pair form</td>
		</tr>
        <tr>
            <td>Boolean</td>
			<td>bool</td>
			<td>holds either <code>True</code> or <code>False</code></td>
		</tr>
        <tr>
            <td>Set</td>
			<td>set, frozeenset</td>
			<td>hold collection of unique items</td>
		</tr>
    </tbody>
</table>

- `int` - holds signed integers of non-limited length.
- `float` - holds floating decimal points and it's accurate up to 15 decimal places
- `complex` - holds complex numbers.
- `list` - List is an ordered collection of similar or different types of items separated by commas and enclosed within square brackets. Lists are **mutable**
- `tuple` - Tuple is an ordered sequence of items same as a list. The only difference is that tuples are **immutable**. Tuples once created cannot be modified.
- `string` - String is a sequence of characters represented by either single or double quotes. Strings are **immutable**.
- `set` - Set is an unordered collection of unique items. Set is defined by values separated by commas inside curly braces. Since sets are unordered collections, indexing has no meaning. Hence, the slicing operator [ ] does not work. Once a set is created, you cannot change its items, but you can remove items and add new items (**mutable**). Duplicates not allowed in a set.
- `frozen set` - Frozen set is just an **immutable** version of a Python set object. While elements of a set can be modified at any time, elements of the frozen set remain the same after creation. Due to this, frozen sets can be used as keys in Dictionary or as elements of another set.
- `dictionary` - Python dictionary is an ordered collection of items. It stores elements in key/value pairs. Here, keys are unique identifiers that are associated with each value.

### Setting the data type :
<table id="dtref" class="ws-table-all notranslate">
<tbody><tr>
<th style="min-width:350px">Example</th>
<th>Data Type</th>
</tr>
<tr>
<td>x = "Hello World"</td>
<td>str</td>
</tr>
<tr>
<td>x = 20</td>
<td>int</td>
</tr>
<tr>
<td>x = 20.5</td>
<td>float</td>
</tr>
<tr>
<td>x = 1j</td>
<td>complex</td>
</tr>
<tr>
<td>x = ["apple", "banana", "cherry"]</td>
<td>list</td>
</tr>
  <tr>
<td>x = ("apple", "banana", "cherry")</td>
<td>tuple</td>
  </tr>
  <tr>
<td>x = range(6)</td>
<td>range</td>
  </tr>
  <tr>
<td>x = {"name" : "John", "age" : 36}</td>
<td>dict</td>
  </tr>
  <tr>
<td>x = {"apple", "banana", "cherry"}</td>
<td>set</td>
  </tr>
  <tr>
<td>x = frozenset({"apple", "banana", "cherry"})</td>
<td>frozenset</td>
  </tr>
  <tr>
<td>x = True</td>
<td>bool</td>
  </tr>
  <tr>
<td>x = b"Hello"</td>
<td>bytes</td>
  </tr>
  <tr>
<td>x = bytearray(5)</td>
<td>bytearray</td>
  </tr>
<tr>
<td>x = memoryview(bytes(5))</td>
<td>memoryview</td>
</tr>
<tr>
<td>x = None</td>
<td>NoneType</td>
</tr>
</tbody></table>

### Setting the specific data type :
<table id="dtref" class="ws-table-all notranslate">
<tbody><tr>
<th style="min-width:350px">Example</th>
<th>Data Type</th>
</tr>
<tr>
<td>x = str("Hello World")</td>
<td>str</td>
</tr>
<tr>
<td>x = int(20)</td>
<td>int</td>
</tr>
<tr>
<td>x = float(20.5)</td>
<td>float</td>
</tr>
<tr>
<td>x = complex(1j)</td>
<td>complex</td>
</tr>
<tr>
<td>x = list(("apple", "banana", "cherry"))</td>
<td>list</td>
</tr>
  <tr>
<td>x = tuple(("apple", "banana", "cherry"))</td>
<td>tuple</td>
  </tr>
  <tr>
<td>x = range(6)</td>
<td>range</td>
  </tr>
  <tr>
<td>x = dict(name="John", age=36)</td>
<td>dict</td>
  </tr>
  <tr>
<td>x = set(("apple", "banana", "cherry"))</td>
<td>set</td>
  </tr>
  <tr>
<td>x = frozenset(("apple", "banana", "cherry"))</td>
<td>frozenset</td>
  </tr>
  <tr>
<td>x = bool(5)</td>
<td>bool</td>
  </tr>
  <tr>
<td>x = bytes(5)</td>
<td>bytes</td>
  </tr>
  <tr>
<td>x = bytearray(5)</td>
<td>bytearray</td>
  </tr>
<tr>
<td>x = memoryview(bytes(5))</td>
<td>memoryview</td>
</tr>
</tbody></table>

<br /><br />

## Operators :
- Python divides the operators in the following groups:
  1) Arithmetic operators
  2) Assignment operators
  3) Comparison operators
  4) Logical operators
  5) Identity operators
  6) Membership operators
  7) Bitwise operators

### Arithmetic operators :
Arithmetic operators are used with numeric values to perform common mathematical operations
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:25%">Operator</th>
<th style="width:35%">Name</th>
<th style="width:30%">Example</th>
</tr>
<tr>
<td>+</td>
<td>Addition</td>
<td>x + y</td>
</tr>
<tr>
<td>-</td>
<td>Subtraction</td>
<td>x - y</td>
</tr>
<tr>
<td>*</td>
<td>Multiplication</td>
<td>x * y</td>
</tr>
<tr>
<td>/</td>
<td>Division</td>
<td>x / y</td>
</tr>
<tr>
<td>%</td>
<td>Modulus</td>
<td>x % y</td>
</tr>
  <tr>
<td>**</td>
<td>Exponentiation</td>
<td>x ** y</td>
  </tr>
<tr>
<td>//</td>
<td>Floor division</td>
<td>x // y</td>
</tr>
</tbody></table>

### Assignment operators :
Assignment operators are used to assign values to variables
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:25%">Operator</th>
<th style="width:20%">Example</th>
<th style="width:20%">Same As</th>
</tr>
<tr>
<td>=</td>
<td>x = 5</td>
<td>x = 5</td>
</tr>
  <tr>
<td>+=</td>
<td>x += 3</td>
<td>x = x + 3</td>
  </tr>
  <tr>
<td>-=</td>
<td>x -= 3</td>
<td>x = x - 3</td>
  </tr>
  <tr>
<td>*=</td>
<td>x *= 3</td>
<td>x = x * 3</td>
  </tr>
  <tr>
<td>/=</td>
<td>x /= 3</td>
<td>x = x / 3</td>
  </tr>
  <tr>
<td>%=</td>
<td>x %= 3</td>
<td>x = x % 3</td>
  </tr>
  <tr>
<td>//=</td>
<td>x //= 3</td>
<td>x = x // 3</td>
  </tr>
  <tr>
<td>**=</td>
<td>x **= 3</td>
<td>x = x ** 3</td>
  </tr>
  <tr>
<td>&amp;=</td>
<td>x &amp;= 3</td>
<td>x = x &amp; 3</td>
  </tr>
  <tr>
<td>|=</td>
<td>x |= 3</td>
<td>x = x | 3</td>
  </tr>
<tr>
<td>^=</td>
<td>x ^= 3</td>
<td>x = x ^ 3</td>
</tr>
<tr>
<td>&gt;&gt;=</td>
<td>x &gt;&gt;= 3</td>
<td>x = x &gt;&gt; 3</td>
</tr>
<tr>
<td>&lt;&lt;=</td>
<td>x &lt;&lt;= 3</td>
<td>x = x &lt;&lt; 3</td>
</tr>
</tbody></table>

### Comparison operators :
Comparison operators are used to compare two values
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:25%">Operator</th>
<th style="width:35%">Name</th>
<th style="width:30%">Example</th>
</tr>
<tr>
<td>==</td>
<td>Equal</td>
<td>x == y</td>
</tr>
<tr>
<td>!=</td>
<td>Not equal</td>
<td>x != y</td>
</tr>
<tr>
<td>&gt;</td>
<td>Greater than</td>
<td>x &gt; y</td>
</tr>
<tr>
<td>&lt;</td>
<td>Less than</td>
<td>x &lt; y</td>
</tr>
  <tr>
<td>&gt;=</td>
<td>Greater than or equal to</td>
<td>x &gt;= y</td>
  </tr>
<tr>
<td>&lt;=</td>
<td>Less than or equal to</td>
<td>x &lt;= y</td>
</tr>
</tbody></table>

### Logical operators :
Logical operators are used to combine conditional statements
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:25%">Operator</th>
<th style="width:35%">Description</th>
<th style="width:30%">Example</th>
</tr>
<tr>
<td>and&nbsp;</td>
<td>Returns True if both statements are true</td>
<td>x &lt; 5 and&nbsp; x &lt; 10</td>
</tr>
<tr>
<td>or</td>
<td>Returns True if one of the statements is true</td>
<td>x &lt; 5 or x &lt; 4</td>
</tr>
<tr>
<td>not</td>
<td>Reverse the result, returns False if the result is true</td>
<td>not(x &lt; 5 and x &lt; 10)</td>
</tr>
</tbody></table>

### Identity operators :
Identity operators are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:25%">Operator</th>
<th style="width:35%">Description</th>
<th style="width:30%">Example</th>
</tr>
<tr>
<td>is&nbsp;</td>
<td>Returns True if both variables are the same object</td>
<td>x is y</td>
</tr>
<tr>
<td>is not</td>
<td>Returns True if both variables are not the same object</td>
<td>x is not y</td>
</tr>
</tbody></table>

### Membership operators :
Membership operators are used to test if a sequence is presented in an object
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:25%">Operator</th>
<th style="width:35%">Description</th>
<th style="width:30%">Example</th>
</tr>
<tr>
<td>in&nbsp;</td>
<td>Returns True if a sequence with the specified value is present in the object</td>
<td>x in y</td>
</tr>
<tr>
<td>not in</td>
<td>Returns True if a sequence with the specified value is not present in the 
object</td>
<td>x not in y</td>
</tr>
</tbody></table>

### Bitwise operators :
Bitwise operators are used to compare (binary) numbers
<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:10%">Operator</th>
<th style="width:15%">Name</th>
<th style="width:75%">Description</th>
</tr>
  <tr>
<td>&amp;&nbsp;</td>
<td>AND</td>
<td>Sets each bit to 1 if both bits are 1</td>
  </tr>
  <tr>
<td>|</td>
<td>OR</td>
<td>Sets each bit to 1 if one of two bits is 1</td>
  </tr>
  <tr>
<td>^</td>
<td>XOR</td>
<td>Sets each bit to 1 if only one of two bits is 1</td>
  </tr>
<tr>
<td>~</td>
<td>NOT</td>
<td>Inverts all the bits</td>
</tr>
<tr>
<td>&lt;&lt;</td>
<td>Zero fill left shift</td>
<td>Shift left by pushing zeros in from the right and let the leftmost bits fall 
off</td>
</tr>
<tr>
<td>&gt;&gt;</td>
<td>Signed right shift</td>
<td>Shift right by pushing copies of the leftmost bit in from the left, and let 
the rightmost bits fall off</td>
</tr>
</tbody></table>
<br /><br />

# Strings

- Strings in python are surrounded by either single quotation marks, or double quotation marks
- You can assign a multiline string to a variable by using three quotes
- Strings in Python are arrays of bytes representing unicode characters. However, Python does not have a character data type, a single character is simply a string with a length of 1.
```python
# Multiline string
a = """hello
world"""
print('**op1 -> ', a)
b = '''hello
world'''
print('**op2 -> ', a)

# Get the character at position 1
c = "Hello, World!"
print('**op3 -> ', c[1])

# looping through string
print('**op4 -> ')
for x in "apple":
  print(x)

# get length of str
print(f'**op5 -> {len("chai")}')

# Check if "free" is present in the following text:
txt = "The best things in life are free!"
print('**op6 -> ',"free" in txt)

# Check if "expensive" is NOT present in the following text:
txt = "The best things in life are free!"
print('**op7 -> ',"expensive" not in txt)

##### OUTPUT
**op1 -> hello
world
**op2 -> hello
world
**op3 -> e
**op4 -> 
a
p
p
l
e
**op5 -> 4
**op6 ->  True
**op7 ->  True
```

## Slicing Strings :
```python
# Get the characters from position 2 to position 5 (not included):
b = "Hello, World!"
print('**op1 -> ', b[2:5])

# Slice From the Start
print('**op2 -> ', b[:5])

# Slice To the End
print('**op3 -> ', b[2:])

# Negative Indexing
print('**op4 -> ', b[-5:-2])

# reverse string
print('**op5 -> ', b[-1:-7:-1])

##### OUTPUT
**op1 ->  llo
**op2 ->  Hello
**op3 ->  llo, World!
**op4 ->  orl
**op5 ->  !dlroW
```

## Python - Modify Strings :
- Python has a set of built-in methods that you can use on strings
```python
# upper case
a = "Hello, World!"
print('**op1 -> ', a.upper())

# lower case
print('**op2 -> ', a.lower())

# remove white space
a = " Hello, World! "
print('**op3 -> ', a.strip())

# replace string
a = "Hello, World!"
print('**op4 -> ', a.replace("H", "J"))

# split string
print('**op5 -> ', a.split(","))

##### OUTPUT
**op1 ->  HELLO, WORLD!
**op2 ->  hello, world!
**op3 ->  Hello, World!
**op4 ->  Jello, World!
**op5 ->  ['Hello', ' World!']
```

## String Concatenation :
- To concatenate, or combine, two strings you can use the + operator
```python
# Merge variable a with variable b into variable c:
a = "Hello"
b = "World"
c = a + b
print('**op1 -> ', c)

# To add a space between them, add a " ":
a = "Hello"
b = "World"
c = a + " " + b
print('**op2 -> ', c)

###### OUTPUT
**op1 ->  HelloWorld
**op2 ->  Hello World
```

## Format - Strings
- As we learned in the Python Variables chapter, we cannot combine strings and numbers like this: `txt = "My name is John, I am " + age`
- But we can combine strings and numbers by using the format() method
- The `format()` method takes the passed arguments, formats them, and places them in the string where the placeholders { } are
```python
# Use the format() method to insert numbers into strings:
age = 36
txt = "My name is John, and I am {}"
print('**op1 -> ', txt.format(age))

# The format() method takes unlimited number of arguments, and are placed into the respective placeholders:
quantity = 3
itemno = 567
price = 49.95
myorder = "I want {} pieces of item {} for {} dollars."
print('**op2 -> ', myorder.format(quantity, itemno, price))

# You can use index numbers {0} to be sure the arguments are placed in the correct placeholders:
quantity = 3
itemno = 567
price = 49.95
myorder = "I want to pay {2} dollars for {0} pieces of item {1}."
print('**op3 -> ', myorder.format(quantity, itemno, price))

###### OUTPUT
**op1 ->  My name is John, and I am 36
**op2 ->  I want 3 pieces of item 567 for 49.95 dollars.
**op3 ->  I want to pay 49.95 dollars for 3 pieces of item 567.
```

## Escape Characters
- To insert characters that are illegal in a string, use an escape character.
- An escape character is a backslash \ followed by the character you want to insert.
- An example of an illegal character is a double quote inside a string that is surrounded by double quotes.
- This will give error : `txt = "We are the so-called "Vikings" from the north."`
- To fix it : `txt = "We are the so-called \"Vikings\" from the north."`
- Some other escape characters are :
<table class="ws-table-all notranslate">
<tbody><tr>
  <th width="25%">Code</th>
  <th>Result</th>
</tr>
<tr>
  <td>\'</td>
  <td>Single Quote</td>
</tr>
<tr>
  <td>\\</td>
  <td>Backslash</td>
</tr>
<tr>
  <td>\n</td>
  <td>New Line</td>
</tr>
<tr>
  <td>\r</td>
  <td>Carriage Return</td>
</tr>
<tr>
  <td>\t</td>
  <td>Tab</td>
</tr>
<tr>
  <td>\b</td>
  <td>Backspace</td>
</tr>
<tr>
  <td>\f</td>
  <td>Form Feed</td>
</tr>
<tr>
  <td>\ooo</td>
  <td>Octal value</td>
</tr>
<tr>
  <td>\xhh</td>
  <td>Hex value</td>
</tr>
</tbody></table>

## String Methods
- Python has a set of built-in methods that you can use on strings
<table class="ws-table-all notranslate">
<tbody><tr>
<th>Method</th>
<th>Description</th>
</tr>
  <tr>
    <td><a href="ref_string_capitalize.asp">capitalize()</a></td><td>Converts the first 
    character to upper case</td>
  </tr>
  <tr>
    <td><a href="ref_string_casefold.asp">casefold()</a></td><td>Converts string into 
    lower case</td>
  </tr>
  <tr>
    <td><a href="ref_string_center.asp">center()</a></td><td>Returns a centered 
    string</td>
  </tr>
  <tr>
    <td><a href="ref_string_count.asp">count()</a></td><td>Returns the number of 
    times a specified value occurs in a string</td>
  </tr>
  <tr>
    <td><a href="ref_string_encode.asp">encode()</a></td><td>Returns an encoded 
    version of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_endswith.asp">endswith()</a></td><td>Returns true if the 
    string ends with the specified value</td>
  </tr>
  <tr>
    <td><a href="ref_string_expandtabs.asp">expandtabs()</a></td><td>Sets the 
    tab size of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_find.asp">find()</a></td><td>Searches the string for a 
    specified value and returns the position of where it was found</td>
  </tr>
  <tr>
    <td><a href="ref_string_format.asp">format()</a></td><td>Formats specified 
    values in a string</td>
  </tr>
  <tr>
    <td>format_map()</td><td>Formats specified 
    values in a string</td>
  </tr>
  <tr>
    <td><a href="ref_string_index.asp">index()</a></td><td>Searches the string 
    for a specified value and returns the position of where it was found</td>
  </tr>
  <tr>
    <td><a href="ref_string_isalnum.asp">isalnum()</a></td><td>Returns True if all 
    characters in the string are alphanumeric</td>
  </tr>
  <tr>
    <td><a href="ref_string_isalpha.asp">isalpha()</a></td><td>Returns True if all 
    characters in the string are in the alphabet</td>
  </tr>
  <tr>
    <td><a href="ref_string_isdecimal.asp">isdecimal()</a></td><td>Returns True if all 
    characters in the string are decimals</td>
  </tr>
  <tr>
    <td><a href="ref_string_isdigit.asp">isdigit()</a></td><td>Returns True if all 
    characters in the string are digits</td>
  </tr>
  <tr>
    <td><a href="ref_string_isidentifier.asp">isidentifier()</a></td><td>Returns True if 
    the string is an identifier</td>
  </tr>
  <tr>
    <td><a href="ref_string_islower.asp">islower()</a></td><td>Returns True if all 
    characters in the string are lower case</td>
  </tr>
  <tr>
    <td><a href="ref_string_isnumeric.asp">isnumeric()</a></td><td>Returns True if 
    all characters in the string are numeric</td>
  </tr>
  <tr>
    <td><a href="ref_string_isprintable.asp">isprintable()</a></td><td>Returns True if 
    all characters in the string are printable</td>
  </tr>
  <tr>
    <td><a href="ref_string_isspace.asp">isspace()</a></td><td>Returns True if all 
    characters in the string are whitespaces</td>
  </tr>
  <tr>
    <td><a href="ref_string_istitle.asp">istitle()</a></td>
    <td>Returns True if the string follows the rules of a 
    title</td>
  </tr>
  <tr>
    <td><a href="ref_string_isupper.asp">isupper()</a></td><td>Returns True if all 
    characters in the string are upper case</td>
  </tr>
  <tr>
    <td><a href="ref_string_join.asp">join()</a></td><td>Joins the elements of 
    an iterable to the end of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_ljust.asp">ljust()</a></td><td>Returns a left justified 
    version of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_lower.asp">lower()</a></td><td>Converts a string into 
    lower case</td>
  </tr>
  <tr>
    <td><a href="ref_string_lstrip.asp">lstrip()</a></td><td>Returns a left trim 
    version of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_maketrans.asp">maketrans()</a></td><td>Returns a 
    translation table to be used in translations</td>
  </tr>
  <tr>
    <td><a href="ref_string_partition.asp">partition()</a></td><td>Returns a tuple 
    where the string is parted into three parts</td>
  </tr>
  <tr>
    <td><a href="ref_string_replace.asp">replace()</a></td><td>Returns a string 
    where a specified value is replaced with a specified value</td>
  </tr>
  <tr>
    <td><a href="ref_string_rfind.asp">rfind()</a></td><td>Searches the string for 
    a specified value and returns the last position of where it was found</td>
  </tr>
  <tr>
    <td><a href="ref_string_rindex.asp">rindex()</a></td><td>Searches the string for 
    a specified value and returns the last position of where it was found</td>
  </tr>
  <tr>
    <td><a href="ref_string_rjust.asp">rjust()</a></td><td>Returns a right justified 
    version of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_rpartition.asp">rpartition()</a></td><td>Returns a tuple 
    where the string is parted into three parts</td>
  </tr>
  <tr>
    <td><a href="ref_string_rsplit.asp">rsplit()</a></td><td>Splits the string at 
    the specified separator, and returns a list</td>
  </tr>
  <tr>
    <td><a href="ref_string_rstrip.asp">rstrip()</a></td><td>Returns a right trim 
    version of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_split.asp">split()</a></td><td>Splits the string at 
    the specified separator, and returns a list</td>
  </tr>
  <tr>
    <td><a href="ref_string_splitlines.asp">splitlines()</a></td><td>Splits the string 
    at line breaks and returns a list</td>
  </tr>
  <tr>
    <td><a href="ref_string_startswith.asp">startswith()</a></td><td>Returns true if 
    the string starts with the specified value</td>
  </tr>
  <tr>
    <td><a href="ref_string_strip.asp">strip()</a></td><td>Returns a trimmed version of the string</td>
  </tr>
  <tr>
    <td><a href="ref_string_swapcase.asp">swapcase()</a></td><td>Swaps cases, lower 
    case becomes upper case and vice versa</td>
  </tr>
  <tr>
    <td><a href="ref_string_title.asp">title()</a></td><td>Converts the first 
    character of each word to upper case</td>
  </tr>
  <tr>
    <td><a href="ref_string_translate.asp">translate()</a></td><td>Returns a 
    translated string</td>
  </tr>
  <tr>
    <td><a href="ref_string_upper.asp">upper()</a></td><td>Converts a string 
    into upper case</td>
  </tr>
<tr><td><a href="ref_string_zfill.asp">zfill()</a></td><td>Fills the string with 
  a specified number of 0 values at the beginning</td></tr>
</tbody></table>
<br><br>

# Lists

- Lists are used to store multiple items in a single variable
- List items are ordered, changeable, and **allow duplicate values**
- When we say that lists are **ordered**, it means that the items have a defined order, and that order will not change.
- If you add new items to a list, the new items will be placed at the end of the list.
- There are some list methods that will change the order, but in general: the order of the items will not change.
- The list is changeable, meaning that we can change, add, and remove items in a list after it has been created
- Since lists are indexed, lists can have items with the same value => **allows duplicates**
- A list **can contain different data types**
```python
# Create a List (approach 1)
thislist = ["apple", "banana", "cherry", "apple"]
print('**op1 -> ', thislist)

# Create a List (approach 2)
thislist = list(("apple", "banana", "cherry", "apple")) # note the double round-brackets
print('**op2 -> ', thislist)

###### OUTPUT
**op1 ->  ['apple', 'banana', 'cherry', 'apple']
**op2 ->  ['apple', 'banana', 'cherry', 'apple']
```

## Access List Items
- List items are indexed and you can access them by referring to the index number
```python
# Print the second item of the list:
thislist = ["apple", "banana", "cherry"]
print('**op1 -> ', thislist[1])

# Negative Indexing
print('**op2 -> ', thislist[-1])

# Range of Indexes
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]
print('**op2 -> ', thislist[2:5])

# Check if Item Exists
print('**op3 -> ')
thislist = ["apple", "banana", "cherry"]
if "apple" in thislist:
  print("Yes, 'apple' is in the fruits list")

###### OUTPUT
**op1 ->  banana
**op2 ->  cherry
**op2 ->  ['cherry', 'orange', 'kiwi']
**op3 -> 
Yes, 'apple' is in the fruits list
```

## Change List Items
```python
# Change Item Value
thislist = ["apple", "banana", "cherry"]
thislist[1] = "blackcurrant"
print('**op1 -> ', thislist)

# Change a Range of Item Values
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "mango"]
thislist[1:3] = ["blackcurrant", "watermelon"]
print('**op2 -> ', thislist)

# If you insert more items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly
thislist = ["apple", "banana", "cherry"]
thislist[1:2] = ["blackcurrant", "watermelon"]
print('**op3 -> ', thislist)

# If you insert less items than you replace, the new items will be inserted where you specified, and the remaining items will move accordingly:
thislist = ["apple", "banana", "cherry"]
thislist[1:3] = ["watermelon"]
print('**op4 -> ', thislist)

# Insert Items -> insert() inserts an item at the specified index
thislist = ["apple", "banana", "cherry"]
thislist.insert(2, "watermelon")
print('**op5 -> ', thislist)

##### OUTPUT
**op1 ->  ['apple', 'blackcurrant', 'cherry']
**op2 ->  ['apple', 'blackcurrant', 'watermelon', 'orange', 'kiwi', 'mango']
**op3 ->  ['apple', 'blackcurrant', 'watermelon', 'cherry']
**op4 ->  ['apple', 'watermelon']
**op5 ->  ['apple', 'banana', 'watermelon', 'cherry']
```

## Add List Items
```python
# Append Items
thislist = ["apple", "banana", "cherry"]
thislist.append("orange")
print('**op1 -> ', thislist)

# Insert Items
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print('**op2 -> ', thislist)

# Extend List
thislist = ["apple", "banana", "cherry"]
tropical = ["mango", "pineapple", "papaya"]
thislist.extend(tropical)
print('**op3 -> ', thislist)

# Add Any Iterable (tuples, sets, dictionaries etc.)
thislist = ["apple", "banana", "cherry"]
thistuple = ("kiwi", "orange")
thislist.extend(thistuple)
print('**op4 -> ', thislist)

##### OUTPUT
**op1 ->  ['apple', 'banana', 'cherry', 'orange']
**op2 ->  ['apple', 'orange', 'banana', 'cherry']
**op3 ->  ['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
**op4 ->  ['apple', 'banana', 'cherry', 'kiwi', 'orange']
```

## Remove List Items
```python
# Remove Specified Item (only removes first occurence)
thislist = ["apple", "banana", "cherry", "banana"]
thislist.remove("banana")
print('**op1 -> ', thislist)

# Remove Specified Index
thislist = ["apple", "banana", "cherry"]
thislist.pop(1)
print('**op2 -> ', thislist)

# If you do not specify the index, the pop() method removes the last item.
thislist = ["apple", "banana", "cherry"]
thislist.pop()
print('**op3 -> ', thislist)

# The del keyword also removes the specified index:
thislist = ["apple", "banana", "cherry"]
del thislist[0]
print('**op4 -> ', thislist)

# The del keyword can also delete the list completely.
thislist = ["apple", "banana", "cherry"]
del thislist

# Clear the List
thislist = ["apple", "banana", "cherry"]
thislist.clear()
print('**op5 -> ', thislist)

##### OUTPUT
**op1 ->  ['apple', 'cherry', 'banana']
**op2 ->  ['apple', 'cherry']
**op3 ->  ['apple', 'banana']
**op4 ->  ['banana', 'cherry']
**op5 ->  []
```

## Loop Lists
```python
# Loop Through a List using for loop
thislist = ["apple", "banana", "cherry"]
print('**op1 -> ')
for x in thislist:
  print(x)

# Loop Through the Index Numbers
print('**op2 -> ')
for i in range(len(thislist)):
  print(thislist[i])

# Using a While Loop
i = 0
print('**op3 -> ')
while i < len(thislist):
  print(thislist[i])
  i = i + 1
    
# Looping Using List Comprehension
print('**op4 -> ')
[print(x) for x in thislist]

##### OUTPUT
**op1 -> 
apple
banana
cherry
**op2 -> 
apple
banana
cherry
**op3 -> 
apple
banana
cherry
**op4 -> 
apple
banana
cherry
```

## List Comprehension
- Syntax is `newlist = [expression for item in iterable if condition == True]`. The return value is a new list, leaving the old list unchanged.
```python
# fruits with the letter "a" in the name
# without list comprehension
fruits = ["apple", "banana", "cherry", "kiwi", "mango"]
newlist = []
for x in fruits:
  if "a" in x:
    newlist.append(x)
print('**op1 -> ', newlist)

# with list comprehension
newlist = [x for x in fruits if "a" in x]
print('**op2 -> ', newlist)

# with condition
newlist = [x for x in fruits if x != "apple"]
print('**op3 -> ', newlist)

# The condition is optional and can be omitted
newlist = [x for x in fruits]
print('**op4 -> ', newlist)

# Iterable (use the range() function to create an iterable)
newlist = [x for x in range(10)]
print('**op5 -> ', newlist)

# Accept only numbers lower than 5
newlist = [x for x in range(10) if x < 5]
print('**op6 -> ', newlist)

# Expression (The expression is the current item in the iteration, but it is also the outcome, which you can manipulate before it ends up like a list item in the new list)
# Set the values in the new list to upper case:
newlist = [x.upper() for x in fruits]
print('**op7 -> ', newlist)

# Set all values in the new list to 'hello'
newlist = ['hello' for x in fruits]
print('**op8 -> ', newlist)

# The expression can also contain conditions, not like a filter, but as a way to manipulate the outcome
# Return "orange" instead of "banana" => "Return the item if it is not banana, if it is banana return orange".
newlist = [x if x != "banana" else "orange" for x in fruits]
print('**op9 -> ', newlist)

##### OUTPUT
**op1 ->  ['apple', 'banana', 'mango']
**op2 ->  ['apple', 'banana', 'mango']
**op3 ->  ['banana', 'cherry', 'kiwi', 'mango']
**op4 ->  ['apple', 'banana', 'cherry', 'kiwi', 'mango']
**op5 ->  [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
**op6 ->  [0, 1, 2, 3, 4]
**op7 ->  ['APPLE', 'BANANA', 'CHERRY', 'KIWI', 'MANGO']
**op8 ->  ['hello', 'hello', 'hello', 'hello', 'hello']
**op9 ->  ['apple', 'orange', 'cherry', 'kiwi', 'mango']
```

## Sort Lists
- List objects have a sort() method that will sort the list alphanumerically, ascending, by default
- You can also customize your own sort function by using the keyword argument `key = function`.
- By default the sort() method is **case sensitive**, resulting in all capital letters being sorted before lower case letters
- So if you want a case-insensitive sort function, use str.lower as a key function
- The `reverse()` method reverses the current sorting order of the elements
```python
# Sort List Alphanumerically
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort()
print('**op1 -> ', thislist)

# Sort the list numerically
thislist = [100, 50, 65, 82, 23]
thislist.sort()
print('**op2 -> ', thislist)

# Sort Descending
thislist = ["orange", "mango", "kiwi", "pineapple", "banana"]
thislist.sort(reverse = True)
print('**op3 -> ', thislist)

thislist = [100, 50, 65, 82, 23]
thislist.sort(reverse = True)
print('**op4 -> ', thislist)

# Customize Sort Function (Sort the list based on how close the number is to 50):
def myfunc(n):
  return abs(n - 50)

thislist = [100, 50, 65, 82, 23]
thislist.sort(key = myfunc)
print('**op5 -> ', thislist)

# Case sensitive sorting can give an unexpected result
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort()
print('**op6 -> ', thislist)

# Perform a case-insensitive sort of the list:
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.sort(key = str.lower)
print('**op7 -> ', thislist)

# Reverse the order of the list items:
thislist = ["banana", "Orange", "Kiwi", "cherry"]
thislist.reverse()
print('**op8 -> ', thislist)

##### OUTPUT
**op1 ->  ['banana', 'kiwi', 'mango', 'orange', 'pineapple']
**op2 ->  [23, 50, 65, 82, 100]
**op3 ->  ['pineapple', 'orange', 'mango', 'kiwi', 'banana']
**op4 ->  [100, 82, 65, 50, 23]
**op5 ->  [50, 65, 23, 82, 100]
**op6 ->  ['Kiwi', 'Orange', 'banana', 'cherry']
**op7 ->  ['banana', 'cherry', 'Kiwi', 'Orange']
**op8 ->  ['cherry', 'Kiwi', 'Orange', 'banana']
```

## Copy Lists
- You cannot copy a list simply by typing `list2 = list1`, because: `list2` will only be a reference to `list1`, and changes made in `list1` will automatically also be made in `list2`
- One way is to use the built-in List method `copy()`
- Another way to make a copy is to use the built-in method `list()`
```python
# Make a copy of a list with the copy() method:
thislist = ["apple", "banana", "cherry"]
mylist = thislist.copy()
print('**op1 -> ', mylist)

# Make a copy of a list with the list() method:
thislist = ["apple", "banana", "cherry"]
mylist = list(thislist)
print('**op2 -> ', mylist)

##### OUTPUT
**op1 ->  ['apple', 'banana', 'cherry']
**op2 ->  ['apple', 'banana', 'cherry']
```

## Join Lists
```python
# Join two list using + operator:
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]
list3 = list1 + list2
print('**op1 -> ', list3)

# Another way to join two lists is by appending all the items from list2 into list1, one by one:
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]
for x in list2:
  list1.append(x)
print('**op2 -> ', list1)

# Or you can use the extend() method, which purpose is to add elements from one list to another list:
list1 = ["a", "b" , "c"]
list2 = [1, 2, 3]
list1.extend(list2)
print('**op3 -> ', list1)

##### OUTPUT
**op1 ->  ['a', 'b', 'c', 1, 2, 3]
**op2 ->  ['a', 'b', 'c', 1, 2, 3]
**op3 ->  ['a', 'b', 'c', 1, 2, 3]
```

## List Methods
- Python has a set of built-in methods that you can use on lists.
<table class="ws-table-all notranslate">
<tbody><tr>
<th>Method</th>
<th>Description</th>
</tr>
<tr><td><a href="ref_list_append.asp">append()</a></td><td>Adds an element at 
  the end of the list</td></tr>
<tr><td><a href="ref_list_clear.asp">clear()</a></td><td>Removes all the 
  elements from the list</td></tr>
<tr><td><a href="ref_list_copy.asp">copy()</a></td><td>Returns a copy of the 
  list</td></tr>
<tr><td><a href="ref_list_count.asp">count()</a></td><td>Returns the number of 
  elements with the specified value</td></tr>
<tr><td><a href="ref_list_extend.asp">extend()</a></td><td>Add the elements of a 
  list (or any iterable), to the end of the current list</td></tr>
<tr><td><a href="ref_list_index.asp">index()</a></td><td>Returns the index of 
  the first element with the specified value</td></tr>
<tr><td><a href="ref_list_insert.asp">insert()</a></td><td>Adds an element at 
  the specified position</td></tr>
<tr><td><a href="ref_list_pop.asp">pop()</a></td><td>Removes the element at the 
  specified position</td></tr>
<tr><td><a href="ref_list_remove.asp">remove()</a></td><td>Removes the  
  item with the specified value</td></tr>
<tr><td><a href="ref_list_reverse.asp">reverse()</a></td><td>Reverses the order 
  of the list</td></tr>
<tr><td><a href="ref_list_sort.asp">sort()</a></td><td>Sorts the list</td></tr>
</tbody></table>
<br><br>

# Tuples

- used to store multiple items in a single variable
- Tuple items are **ordered** *(items have a defined order, and that order will not change)*, **unchangeable** *(we cannot change, add or remove items after the tuple has been created)*, and **allow duplicate values** *(they can have items with the same value)*
- Tuples are written with round brackets
- Tuple items are **indexed**

> **Note: When creating a tuple with only one item, remember to include a comma after the item, otherwise it will not be identified as a tuple.**

```python
# Create a Tuple (way 1)
thistuple = ("apple", "banana", "cherry")
print('**op1 -> ', thistuple)

# Create a Tuple (way 2)
thistuple = tuple(("apple", "banana", "cherry")) # note the double round-brackets
print('**op2 -> ', thistuple)

##### OUTPUT
**op1 ->  ('apple', 'banana', 'cherry')
**op2 ->  ('apple', 'banana', 'cherry')
```

## Access Tuple Items

*----- SAME AS LISTS ------*

## Update Tuples
```python
# Change Tuple Values
x = ("apple", "banana", "cherry")
y = list(x)
y[1] = "kiwi"
x = tuple(y)
print('**op1 -> ', x)

# Add Items (approach 1 - Convert into a list)
thistuple = ("apple", "banana", "cherry")
y = list(thistuple)
y.append("orange")
thistuple = tuple(y)
print('**op2 -> ', thistuple)

# Add Items (approach 2 - Add tuple to a tuple)
thistuple = ("apple", "banana", "cherry")
y = ("orange",)
thistuple += y
print('**op3 -> ', thistuple)

# Remove Items
thistuple = ("apple", "banana", "cherry")
y = list(thistuple)
y.remove("apple")
thistuple = tuple(y)
print('**op4 -> ', thistuple)

# delete the tuple
thistuple = ("apple", "banana", "cherry")
del thistuple

##### OUTPUT
**op1 ->  ('apple', 'kiwi', 'cherry')
**op2 ->  ('apple', 'banana', 'cherry', 'orange')
**op3 ->  ('apple', 'banana', 'cherry', 'orange')
**op4 ->  ('banana', 'cherry')
```

## Unpack Tuples
- When we create a tuple, we normally assign values to it. This is called *packing* a tuple
- But, in Python, we are also allowed to extract the values back into variables. This is called *unpacking*
- If the number of variables is less than the number of values, you can add an **astrisk** to the variable name and the values will be assigned to the variable as a list
- If the asterisk is added to another variable name than the last, Python will assign values to the variable until the number of values left matches the number of variables left.
```python
# Packing a tuple:
fruits = ("apple", "banana", "cherry")
print('**op1 -> ', fruits)

# Unpacking a tuple [NOTE: The number of variables must match the number of values in the tuple, if not, you must use an asterisk to collect the remaining values as a list.]
(green, yellow, red) = fruits
print('**op2 -> ')
print(green)
print(yellow)
print(red)

# Using Asterisk* on last variable
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")
(green, yellow, *red) = fruits
print('**op3 -> ')
print(green)
print(yellow)
print(red)

# Using Asterisk* on not the last variable
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")
(green, *yellow, red) = fruits
print('**op4 -> ')
print(green)
print(yellow)
print(red)

###### OUTPUT
**op1 ->  ('apple', 'banana', 'cherry')
**op2 -> 
apple
banana
cherry
**op3 -> 
apple
banana
['cherry', 'strawberry', 'raspberry']
**op4 -> 
apple
['banana', 'cherry', 'strawberry']
raspberry
```
## Loop Tuples

*----- SAME AS LISTS ------*

## Join Tuples

```python
# Join two tuples using + operator :
tuple1 = ("a", "b" , "c")
tuple2 = (1, 2, 3)
tuple3 = tuple1 + tuple2
print('**op1 -> ', tuple3)

# Multiply Tuples
fruits = ("apple", "banana", "cherry")
mytuple = fruits * 2
print('**op3 -> ', mytuple)

###### OUTPUT
**op1 ->  ('a', 'b', 'c', 1, 2, 3)
**op3 ->  ('apple', 'banana', 'cherry', 'apple', 'banana', 'cherry')
```

## Tuple Methods

<table class="ws-table-all notranslate">
<tbody><tr>
<th style="width:20%">Method</th>
<th>Description</th>
</tr>
<tr><td><a href="ref_tuple_count.asp">count()</a></td><td>Returns the number of times a specified value occurs in a tuple</td></tr>
<tr><td><a href="ref_tuple_index.asp">index()</a></td><td>Searches the tuple for a specified value and returns the position of where it was found</td></tr>
</tbody></table>

# Sets

- used to store multiple items in a single variable
- A set is a collection which is unordered, unchangeable, and unindexed
- Set items are **unchangeable**, but you can remove items and add new items
- Sets are **unordered**, so you cannot be sure in which order the items will appear.
- Sets **do not allow duplicate values**
- A set can contain different data types

```python
# Duplicate values will be ignored:
thisset = {"apple", "banana", "cherry", "apple"}
print('**op1 -> ', thisset)

# Using the set() constructor to make a set:
thisset = set(("apple", "banana", "cherry")) # note the double round-brackets
print('**op2 -> ', thisset)

###### OUTPUT
**op1 ->  {'banana', 'cherry', 'apple'}
**op2 ->  {'banana', 'cherry', 'apple'}
```

## Access Set Items
- You **cannot access** items in a set by referring to an index or a key
- But you can loop through the set items using a **for loop**, or ask if a specified value is present in a set, by using the **in** keyword

## Add Set Items

```python
# Add an item to a set, using the add() method:
thisset = {"apple", "banana", "cherry"}
thisset.add("orange")
print('**op1 -> ', thisset)

# To add items from another set into the current set, use the update() method.
thisset = {"apple", "banana", "cherry"}
tropical = {"pineapple", "mango", "papaya"}
thisset.update(tropical)
print('**op2 -> ', thisset)

# Add Any Iterable
thisset = {"apple", "banana", "cherry"}
mylist = ["kiwi", "orange"]
thisset.update(mylist)
print('**op3 -> ', thisset)

##### OUTPUT
**op1 ->  {'banana', 'cherry', 'apple', 'orange'}
**op2 ->  {'papaya', 'cherry', 'apple', 'mango', 'banana', 'pineapple'}
**op3 ->  {'orange', 'kiwi', 'cherry', 'apple', 'banana'}
```

## Remove Set Items

```python
# Remove by using the remove() method
# Note: If the item to remove does not exist, remove() will raise an error.
thisset = {"apple", "banana", "cherry"}
thisset.remove("banana")
print('**op1 -> ', thisset)

# Remove by using the discard() method:
# Note: If the item to remove does not exist, discard() will NOT raise an error.
thisset = {"apple", "banana", "cherry"}
thisset.discard("banana")
print('**op2 -> ', thisset)

# Remove a random item by using the pop() method:
# Sets are unordered, so when using the pop() method, you do not know which item that gets removed.
thisset = {"apple", "banana", "cherry"}
x = thisset.pop()
print('**op3 -> ')
print(x)
print(thisset)

# The clear() method empties the set:
thisset = {"apple", "banana", "cherry"}
thisset.clear()
print('**op4 -> ', thisset)

# The del keyword will delete the set completely:
thisset = {"apple", "banana", "cherry"}
del thisset

###### OUTPUT
**op1 ->  {'cherry', 'apple'}
**op2 ->  {'cherry', 'apple'}
**op3 -> 
banana
{'cherry', 'apple'}
**op4 ->  set()
```

## Loop Sets
- You can loop through the set items by using a for loop
- Can't use while loop since indexing doesn't work in sets

## Join Sets

```python
# union() method that returns a new set containing all items from both sets
set1 = {"a", "b" , "c"}
set2 = {1, 2, 3}
set3 = set1.union(set2)
print('**op1 -> ', set3)

# update() method that inserts all the items from one set into another:
set1 = {"a", "b" , "c"}
set2 = {1, 2, 3}
set1.update(set2)
print('**op2 -> ', set1)

# Note: Both union() and update() will exclude any duplicate items

##### OUTPUT
**op1 ->  {1, 'b', 2, 3, 'c', 'a'}
**op2 ->  {1, 'b', 2, 3, 'c', 'a'}
```

## Set Methods

<table class="ws-table-all notranslate">
<tbody><tr>
<th>Method</th>
<th>Description</th>
</tr>
<tr><td><a href="ref_set_add.asp">add()</a></td><td>Adds an element to the 
  set</td></tr>
<tr><td><a href="ref_set_clear.asp">clear()</a></td><td>Removes all the 
  elements from the set</td></tr>
<tr><td><a href="ref_set_copy.asp">copy()</a></td><td>Returns a copy of the set</td></tr>
  <tr>
    <td><a href="ref_set_difference.asp">difference()</a></td><td>Returns a set 
    containing the difference between two or more sets</td>
  </tr>
  <tr>
    <td><a href="ref_set_difference_update.asp">difference_update()</a></td><td>Removes the 
    items in this set that are also included in another, specified set</td>
  </tr>
<tr><td><a href="ref_set_discard.asp">discard()</a></td><td>Remove the specified 
  item</td></tr>
  <tr>
    <td><a href="ref_set_intersection.asp">intersection()</a></td><td>Returns a set, 
    that is the intersection of two other sets</td>
  </tr>
<tr><td><a href="ref_set_intersection_update.asp">intersection_update()</a></td><td>
  Removes the items in this set that are not present in other, specified set(s)</td></tr>
  <tr>
    <td><a href="ref_set_isdisjoint.asp">isdisjoint()</a></td><td>Returns whether 
    two sets have a intersection or not</td>
  </tr>
  <tr>
    <td><a href="ref_set_issubset.asp">issubset()</a></td><td>Returns whether 
    another set contains this set or not</td>
  </tr>
<tr><td><a href="ref_set_issuperset.asp">issuperset()</a></td><td>Returns whether 
  this set contains another set or not</td></tr>
<tr><td><a href="ref_set_pop.asp">pop()</a></td><td>Removes an element from the 
  set</td></tr>
<tr><td><a href="ref_set_remove.asp">remove()</a></td><td>Removes the specified element</td></tr>
  <tr>
    <td><a href="ref_set_symmetric_difference.asp">symmetric_difference()</a></td><td>Returns 
    a set with the symmetric differences of two sets</td>
  </tr>
<tr><td><a href="ref_set_symmetric_difference_update.asp">symmetric_difference_update()</a></td><td>
  inserts the symmetric differences from this set and another</td></tr>
  <tr>
    <td><a href="ref_set_union.asp">union()</a></td><td>Return a set containing 
    the union of sets</td>
  </tr>
<tr><td><a href="ref_set_update.asp">update()</a></td><td>Update the set with the 
  union of this set and others</td></tr>
</tbody></table>

# Dictionaries
- used to store data values in **key:value** pairs.
- A dictionary is a collection which is ordered, changeable and do not allow duplicates.
- When we say that **dictionaries are ordered**, it means that the items have a defined order, and that order will not change.
- As of Python version 3.7, dictionaries are ordered. In Python 3.6 and earlier, dictionaries are unordered.
- **Dictionaries are changeable**, meaning that we can change, add or remove items after the dictionary has been created.
- **Duplicates Not Allowed** -> Dictionaries cannot have two items with the same key
- ways to create dict:<br>
  `thisdict = dict(name = "John", age = 36, country = "Norway")`<br>
  `thisdict = {"brand": "Ford", "model": "Mustang", "year": 1964}`
- `OrderedDict` has two extra features (methods) that a regular Dictionary doesn’t have — `reversed` and `move_to_end`

## Access Dictionary Items

```python
# access the items of a dictionary by referring to its key name, inside square brackets:
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
x = thisdict["model"]
print('**op1 -> ', x)

# using a method called get()
x = thisdict.get("model")
print('**op2 -> ', x)

# Get ist of all the keys in the dictionary.
x = thisdict.keys()
print('**op3 -> ', x)

# Get ist of all the values in the dictionary.
x = thisdict.values()
print('**op4 -> ', x)

# Get Items - items() method will return each item in a dictionary, as tuples in a list.
x = thisdict.items()
print('**op5 -> ', x)

# NOTE : if u change the original dict after reading the list of keys/values/items, the list will automatically get updated

# Check if Key Exists
if "model" in thisdict:
  print('**op6 -> Yes!!')

##### OUTPUT
**op1 ->  Mustang
**op2 ->  Mustang
**op3 ->  dict_keys(['brand', 'model', 'year'])
**op4 ->  dict_values(['Ford', 'Mustang', 1964])
**op5 ->  dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])
**op6 -> Yes!!
```

## Change Dictionary Items

```python
# Change Values
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict["year"] = 2018
print('**op1 -> ', thisdict)

# Update Dictionary
# The update() method will update the dictionary with the items from the given argument
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict.update({"year": 2020})
thisdict.update({"color": 'black'})
print('**op2 -> ', thisdict)

##### OUTPUT
**op1 ->  {'brand': 'Ford', 'model': 'Mustang', 'year': 2018}
**op2 ->  {'brand': 'Ford', 'model': 'Mustang', 'year': 2020, 'color': 'black'}
```

## Add Dictionary Items

```python
# Adding an item -> done by using a new index key and assigning a value to it:
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict["color"] = "red"
print('**op1 -> ', thisdict)

# The update() method will update the dictionary with the items from a given argument. If the item does not exist, the item will be added.
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict.update({"color": "red"})
print('**op2 -> ', thisdict)

##### OUTPUT
**op1 ->  {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
**op2 ->  {'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'red'}
```

## Remove Dictionary Items

```python
# pop() method removes the item with the specified key name
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict.pop("model")
print('**op1 -> ', thisdict)

# popitem() method removes the last inserted item (in versions before 3.7, a random item is removed instead):
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict.popitem()
print('**op2 -> ', thisdict)

# del keyword removes the item with the specified key name:
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
del thisdict["model"]
print('**op3 -> ', thisdict)

# clear() method empties the dictionary:
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
thisdict.clear()
print('**op4 -> ', thisdict)

###### OUTPUT
**op1 ->  {'brand': 'Ford', 'year': 1964}
**op2 ->  {'brand': 'Ford', 'model': 'Mustang'}
**op3 ->  {'brand': 'Ford', 'year': 1964}
**op4 ->  {}
```

## Loop Dictionaries
- When looping through a dictionary, the return value are the keys of the dictionary, but there are methods to return the values as well

```python
# Print all key names in the dictionary
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
print('**op1 -> ')
for x in thisdict:
  print(x)

# Print all values in the dictionary
print('**op2 -> ')
for x in thisdict:
  print(thisdict[x])

# use the values() method to return values of a dictionary:
print('**op3 -> ')
for x in thisdict.values():
  print(x)

# use the keys() method to return the keys of a dictionary:
print('**op4 -> ')
for x in thisdict.keys():
  print(x)

# Loop through both keys and values, by using the items() method
print('**op5 -> ')
for x, y in thisdict.items():
  print(x, y)

##### OUTPUT
**op1 -> 
brand
model
year
**op2 -> 
Ford
Mustang
1964
**op3 -> 
Ford
Mustang
1964
**op4 -> 
brand
model
year
**op5 -> 
brand Ford
model Mustang
year 1964
```

## Copy Dictionaries
- You cannot copy a dictionary simply by typing `dict2 = dict1`, because: `dict2` will only be a reference to `dict1`, and changes made in `dict1` will automatically also be made in `dict2`.

```python
# using copy() method
thisdict = {"brand": "Ford","model": "Mustang","year": 1964}
mydict = thisdict.copy()
print('**op1 -> ', mydict)

# use the built-in function dict().
mydict = dict(thisdict)
print('**op1 -> ', mydict)

###### OUTPUT
**op1 ->  {'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
**op1 ->  {'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
```

## Dictionary Methods
<table class="ws-table-all notranslate">
<tbody><tr>
<th>Method</th>
<th>Description</th>
</tr>
<tr><td><a href="ref_dictionary_clear.asp">clear()</a></td><td>Removes all the elements from the dictionary</td></tr>
<tr><td><a href="ref_dictionary_copy.asp">copy()</a></td><td>Returns a copy of the dictionary</td></tr>
<tr><td><a href="ref_dictionary_fromkeys.asp">fromkeys()</a></td><td>Returns a dictionary with the specified keys and value</td></tr>
<tr><td><a href="ref_dictionary_get.asp">get()</a></td><td>Returns the value of the specified key</td></tr>
<tr><td><a href="ref_dictionary_items.asp">items()</a></td><td>Returns a list containing a tuple for each key value pair</td></tr>
<tr><td><a href="ref_dictionary_keys.asp">keys()</a></td><td>Returns a list containing the dictionary's keys</td></tr>
<tr><td><a href="ref_dictionary_pop.asp">pop()</a></td><td>Removes the element with the specified key</td></tr>
<tr><td><a href="ref_dictionary_popitem.asp">popitem()</a></td><td>Removes the last 
  inserted key-value pair</td></tr>
<tr><td><a href="ref_dictionary_setdefault.asp">setdefault()</a></td><td>Returns the value of the specified key. If the key does not exist: insert the key, with the specified value</td></tr>
<tr><td><a href="ref_dictionary_update.asp">update()</a></td><td>Updates the dictionary with the specified key-value pairs</td></tr>
<tr><td><a href="ref_dictionary_values.asp">values()</a></td><td>Returns a list of all the values in the dictionary</td></tr>
</tbody></table>

# Conditional Execution & Loops

*(made notes for only important and new things)*

```python
# while else loop
i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i is no longer less than 6")

#### OUTPUT
1
2
3
4
5
i is no longer less than 6
```
```python
# for else loop
# The else block will NOT be executed if the loop is stopped by a break statement.
print('**op1 -> ')
for x in range(6):
  if x == 3: break
  print(x)
else:
  print("Finally finished!")

print('\n**op1 -> ')
for x in range(6):
  print(x)
else:
  print("Finally finished!")

##### OUTPUT
**op1 -> 
0
1
2

**op1 -> 
0
1
2
3
4
5
Finally finished!
```

# Comprehensions
- Comprehensions in Python provide us with a short and concise way to construct new sequences (such as lists, set, dictionary etc.) using sequences which have been already defined.
- Python supports the following 4 types of comprehensions:
    1. List Comprehensions
    2. Dictionary Comprehensions
    3. Set Comprehensions
    4. Generator Comprehensions

## List Comprehensions:

- Syntax of different comprehensions
  <br>
  `new_list = [expression for variable in iterable]`<br>
  `new_list = [expression for variable in iterable if condition == True]`<br>
  `new_list = [expression if condition else expression for variable in iterable]`

```python
# way 1
res = [num for num in range(8)]
print('**op1 -> ', res)

# way 2
res = [num for num in range(8) if num%2==0]
print('**op2 -> ', res)

# way 3
res = [num if num%2==0 else 'odd' for num in range(8)]
print('**op3 -> ', res)

# nested comprehension example
matrix = [[j for j in range(5)] for i in range(3)]
print('**op4 -> ', matrix)

##### OUTPUT
**op1 ->  [0, 1, 2, 3, 4, 5, 6, 7]
**op2 ->  [0, 2, 4, 6]
**op3 ->  [0, 'odd', 2, 'odd', 4, 'odd', 6, 'odd']
**op4 ->  [[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]
```

- **Any** and **All** methods are useful in checking if every element in the list or Any of the elements in the list satisfy the conditions.

```python
# all method
# check if all the elements in the list are even
res = all(x % 2 == 0 for x in range(8))
print('**op1 -> ', res)

# any method
# check if any element in the list is even.
res = any(x % 2 == 0 for x in range(8))
print('**op2 -> ', res)

##### OUTPUT

**op1 ->  False
**op2 ->  True
```

## Dictionary Comprehensions
- Syntax <br>
  `output_dict = {key:value for (key, value) in iterable if (key, value satisfy this condition)}`

```python
# example 1
input_list = [1,2,3,4,5,6,7]
dict_using_comp = {var:var ** 3 for var in input_list if var % 2 != 0}
print('**op1 -> ', dict_using_comp)

# example 2
state = ['Gujarat', 'Maharashtra', 'Rajasthan']
capital = ['Gandhinagar', 'Mumbai', 'Jaipur']
print(zip(state, capital))
dict_using_comp = {key:value for (key, value) in zip(state, capital)}
print('**op2 -> ', dict_using_comp)

##### OUTPUT
**op1 ->  {1: 1, 3: 27, 5: 125, 7: 343}
<zip object at 0x000001A8702CB480>
**op2 ->  {'Gujarat': 'Gandhinagar', 'Maharashtra': 'Mumbai', 'Rajasthan': 'Jaipur'}
```

## Set Comprehensions
- Set comprehensions are pretty similar to list comprehensions. The only difference between them is that set comprehensions use curly brackets { }
- Syntax <br>
  `my_set = {<expression> for <item> in <iterable> if <condition>}`
```python
# example 1
input_list = [1, 2, 3, 4, 4, 5, 6, 6, 6, 7, 7]
set_using_comp = {var for var in input_list if var % 2 == 0}
print('**op1 -> ', set_using_comp)

##### OUTPUT
**op1 ->  {2, 4, 6}
```

## Generator Comprehensions
- Generator Comprehensions are very **similar to list comprehensions**. 
- One difference between them is that generator comprehensions use **circular brackets** whereas list comprehensions use square brackets. 
- The major difference between them is that generators **don’t allocate memory for the whole list**. Instead, they generate each value one by one which is why they are **memory efficient**.
- it is usually generated from a function with `yield` keyword but in comprehention we don't need the yield keyword
- Syntax <br>
  `my_gen = (<expression> for <item> in <iterable> if <condition>)`

```python
# not using comprehension
def even_generator(numbers):
    for n in numbers:
        if n % 2 == 0:
            yield int(n/2)
eg = even_generator(range(10))
print('**op1 -> ', eg)
print('**op2 -> ')
print(next(eg))
print(next(eg))
print(next(eg))
print(next(eg))
print(next(eg)) # after this no more left, StopIteration error will come

# using comprehension
eg = (int(number/2) for number in range(10) if number % 2 == 0)
print('**op3 -> ')
print(next(eg))
print(next(eg))
print(next(eg))
print(next(eg))
print(next(eg)) # after this no more left, StopIteration error will come

print('**op4 -> ') # another way to check op
# can't reuse eg from previous line since we already printed all op values from it, so had to recreate the eg list
eg = (int(number/2) for number in range(10) if number % 2 == 0)
for var in eg:
    print(var, end = ' ')

###### OUTPUT
**op1 ->  <generator object even_generator at 0x000001A870BF8660>
**op2 -> 
0
1
2
3
4
**op3 -> 
0
1
2
3
4
**op4 -> 
0 1 2 3 4 
```

# Functions
- A function is a block of code which only runs when it is called
- A **parameter** is the variable listed inside the parentheses in the function definition.
- An **argument** is the value that is sent to the function when it is called.

```python
# Creating a Function
def my_function():
  print("Hello from a function")

# Calling a Function
print('\n**op1 -> ')
my_function()

# Number of Arguments
print('\n**op2 -> ')
def my_function(fname, lname):
  print(fname + " " + lname)
my_function("Emil", "Refsnes")

# Arbitrary Arguments
# If you do not know how many arguments that will be passed into your function, add a * before the parameter name
print('\n**op3 -> ')
def my_function(*kids):
  print("The youngest child is " + kids[2])
my_function("Emil", "Tobias", "Linus")

# Keyword Arguments
# You can also send arguments with the key = value syntax. order of the arguments does not matter.
print('\n**op4 -> ')
def my_function(child3, child2, child1):
  print("The youngest child is " + child3)
my_function(child1 = "Emil", child2 = "Tobias", child3 = "Linus")

# Arbitrary Keyword Arguments, **kwargs
# If you do not know how many keyword arguments that will be passed into your function, add two asterisk: ** before the parameter name
print('\n**op5 -> ')
def my_function(**kid):
  print("His last name is " + kid["lname"])
my_function(fname = "Tobias", lname = "Refsnes")

# Default Parameter Value
# If we call the function without argument, it uses the default value:
print('\n**op6 -> ')
def my_function(country = "Norway"):
  print("I am from " + country)
my_function("Sweden")
my_function("India")
my_function()

###### OUTPUT
**op1 -> 
Hello from a function

**op2 -> 
Emil Refsnes

**op3 -> 
The youngest child is Linus

**op4 -> 
The youngest child is Linus

**op5 -> 
His last name is Refsnes

**op6 -> 
I am from Sweden
I am from India
I am from Norway
```

## Recursion
- Recursion means a defined function can call itself
- The developer should be very careful with recursion as it can be quite easy to slip into writing a function which never terminates, or one that uses excess amounts of memory or processor power. However, when written correctly recursion can be a very efficient and mathematically-elegant approach to programming.

```python
def tri_recursion(k):
  if(k > 0):
    result = k + tri_recursion(k - 1)
    print(result)
  else:
    result = 0
  return result

print("\n\nRecursion Example Results")
tri_recursion(6)

##### OUTPUT
Recursion Example Results
1
3
6
10
15
21
```

- When dealing with recursive functions, each recursive call has its own execution context, so to maintain state during recursion you have to either:
1) Thread the state through each recursive call so that the current state is part of the current call’s execution context
2) Keep the state in global scope
   
```python
## ----- way 1
def sum_recursive(current_number, accumulated_sum):
    # Base case
    # Return the final state
    if current_number == 11:
        return accumulated_sum

    # Recursive case
    # Thread the state through the recursive call
    else:
        return sum_recursive(current_number + 1, accumulated_sum + current_number)

## ----- way 2
# Global mutable state
current_number = 1
accumulated_sum = 0


def sum_recursive():
    global current_number
    global accumulated_sum
    # Base case
    if current_number == 11:
        return accumulated_sum
    # Recursive case
    else:
        accumulated_sum = accumulated_sum + current_number
        current_number = current_number + 1
        return sum_recursive()
```

# Modules
- A Python module is a file containing Python **definitions and statements**. 
- A module can define **functions, classes, and variables**. 
- A module can also include **runnable code**. 
- Grouping related code into a module makes the code **easier to understand and use**.

```python
# ----- Create a Module
# Save this code in a file named mymodule.py
def greeting(name):
  print("Hello, " + name)

# ------ Use a Module
# Note: When using a function from a module, use the syntax: module_name.function_name.
import mymodule
mymodule.greeting("Jonathan")

# ------ Variables in Module
# Save this code in the file mymodule.py
person1 = {
  "name": "John",
  "age": 36,
  "country": "Norway"
}

# Import the module named mymodule, and access the person1 dictionary:
import mymodule
a = mymodule.person1["age"]
print(a)

# ------ Naming a Module
# You can name the module file whatever you like, but it must have the file extension .py

# ------ Re-naming a Module
# Create an alias for mymodule called mx:
import mymodule as mx
a = mx.person1["age"]
print(a)

# ------ Built-in Modules
# There are several built-in modules in Python, which you can import whenever you like.
import platform
x = platform.system()
print(x)

# ------- Using the dir() Function
# There is a built-in function to list all the function names (or variable names) in a module. The dir() function:
# Note: The dir() function can be used on all modules, also the ones you create yourself.
import platform
x = dir(platform)
print(x)
    
# ------- Import From Module
# You can choose to import only parts from a module, by using the from keyword.
# Note: When importing using the from keyword, do not use the module name when referring to elements in the module. Example: person1["age"], not mymodule.person1["age"]
from mymodule import person1
print (person1["age"])
```

# Namespaces and Scope
- A **namespace** determines which identifiers (e.g. variables, functions, classes) are available for use, and a **scope** defines where — in your written code — a namespace can be accessed.
- For more info with examples and proper examples refer to this [doc](./Utils/Mastering_Python_Namespaces_and_Scopes.pdf)

<br>

# File handling
- The open() function takes two parameters; *filename*, and *mode*
- There are four different methods (modes) for opening a file:
```
  1) "r" - Read - Default value. Opens a file for reading, error if the file does not exist
  2) "a" - Append - Opens a file for appending, creates the file if it does not exist
  3) "w" - Write - Opens a file for writing, creates the file if it does not exist
  4) "x" - Create - Creates the specified file, returns an error if the file exists
```
- In addition you can specify if the file should be handled as binary or text mode
```
  1) "t" - Text - Default value. Text mode
  2) "b" - Binary - Binary mode (e.g. images)
```

## Read Files

```python
# open a file
f = open("demofile.txt")

# The code above is the same as
f = open("demofile.txt", "rt")

# Note: Make sure the file exists, or else you will get an error.

# ------- demofile.txt ---------

# Hello! Welcome to demofile.txt
# This file is for testing purposes.
# Good Luck!

# ------------------------------

# Open a File on the Server
# The open() function returns a file object, which has a read() method for reading the content of the file:
f = open("demofile.txt", "r")
print(f.read()) # will print the file content

# Read Only Parts of the File
# By default the read() method returns the whole text, but you can also specify how many characters you want to return:
f = open("demofile.txt", "r")
print(f.read(5)) # --> Hello

# Read Lines
# Read one line of the file:
f = open("demofile.txt", "r")
print(f.readline()) # -> Hello! Welcome to demofile.txt

# By calling readline() two times, you can read the two first lines:
f = open("demofile.txt", "r")
print(f.readline()) # -> Hello! Welcome to demofile.txt
print(f.readline()) # -> This file is for testing purposes.

# By looping through the lines of the file, you can read the whole file, line by line:
f = open("demofile.txt", "r")
for x in f:
  print(x)

# Close Files
f = open("demofile.txt", "r")
print(f.readline())
f.close()

# Note: You should always close your files, in some cases, due to buffering, changes made to a file may not show until you close the file.

```

## Write/Create Files
- To write to an existing file, you must add a parameter to the open() function:
```
"a" - Append - will append to the end of the file
"w" - Write - will overwrite any existing content
```
- To create a new file in Python, use the open() method, with one of the following parameters:

```
"x" - Create - will create a file, returns an error if the file exist
"a" - Append - will create a file if the specified file does not exist
"w" - Write - will create a file if the specified file does not exist
```

```python
# Write to an Existing File
# Open the file "demofile2.txt" and append content to the file:
f = open("demofile2.txt", "a")
f.write("Now the file has more content!")
f.close()

# Open the file "demofile3.txt" and overwrite the content:
# Note: the "w" method will overwrite the entire file.
f = open("demofile3.txt", "w")
f.write("Woops! I have deleted the content!")
f.close()

# Create a file called "myfile.txt":
f = open("myfile.txt", "x")

# Create a new file if it does not exist:
f = open("myfile.txt", "w")
```

## Delete File

```python
# To delete a file, you must import the OS module, and run its os.remove() function:
import os
os.remove("demofile.txt")

# Check if File exist
# To avoid getting an error, you might want to check if the file exists before you try to delete it:
import os
if os.path.exists("demofile.txt"):
  os.remove("demofile.txt")
else:
  print("The file does not exist")

# Delete Folder
# To delete an entire folder, use the os.rmdir() method:
# Note: You can only remove empty folders.
import os
os.rmdir("myfolder")
```

# OOPs bullet points
- In detail explaination of oops is in this location -> ./Utils/OOPs
- A **class** is a blueprint for the object. To create an object we require a model or plan or blueprint which is nothing but class.
- An **object** is an instance of a class. It is a collection of attributes (variables) and methods. We use the object of a class to perform actions.
- A **constructor** is a special method used to create and initialize an object of a class. This method is defined in the class.
- In Python, Object creation is divided into two parts in **Object Creation** and **Object initialization**
  - Internally, the `__new__` is the method that creates the object
  - And, using the `__init__()` method we can implement constructor to initialize the object.
- In Python, we have the following **three types of constructors** - *Default Constructor, Non-parametrized constructor, Parameterized constructor*
- **Constructor overloading** is a concept of having more than one constructor with a different parameters list in such a way so that each constructor can perform different tasks. *Python does not support constructor overloading*. If we define multiple constructors then, the interpreter will considers only the last constructor and throws an error if the sequence of the arguments doesn’t match as per the last constructor.
- **Constructor chaining** is the process of calling one constructor from another constructor. Using the `super()` method we can invoke the parent class constructor from a child class. Example : `super().__init__(engine, max_speed)`
- The `__init__()` is **required to return None**. We can not return something else. If we try to return a non-None value from the `__init__()` method, it will raise TypeError.
- **Destructor** gets called in the following two cases : When an object goes out of scope or the reference counter of the object reaches 0.
- The magic method `__del__()` is used as the destructor in Python. The `__del__()` method will be implicitly invoked when all references to the object have been deleted, i.e., is when an object is eligible for the garbage collector. This method is also called a **finalizer** or (improperly) a destructor.
- Note: The __del__() method arguments are optional. We can define a destructor with any number of arguments.
- The **destructor will not invoke** when we delete object reference. It will only invoke when all references to the objects get deleted.
- In Python, if any **exception occurs in the init method** while initializing the object, the method `del` gets called. But actually, an object is not created successfully, and resources are not allocated to it even though the object was never initialized correctly, the del method will try to empty all the resources and, in turn, may lead to another exception.
- In Python, **Method Resolution Order(MRO)** is the order by which Python looks for a method or attribute. This order is also called the **Linearization** of a class. First, it searches in the current parent class if not available, then searches in the parents class specified while inheriting (that is **left to right**). We can get the MRO of a class by using either the `mro` attribute or the `mro()` method.
- Instance variables are not shared by objects. Every object has its **own copy** of the instance attribute. In Python, to work with an instance variable and method, we use the `self` keyword. We use a constructor to define and initialize the instance variables. Use the `__dict__` function of an object to get all instance variables along with their value.
- If we use instance variables inside a method, such methods are called **instance methods**. It must have a self parameter to refer to the current object. By Using `self.__class__` attribute we can access the class attributes and change the class state. Therefore **instance method gives us control of changing the object as well as the class state**. Instance variables can be created in any method not just init method. We can use `MethodType()` function to add a method at runtime to that particular instance. Example:
```python
# create new method
def welcome(self):
    print("Hello", self.name, "Welcome to Class IX")

# create object
s1 = Student("Jessa", 15)

# Add instance method to object
s1.welcome = types.MethodType(welcome, s1)

# call newly added method
s1.welcome()
```
- If the value of a variable is not varied from object to object, such types of variables are called **class variables** or **static variables**. A class variable is declared inside of class, but outside of any instance method or `__init__()` method. It is **best practice to use a class name to change the value of a class variable**. Because if we try to change the class variable’s value by using an object, a new instance variable is created for that particular object, which shadows the class variables.
- **Class methods** are methods that are called on the class itself, not on a specific object instance. Therefore, it belongs to a class level, and all class instances share a class method.

# Iterators

- **Iterators** are methods that iterate collections like lists, tuples etc.
- Using iterator method, we can loop through an object and return its elements
- Technically, **iterator object** should implement two special methods, `__iter()__` and `__next()__`, collectively known as **iterator protocol**

## Iterating through an iterator

```python
# define a list
my_list = [4, 7, 0]

# create an iterator from the list
iterator = iter(my_list)

# get the first element of the iterator
print(next(iterator))  # prints 4

# get the second element of the iterator
print(next(iterator))  # prints 7

# get the third element of the iterator
print(next(iterator))  # prints 0

# get fourth element
print(next(iterator))  # throws "StopIteration" Error

###### OUTPUT
4
7
0
---------------------------------------------------------------------------
StopIteration                             Traceback (most recent call last)
Input In [2], in <module>
     13 # get the third element of the iterator
     14 print(next(iterator))  # prints 0
---> 15 print(next(iterator))

StopIteration: 
```

## Itearting through an iterator using a for loop

```python
# define a list
my_list = [4, 7, 0]

# create an iterator from the list
iterator = iter(my_list)

for element in iterator:
    print(element)

####### OUTPUT
4
7
0
```

## Building custom iterators

- For building custom iterators, we just have to implement `__iter()__` and `__next()__` methods.
- `__iter__()` returns the iterator object itself. If required, some initialization can be performed.
- `__next__()` must return the next item in the sequence. On reaching the end, and in subsequent calls, it must raise `StopIteration`.
- Let's see an example that will give us the next power of 2 in each iteration. Power exponent starts from zero up to a user set number,
```python
class PowTwo:
    '''class to get powers of two upto user set number'''
    def __init__(self, max=0):
        self.max = max
        
    def __iter__(self):
        self.n = 0
        return self
    
    def __next__(self):
        if self.n <= self.max:
            result = 2 ** self.n
            self.n += 1
            return result
        else:
            raise StopIteration
            
obj = PowTwo(2)

i = iter(obj)

print(next(i))
print(next(i))
print(next(i))
print(next(i))

######## OUTPUT
1
2
4
---------------------------------------------------------------------------
StopIteration                             Traceback (most recent call last)
Input In [11], in <module>
     23 print(next(i))
     24 print(next(i))
---> 25 print(next(i))

Input In [11], in PowTwo.__next__(self)
     14     return result
     15 else:
---> 16     raise StopIteration

StopIteration: 
```

## Infinite Iterators

- An infinite iterator will continue to produce elements indefinitely.
- Here is an example of how to create an infinite iterator in Python using the `count()` function from the `itertools` module,

```python
from itertools import count

# create an infinite iterator that starts at 1 and increments by 1 each time
infinite_iterator = count(1)

# print the first 5 elements of the infinite iterator
for i in range(5):
    print(next(infinite_iterator))

####### OUTPUT
1
2
3
4
5
```

# Generators

- A generator is a function that returns an iterator that produces a sequence of values when iterated over.

## Create Python Generator

- Like any other normal function, we can define a generator function using the `def` keyword, but instead of the `return` statement we use the `yield` statement.

```python
def generator_name(arg):
    # statements
    yield something
```

- Here, the `yield` keyword is used to produce a value from the generator.
- When the generator function is called, it does not execute the function body immediately. Instead, it returns a generator object that can be iterated over to produce the values.
- Example,
```python
def my_generator(n):

    # initialize counter
    value = 0

    # loop until counter is less than n
    while value < n:

        # produce the current value of the counter
        yield value

        # increment the counter
        value += 1

# iterate over the generator object produced by my_generator
for value in my_generator(3):

    # print each value produced by generator
    print(value)

###### OUTPUT
0
1
2
```

- In the above example, the `my_generator()` generator function takes an integer n as an argument and produces a sequence of numbers from 0 to n-1.
- The yield keyword is used to produce a value from the generator and pause the generator function's execution until the next value is requested.
- We can also create a generator object from the generator function by calling the function like we would any other function as,

```python
generator = my_range(3)
print(next(generator))  # 0
print(next(generator))  # 1
print(next(generator))  # 2
```

## Generator Expression

- A generator expression is a concise way to create a generator object.
- Generator expression syntax -> `(expression for item in iterable)`
- Here, `expression` is a value that will be returned for each item in the `iterable`.
- Example,
```python
# create the generator object
squares_generator = (i * i for i in range(5))

# iterate over the generator and print the values
for i in squares_generator:
    print(i)

###### OUTPUT
0
1
4
9
16
```

## Use of Python Generators

1) **Easy to Implement** - Generators can be implemented in a clear and concise way as compared to their iterator class counterpart. Lets implement the power of 2 in generator
```python
def PowTwoGen(max=0):
    n = 0
    while n < max:
        yield 2 ** n
        n += 1
```
2) **Memory Efficient** - A normal function to return a sequence will create the entire sequence in memory before returning the result. This is an overkill, if the number of items in the sequence is very large. Generator implementation of such sequences is memory friendly and is preferred since it only produces one item at a time.
3) **Represent Infinite Stream** - Generators are excellent mediums to represent an infinite stream of data. Infinite streams cannot be stored in memory, and since generators produce only one item at a time, they can represent an infinite stream of data.
4) **Pipelining Generators** - Multiple generators can be used to pipeline a series of operations. Example :Suppose we have a generator that produces the numbers in the Fibonacci series. And we have another generator for squaring numbers.If we want to find out the sum of squares of numbers in the Fibonacci series, we can do it in the following way by pipelining the output of generator functions together.
```python
def fibonacci_numbers(nums):
    x, y = 0, 1
    for _ in range(nums):
        x, y = y, x+y
        yield x

def square(nums):
    for num in nums:
        yield num**2

print(sum(square(fibonacci_numbers(10))))

# Output: 4895
```

# Closures

- Python closure is a nested function that allows us to access variables of the outer function even after the outer function is closed.
- A closure is a nested function which has access to a free variable from an enclosing function that has finished its execution. Three characteristics of a Python closure are: it is a nested function, it has access to a free variable in outer scope, it is returned from the enclosing function.
- A **free variable** is a variable that is not bound in the local scope. In order for closures to work with immutable variables such as numbers and strings, we have to use the **nonlocal** keyword. The `nonlocal` keyword allows us to modify a variable with immutable type in the outer function scope.
- In the below example, we have created a function named `greet()` that returns a nested anonymous function. The returned function is now assigned to the `message` variable. At this point, the execution of the outer function is completed, so the `name` variable should be destroyed. However, when we call the anonymous function using `print(message())` we are able to access the `name` variable of the outer function. It's possible because the nested function now acts as a closure that closes the outer scope variable within its scope even after the outer function is executed.

```python
def greet():
    # variable defined outside the inner function
    name = "John"
    
    # return a nested anonymous function
    return lambda: "Hi " + name

# call the outer function
message = greet()

# call the inner function
print(message())

####### OUTPUT
Hi John
```

- Another example, here we can access the `num` variable of `calculate()` even after completing the outer function.

```python
def calculate():
    num = 1
    def inner_func():
        nonlocal num
        num += 2
        return num
    return inner_func

# call the outer function
odd = calculate()

# call the inner function
print(odd())
print(odd())
print(odd())

# call the outer function again
odd2 = calculate()
print(odd2())

##### OUTPUT
3
5
7
3
```

## When to use closures?
- Closures can be used to avoid global values and provide data hiding, and can be an elegant solution for simple cases with one or few methods.
- For larger cases with multiple attributes and methods, a class implementation may be more appropriate.

```python
def make_multiplier_of(n):
    def multiplier(x):
        return x * n
    return multiplier


# Multiplier of 3
times3 = make_multiplier_of(3)

# Multiplier of 5
times5 = make_multiplier_of(5)

# Output: 27
print(times3(9))

# Output: 15
print(times5(3))

# Output: 30
print(times5(times3(2)))
```

- NOTE : it is good to point out that the values that get enclosed in the closure function can be found out. All function objects have a `__closure__` attribute that returns a tuple of cell objects if it is a closure function. Referring to the example above, we know times3 and times5 are closure functions.

## Python closures vs classes

- Python closures can be an alternate solution to small classes.

```python
class Summer():

    def __init__(self):
        self.data = []

    def __call__(self, val):

        self.data.append(val)
        _sum = sum(self.data)

        return _sum

summer = Summer()

s = summer(1)
print(s)

s = summer(2)
print(s)

s = summer(3)
print(s)

s = summer(4)
print(s)

####### OUTPUT
1
3
6
10
```

```python
def make_summer():

    data = []

    def summer(val):
        # Because the data is a list which is mutable, we do not have to use the nonlocal keyword
        data.append(val)
        _sum = sum(data)

        return _sum

    return summer

summer = make_summer()

s = summer(1)
print(s)

s = summer(2)
print(s)

s = summer(3)
print(s)

s = summer(4)
print(s)

###### OUTPUT
1
3
6
10
```

# Decorators
- A decorator is a design pattern that allows you to modify the functionality of a function by wrapping it in another function.
- The outer function is called the decorator, which takes the original function as an argument and returns a modified version of it.
- Some prerequisites needed
```python
##### NESTED FUNCTION
def outer(x):
    def inner(y):
        return x + y
    return inner

add_five = outer(5)
result = add_five(6)
print(result)  # prints 11

# Output: 11

###### PASS FUNCTION AS ARGUMENT
def add(x, y):
    return x + y

def calculate(func, x, y):
    return func(x, y)

result = calculate(add, 4, 6)
print(result)  # prints 10

##### RETURN A FUNCTION AS A VALUE
def greeting(name):
    def hello():
        return "Hello, " + name + "!"
    return hello

greet = greeting("Atlantis")
print(greet())  # prints "Hello, Atlantis!"

# Output: Hello, Atlantis!
```

- Any object which implements the special __call__() method is termed callable. So, in the most basic sense, a decorator is a callable that returns a callable.
- Simple example,

```python
def make_pretty(func):
    # define the inner function 
    def inner():
        # add some additional behavior to decorated function
        print("I got decorated")

        # call original function
        func()
    # return the inner function
    return inner

# define ordinary function
def ordinary():
    print("I am ordinary")
    
# decorate the ordinary function
decorated_func = make_pretty(ordinary)

# call the decorated function
decorated_func()

###### OUTPUT
I got decorated
I am ordinary
```

## @ Symbol With Decorator
- Instead of assigning the function call to a variable, Python provides a much more elegant way to achieve this functionality using the `@` symbol
- Example : Here, the `ordinary()` function is decorated with the `make_pretty()` decorator using the `@make_pretty` syntax, which is equivalent to calling `ordinary = make_pretty(ordinary)`.

```python
def make_pretty(func):

    def inner():
        print("I got decorated")
        func()
    return inner

@make_pretty
def ordinary():
    print("I am ordinary")

ordinary()  

###### OUTPUT
I got decorated
I am ordinary
```

## Decorating Functions with Parameters
- The above decorator was simple and it only worked with functions that did not have any parameters. What if we had functions that took in parameters?
- Example : 

```python
def smart_divide(func):
    def inner(a, b):
        print("I am going to divide", a, "and", b)
        if b == 0:
            print("Whoops! cannot divide")
            return

        return func(a, b)
    return inner

@smart_divide
def divide(a, b):
    print(a/b)

divide(2,5)

divide(2,0)

####### OUTPUT
I am going to divide 2 and 5
0.4
I am going to divide 2 and 0
Whoops! cannot divide
```

## Chaining Decorators in Python
- To chain decorators in Python, we can apply multiple decorators to a single function by placing them one after the other, with the most inner decorator being applied first.

```python
def one(func):
    def inner():
        print('******************')
        func()
        print('******************')
    return inner
        
def two(func):
    def inner():
        print('$$$$$$$$$$$$$$$$$$')
        func()
        print('$$$$$$$$$$$$$$$$$$')
    return inner

@one
@two
def original():
    print('\nHello\n')

# the above four lines are equivalent to
# original = one(two(original))
    
original()

####### OUTPUT
******************
$$$$$$$$$$$$$$$$$$

Hello

$$$$$$$$$$$$$$$$$$
******************
```

# Property
- Python programming provides us with a built-in `@property` decorator which makes usage of getter and setters much easier in Object-Oriented Programming.

## Class Without Getters and Setters
- Here, the extra decimal places when converting into Fahrenheit is due to the Floating Point Arithmetic Error.
- So, whenever we assign or retrieve any object attribute like temperature as shown below, Python searches it in the object's built-in `__dict__` dictionary attribute as
```
print(human.__dict__) 
# Output: {'temperature': 37}
```
- Therefore, `human.temperature` internally becomes `human.__dict__['temperature']`.
```python
# Basic method of setting and getting attributes in Python
class Celsius:
    def __init__(self, temperature=0):
        self.temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32


# Create a new object
human = Celsius()

# Set the temperature
human.temperature = 37

# Get the temperature attribute
print(human.temperature)

# Get the to_fahrenheit method
print(human.to_fahrenheit())

##### OUTPUT
37
98.60000000000001
```

## Using Getters and Setters
- Suppose we want to extend the usability of the `Celsius` class defined above. We know that the temperature of any object cannot reach below -273.15 degrees Celsius. Lets implement that using getters and setters

```python
# Making Getters and Setter methods
class Celsius:
    def __init__(self, temperature=0):
        self.set_temperature(temperature)

    def to_fahrenheit(self):
        return (self.get_temperature() * 1.8) + 32

    # getter method
    def get_temperature(self):
        return self._temperature

    # setter method
    def set_temperature(self, value):
        if value < -273.15:
            raise ValueError("Temperature below -273.15 is not possible.")
        self._temperature = value


# Create a new object, set_temperature() internally called by __init__
human = Celsius(37)

# Get the temperature attribute via a getter
print(human.get_temperature())

# Get the to_fahrenheit method, get_temperature() called by the method itself
print(human.to_fahrenheit())

# new constraint implementation
human.set_temperature(-300)

# Get the to_fahreheit method
print(human.to_fahrenheit())

###### OUTPUT
37
98.60000000000001
Traceback (most recent call last):
  File "<string>", line 30, in <module>
  File "<string>", line 16, in set_temperature
ValueError: Temperature below -273.15 is not possible.
```

- However, the **bigger problem** with the above update is that all the programs that implemented our previous class have to modify their code from `obj.temperature` to `obj.get_temperature()` and all expressions like `obj.temperature = val` to `obj.set_temperature(val)`. Which can cause problems while dealing with hundreds of thousands of lines of codes. **This is where `@property` comes to rescue**.

## The property Class
- A pythonic way to deal with the above problem is to use the `property` class.
- `temperature = property(get_temperature, set_temperature)` Simply put, property attaches some code (`get_temperature` and `set_temperature`) to the member attribute accesses (`temperature`).

```python
# using property class
class Celsius:
    def __init__(self, temperature=0):
        self.temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    # getter
    def get_temperature(self):
        print("Getting value...")
        return self._temperature

    # setter
    def set_temperature(self, value):
        print("Setting value...")
        if value < -273.15:
            raise ValueError("Temperature below -273.15 is not possible")
        self._temperature = value

    # creating a property object
    temperature = property(get_temperature, set_temperature)


human = Celsius(37)
print('****')
print(human.temperature)
print('****')
print(human.to_fahrenheit())
print('****')
human.temperature = -300

###### OUTPUT
Setting value...
****
Getting value...
37
****
Getting value...
98.60000000000001
****
Setting value...
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
Input In [40], in <module>
     29 print(human.to_fahrenheit())
     30 print('****')
---> 31 human.temperature = -300

Input In [40], in Celsius.set_temperature(self, value)
     16 print("Setting value...")
     17 if value < -273.15:
---> 18     raise ValueError("Temperature below -273.15 is not possible")
     19 self._temperature = value

ValueError: Temperature below -273.15 is not possible
```

- As we can see, any code that retrieves the value of temperature will automatically call `get_temperature()` instead of a dictionary (`__dict__`) look-up.
- Similarly, any code that assigns a value to temperature will automatically call `set_temperature()`.
- **By using `property`, we can see that no modification is required in the implementation of the value constraint. Thus, our implementation is backward compatible.**
- NOTE: The actual temperature value is stored in the private `_temperature` variable. The `temperature` attribute is a property object which provides an interface to this private variable.

## The @property Decorator
- In Python, `property()` is a built-in function that creates and returns a property object. The syntax of this function is: `property(fget=None, fset=None, fdel=None, doc=None)`
- Here,<br>
`fget` is function to get value of the attribute<br>
`fset` is function to set value of the attribute<br>
`fdel` is function to delete the attribute<br>
`doc` is a string (like a comment)<br>
- As seen from the implementation, these function arguments are optional.
- This line:<br>
```temperature = property(get_temperature,set_temperature)```
- Can be broken down as:
```
# make empty property
temperature = property()

# assign fget
temperature = temperature.getter(get_temperature)

# assign fset
temperature = temperature.setter(set_temperature)
```

- We can even not define the names get_temperature and set_temperature as they are unnecessary and pollute the class namespace.
- For this, we reuse the temperature name while defining our getter and setter functions. Let's look at how to implement this as a decorator:

```python
# Using @property decorator
class Celsius:
    def __init__(self, temperature=0):
        self.temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    @property
    def temperature(self):
        print("Getting value...")
        return self._temperature

    @temperature.setter
    def temperature(self, value):
        print("Setting value...")
        if value < -273.15:
            raise ValueError("Temperature below -273 is not possible")
        self._temperature = value


# create an object
human = Celsius(37)
print('****')
print(human.temperature)
print('****')
print(human.to_fahrenheit())
print('****')
coldest_thing = Celsius(-300)

###### OUTPUT
Setting value...
****
Getting value...
37
****
Getting value...
98.60000000000001
****
Setting value...
---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
Input In [40], in <module>
     29 print(human.to_fahrenheit())
     30 print('****')
---> 31 human.temperature = -300

Input In [40], in Celsius.set_temperature(self, value)
     16 print("Setting value...")
     17 if value < -273.15:
---> 18     raise ValueError("Temperature below -273.15 is not possible")
     19 self._temperature = value

ValueError: Temperature below -273.15 is not possible
```

# Regular Expressions
- A Regular Expression (RegEx) is a sequence of characters that defines a search pattern.
- For example, `^a...s$` -> This code defines a RegEx pattern. The pattern is: any five letter string starting with `a` and ending with `s`.

<table border="0" cellpadding="1" cellspacing="1" summary="RegEx Match">
	<thead>
		<tr>
			<th scope="col">Expression</th>
			<th scope="col">String</th>
			<th scope="col">Matched?</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td rowspan="5"><code>^a...s$</code></td>
			<td><code>abs</code></td>
			<td>No match</td>
		</tr>
		<tr>
			<td><code>alias</code></td>
			<td>Match</td>
		</tr>
		<tr>
			<td><code>abyss</code></td>
			<td>Match</td>
		</tr>
		<tr>
			<td><code>Alias</code></td>
			<td>No match</td>
		</tr>
		<tr>
			<td><code>An abacus</code></td>
			<td>No match</td>
		</tr>
	</tbody>
</table>

- Python has a module named `re` to work with RegEx. Here's an example:
  
```python
import re

pattern = '^a...s$'
test_string = 'abyss'
# returns a match object if the search is successful. If not, it returns None
result = re.match(pattern, test_string)

if result:
  print("Search successful.")
else:
  print("Search unsuccessful.")

###### OUTPUT
Search successful.
```

**For more info refer [here](./Utils/RegEx.html)**

# Lambda/Anonymous Function
- In Python, a lambda function is a special type of function without the function name. 
- Example, `lambda : print('Hello World')`

## Lambda Function Declaration without arguments
- We use the `lambda` keyword instead of `def` to create a lambda function. Here's the syntax to declare the lambda function: `lambda argument(s) : expression`
- Here, `argument(s)` - any value passed to the lambda function, `expression` - expression is executed and returned
- Example,
```python
greet = lambda : print('Hello World')
greet()

##### OUTPUT
Hello World
```

## Lambda Function with an Argument

```python
# lambda that accepts one argument
greet_user = lambda name : print('Hey there,', name)

# lambda call
greet_user('Delilah')

####### OUTPUT
Hey there, Delilah
```

## How to use the lambda function with filter()?
- The filter() function in Python takes in a function and an iterable (lists, tuples, and strings) as arguments.
- The function is called with all the items in the list and a new list is returned which contains items for which the function evaluates to True.
- Let's see an example,
```python
# Program to filter out only the even items from a list
my_list = [1, 5, 4, 6, 8, 11, 3, 12]

new_list = list(filter(lambda x: (x%2 == 0) , my_list))

print(new_list)

# Output: [4, 6, 8, 12]
```

## How to use the lambda function with map()?
- The map() function in Python takes in a function and an iterable (lists, tuples, and strings) as arguments.
- The function is called with all the items in the list and a new list is returned which contains items returned by that function for each item.
- Let's see an example,
```python
# Program to double each item in a list using map()

my_list = [1, 5, 4, 6, 8, 11, 3, 12]

new_list = list(map(lambda x: x * 2 , my_list))

print(new_list)

# Output: [2, 10, 8, 12, 16, 22, 6, 24]
```







