#########
Functions
#########

Functions are reusable blocks of code. ArcScript simplifies function definition with an implicit return feature.

Defining Functions
==================
You can define a function using the ``def``, ``fn``, or ``function`` keywords.

**ArcScript:**

.. code-block:: text

    def add(a, b)
        a + b

    result = add(5, 10)
    print(result)

Implicit Return
===============
The **last expression** in a function's body is automatically returned. You do not need a ``return`` keyword.

**ArcScript:**

.. code-block:: text

    # This function calculates a value and returns it
    function calculate_price(base, tax_rate)
        tax = base * tax_rate
        base + tax # This value is returned

**JavaScript Output:**

.. code-block:: javascript

    function calculate_price(base, tax_rate) {
        let tax = base * tax_rate;
        return base + tax;
    }

Calling Functions
=================
Call functions using their name followed by parentheses with arguments.

**ArcScript:**

.. code-block:: text

    say_hello()
    total = add(15, 30)

**JavaScript Output:**

.. code-block:: javascript

    say_hello();
    total = add(15, 30);
