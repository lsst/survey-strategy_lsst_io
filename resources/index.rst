.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _Community-Resources:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

#########
Resources
#########

.. _Resources-Software:

Software
========

Simulations of the LSST are generated using the Feature Based Scheduler (FBS) and associated models of the telescope and weather conditions. Evaluations of the resulting simulated pointing histories are carried out with the Metrics Analysis Framework (MAF).

More documentation on the FBS and site models is available in the `rubin_scheduler <https://rubin-scheduler.lsst.io>`_ documentation under the FBS Scheduler and Site Models sections. There are also notebooks containing `scheduler tutorials <https://github.com/lsst/rubin_sim_notebooks/tree/main/scheduler>`_ available illustrating how to set up and run the scheduler.

More documentation on MAF is also available in the `rubin_sim <https://rubin-sim.lsst.io>`_ documentation, in the MAF section, however more extensive information is available in our `MAF tutorials <https://github.com/lsst/rubin_sim_notebooks/tree/main/maf/tutorial>`_.

Please note that both of these software packages can be easily installed via
conda or pip. For most use-cases, additional data must also be downloaded, following instructions
at https://rubin-sim.lsst.io/data-download.html#downloading-necessary-data.


.. _Resources-Simulations:

Simulations
===========

The most recent set of simulations (v3.4) are available for download at https://s3df.slac.stanford.edu/data/rubin/sim-data/sims_featureScheduler_runs3.4/

Previous sets of simulations are also available for download, under similar URLs at
https://s3df.slac.stanford.edu/data/rubin/sim-data/

Metric Evaluation Outputs
=========================

The outputs of our standard metric evaluations (via MAF) for the above simulations
are available at http://astro-lsst-01.astro.washington.edu:8080.



Support
=======

Support for evaluating MAF metrics or understanding survey strategy simulations
is available via posts on the Rubin Community Forum in the
`survey strategy <https://community.lsst.org/c/sci/survey-strategy/>`_ area,
or via questions on the LSSTC slack on channel #sims-maf or #sims.