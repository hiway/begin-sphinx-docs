Build
=====

.. note::

    If you quit the terminal window from the previous step,
    run the following commands to enter the virtual environment
    before you continue:

    - ``cd ~/Documents/howto-docs``
    - ``pipenv shell``


Sphinx uses the ``make`` tool to simplify running common tasks:

Before every new session of editing run ``make clean``
to delete any remainin files from last build:

- ``make clean``

Ensure you have not misppelled a word:

- ``make spelling``

Build HTML document:

- ``make html``

Buld an ebook:

- ``make epub``

.. note::

    Output from the build is stored in a directory named ``build``
    within your project directory, if you want to keep the generated files
    for archive, copy/move the files into another directory
    since they will be deleted on the next ``make clean``.

