.. image:: https://img.shields.io/badge/sqr--090-lsst.io-brightgreen.svg
   :target: https://sqr-090.lsst.io
.. image:: https://github.com/lsst-sqre/sqr-090/workflows/CI/badge.svg
   :target: https://github.com/lsst-sqre/sqr-090/actions/

##########################################################
System for collecting user feedback in Rubin documentation
##########################################################

SQR-090
=======

A straightforward way to determine the effectiveness of documentation, and determine ways to improve that documentation, is to let our users tell us. This technote describes the architecture for a system for collecting feedback such as ratings and comments from Sphinx/Documenteer documentation sites published on ``lsst.io`` and storing that feedback for subsequent querying in Sasquatch/InfluxDB. Ook, the documentation librarian service, serves as an intermediary for safely receiving feedback submissions.

**Links:**

- Publication URL: https://sqr-090.lsst.io
- Alternative editions: https://sqr-090.lsst.io/v
- GitHub repository: https://github.com/lsst-sqre/sqr-090
- Build system: https://github.com/lsst-sqre/sqr-090/actions/


Build this technical note
=========================

You can clone this repository and build the technote locally if your system has Python 3.11 or later:

.. code-block:: bash

   git clone https://github.com/lsst-sqre/sqr-090
   cd sqr-090
   make init
   make html

Repeat the ``make html`` command to rebuild the technote after making changes.
If you need to delete any intermediate files for a clean build, run ``make clean``.

The built technote is located at ``_build/html/index.html``.

Publishing changes to the web
=============================

This technote is published to https://sqr-090.lsst.io whenever you push changes to the ``main`` branch on GitHub.
When you push changes to a another branch, a preview of the technote is published to https://sqr-090.lsst.io/v.

Editing this technical note
===========================

The main content of this technote is in ``index.rst`` (a reStructuredText file).
Metadata and configuration is in the ``technote.toml`` file.
For guidance on creating content and information about specifying metadata and configuration, see the Documenteer documentation: https://documenteer.lsst.io/technotes.
