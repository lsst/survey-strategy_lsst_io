.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _Baseline-WFD:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

#####################
Wide Fast Deep (WFD)
#####################

.. This section should provide a brief, top-level description of the page.

The Wide Fast Deep (WFD) composes the bulk of the survey visits. The WFD sky
includes low-dust extinction area, useful for extragalactic science, as well
as higher stellar density areas (with higher dust extinction), useful for
galactic science. The total area in the WFD is approximately 19.6k square degrees.

.. image:: ../notebooks/WFD_footprint.png
  :width: 600
  :alt: The Wide Fast Deep regions in the survey footprint.


All of the WFD area receives approximately the same number of visits per pointing
(around 800), although the balance of visits between different filters varies
between the low-dust and other areas.

The low-dust WFD uses a *rolling cadence*, alternating high and low activity
areas on the sky each year.  There is no rolling in year 1, to provide uniform
all-sky coverage at DR2 for better calibration and catalog creation.

Visits in the WFD are typically obtained in pairs - the first and second
visit to a pointing are separated by about 33 minutes. These pairs are obtained
in different filters except for y band: u+g, u+r, g+r, r+i, i+z, z+y, y+y.
Using different filters for pairs allows determination of colors for variables
and transients.
About 3% of all pairs (4% of all visits) receive a later (3-7 hours later) third visit in the
same filter as one of the earlier pair. While these triplets are a small fraction
of the overall visits, they provide valuable opportunities for fast transient
identification.

In general, each pointing receives a return visit between 2 to 4 days later,
when the pointing is in an active rolling season. Inactive seasons have a lower
cadence. These return visits will often be in a different set of filters, but
this depends on the lunar phase.

The filters in use depend on the lunar phase, with u and y band being loaded
into and out of the camera every two weeks. Approximately 7 days after new moon,
the u band filter comes out of the camera and the y band filter is put in; this
process reverses 7 days before new moon.



.. toctree::
    :maxdepth: 2
    :titlesonly:
    :glob:


..   *
