Configure
=========

We installed Python and Sphinx in the `previous step <install_sphinx>`_.

All that's left is to set up our documentation project with Sphinx.
This is a one time setup.

.. note::

    If you quit the terminal window from the previous step,
    run the following commands to enter the virtual environment
    before you continue:

    - ``cd ~/Documents/howto-docs``
    - ``pipenv shell``


Sphinx Quickstart
-----------------

Sphinx has a helper program to start a new documentation project,
it asks questions one by one and sets up the project
based on your responses.

Type the following command at the prompt and press ``Enter``.

- ``sphinx-quickstart``

.. tip::

    - Available options are shown in parenthesis
      separated by a slash, such as ``(y/n)``
    - Default options are shown in square brackets, ``[y]``.
    - To choose a default, press ``Enter``.
    - Or type the option/value you want and press ``Enter``.

Options that you need to enter/change:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  - ``Separate source and build directories (y/n) [n]:`` **y**
  - ``Project name:`` **choose a short project name**
  - ``Author name(s):`` **names of authors**
  - ``Project release []:`` **2018.08.27**
  - ``Do you want to use the epub builder (y/n) [n]:`` **y**
  - ``githubpages: create .nojekyll file to publish the document on GitHub pages (y/n) [n]:`` **y**

Sphinx will now create the expected directory structure
and required files for your project.

Next we will edit ``conf.py`` to enable:

- Spell check extension.
- Epub output to generate an e-book.


.. note:: How to edit a file from command-line.

    - ``$EDITOR source/conf.py``

    - Substitute ``$EDITOR`` with a text/source code editor:

      - ``subl`` - Sublime Text
      - ``charm`` - PyCharm
      - ``nano`` - Nano

    Here's how the command will actually be entered:

    - ``nano source/conf.py``


Edit ``source/conf.py``:
------------------------------

We will make four separate changes in the file as below:

E-book extension requires a version number to be set,
it is empty by default so let us fill in something useful,
like today's date, formatted as YYYY.MM.DD.

::

    version = '2018.08.27'  # <-- edit appropriate version number.

Next, enable the spelling extension by adding a single line,
appending to the list of extensions:

::

    extensions = [
        'sphinx.ext.githubpages',
        'sphinxcontrib.spelling', # <-- add this line
    ]

The epub extension provides several options,
we will set up only the ones required
to output an ebook from the documentation.

Next block of text goes at the bottom of the ``source/conf.py`` file.

::

    # Bibliographic info.
    epub_title = project
    epub_author = author
    epub_publisher = author
    epub_copyright = copyright

    # A list of files that should not be packed into the epub file.
    epub_exclude_files = ['search.html']

Finally, configure the spelling extension.
You can set one or more ``spelling_ignore_...`` options to ``False``
if you want stricter control on what is considered as misspelled.

Next block of text goes at the bottom of the ``source/conf.py`` file,
below epub configuration.

::

    # Spelling
    spelling_lang = 'en_US'
    spelling_word_list_filename = 'jargon.txt'
    spelling_show_suggestions = True
    spelling_ignore_pypi_package_names = True
    spelling_ignore_wiki_words = True
    spelling_ignore_acronyms = True
    spelling_ignore_python_builtins = True
    spelling_ignore_importable_modules = True

One final step before writing our docs -
set up a jargon file to tell spell-check
the words are definitely *not* misspelled.

Edit ``source/jargon.txt``
--------------------------

The standard dictionary flags "Indices" as misspelled,
let us add that (one word on a line) to our jargon file.

- ``nano source/jargon.txt``


::

    Indices

If you expect any names/words to be marked as misspelled words,
add them to this file, one word per line.

Close the editor and get back to shell prompt.


.. tip:: New to using command-line interfaces?

    If you are using ``bash``, which is commonly the default shell,
    try this technique to type less (and make less mistakes)
    by using a few keyboard shortcuts:

    - Hit ``Up Arrow`` once, this brings back previous command to edit.
    - Hit ``Escape``, then ``Backspace``
      to delete a word, here the file extension.
    - Hit ``Escape``, then ``Backspace`` again...
      to delete the previous command's filename,
      while keeping ``source/`` at the end of the command.
    - Now type ``index`` and hit ``Tab``
    - You should have a prompt that looks like this:
    - ``nano source/index.rst``
    - Hit ``Enter`` and you're back in the editor with another file.
