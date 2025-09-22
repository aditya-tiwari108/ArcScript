###############
Language Basics
###############

This section covers the basic building blocks of the ArcScript language.

Variables
=========
Variables are declared using a name followed by ``=`` and an expression.

**ArcScript:**

.. code-block:: text

    message = "Hello, World!"
    count = 100

**JavaScript Output:**

.. code-block:: javascript

    let message = "Hello, World!";
    let count = 100;

Printing to the Console
=======================
The ``print()`` function transpiles to ``console.log()`` in JavaScript. It can accept multiple arguments.

**ArcScript:**

.. code-block:: text

    user_name = "Alex"
    score = 95
    print("User:", user_name, "Score:", score)

**JavaScript Output:**

.. code-block:: javascript

    let user_name = "Alex";
    let score = 95;
    console.log("User:", user_name, "Score:", score);


Operators
=========
ArcScript supports standard arithmetic, comparison, and logical operators.

Arithmetic Operators
--------------------
Standard operators for calculations.

-   Addition: ``+``
-   Subtraction: ``-``
-   Multiplication: ``*``
-   Division: ``/``
-   Modulous: ``%``

Comparison Operators
--------------------
Used in conditional logic.

-   Equal: ``==``
-   Not Equal: ``!=``
-   Greater Than: ``>``
-   Less Than: ``<``
-   Greater Than or Equal: ``>=``
-   Less Than or Equal: ``<=``

Logical Operators
-----------------
ArcScript keywords are transpiled to their JavaScript equivalents.

-   ``and`` becomes ``&&``
-   ``or`` becomes ``||``
-   ``not`` becomes ``!``
-   ``is`` becomes ``===``
-   ``True`` becomes ``true``
-   ``False`` becomes ``false``

**ArcScript:**

.. code-block:: text

    is_active = True
    score = 80
    if score > 50 and is_active is True
        print("You can proceed.")

**JavaScript Output:**

.. code-block:: javascript

    let is_active = true;
    let score = 80;
    if (score > 50 && is_active === true) {
        console.log("You can proceed.");
    }
