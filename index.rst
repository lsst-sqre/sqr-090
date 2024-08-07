##########################################################
System for collecting user feedback in Rubin documentation
##########################################################

.. abstract::

   A straightforward way to determine the effectiveness of documentation, and determine ways to improve that documentation, is to let our users tell us. This technote describes the architecture for a system for collecting feedback such as ratings and comments from Sphinx/Documenteer documentation sites published on ``lsst.io`` and storing that feedback for subsequent querying in Sasquatch/InfluxDB. Ook, the documentation librarian service, serves as an intermediary for safely receiving feedback submissions.

High-level system architecture
==============================

This system consists of three main components:

1. **The front-end feedback UI**. The user interface is embedded into the Sphinx documentation sites published on ``lsst.io``. The code for these UIs is developed in the Documenteer_ python package. Since all Rubin documentation sites and Sphinx-based technotes are built with Documenteer, the feedback UI can be efficiently deployed to documentation sites without individual documentation teams needing to do any configuration for their projects.

2. **The feedback collection API**. This API receives submissions from the feedback UI components. This feedback API and service is implemented in the existing Ook_ application, which runs in the Roundtable Kubernetes cluster for internal SQuaRE services. The role of this service is to receive submissions, vet them for spam, transform the data, and forward the feedback into Sasquatch_.

3. **Sasquatch** is an platform for collecting, storing, and making Rubin telemetry and metrics available. We wish to collect the feedback in Sasquatch so that it is available in a single, familiar place for querying and analysis. Sasquatch uses InfluxDB as its backend storage.

.. _Ook: https://github.com/lsst-sqre/ook
.. _Sasquatch: https://sasquatch.lsst.io
.. _Documenteer: https://documenteer.lsst.io
