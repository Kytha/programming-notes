# Basic -

You can think of Python variables as symbolic names which stores data. In Python, variables do not need to be declared in advance. To create a variable, all we need to do is write an **assignment statement** like so:

```Python
a = "Hello World"
```

We can interpreted this as "a is assigned the value of 'Hello World'". Now a can be used in statements and expressions and it's value will be plugged in when we run our program.

```Python
print(a)
# Output: Hello World
```

We can change the value a refers to later if we want. This is called a reassignment statement.

```Python
a = "Bye World"
```

Python also allows chained assignments, so you can assign multiple variables at once:

```Python
a = b = c = "foo"
print(a+b+c)
# Output: foofoofoo
```

Or you can do something like this

```Python
a, b = "foo", "bar"
print(a + b)
# Output: foobar
```

A note on variable names. Officially, variable names in Python can be any length and can consist of uppercase and lowercase letters (A-Z, a-z), digits (0-9), and the underscore character (\_). An additional restriction is that, although a variable name can contain digits, the first character of a variable name cannot be a digit.

# Advanced - Under the hood

If we take a closer look at Python we can realize something rather strange. Python doesn't actually have variables! At least not in the conventional sense. A variable in other programming languages like C++ or Java is a name given to a memory address which can store a particular data type.

### C variable assignment

Let's take a look at C to gain some insights into variables. Let's say you had the following C code:

```C
int a = 50;
```

This line of code has several steps:

- Allocate enough memory for an integer
- Assign the value 50 to that memory location
- Indicate that x points to that memory location

A chart of the resulting memory layout would look like this:

| X        |       |
| -------- | ----- |
| Location | 0x6e3 |
| Value    | 50    |

If you then wrote the code

```C
a = 100;
```

The program would assign the value 100 to memory location of x, thereby overwriting the previous value of 50. Now the memory layout would look like this:

| X        |       |
| -------- | ----- |
| Location | 0x6e3 |
| Value    | 100   |

Notice how the location didn't change. So if you imagine memory as real estate, then x effectively "owns" that memory location. This is the classical sense of what "variable" means.

### It's all about the objects

So how is this different from Python? Well in Python **everything is an object**. Yes everything. And I can prove it. Take a look at the code below:

```Python
def foo():
    return

isinstance(1, object)
# True
isinstance("Hello World", object)
# True
isinstance(list(), object)
# True
isinstance(foo, object)
# True

```

You can run the code for yourself but you'll get the same results. So what does this mean for our memory layout? Well objects consist of 4 main components:

- Id
- Reference count
- Type
- Value

The id is a unique identifier given to every object created. No two objects will exist at the same time with the same id.

The reference count is used for memory management. It stores the number of current references to the object during runtime. When the reference count reaches 0 this indicates the object has reached it's **end of life** and has been orphaned. When this happens the object will soon be destroyed and it's allocated memory reclaimed. This process is called **garbage collection**. Python does this automatically but other languages, like C++, do not.

The type is used at the CPython level to ensure type safety. And finally, the value is the actual value associated with the object.

### Python variable assignment

So to get back to our question about the memory layout, let's redo our experiment but with Python code instead.

```Python
x = 50
```

Let's take a look at the steps for this line of Python code:

1. Create a PyObject
2. Set the typecode to integer for the PyObject
3. Set the value of the PyObject to 50
4. Create a name called x
5. Point x to the new object
6. Increase the object's reference count by 1

| PyObject  |         |
| --------- | ------- |
| Id        | D68B0   |
| Type      | integer |
| Value     | 50      |
| Ref Count | 1       |

x -> pyObject[D68B0] (x now points to the object with id D68B0)

So by running that line of code, we have created a new object and have assigned a name, x, to that object

When we do our reassignment,

```Python
x = 100
```

We now have a memory layout which looks like this

| PyObject  |         |
| --------- | ------- |
| Id        | D68B0   |
| Type      | integer |
| Value     | 50      |
| Ref Count | 0       |

| PyObject  |         |
| --------- | ------- |
| Id        | 3FFEA   |
| Type      | integer |
| Value     | 50      |
| Ref Count | 1       |

x -> pyObject[3FFEA] (x now points to the object with id 3FFEA)

Notice how when we reassign x, we don't overwrite the original value. Instead we create a completely new object with a new value. We then simply tell x to point to that object instead. The first object (D68B0) now has no references and will be disposed by the garbage collector.

So what's the big deal? Well if we consider the C style of variables "owning" memory real estate, we can consider the Python method as "renting" memory real estate. And as anyone who pays pays for housing knows, their are pros and cons to both.

Another important thing to note is that we **never** actually changed the original object. This is what is called an **immutable** object.

So in conclusion, we can think of conventional variables as assigning memory locations to names and Python's method as assigning names to objects. A more accurate word for variables in Python would be just names, since thats all they are!

Even though some of the distinctions between names and variables seem pedantic, fundamentally understanding these key terms expands your understanding of how Python handles variables.
