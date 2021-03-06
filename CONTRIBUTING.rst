Contributing to PyLD
====================

Want to contribute to PyLD? Great! Here are a few notes:

Code
----

* In general, follow the common `PEP 8 Style Guide`_.
* Try to make the code pass flake8_ checks.

  * ``flake8 lib/pyld/jsonld.py``
  
* Use version X.Y.Z-dev in dev mode.
* Use version X.Y.Z for releases.

Versioning
----------

* Follow the `Semantic Versioning`_ guidelines.

Release Process
---------------

* ``$EDITOR CHANGELOG.md``: update CHANGELOG with new notes, version, and date.
* commit changes
* ``$EDITOR lib/pyld/jsonld.py``: update to release version and remove ``-dev``
  suffix.
* ``git commit CHANGELOG.md lib/pyld/jsonld.py -m "Release {version}."``
* ``git tag {version}``
* ``$EDITOR lib/pyld/jsonld.py``: update to next version and add ``-dev`` suffix.
* ``git commit lib/pyld/jsonld.py -m "Start {next-version}."``
* ``git push --tags``

To ensure a clean upload, use a clean checkout, and run the following:

* ``git checkout {version}``
* ``python setup.py sdist upload``

.. _PEP 8 Style Guide: http://www.python.org/dev/peps/pep-0008/
.. _flake8: https://pypi.python.org/pypi/flake8
.. _Semantic Versioning: http://semver.org/
