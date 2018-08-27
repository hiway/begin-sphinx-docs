Write
=====


Edit ``source/index.rst``
-------------------------

Elaborate on who is the right audience for this document,
why they would find this information useful
and any context and details they need to know.


::

    A How-To about Stuff
    ====================

    >introduction goes here<

    .. toctree::
       :maxdepth: 2
       :caption: Contents:

       howto
       checklists



Create documentation files
--------------------------

.. code-block:: text

    touch source/{howto,checklists}.rst

Add relevant content to the files with:

- ``nano source/howto.rst``
- ``nano source/checklists.rst``


What to Write?
--------------

``howto.rst``
^^^^^^^^^^^^^

A step-by-step guide to perform the task introduced in index.

::

    How To Handle Everything?!
    ==========================

    Step 1. Observe.
    ----------------

    Before you do anything, observe…
    what do you have here?

    - What is happening?
    - What are the risks?
    - How much time do you have to resolve it?

    Step 2. Orient.
    ---------------

    Now orient yourself to grasp the situation.

    - What options do you have?
    - What are the constraints that must be met?
    - Who can you ask for help?
    - Who can give you a different perspective?

    Step 3. Decide.
    ---------------

    Decide on what you are about to do and why.

    Step 4. Act.
    ------------

    Make it so!

    Step 5. Repeat as necessary.
    ----------------------------

    - If the situation changes, adapt.
    - If the decision made before did not work, adapt.
    - If no further action required, do something else.


``checklists.rst``
^^^^^^^^^^^^^^^^^^

Provide handy checklists where applicable.

::

    Checklists
    ==========

    - A checklist to ensure everything is functional
      after taking the steps in the howto section.
    - A checklist to help troubleshoot known issues.
    - A checklist to help diagnose and escalate unknown/new issues.



