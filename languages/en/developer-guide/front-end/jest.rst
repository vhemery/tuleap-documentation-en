.. _jest_unit_test:

Jest unit tests
===============

`Jest <https://jestjs.io/>`_ is Javascript testing framework to write down our JavaScript unit tests.

You must provide some unit tests for any front-end development.

In this section you will find guidelines on how to setup your own Jest tests.

How to bootstrap your unit tests
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

First, it is necessary to have a Jest configuration file named ``jest.config.js``.
This config file is pretty easy to set up.

.. code-block:: JavaScript

    // tuleap/plugins/<your_plugin>/scripts/jest.config.js

    module.exports = require("../../../tests/jest/jest.config.js");


You will then need to add a test script in your `package.json` file to launch the
Jest when `npm test` is used.


.. code-block:: JavaScript

    // tuleap/plugins/<your_plugin>/scripts/package.json
    {
        //...
        "config": {
            "bin": "../../../node_modules/.bin/"
        },
        //...
        "scripts": {
            //...
            "test": "$npm_package_config_bin/jest"
            //...
        }
    }


How to debug tests
^^^^^^^^^^^^^^^^^^

If you are using an IDE from JetBrains you should be able to run
the tests and add breakpoints out of the box. For more information
you can consult the `Jest documentation about debugging in WebStorm <https://jestjs.io/docs/en/troubleshooting#debugging-in-webstorm>`_.

For others tools, like VS Code check out the `Jest documentation <https://jestjs.io/docs/en/troubleshooting#debugging-in-vs-code>`_.


Best-practices for Tuleap
-------------------------

When you submit a patch for review, we may request changes to better match the following best practices. Please try to follow them.

* Always name unit test files with the same name as their test subject and suffixed with ``.test.js``. For example: ``form-tree-builder.test.js`` tests ``form-tree-builder.js``, ``DocumentBreadcrumb.test.js`` tests ``DocumentBreadcrumb.vue``.
* Always put unit test files next to their test subject, in the same folder. See `Angular.js Style Guide rule`_ for reasons why having unit tests close to the source is a good idea.

Resources
^^^^^^^^^

- `Angular.js Style Guide rule`_ related to unit test file location.
- Google Best Practice Recommendations for Angular App Structure: https://docs.google.com/document/d/1XXMvReO8-Awi1EZXAXS4PzDzdNvV6pGcuaF4Q9821Es/pub
- React File Structure recommendation: https://reactjs.org/docs/faq-structure.html

.. note:: The Vue.js community has no recommendation at the time of writing. Some projects write unit tests in a separate folder hierarchy, some write them side-by-side with source files. We chose the latter for reasons outlined in the `Angular.js Style Guide rule`_.

.. _Angular.js Style Guide rule: https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md#style-y197
