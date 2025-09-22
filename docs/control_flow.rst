############
Control Flow
############

ArcScript uses indentation to define code blocks for control flow statements, similar to Python.

If-Else Statements
==================
Use ``if`` and ``else`` for conditional logic.

**ArcScript:**

.. code-block:: text

    age = 20
    if age >= 18
        print("Adult")
    else
        print("Minor")

**JavaScript Output:**

.. code-block:: javascript

    let age = 20;
    if (age >= 18) {
        console.log("Adult");
    }
    else {
        console.log("Minor");
    }

While Loops
===========
The ``while`` loop executes a block of code as long as a specified condition is true.

**ArcScript:**

.. code-block:: text

    counter = 0
    while counter < 3
        print(counter)
        counter = counter + 1

**JavaScript Output:**

.. code-block:: javascript

    let counter = 0;
    while (counter < 3) {
        console.log(counter);
        counter = counter + 1;
    }

For Loops
=========
ArcScript provides two types of ``for`` loops: one for iterating over collections and another for numeric ranges.

Looping over an Iterable
------------------------
This is equivalent to a ``for...of`` loop in JavaScript.

**ArcScript:**

.. code-block:: text

    items = grabAll ".item-class"
    for item in items
        print(item)

**JavaScript Output:**

.. code-block:: javascript

    let items = document.querySelectorAll(".item-class");
    for (let item of items) {
        console.log(item);
    }

Numeric Range Loops
-------------------
This is a powerful feature for creating traditional ``for`` loops with a simpler syntax.

**Form 1: ``for i in [end]``** (starts at 0, increments by 1)

.. code-block:: text

    for i in [5]
        print(i) # Prints 0, 1, 2, 3, 4

.. code-block:: javascript

    for (let i = 0; i < 5; i++) {
        console.log(i);
    }

**Form 2: ``for i in [start, end]``** (increments or decrements by 1)

.. code-block:: text

    # Counts up
    for i in [3, 7]
        print(i) # Prints 3, 4, 5, 6

    # Counts down
    for i in [10, 5]
        print(i) # Prints 10, 9, 8, 7, 6

.. code-block:: javascript

    // Counts up
    for (let i = 3; i < 7; i++) {
        console.log(i);
    }

    // Counts down
    for (let i = 10; i > 5; i--) {
        console.log(i);
    }

**Form 3: ``for i in [start, end, step]``** (increments or decrements by a step value)

.. code-block:: text

    # Counts down by 2
    for i in [10, 0, 2]
        print(i) # Prints 10, 8, 6, 4, 2

.. code-block:: javascript

    for (let i = 10; i > 0; i -= 2) {
        console.log(i);
    }
