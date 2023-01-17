# Introduction To Python
---
<br /><br />

## Python key features :
- General purpose language
- Interpreted
- Supports both object oriented and procedure oriented programming
- High level (easy for humans to understand)
- Memory efficient (variables with same value will point to the same memory location instead of having two copies)

##
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
---
<br>

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
---
<br>

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

something






















