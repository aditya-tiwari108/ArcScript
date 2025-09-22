################
DOM Manipulation
################

ArcScript provides a simple and powerful syntax for interacting with the Document Object Model (DOM).

Selecting Elements
==================
Use ``grab`` and ``grabAll`` to select elements from the page.

grab
----
Selects the first element that matches a CSS selector. Transpiles to ``document.querySelector()``.

**ArcScript:**
``main_container = grab "#main"``

**JavaScript Output:**
``let main_container = document.querySelector("#main");``

grabAll
-------
Selects all elements that match a CSS selector. Transpiles to ``document.querySelectorAll()``.

**ArcScript:**
``all_buttons = grabAll ".btn"``

**JavaScript Output:**
``let all_buttons = document.querySelectorAll(".btn");``

Creating and Placing Elements
=============================

create
------
Creates a new HTML element.

**ArcScript:**
``new_paragraph = create "p"``

**JavaScript Output:**
``let new_paragraph = document.createElement("p");``

append
------
Appends an element as the last child of a parent.

**ArcScript:**
``append new_paragraph to main_container``

**JavaScript Output:**
``main_container.appendChild(new_paragraph);``

insert
------
Inserts an element into a parent before a specified reference element.

**ArcScript:**
``insert new_element before old_element in main_container``

**JavaScript Output:**
``main_container.insertBefore(new_element, old_element);``


Accessing and Setting Properties
================================
You can easily get and set properties of DOM elements.

**Property Access Shortcuts:**
- ``html`` is a shortcut for ``innerHTML``.
- ``text`` is a shortcut for ``innerText``.

**ArcScript:**

.. code-block:: text

    # Get a property
    title_text = grab "h1" text

    # Set a property
    grab "#content" html = "<h2>New Section</h2>"

**JavaScript Output:**

.. code-block:: javascript

    let title_text = document.querySelector("h1").innerText;
    document.querySelector("#content").innerHTML = "<h2>New Section</h2>";

Styling Elements with Style Blocks
==================================
ArcScript provides a CSS-like syntax for applying multiple styles to an element.

**ArcScript:**

.. code-block:: text

    # Select an element and apply styles
    grab "#header"
        color = "'blue'"
        fontSize = "'24px'"
        backgroundColor = "'#f0f0f0'"

**JavaScript Output:**

.. code-block:: javascript

    document.querySelector("#header").style.color = 'blue';
    document.querySelector("#header").style.fontSize = '24px';
    document.querySelector("#header").style.backgroundColor = '#f0f0f0';


Event Listeners
===============
Attach event listeners with an indented block of code as the handler.

**ArcScript:**

.. code-block:: text

    button = grab "#my-button"

    # Define the event handler inline
    button click event
        print("Button was clicked!")
        button text = "Clicked!"

**JavaScript Output:**

.. code-block:: javascript

    let button = document.querySelector("#my-button");

    button.addEventListener('click', (event) => {
        console.log("Button was clicked!");
        button.innerText = "Clicked!";
    });

You can also use a pre-defined function as a handler:

**ArcScript:**

.. code-block:: text

    def handle_click()
        print("Handler function called")

    grab "#my-button" click handle_click

**JavaScript Output:**

.. code-block:: javascript

    function handle_click() {
        console.log("Handler function called");
    }
    document.querySelector("#my-button").addEventListener('click', handle_click);
