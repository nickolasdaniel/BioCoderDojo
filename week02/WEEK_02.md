# O PREZENTARE REALIZATA,....DE NICU MASONU' 666 A

# Numbers

Numbers are mainly of two types - integers and floats.
An examples of an integer is **2** which is just a whole number.
Examples of floating point numbers (or floats for short) are **3.23** and **52.3E-4** . The
*E* notation indicates powers of 10. In this case, *52.3E-4* means *52.3 * 10^-4^*.

**NOTE:** There is no separate long type. The int type can be an integer of
any size unlike C++ or other languages.

# Strings

A string is a sequence of **characters**. Strings are basically just a bunch of words.

## Single Quote
You can specify strings using single quotes such as **'Ana nu are mere. E saraca, din cauza crizei economice'** .
All white space i.e. spaces and tabs, within the quotes, are preserved as-is.
## Double Quote
Strings in double quotes work exactly the same way as strings in single quotes. An
example is **"Nici Relu nu sta mai bine, dar e putin mai norocos pentru ca are pomi in gradina"** .
## Triple Quotes
You can specify multi-line strings using triple quotes - ( """ or ''' ). You can use
single quotes and double quotes freely within the triple quotes. An example is:
```
'''Oh wow aparent pot sa scriu pe mai multe linii
Hehe, bengoasa treaba
Misto limbaju asta
Vand golf 4 
'''
```

Strings are **immutable**. This means that once you have created a string, you cannot change it. Although this
might seem like a bad thing, it really isn’t.

For example:

```Python
name_1 = "Costelian"
name_1[0] = 'K'
```

You cannot do that because it will raise this error:

```
Traceback (most recent call last):
  File "main.py", line 2, in <module>
    name_1[0] = 'T'
TypeError: 'str' object does not support item assignment
```
A possible solution to this would be:

```Python
name_1 = "Costelian"
name_2 = "K"+ name_1[1:]
print("name_1 = ", name_1, "and name_2 = ", name_2)
```
Output: ```name_1 =  Costelian and name_2 =  Kostelian```

To identify that they are different strings, check with the ```id()``` function:
```Python
name_1 = "Costelian"
name_2 = "K" + name_1[1:]
print("id of name_1 = ", id(name_1))
print("id of name_2 = ", id(name_2))
```

Ouput: 
```
id of name_1 =  140128875342232
id of name_2 =  140128875342848
```

To dig deeper, execute the following statements:
```Python
name_1 = "Costelian"
print("id of name_1 = ", id(name_1))

name_1 = "Kostelian"
print("id of name_1 afer initialing with new value = ", id(name_1))
```

Output:
```
id of name_1 =  139733963802976
id of name_1 afer initialing with new value =  139733963803592
```

As can be seen in the above example, when a string reference is *reinitialized with a new value*, it is *creating a new object* rather than o*verwriting the previous value*.

In Python, strings are made immutable so that programmers cannot alter the contents of the object (even by mistake). This avoids unnecessary bugs.

Some other immutable objects are integer, float, tuple, and bool.

## The format method

Sometimes we may want to construct strings from other information. This is where the
**format()** method is useful.

```Python
age = 20
name = 'Nicu beleaua'
print('{0} nu stie sa citeasca si are {1} de ani, cam cringe.'.format(name, age))
print('De ce asculta {0} manele?'.format(name))
```

Output:
```
Nicu beleaua nu stie sa citeasca si are 20 de ani, cam cringe.
De ce asculta Nicu beleaua manele?
```

The conversion to string would be done
automatically by the format method instead of the explicit conversion to strings needed
in this case.

## Escape Sequences

Suppose, you want to have a string which contains a single quote ( ' ), how will you
specify this string? For example, the string is *"What’s your name?"* . You cannot
specify *'What’s your name?'* because Python will be confused as to where the
string starts and ends. So, you will have to specify that this single quote does not
indicate the end of the string. This can be done with the help of what is called an **escape sequence**. You specify the single quote as \' : notice the backslash. Now, you can
specify the string as *'What\'s your name?'* .
Another way of specifying this specific string would be "What’s your name?" i.e.
using double quotes. Similarly, you have to use an escape sequence for using a double
quote itself in a double quoted string. Also, you have to indicate the backslash itself
using the escape sequence \\ .
What if you wanted to specify a two-line string? One way is to use a triple-quoted string
as shown previously or you can use an escape sequence for the newline character -
\n to indicate the start of a new line. An example is:

```
'This is the first line\nThis is the second line'
```

Another useful escape sequence to know is the tab: **\t**

One thing to note is that in a string, a single backslash at the end of the line indicates
that the string is continued in the next line, but no newline is added. For example:

```Python
s = "Nicu masonu 666 e cel mai tare. \
Tot ce am zis mai sus dar pe alta linie"
print(s)
```

This is equivalent to:

```Python
s = "Nicu masonu 666 e cel mai tare. Tot ce am zis mai sus dar pe alta linie." #nu chiar
print(s)
```

## String slicing

Subsets of strings can be taken using the slice operator ([ ] and [:] ) with indexes starting at 0 in the beginning of the string and working their way from -1 at the end.

For example:
```Python
str = 'Hello World!'

print(str)          # Prints complete string
print(str[0])       # Prints first character of the string
print(str[2:5])     # Prints characters starting from 3rd to 5th
print(str[2:])      # Prints string starting from 3rd character
print(str * 2)      # Prints string two times
print(str + "TEST") # Prints concatenated string
```
Output:
```
Hello World!
H
llo
llo World!
Hello World!Hello World!
Hello World!TEST
```


# Variable
Using just literal constants can soon become boring - we need some way of storing
any information and manipulate them as well. This is where variables come into the
picture. Variables are exactly what the name implies - their value can vary, i.e., you can
store anything using a variable. Variables are just parts of your computer’s memory
where you store some information. Unlike literal constants, you need some method of
accessing these variables and hence you give them names.

Variables are nothing but reserved **memory locations** to store values. This means that when you create a variable you **reserve some space in memory**.

Based on the data type of a variable, the interpreter **allocates memory** and decides what can be stored in the reserved memory. Therefore, by assigning different data types to variables, you can *store* integers, decimals or characters in these variables.

## Assigning Values to Variables
Python variables **do not need explicit declaration** to reserve memory space. The declaration happens automatically when you assign a value to a variable. The equal sign **(=)** is used to assign values to variables.

The operand to the left of the = operator is the name of the variable and the operand to the right of the = operator is the value stored in the variable. For example:
```Python
counter = 77777          # An integer assignment
kilometers   = 21.5       # A floating point
name    = "Nicolae Teslea"       # A string

print(counter)
print(miles)
print(name)
```

## Multiple assignment

Python allows you to assign a single value to several variables simultaneously. For example:
```Python
a = b = c = 1
```

Here, an integer object is created with the value 1, and all three variables are assigned to the same memory location. You can also assign multiple objects to multiple variables. For example:

```Python
a,b,c = 1,2,"Traian Basescu"
```

Here, two integer objects with values 1 and 2 are assigned to variables a and b respectively, and one string object with the value "Traian Basescu" is assigned to the variable c.


## Identifier naming

Variables are examples of identifiers. Identifiers are names given to identify something.
There are some rules you have to follow for naming identifiers:
- The first character of the identifier must be a letter of the alphabet (uppercase ASCII
or lowercase ASCII or Unicode character) or an underscore ( _ ).
- The rest of the identifier name can consist of letters (uppercase ASCII or lowercase
ASCII or Unicode character), underscores ( _ ) or digits (0-9).
- Identifier names are case-sensitive. For example, myname and myName are not
the same. Note the lowercase n in the former and the uppercase N in the latter.
- Examples of valid identifier names are i , name_2_3 . Examples of invalid identifier
names are 2things , this is spaced out , my-name and >a1b2_c3 .


# Data Types

## Standard Data Types
The data stored in memory can be of many types. For example, a person's age is stored as a numeric value and his or her address is stored as alphanumeric characters. Python has various standard data types that are used to define the operations possible on them and the storage method for each of them.

Python has five standard data types:
- Numbers
- String
- List
- Tuple
- Dictionary

## Lists

Lists are the most versatile of Python's compound data types. A list contains items separated by commas and enclosed within square brackets ([]). To some extent, lists are similar to arrays in C. One difference between them is that all the items belonging to a list can be of different data type.

The values stored in a list can be accessed using the slice operator ([ ] and [:]) with indexes starting at 0 in the beginning of the list and working their way to end -1. The plus (+) sign is the list concatenation operator, and the asterisk (*) is the repetition operator. For example
```Python
list = [ 'abcd', 786 , 2.23, 'john', 70.2 ]
tinylist = [123, 'john']

print(list)          # Prints complete list
print(list[0])       # Prints first element of the list
print(list[1:3])     # Prints elements starting from 2nd till 3rd 
print(list[2:])      # Prints elements starting from 3rd element
print(tinylist * 2)  # Prints list two times
print(list + tinylist) # Prints concatenated lists
```

Output:
```
['abcd', 786, 2.23, 'john', 70.2]
abcd
[786, 2.23]
[2.23, 'john', 70.2]
[123, 'john', 123, 'john']
['abcd', 786, 2.23, 'john', 70.2, 123, 'john']
```

## Tuples 

A tuple is another sequence data type that is similar to the list. A tuple consists of a number of values separated by commas. Unlike lists, however, tuples are enclosed within parentheses.

The main differences between lists and tuples are: Lists are enclosed in brackets ( [ ] ) and their elements and size can be changed, while tuples are enclosed in parentheses ( ( ) ) and cannot be updated (immutable). Tuples can be thought of as read-only lists. For example:

```Python
tuple = ( 'abcd', 786 , 2.23, 'john', 70.2  )
tinytuple = (123, 'john')

print(tuple)               # Prints the complete tuple
print(tuple[0])            # Prints first element of the tuple
print(tuple[1:3])          # Prints elements of the tuple starting from 2nd till 3rd 
print(tuple[2:])           # Prints elements of the tuple starting from 3rd element
print(tinytuple * 2)       # Prints the contents of the tuple twice
print(tuple + tinytuple)   # Prints concatenated tuples
```

Output:
```
('abcd', 786, 2.23, 'john', 70.2)
abcd
(786, 2.23)
(2.23, 'john', 70.2)
(123, 'john', 123, 'john')
('abcd', 786, 2.23, 'john', 70.2, 123, 'john')
```

## Dictionary
Python's dictionaries are kind of hash table type. They work like associative arrays or hashes and consist of key-value pairs. A dictionary key can be almost any Python type, but are usually numbers or strings. Values, on the other hand, can be any arbitrary Python object.

Dictionaries are enclosed by curly braces ({ }) and values can be assigned and accessed using square braces ([]). For example:

```Python
dict = {}
dict['one'] = "This is one"
dict[2]     = "This is two"

tinydict = {'name': 'john','code':6734, 'dept': 'sales'}


print(dict['one'])       # Prints value for 'one' key
print(dict[2])           # Prints value for 2 key
print(tinydict)          # Prints complete dictionary
print(tinydict.keys())   # Prints all the keys
print(tinydict.values()) # Prints all the values
```
Output:
```
This is one
This is two
{'dept': 'sales', 'code': 6734, 'name': 'john'}
['dept', 'code', 'name']
['sales', 6734, 'john']
```

## Data Type Conversion

Sometimes, you may need to perform conversions between the built-in types. To convert between types, you simply use the type name as a function.

There are several built-in functions to perform conversion from one data type to another. These functions return a new object representing the converted value.

Examples:
- int(x) - Converts x to int
- str(x) - Converts x to string
- float(x) - Converts x to a floating point number
- list(x) - Converts x to a list
- tupple(x) - Converts x to a tupple

# Logical and Physical Line

A physical line is what you see when you write the program. A logical line is what
Python sees as a single statement. Python implicitly assumes that each physical line
corresponds to a logical line.
An example of a logical line is a statement like ```print('hello world')``` - if this was on
a line by itself (as you see it in an editor), then this also corresponds to a physical line.
Implicitly, Python encourages the use of a single statement per line which makes code
more readable.

f you want to specify more than one logical line on a single physical line, then you have
to explicitly specify this using a semicolon ( ; ) which indicates the end of a logical line/
statement. For example:
```Python
i = 5
print(i)
```

is effectively same as

```Python
i = 5;;
print(i);;
```

which is also same as

```Python
i = 5; print(i);
```

# Identation

Whitespace is important in Python. Actually, **whitespace at the beginning of the line
is important**. This is called **indentation**. Leading whitespace (spaces and tabs) at the
beginning of the logical line is used to determine the indentation level of the logical line,
which in turn is used to determine the grouping of statements.
This means that statements which go together must have the same indentation. Each
such set of statements is called a **block**.

One thing you should remember is that wrong indentation can give rise to errors. For
example:

```Python
name = "Nicu"
# Error below! Notice a single space at the start of the line
 print('Eu sunt {}'.format(name) 
print('Ma n-auzi, ma cheama {}'.format(name) 
```
will raise error ```IndentationError: unexpected indent```

Use four spaces for indentation. This is the official Python language
recommendation. Good editors will automatically do this for you. Make sure you use a
consistent number of spaces for indentation, otherwise your program will show errors.

