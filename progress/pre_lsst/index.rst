.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _PreLSST-Index:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

###################################
Pre-LSST Overview
###################################

.. This section should provide a brief, top-level description of the page.

Following the handover from the Construction Project in late October 2025,
Rubin Observatory has been in a period of early operations optimization known
colloquially as "Pre-LSST".
Observations during this period, October 2025 to present, have been a mixture of
intensive engineering time and Feature Based Scheduler (FBS) driven "Pre-LSST"
observations.

The engineering time has focused on tuning of the Simonyi Survey Telescope,
including its Active Optics System, to improve image quality.
The Pre-LSST FBS observations' primary goal is to facilitate evaluation of
summit performance in terms of image quality and survey speed.

The configuration of the FBS observations follow the SCOC Phase 3 recommendations,
but at times add constraints to facilitate image quality investigations.
The FBS configuration also adds a template acquisition survey mode to
compliment lessons learned during commissioning. The general configuration
was similar to v5.0, but with the addition of this single-visit template tier.



.. toctree::
    :maxdepth: 2
    :titlesonly:
    :glob:

    dp2
    pre_lsst_20260607


.. admonition:: Last Updated

   Last Updated 2026/06/28

..   *
