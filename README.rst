======================
cookiecutter-pylibrary
======================

`Cookiecutter <https://github.com/audreyr/cookiecutter>`_ template for a Python python library. This is largely designed
to address this `blog post about packaging python libraries <http://blog.ionelmc.ro/2014/05/25/python-packaging/>`_.

There's a bare library using this template (if you're curious about the final result): https://github.com/ionelmc/python-nameless-minimal.

.. list-table::
    :stub-columns: 1
    
    * - *Note:*
      - You should use `cookiecutter-pylibrary <https://github.com/ionelmc/cookiecutter-pylibrary>`_ instead - it's just like this
        (just use ``no`` for the ``test_matrix_configurator`` option) but with ``py.test`` as the test runner. 

Features
--------

* BSD 2-clause license.
* Tox_ for testing Python 2.6, 2.7, 3.3, PyPy etc. 
* Travis-CI_ and Coveralls_ for continuous testing and coverage tracking (using Tox_).
* Documentation with Sphinx_, ready for ReadTheDocs_.
* Configurations for:

  * `isort <https://pypi.python.org/pypi/isort>`_
  * `bumpversion <https://pypi.python.org/pypi/bumpversion>`_

Requirements
------------

Projects using this template have these minimal dependencies:

* Tox_ - for running the tests
* Setuptools_ - for building the package, wheels etc. Now-days Setuptools is widely available, it shouldn't pose a
  problem :)

Usage
-----

Generate your project::

    cookiecutter https://github.com/ionelmc/cookiecutter-pylibrary-minimal.git

..

    .. list-table:: The variables
        :stub-columns: 1

        * - project_name
          - Verbose project name, used in headings (docs, readme, etc)
        * - repo_name
          - Repository name on github
        * - package_name
          - Python package name (whatever you would import)
        * - distribution_name
          - PyPI distribution name (what you would ``pip install``)

After this you can create the initial repository (make sure you `create <https://github.com/new>`_ an *empty* Github
project)::

    git init .
    git add .
    git commit -m "Initial skel."
    git remote add origin git@github.com:ionelmc/python-nameless.git
    git push -u origin master

Then:

* `Enable the repository in your Travis CI account <https://travis-ci.org/profile>`_.
* `Enable the repository in your Coveralls account <https://coveralls.io/repos/new>`_.
* `Add the repo to your ReadTheDocs account <https://readthedocs.org/dashboard/import/>`_ + turn on the ReadTheDocs
  service hook. Don't forget to enable virtualenv and specify ``docs/requirements.txt`` as the requirements file in
  `Advanced Settings`.
* Release your package. This template comes with a tox environment (``check``) that will:

  * Check if your ``README.rst`` is valid.
  * Check if the ``MANIFEST.in`` has any issues.
  * Run ``flake8`` (a combo of PEP8, pyflakes and McCabe checks)

Not Exactly What You Want?
--------------------------

There's `more intricate variant <https://github.com/ionelmc/cookiecutter-pylibrary>`_ of this template that:

* Has a generator script for the test matrix (there's a ``configure`` script that generates ``tox.ini``/``.travis.yml``).
* Uses Pytest_ for the test runner.
* Has support for building C extensions.

If you have criticism or suggestions please open up an Issue or Pull Request.

.. _Travis-CI: http://travis-ci.org/
.. _Tox: http://testrun.org/tox/
.. _Sphinx: http://sphinx-doc.org/
.. _Coveralls: https://coveralls.io/
.. _ReadTheDocs: https://readthedocs.org/
.. _Setuptools: https://pypi.python.org/pypi/setuptools
.. _Pytest: http://pytest.org/
