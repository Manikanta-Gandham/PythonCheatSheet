
# Python strings
In Python, strings are immutable, meaning their values cannot be changed once they're created. For instance, if you have the string "Hello", attempting to modify a character directly, like __string[0] = 'J', will result in a XTypeError__. Instead, you create a new string with the desired changes. For example:

 ``` python
Copy code
original_string = "Hello"
new_string = "J" + original_string[1:]
```
In this example, the original string remains unchanged, and a new string is created. This design decision brings predictability, as the original string's value won't unexpectedly change. Additionally, strings' immutability allows them to be used as keys in dictionaries and elements in sets. While you can create new strings at will, the concept encourages efficient programming practices that minimize unintended side effects and optimize memory usage. It's about creating a new string, like this:

``` python
Copy code
string_list = list("Hello")
string_list[0] = 'J'
modified_string = ''.join(string_list)
```
This approach highlights the immutability concept, as the original string is not modified in place. Instead, a new string is created from a modified list. Overall, the immutability of strings in Python is a conceptual constraint promoting good programming practices rather than a strict technical limitation.




# Mutable and Immutable

Certainly! Here's a table summarizing some common mutable and immutable objects in Python:

``` Python
Mutable Objects	Examples
Lists	my_list = [1, 2, 3]
Dictionaries	my_dict = {'a': 1, 'b': 2}
Sets	my_set = {1, 2, 3}
Byte Arrays	my_bytes = bytearray(b'hello')

Immutable Objects Examples
Integers	x = 5
Floats	pi = 3.14159
Strings	s = "Hello, World!"
Tuples	my_tuple = (1, 2, 3)
Frozen Sets	my_set = frozenset([1, 2, 3])
Namedtuples	Point = namedtuple('Point', ['x', 'y'])<br>p = Point(x=1, y=2)
Enums	from enum import Enum<br>class Color(Enum):<br> RED = 1<br> GREEN = 2<br> BLUE = 3
Booleans	flag = True
```

This table provides a quick overview of common mutable and immutable objects in Python. Keep in mind that this is not an exhaustive list, and there are other mutable and immutable objects in the Python standard library and third-party libraries.

*when you pass immutable object as reference in python it will not be changed*
