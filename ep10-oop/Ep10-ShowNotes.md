# Episode 10: Python Classes and Object-Oriented Programming

[[Watch Episode 10](https://youtu.be/7wb2wUMrkkE)]

The process of using classes and objects is called object-oriented programming. Fun fact: Python is a (heavily) object-oriented programming language! 

Technically, you could be programming in Python without creating your own classes. Instead, you could just stick to writing regular functions. 

However, creating classes can be very useful in certain contexts when you have complicated objects and want to track their states. This is especially true in machine learning and deep learning contexts. For example, think of big neural networks and their associated weight parameters. Instead of manually passing these weight parameters through functions, it's much easier to attach the weights as so-called attributes to the neural network and its layers. But let's not get ahead of ourselves and talk about what Python classes are in general.




## Classes are Templates

In a nutshell, you can think of a class as a template that you can use to create new objects. If you like baking, the classic analogy is that the class is your cookie-cutter, and a cookie represents the associated cookie you create using this template. Note that stamping out new cookies does not affect the cookie cutter itself. Using the cookie-cutter, the original shapes of the cookies are all similar. However, you can manually tweak each cookie individually (e.g., put chocolate on it, sprinkle it, and so forth.)

For non-trivial code projects, classes are a great way to organize and reuse your code!

## Python Class Terminology 101

Instead of just recapping the examples we discussed in [[Episode 10](https://youtu.be/7wb2wUMrkkE)], this shownotes article lists some of the core concepts and terminology when learning about and working with Python classes. We will keep it concise so you can use it as quick reference material.


So, as promised, here are some of the key terms and concepts that are helpful:

- functions
- variables
- classes
- methods
- objects
- attributes

Let's briefly go over some examples to define what those are.

### Functions

You are probably already familiar with regular Python functions. They allow us to define code for easy reuse:


[In]:

```python
def my_function(a, b):
    return f"{a} + {b} is {a + b}"

print(my_function(1, 2))
```

[Out]:

```
1 + 2 is 3
```

[In]:
```python
print(my_function(4, 5))
```

[Out]:

```
4 + 5 is 9
```

A function is essentially reusable code that we can execute upon calling the function.

### Variables

Variables are names or containers that we can use to store values so that we can reuse them later:



[In]:

```python
var1 = my_function(1, 2)
var2 = my_function(4, 5)

print(var2 + " & " + var1)
```

[Out]:

```
var2 + " & " + var1
```



### Classes

Now, somewhat similar to the idea behind functions, classes allow us to define reusable code. However, as we will see below, classes are a bit more "comprehensive."

### Methods

Classes come with methods, and we can think of methods as a Python function that is attached to the class:

```python
class MyClass:
    def __init__(self):
        print('__init__ was called')
        
    def my_computation(self):
        print('my_computation was called')
```

In the code example above, there are two methods: `__init__` and `my_computation`. 

The `__init__` method is a special-purpose method referred to as "constructor." It is executed when we initialize the class (more on that in the section on "Objects" below.)



### Objects

Objects are new instances that we create using a Python class (the class acts as a cookie cutter here). For instance, we can create a new object using the `MyClass` class we defined earlier as follows:

[In]:

```python
my_object = MyClass()
```

[Out]:

```
__init__ was called
```

As we can see above, the `__init__` method was automatically executed upon creating (constructing) the new object. Hence, it's called the "constructor" method. In contrast, we have to call other methods explicitely:

[In]:

```python
my_object.my_computation()
```

[Out]:

```
my_computation was called
```




### Attributes

Previously, we said that Python methods are analogous to Python functions. Howeverm the difference is that methods belong to a class (and its corresponding objects) whereas functions stand on their own. 

Similar to the relationship between functions on methods, we can think of "attributes" as variables attached to a class. In the following example, we define a new class with an attribute `some_attribute`. 

[In]:

```python
class MyClass:
    def __init__(self, value):
        print('__init__ was called')
        self.some_attribute = value
        
    def my_computation(self):
        print('my_computation was called')
        
        new_value = self.some_attribute * 2
        print(f'value times 2 is {new_value}')
        
my_object = MyClass(value=123)
```


[Out]:

```
__init__ was called
```

[In]:

```python
my_object.my_computation()
```

[Out]:

```
my_computation was called
value times 2 is 246
```


The `self` here is a convention indicating that an attribute belongs to the class (or object) so that we can refer to it in the class methods.







---




## Questions Or Suggestions?

If you have questions or suggestions, please don't hesitate to reach out to William ([@_willfalcon](https://twitter.com/_willfalcon)) and Sebastian ([@rasbt](https://twitter.com/rasbt)) on Twitter or join our [Slack Channel](https://pytorch-lightning.slack.com/archives/C03GS6MTCCQ). For more episodes, also check out the [Lightning Bits: Engineering for Researchers](http://pytorchlightning.ai/edu/engineering-class).

