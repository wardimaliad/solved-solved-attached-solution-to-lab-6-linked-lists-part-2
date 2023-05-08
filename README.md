Download Link: https://assignmentchef.com/product/solved-solved-attached-solution-to-lab-6-linked-lists-part-2
<br>
Learning outcomesBy the end of this lab, you will be able to:

Use both hand-drawn diagrams and the PyCharm debugger to trace and debug code that operates on linked lists.Implement methods that mutate linked lists.Task 0 – SetupDownload linked_list_v2.py and put it into your labs/lab6 folder.

Task 1 – Completely understanding linked list diagramsThis week you will write mutating methods, meaning the state of self when the method ends will not be the same as when it began.

Mutating methods are generally more difficult than non-mutating methods. This week, more than ever, it will help if you draw lots of pictures. It’s easiest if you draw abstract pictures like this:

Linked List diagram.

But only if you understand exactly what each component of the diagram represents: what variable or attribute it is, or what class it is an instance of.

Suppose we execute the following in the shell:

linky = LinkedList([6, 2, 18])print(linky)[6 – 2 – 18]Draw an abstract diagram of the linked list, using the same format as the in diagram above.

Now draw a detailed “memory model” diagram of the linked list. It should have

a box for each instance of a classan id value in the upper-left corner of the boxthe object’s type in the upper-right cornerthe attributes of the instance inside the boxHow many boxes are in your diagram?

Compare the two diagrams and find the correspondences between the components of each.

Write down the output that each line below would produce. Don’t just do this in your head. Write it down on the page where you are drawing your lovely diagrams.

type(linky._first.next)

type(linky)

type(linky._first.next.item)

Task 2 – Inspecting a linked list and tracing linked list code in the debuggerAdd to the start of the main block of linked_list_v2.py a single line of code to create a linked list with 4 nodes (you can pick the values to put into it) and another line to print the linked list.

Set a breakpoint at the print statement, and run the module in the debugger so that it will stop on that line.

Look in the debugger pane and find your variable that holds an instance of LinkedList. Click the arrow to open it up and see what it refers to. You’ll see its instance variable _first. (There is also an instance variable called _iter_node. You will use this when you get to the additional exercises.)

Click to open it and see what _first refers to: an instance of _Node.Continue opening nodes until the whole linked list is revealed all the way to the None at the end. How cool is that?

Now we’re going to use the debugger to trace a method as it runs. Click the red “X” to close the debugger pane so we can start again.

Create a breakpoint on the line you wrote that creates the LinkedList, and run the module again in the debugger so that it will stop on that line.

Use the “step into” button so that you can watch the program as it moves into our __init__ method.

Now step one line at a time through that method, using the step over button (so that you don’t have to follow execution into your __init__ method for _Node every time a new node is created.) Open up all the variables in the debugger pane so that it will show you what’s happening. At the same time, create and continually update a diagram in the abstract style shown above.

Make sure that you are completely comfortable with the correspondence between your diagram and what you see in the debugger.

Task 3 – Mutating linked list methodsNow you are really ready to write some mutating methods!

Read the docstrings and implement each of the following methods:

clearappend__setitem__extendAs you complete each one, run the doctests to check correctness on at least some basic cases.

Additional exercisesIf you finish the tasks above, here are some additional exercises that you should try.

Map

Learning goals:

Traverse and create a node-based linked listWork with an argument of function typeIn Python, functions are first-class objects, which means, among other things, that they can be passed as arguments to other functions. For example, the following function takes in two arguments: a function and an object, and tries to call the function on that object and see whether the result is True or not.

def try_function(f, arg):if f(arg):print(‘Success!’)else:print(‘Failure…’)

def positive(n):return n 0

try_function(positive, 10)‘Success!’try_function(positive, -4)‘Failure…’Implement the function map, which creates a new linked list created by applying a function to each item in the original list. Note that this does not change the original list.

Iterator

An iterator is an object that provides access to a sequence of items. In Python you iterate over a class that supports iteration using the for item in my_iterable_object syntax. Our goal is to make the LinkedList class support iteration, so that we can write code like:

lst = LinkedList([1, 2, 3])for item in lst:…To make a class support iteration, it must implement two magic methods: __iter__, which is called when the loop is first encountered to create an iterable object, and __next__, which is called at each loop iteration to get the next item to use in the loop. __next__ raises a StopIteration exception if there are no more items; so it turns out that for loops are actually implemented using exceptions in Python!

Implement the __iter__ and the __next__ method for the LinkedList class. Look through the starter code for hints on how to do this.

Once you are done, go back and see if the new for syntax makes it easier to implement __contains__, count, and map for linked lists. Does the new syntax make delete_item easier to implement? Why or why not?