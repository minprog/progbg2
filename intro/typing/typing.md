## Typing

In Python all values have a specific type. Python has various built-in types:

| type    | description                     | example                | mutability |
| ------- | ------------------------------- | ---------------------- | ---------- |
| `int`   | whole number                    | `5`, `-8`, `2*3`       | immutable  |
| `float` | floating point number           | `5.0`, `3.8`, `4/1`    | immutable  |
| `bool`  | boolean                         | `True`, `False`, `3>1` | immutable  |
| `str`   | string                          | `"hello"`, `'world'`   | immutable  |
| `list`  | list of same type               | `[1,2,3,4]`            | mutable    |
| `tuple` | groups possibly different types | `(1,2,'abc',True)`     | immutable  |

more types later... 

Python is dynamically-typed language, that means a type is associated
with a value and not with a variable (like in the C programming
langue). Because of this a variable can change type when you give it a
new value:

    >>> my_var = 42
    >>> print(  type(my_var) )
    <class 'int'>
    >>> my_var = 3>1
    >>> print( type(my_var) )
    <class 'bool'>
    >>> my_var = "hello world"
    >>> print( type(my_var) )
    <class 'str'>

When you use a value it is important to know its type
because expressions behave differently for different types:

    >>> my_var = 42
    >>> print( my_var + my_var )
    84
    >>> my_var = "hello"
    >>> print( my_var + my_var )
    hellohello

Sometimes it is unclear what type a value has, for example the value
your get from a function. In those cases you could try to:

    def some_function():
      return [ ('a',1), ('b',2), ('c',3) ]

    print( some_function() )               # print the value and deduce the type
    print( type(some_function())  )        # or print the type of the value
    if isinstance(some_function(), list):  # or test if the value has a specific type
       print("the type is a list")


## (im)mutable

Some types like 'int' are 'immutable', meaning that the value itself
can not mutate or change in place. Other types like 'list' are
'mutable', the value can mutate or change in place. The difference is
important, lets first look at an immutable type:

    >>> v1 = 111               # 'int': immutable type
    >>> v2 = v1                # v2 gets bound to the same value a v1
    >>> v1 += 222              # value can not mutate so v1 gets bound to a new value
    >>> print("v1: ", v1, "v2: ", v2, "   id(v1):", id(v1), "id(v2):", id(v2)  )
    v1:  333 v2:  111    id(v1): 139754131600176 id(v2): 10918016

The output is as expected, v1 is changed and v2 still has the intial
value of 111. For mutable types this is different:

    >>> v1 = [111]              # 'list': mutable type
    >>> v2 = v1                 # v2 gets bound to the same value a v1
    >>> v1.append(222)          # mutates the existing value, so also changes v2
    >>> print("v1: ", v1, "v2: ", v2, "   id(v1):", id(v1), "id(v2):", id(v2)  )
    v1:  [111, 222] v2:  [111, 222]    id(v1): 139754131779912 id(v2): 139754131779912

Surprise!, v2 now has the same value a v1 even though v1 is changed
after assignment 'v2 = v1'. This is because the assignment 'v2 = v1'
binds variable v2 to the same value v1 is bound to. They now share the
same value, no copy is made. This can also be seen by observing
'id(v1)' and 'id(v2)' are the same, they share the same
memory. Therefore a change in v1 will now also effect v2 and vice
versa.

Sometimes you don't want this and want 'v2' to have an independent
copy of the value of a mutable type. One way of doing this is to use
function deepcopy():

    >>> import copy              # requires module 'copy' 
    >>> v1 = [111]               # 'list': mutable type
    >>> v2 = copy.deepcopy(v1)   # deepcopy makes an independent copy
    >>> v1.append(222)           # changes v1, but doesn't change v2
    >>> print("v1: ", v1, "v2: ", v2, "   id(v1):", id(v1), "id(v2):", id(v2)  )
    v1:  [111, 222] v2:  [111]    id(v1): 139754131347912 id(v2): 139754131363720

Now v2 is an indepentent copy of the value of v1 and is not effected
by any change in v1. But keep in mind that copying large values (a
list with many thousands of elements) can be slow and more memory is
going to be needed, so only make an independent copy if you really
need one.
