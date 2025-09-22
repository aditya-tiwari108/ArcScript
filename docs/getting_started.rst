###############
Getting Started
###############

This section will help you get the ArcScript transpiler up and running.

Installation
============

ArcScript is a Python script that uses the ``lark`` library for parsing.

1.  **Ensure you have Python 3 installed.**
2.  Install the required library:

    .. code-block:: bash

        pip install lark

Usage
=====

To transpile an ArcScript file (e.g., ``input.arc``) to JavaScript (e.g., ``output.js``), run the script from your terminal:

.. code-block:: bash

    python main.py input.arc output.js

This will generate an ``output.js`` file containing the transpiled JavaScript code.

File Modes
==========

ArcScript supports two modes of operation for flexibility.

Pure ArcScript Mode
-------------------
If your file contains only ArcScript code, the transpiler will convert the entire file. This is the default and most common way to use ArcScript.

**Example ``app.arc``:**

.. code-block:: text

    print("Hello from ArcScript!")


Mixed Code Mode
---------------
For situations where you need to include raw JavaScript alongside ArcScript, you can use special headers.

-  ``[JS]``: Any code written below this header will be treated as raw JavaScript and will be prepended to the final output file as-is.
-  ``[ARC]``: Code below this header will be treated as ArcScript and transpiled.

This is useful for including libraries or writing complex JavaScript functions that are not yet supported by ArcScript.

**Example ``app.arc``:**

.. code-block:: text

    [JS]
    // This is raw JavaScript
    function showAlert(message) {
      alert(message);
    }

    [ARC]
    # This is ArcScript
    print("This message is from the console.")
    showAlert("This message is from the alert box!")

**Resulting ``app.js``:**

.. code-block:: javascript

    // This is raw JavaScript
    function showAlert(message) {
      alert(message);
    }

    console.log("This message is from the console.");
    showAlert("This message is from the alert box!");
