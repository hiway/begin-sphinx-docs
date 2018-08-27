.. _install_sphinx:

Install
=======

.. note:: Instructions below are for unix-like systems:

  - Supported:

    - MacOS
    - Debian / Ubuntu
    - FreeBSD
  - Android *may* work using Termux app, though it is not covered here.
  - Windows is not covered at the moment by this tutorial.

Accessing the Terminal
----------------------

To run the commands that follow, open a Terminal app on your computer.

**MacOS**

- Press ``Cmd+Space``, to invoke Spotlight Search and type "terminal".
- Spotlight selects Terminal app as the top hit.
- Press ``Enter``.
- Type (or copy/paste) commands into the terminal, one by one.


**Debian / Ubuntu / FreeBSD**

- Only required if you are in a desktop environment.
  ``Alt+F2`` or ``Alt+R`` should bring up a dialog asking for command to run.
- Type "xterm".
- Press ``Enter``.
- Type (or copy/paste) commands into the terminal, one by one.


Install Python 3
----------------

**MacOS**

``Brew`` is a package manager for MacOS
that makes it easy to install and manage software from the command line.
If you don't have brew installed, get it at: https://brew.sh/

Once brew is installed, type the following and press enter to install Python.
As brew defaults to Python-3 as of Aug 2018, we don't need to specify the version.

- ``brew install python``


**Debian / Ubuntu**

Use ``apt-get`` to install the latest Python-3.
On other flavours of Linux,
you will have ``yum`` or another package manager,
you can use it to install python3.

- ``sudo apt-get install python3``

`You may be asked for your password when running sudo.`


**FreeBSD**

- ``sudo pkg install python3``

`You may be asked for your password when running sudo.`


Install pip and pipenv
----------------------

Now Python is installed system-wide.
The installed packages are available to all users.

Following three commands require administrator access.
You may be asked for your password when running these commands.

First will install and upgrade Python's package manager called ``pip``,
so that we can install Python packages from https://pypi.org.

- ``sudo -H python3 -m ensurepip``
- ``sudo -H python3 -m pip install -U pip``

Next, we will install ``pipenv``,
which helps us isolate Python environments for every project.

- ``sudo -H python3 -m pip install -U pipenv``

Almost done!

Create a project directory
--------------------------

Create a directory to hold all the related files.

- ``mkdir ~/Documents/howto-docs``
- ``cd ~/Documents/howto-docs``


Create and use a virtual environment
------------------------------------

- ``pipenv --three``
- ``pipenv shell``


.. tip::

   After you have created a Python virtual environment,
   you can open a new terminal window and enter the environment
   with the following set of commands:

   - ``cd ~/Documents/howto-docs``
   - ``pipenv shell``

   Make it easier to remember by putting the following line in ``~/.bash_profile``.

   - ``alias howtoenv="cd ~/Documents/howto-docs && pipenv shell"``

   Now you can open a new terminal and type ``howtoenv`` to jump right in!


Install Sphinx and required libraries
-------------------------------------

The Python virtual environment is ready to install packages
that are only visible to the virtual environment.
This will not require administrator rights
and will not overwrite the python packages installed on system.

Let's install the packages we need:

- ``pipenv install sphinx pyenchant sphinxcontrib-spelling``

.. tip::

    You can create more virtual environments as needed
    to try out packages from https://pypi.org
    without clobbering your working environment.

