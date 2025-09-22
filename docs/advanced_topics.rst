###############
Advanced Topics
###############

This section covers more advanced features and use cases for ArcScript.

Mixed Code Mode
===============
As mentioned in the Getting Started guide, the mixed code mode using ``[JS]`` and ``[ARC]`` headers is a powerful feature for integrating ArcScript with existing JavaScript code or libraries.

The raw JavaScript block is always placed at the very top of the output file, making it ideal for imports or global configurations.

**Example ``app.arc``:**

.. code-block:: text

    [JS]
    import { Chart } from 'chart.js';

    function createChart(element) {
        new Chart(element, {
            type: 'bar',
            data: {
                labels: ['Red', 'Blue', 'Yellow'],
                datasets: [{
                    label: '# of Votes',
                    data: [12, 19, 3],
                }]
            }
        });
    }

    [ARC]
    # ArcScript code can now use the functions defined above
    chart_canvas = grab "#myChart"
    createChart(chart_canvas)
    print("Chart has been initialized.")

**Resulting ``app.js``:**

.. code-block:: javascript

    import { Chart } from 'chart.js';

    function createChart(element) {
        new Chart(element, {
            type: 'bar',
            data: {
                labels: ['Red', 'Blue', 'Yellow'],
                datasets: [{
                    label: '# of Votes',
                    data: [12, 19, 3],
                }]
            }
        });
    }

    let chart_canvas = document.querySelector("#myChart");
    createChart(chart_canvas);
    console.log("Chart has been initialized.");
