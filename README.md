#Python Installation:
   1. Download Python from https://www.python.org/downloads/
   2. Installation - http://docs.python-guide.org/en/latest/starting/installation/
   3. Pycharm community edition download - https://www.jetbrains.com/pycharm/download/
   4. Anaconda Download - https://www.anaconda.com/download/
   5. Anaconda Installation - https://conda.io/docs/user-guide/install/index.html
   
#Compiler vs Interpreter
  1. Compiler and Interpreter are two different ways to execute a program written in a programming or scripting language.
  2. A compiler takes entire program and converts it into object code which is typically stored in a file. The object code is also
     refereed as binary code and can be directly executed by the machine after linking. 
	 
  3. An Interpreter directly executes instructions written in a programming or scripting language without previously converting them
     to an object code or machine code. Examples of interpreted languages are Perl, Python and Matlab.
	 
#Python	 
  1. Python is an interpreted, interactive, object-oriented programming language.  
  2. It incorporates modules, exceptions, dynamic typing, very high level dynamic data types, and classes.  
  3. Python combines remarkable power with very clear syntax.
  
#Static vs. dynamic:
   Static | dynamic
   ------ | -------
   In a statically typed language, every variable name is bound both | In a dynamically typed language, every variable name is (unless it is null) bound only to an object.
   
#Data types in Python
  1. Every value in Python has a datatype. Since everything is an object in Python programming, data types are actually classes and
    variables are instance (object) of these classes.
	  Ex . String, Number, List, Tupple, Set, Dictionary
  2. Conversion between data types possible.
  3. Strongly typed.
   
#"Hello world" Example:
   print print "Hello World"   [2.*]
   print(print "Hello World")  [3.*]
   
#Variable assignment
   1. a = 5
   2. a, b, c = 5, 8.2, "Hello"  [Multiple assignments]
   3. x = y = z = "same" [Multi Variable assignments]
   
#Numbers
  1.  >>> a = 3
      >>> type(a)
      <type 'int'>
  2. >>> a = 1+2j
     >>> print isinstance(a,complex)
	 True
	 
#String
  1. String is sequence of Unicode characters. We can use single quotes or double quotes to represent strings. Multi-line strings      
     can be denoted using triple quotes, ''' or """.

  >>> s = "This is a string"
  >>> s = '''a multiline
  
  2. slicing operator [ ] can be used with string. Strings are immutable.
  
     s = 'Hello world!'
#List:
   1. List is an ordered sequence of items. All the items in a list do not need to be of the same type.
      We can use the slicing operator [ ] on list.
   2. >>> a = [1, 2.2, 'python']
   3. Lists are mutable, meaning, value of elements of a list can be altered.
   4. >>> a = [1,2,3]
      >>> a[2]=4
      >>> a
      [1, 2, 4]
#Tuple
  1. Tuple is an ordered sequence of items same as list.The only difference is that tuples are immutable. Tuples once created cannot
     be modified.
  2. Tuples are used to write-protect data and are usually faster than list as it cannot change dynamically.
     >>> t = (5,'program', 1+3j)
  3. We can use the slicing operator [] to extract items but we cannot change its value.

#Dictionary
  1. Dictionary is an unordered collection of key-value pairs.
  2. >>> d = {1:'value','key':2}
     >>> type(d)
     <class 'dict'>

#Set
   1. Set is an unordered collection of unique items. 
      Items in a set are not ordered.
   2. >>> a = {1,2,2,3,3,3}
      >>> a
     {1, 2, 3}
  
#Conversion between data types
   1. >>> float(5)
      5.0
   2. >>> int(10.6)
      10
   3. >>> list('hello')
      ['h', 'e', 'l', 'l', 'o']
   4. >>> list((1, "ee", 2))
     [1, 'ee', 2]
   5. >>> dict([[1,2],[3,4]])
      {1: 2, 3: 4}
   6. >>> dict([(3,26),(4,44)])
      {3: 26, 4: 44}
   7. >>> set([1,2,3])
      {1, 2, 3}
   8. >>> tuple({5,6,7})
     (5, 6, 7)
	 
#if & elif & else
    if x < 0:
...     print('Negative')
... elif x == 0:
...     print('Zero')
... elif x == 1:
...     print('Single')
... else:
...     print('More')

#"for" or "while" Statements:
    words = ['cat', 'window', 'defenestrate']
    >>> for w in words:
        print w

#break and continue Statements, and else Clauses on Loops:
    >>> for n in range(2, 10):
...         for x in range(2, n):
...             if n % x == 0:
...                 print n
...                 break
...     else:
...         print n+' is a prime number'

   >>> for num in range(2, 10):
...        if num % 2 == 0:
...            print "Found an even number " +str(num)
...            continue
...        print "Found a number "+str(num)

#Defining Functions
    >>> def add(x):
    ...     return x * x
    ... 
    >>> add(5)
    25

#pass Statements
    >>> def initlog(*args):
...         pass   # Remember to implement
...
# Iterators & Generator

   class IterExample:
    def __init__(self, n):
        self.i = 0
        self.n = n

    def __iter__(self):
        return self

    def next(self):
        if self.i < self.n:
            i = self.i
            self.i += 1
            return i
        else:
            raise StopIteration()

   >>> for i in [1, 2, 3, 4]:
   ...     print i,
   ...
   1
   2
   3
   4
   
   
   >>> for k in {"x": 1, "y": 2}:
   ...     print k
   ...
   y
   x
   
   

   def Ex(n):
       i = 0
       while i < n:
           yield i
           i += 1

   >>> y = yrange(3)
   >>> y
   <generator object yrange at 0x401f30>
   >>> y.next()
   0
   >>> y.next()
   1
   >>> y.next()
   2
   >>> y.next()
   Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
   StopIteration
   
   1. When a generator function is called, it returns a generator object without even beginning execution of the function. When next method is called for the first time, the function starts executing until it reaches yield statement. The yielded value is returned by the next call.
  	 
#List Comprehensions
   >>> squares = []
   >>> for x in range(10):
   ...     squares.append(x**2)
   ...
   >>> squares
   
   squares = [x**2 for x in range(10)]
   
   >>> [(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]
   
   >>> combs = []
   >>> for x in [1,2,3]:
   ...     for y in [3,1,4]:
   ...         if x != y:
   ...             combs.append((x, y))
   ...
   >>> combs
   
#Buit In functions

  1. #Enumerate
  
    my_list = ['apple', 'banana', 'grapes', 'pear']
    for c, value in enumerate(my_list, 1):
       print c + ' : ' + value
	   
#Documentation Strings:
  1. multi-line docstring
  2. # for inline
  
#Coding Style
 1.PEP 8
