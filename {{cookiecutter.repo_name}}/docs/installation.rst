.. highlight:: shell

.. _installation:

============
Installation
============

Stable release
--------------

Using pip
+++++++++

Python comes with an inbuilt package management system, `pip`_. Pip can install, update, or delete any official package.

To install {{ cookiecutter.project_name }} using pip, run this command in your terminal:

.. code-block:: console

    $ pip install git+ssh://git@github.com/anmut-consulting/{{ cookiecutter.repo_name }}.git@latest

This will always install the latest version of `{{ cookiecutter.repo_name }}` provided you have `SSH set up on GitHub`_.

To activate the environment (assuming you are using one), run this command from the root directory of the repo::

    $ source env/bin/activate

And to deactivate the environment::

    $ deactivate

If you don't have pip installed, these `Python installation guides`_ can guide you through the process depending on your operating system and which python version you need.

.. _pip: https://pip.pypa.io/en/stable/
.. _SSH set up on GitHub: https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh
.. _Python installation guides: http://docs.python-guide.org/en/latest/starting/installation/

Using pipenv
++++++++++++

Pipenv is a tool that automatically creates and manages a virtualenv for your projects so that you no longer need to use pip and `virtualenv`_ separately.
It will add/remove packages from your Pipfile as you install/uninstall packages, and generate the ever-important Pipfile.lock which is used to produce deterministic builds.

If you're using **pipenv** for your virtual environment and you'd like to install from the repo, the command becomes (notice the ``#egg={{ cookiecutter.repo_name }}`` section)::

    $ pipenv install git+ssh://git@github.com/anmut-consulting/{{ cookiecutter.repo_name }}.git@latest#egg={{ cookiecutter.repo_name }}

To activate the environment, the command is::

    $ pipenv shell

You should see ``({{ cookiecutter.repo_name }})`` at the start of the prompt now.  This indicates you are in the activated environment.  If you don't see it - something has gone wrong.

To deactivate the environment again, simply run::

    $ exit

.. _virtualenv: https://virtualenv.pypa.io/en/latest/

From sources
------------

You can build any of the packages from source. Those involved in development may take this route to get developmental versions or alter source code.

The sources for {{ cookiecutter.project_name }} can be downloaded from the:

    * `Github repo`_, or
    * `Distributions`_ SharePoint folder.

.. _Github repo: https://github.com/anmut-consulting/{{ cookiecutter.repo_name }}
.. _Distributions:

GitHub
++++++

You can either clone the public repository:

.. code-block:: console

    $ git clone git://github.com/anmut-consulting/{{ cookiecutter.repo_name }}

Or download the `tarball`_:

.. code-block:: console

    $ curl -OL https://github.com/anmut-consulting/{{ cookiecutter.repo_name }}/tarball/latest

.. _tarball: https://github.com/anmut-consulting/{{ cookiecutter.repo_name }}/tarball/latest

SharePoint
++++++++++

Version zips and tarballs are also downloadable from the `Distributions`_ folder within the Anmut Hub - Software Products SharePoint.

Once you have a copy of the source downloaded and decompressed on your machine, you can install it with:

.. code-block:: console

    $ python setup.py install
