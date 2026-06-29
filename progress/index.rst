.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _Progress-Index:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

###############
Survey Progress
###############

.. This section should provide a brief, top-level description of the page.


:doc:`LSST <lsst/index>`
#########################

Current status: Rubin Observatory has begun the 10-year Legacy Survey of Space and Time (LSST)
as of June 29, 2026. The :doc:`baseline survey strategy <../baseline/index>`
is in place.

`Nightly Scheduler Reports <https://s3df.slac.stanford.edu/data/rubin/sim-data/schedview/reports/>`_
(updated daily) provide a summary of observations taken,
along with pre-night simulations of upcoming nights and a
comparison of the actual visits against predictions.


.. toctree::
   :maxdepth: 2
   :titlesonly:
   :glob:

   lsst/index


:doc:`Pre-LSST <prelsst/index>`
################################

Following the handover from the Construction Project in late October 2025,
Rubin Observatory was in a period of early operations optimization known
colloquially as "Pre-LSST".
Observations during this period, October 2025 to June 2026, have been a mixture of
intensive engineering time and Feature Based Scheduler (FBS) driven "Pre-LSST"
observations.

.. toctree::
   :maxdepth: 2
   :titlesonly:
   :glob:

   prelsst/index



:doc:`2025 Science Validation Survey <sv_status/index>`
########################################################

The Rubin Construction Project's Commissioning team executed the Science Validation (SV) survey
described in `SITCOMTN-005 <https://sitcomtn-005.lsst.io>`_ section 6 during the last 6 months of the Project,
from April to September 2025.
Data acquired during this commissioning period will be released as part of Data Preview 2 (DP2), described in
`RTN-011 <https://rtn-011.lsst.io>`_.

The SV survey progress pages were updated weekly and
contained forecast information, as well as current status.

.. toctree::
   :maxdepth: 2
   :titlesonly:
   :glob:

   sv_status/index

.. admonition:: Last Updated

   Last Updated 2026/06/22

..   *
