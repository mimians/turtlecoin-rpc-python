
A Python wrapper for MIMI Money JSON-RPC API.

It integrates with `Walletd` and `MIMIMoneyd`

Example
-------

.. code-block:: python

    wallet.get_addresses()
    'Nsere...'
    {'id': 0, 'jsonrpc': '2.0', 'result': {'addresses': ['Nsere...']}}

    wallet.get_balance()
    {'id': 0, 'jsonrpc': '2.0', 'result': {'availableBalance': 50, 'lockedAmount': 0}}

    recipients = [{'address': 'Nsere...', 'amount': 50}]
    wallet.send_transaction(transfers=recipients)
    {'id': 0, 'jsonrpc': '2.0', 'result': {'transactionHash': 'ae57e...'}}

Installation
------------

You can install the latest version from PyPI:

.. code-block:: bash

    $ pip3 install mimimoney

Documentation
-------------

The documentation is available at http://api.mimi.money

Developer setup
---------------

Clone the repo and install the dependencies with ...pipenv:

.. code-block:: bash

    $ git clone ...
    $ cd mimimoney-python
    $ pipenv install --dev

To generate the HTML documentation you need to have the mimimoney module in
your PYTHONPATH. This is used to automatically generate the api docs.
Afterwards you can run the makefile target:

.. code-block:: bash

    $ pipenv run python setup.py develop
    $ pipenv run make html

The documentation on readthedocs is automatically updated on
each push to the master branch (via webhook).

To release a new version on PyPI, increment the version number
in `mimimoney/__version__.py` and run:

.. code-block:: bash

    $ pipenv run python setup.py upload

This will also create a git tag with the version number.
