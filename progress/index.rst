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

Current status: early operations optimization (pre-lsst) is ongoing.


The Science Validation (SV) survey
described in `SITCOMTN-005 <https://sitcomtn-005.lsst.io>`_ section 6 is complete. The SV survey, along with pre-lsst data up to Jan 2026, will be included in Data Preview 2.

Plans for early data releases are described in
`RTN-011 <https://rtn-011.lsst.io>`_, including timelines for the start of the LSST.

Automated daily updates of survey coverage are available at
`Nightly survey monitoring <https://s3df.slac.stanford.edu/data/rubin/sim-data/schedview/reports/>`_.


.. toctree::
    :maxdepth: 2
    :titlesonly:
    :glob:

    sv_status/index
    pre_lsst/index

.. admonition:: Last Updated

   Last Updated 2026/04/20

..   *
