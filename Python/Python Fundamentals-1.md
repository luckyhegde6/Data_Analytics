 # Python Fundamentals and common used commands

 ## Using the Python Interpreter
 The Python interpreter is usually installed as /usr/local/bin/python3.10 on those machines where it is available; putting /usr/local/bin in your Unix shell’s search path makes it possible to start it by typing the command:

``` python3.10 ```

## Argument Passing
When known to the interpreter, the script name and additional arguments thereafter are turned into a list of strings and assigned to the argv variable in the `sys` module. You can access this list by executing `import sys`. The length of the list is at least one; when no script and no arguments are given, `sys.argv[0]` is an empty string. When the script name is given as '-' (meaning standard input), `sys.argv[0]` is set to '-'.

## Interactive Mode

When commands are read from a tty, the interpreter is said to be in interactive mode. In this mode it prompts for the next command with the primary prompt, usually three greater-than signs **(>>>)**; for continuation lines it prompts with the secondary prompt, by default three dots **(...)**.

## Python Indentation

Indentation refers to the spaces at the beginning of a code line.

Where in other programming languages the indentation in code is for readability only, the indentation in Python is very important.

Python uses indentation to indicate a block of code.

**Note:**
- **Python will give you an error if you skip the indentation**
- **You have to use the same number of spaces in the same block of code, otherwise Python will give you an error**

## Python Variables

- Python has no command for declaring a variable. A variable is created the moment you first assign a value to it.

```python
x = 5
y = "John"
```
- Variables do not need to be declared with any particular type, and can even change type after they have been set.

- If you want to specify the data type of a variable, this can be done with casting.
```python
x = str(3)    # |x will be '3'
y = int(3)    # y will be 3
z = float(3)  # z will be 3.0 
```

- You can get the data type of a variable with the `type()` function.

- **Variable names are case-sensitive.**
```python
a = 4
A = "Sally"
#A will not overwrite a 
```

Rules for Python variables:

   - A variable name must start with a letter or the underscore character
   - A variable name cannot start with a number
   - A variable name can only contain alpha-numeric characters and underscores (A-z, 0-9, and _ )
   - Variable names are case-sensitive (age, Age and AGE are three different variables)

- Many Values to Multiple Variables : **Python allows you to assign values to multiple variables in one line**
```python
x, y, z = "Orange", "Banana", "Cherry"
```
- One Value to Multiple Variables : **You can assign the same value to multiple variables in one line**
```python
x = y = z = "Orange"
```

- If you have a collection of values in a list, tuple etc. Python allows you to extract the values into variables. This is called unpacking.
```python
fruits = ["apple", "banana", "cherry"]
x, y, z = fruits
```

## Python - Global Variables

Variables that are created outside of a function (as in all of the examples above) are known as global variables.

Global variables can be used by everyone, both inside of functions and outside.

Note : Normally, when you create a variable inside a function, that variable is local, and can only be used inside that function.

**To create a global variable inside a function, you can use the `global` keyword. Also, use the `global` keyword if you want to change a global variable inside a function**

## Data Types

**Text Type:** 	`str`
**Numeric Types:** 	`int, float, complex`
**Sequence Types:** 	`list, tuple, range`
**Mapping Type:** 	`dict`
**Set Types:** 	`set, frozenset`
**Boolean Type:** `bool`
**Binary Types:** 	`bytes, bytearray, memoryview`

|Example|Data Type|
|:-----|:------|
|x = "Hello World"| 	str 	|
|x = 20 | 	int 	|
|x = 20.5 |	float 	|
|x = 1j |	complex 	|
|x = ["apple", "banana", "cherry"] |	list 	|
|x = ("apple", "banana", "cherry") |	tuple 	|
|x = range(6) |	range 	|
|x = {"name" : "John", "age" : 36} |	dict 	|
|x = {"apple", "banana", "cherry"} |	set 	|
|x = frozenset({"apple", "banana", "cherry"}) |	frozenset |	
|x = True |	bool 	|
|x = b"Hello" |	bytes 	|
|x = bytearray(5) |	bytearray |	
|x = memoryview(bytes(5)) |	memoryview |

### Numbers
- The integer numbers (e.g. 2, 4, 20) have type **int**, the ones with a fractional part (e.g. 5.0, 1.6) have type **float**. 

- Division **(/)** always returns a float. To do floor division and get an integer result (discarding any fractional result) you can use the **//** operator; to calculate the remainder you can use **%**.

- With Python, it is possible to use the `**` operator to calculate powers

- The equal sign (=) is used to assign a value to a variable. Afterwards, no result is displayed before the next interactive prompt

- If a variable is not **“defined”** (assigned a value), trying to use it will give you a `Name error`

- In addition to int and float, Python supports other types of numbers, such as `Decimal` and `Fraction`. Python also has built-in support for complex numbers, and uses the `j` or `J` suffix to indicate the imaginary part (e.g. `3+5j`).

### Strings

- Python can also manipulate strings, which can be expressed in several ways. They can be enclosed in single quotes **('...')** or double quotes **("...")** with the same result.

- If you don’t want characters prefaced by `\` to be interpreted as special characters, you can use raw strings by adding an r before the first quote for e.g 

```python
print(r'C:\some\name')  # note the r before the quote
#C:\some\name 

```
- String literals can span multiple lines. One way is using triple-quotes: """...""" or '''...'''. End of lines are automatically included in the string, but it’s possible to prevent this by adding a \ at the end of the line. The following example:
```python
print("""\
Usage: thingy [OPTIONS]
     -h                        Display this usage message
     -H hostname               Hostname to connect to
""")

```

- Strings can be concatenated (glued together) with the `+` operator, and repeated with `*`

- If you want to concatenate variables or a variable and a literal, use `+`.

- Strings can be indexed (subscripted), with the first character having index **0**. There is no separate character type; a character is simply a string of size one. Indices may also be negative numbers, to start counting from the right. **Note that since -0 is the same as 0, negative indices start from -1**.

- Slicing is also supported. While indexing is used to obtain individual characters, slicing allows you to obtain substring `word[0:2]  # characters from position 0 (included) to 2 (excluded)`

Slice indices have useful defaults; an omitted first index defaults to zero, an omitted second index defaults to the size of the string being sliced. 
```python
>>> word[:2]   # character from the beginning to position 2 (excluded)
'Py'
>>> word[4:]   # characters from position 4 (included) to the end
'on'
>>> word[-2:]  # characters from the second-last (included) to the end
'on'
```
- One way to remember how slices work is to think of the indices as pointing between characters, with the left edge of the first character numbered 0. Then the right edge of the last character of a string of n characters has index n, for example:
```
 +---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
```

- **Python strings cannot be changed — they are immutable. Therefore, assigning to an indexed position in the string results in an error**

- The built-in function `len()` returns the length of a string

- **For Str method visit -  https://docs.python.org/3/library/stdtypes.html#string-methods**

### Sequence Types — list, tuple, range

- Python knows a number of compound data types, used to group together other values. The most versatile is the list, which can be written as a list of comma-separated values (items) between square brackets. Lists might contain items of different types, but usually the items all have the same type

- All slice operations return a new list containing the requested elements. This means that the following slice returns a shallow copy of the list

- Unlike strings, which are immutable, lists are a mutable type, i.e. it is possible to change their content
**You can also add new items at the end of the list, by using the `append()` method.**
Assignment to slices is also possible, and this can even change the size of the list or clear it entirely.



- **For more refer : https://docs.python.org/3/library/stdtypes.html#sequence-types-list-tuple-range**



