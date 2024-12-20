.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _Baseline-DDF:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

#####################
Deep Drilling Fields
#####################

.. This section should provide a brief, top-level description of the page.

The Deep Drilling Field program includes 5 DDF fields,
chosen to maximize multi-wavelength coverage with pre-existing surveys.
One of the pointings, the Euclid Deep Field South (EDFS) pointing, is a larger field
and so is split between an 'a' and 'b' pointing which share the DDF visits.

The DDFs use a total of about 6.5% of the total survey time.
Each DDF receives on the order of 23,000 visits, except COSMOS which receives
approximately double that. The COSMOS
field has been selected to receive additional coverage, in order to
reach 10-year DDF depth within the first 3 years of the survey as a pathfinder
for Data Management processing and science opportunities.

The cadence for DDF visits is still under development, but will retain
sequences of 10-20 visits per filter within a night, offering the opportunity
for fainter per-night measurements as well as sub-minute time sampling.

=======  =========  =========  =======  ========  ========  ========
..         ELAISS1    XMM_LSS    ECDFS    COSMOS    EDFS_a    EDFS_b
=======  =========  =========  =======  ========  ========  ========
RA            9.45      35.57    52.98    150.11     58.9      63.6
Dec         -44.02      -4.82   -28.12      2.23    -49.32    -47.6
Gal l       311.29     171.1    224.07    236.78    257.9     254.48
Gal b       -72.88     -58.91   -54.6      42.13    -48.46    -45.77
Eclip l     346.66      31.59    40.81    151.39     32        40.97
Eclip b     -43.2      -17.92   -45.44     -9.34    -66.61    -66.6
=======  =========  =========  =======  ========  ========  ========




.. toctree::
    :maxdepth: 2
    :titlesonly:
    :glob:

..   *
