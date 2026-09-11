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

#########################
Deep Drilling Fields
#########################

.. This section should provide a brief, top-level description of the page.

Rubin Observatory's LSST Deep Drilling Field (DDF) program includes 5 DDF fields,
chosen to maximize multi-wavelength coverage with pre-existing surveys.
One of the pointings, the Euclid Deep Field South (EDFS) pointing, is a larger field
and so is split between an 'a' and 'b' pointing which share the DDF visits.

The DDF visits are expected to use between about 6.5% to 7% of the total survey time.
Each DDF receives on the order of 20,000 visits, except COSMOS which receives
approximately double that. The COSMOS
field has been selected to receive additional coverage, in order to
reach 10-year DDF depth within the first 3 years of the survey as a pathfinder
for Data Management processing and science opportunities.

The cadence for the DDFs involves a mixture of "deep" and "ultradeep" seasons.
In every season, short sequences execute every two to three days, keeping a tight monitoring cadence on the DDF fields. These are the deep seasons.
In an ultradeep season, longer sequences of approximately 100 visits are added
every few nights.
The bulk of each DDFs visits are acquired in these ultradeep seasons.
All DDFs except COSMOS have a single ultradeep season; COSMOS has multiple.


Deep Drilling Field Locations
=============================

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


Deep Drilling Field Schedule
============================

For the LSST Deep Drilling Fields, we pre-compute desirable times to schedule the observations. These pre-scheduled times account for field airmass, lunar phase, desired cadence, season length, etc. The resulting schedule is stored as a numpy array. Some fields of note in the array

 *   mjd : This is the Modified Julian Date when the observation should be taken. Things like weather and downtime may can result in the observation being taken at a different time.
 *   mjd_tol : A tolerance factor for the MJD. If the current MJD is within mjd +/- mdj_tol, the scheduler will attempt the observation. This term is essentially here so if the desired MJD is only 2 minutes away, we go ahead and execute the DDF slightly early, rather than risk waiting an hour for a longer set of observations to compete.
 *   RA, dec : The Right Ascension and Declination of the pointing. Note these values are stored as radians and may be shifted by the scheduler on-the-fly to ensure adequate spatial dithering of the DDF. Spatial dithers are typically of order 0.2 degrees.
 *   rotSkyPos. rotTelPos : The rotation angle of the camera. Like the final RA,dec position, this is often set on-the-fly by the scheduler.
 *   band : The bandpass for the observation.
 *   HA_min, HA_max : Hour angle limits for the observation. The scheduler will not attempt the observations if they are outside the HA limits.
 *   flush_by_mjd : This is the Modified Julian Date beyond which the scheduler will stop attempting to complete an observation. This is typically ~2 days after the mjd value.

Along with dynamically adjusting spatial and rotational dither positions, the scheduler may re-order observations while executing them, e.g., executing r-band observations in multiple DDF fields then executing z-band to decrease the total number of filter changes.

An example of downloading and using the latest DDF schedule array can be found in the repo https://github.com/lsst/ddf_schedule/blob/main/ddf_schedule/DDF_schedule.ipynb

.. image:: https://github.com/lsst/ddf_schedule/blob/main/ddf_schedule/ddf_schedule.png?raw=true
  :width: 700
  :alt: The progress of the different DDF fields.



.. toctree::
    :maxdepth: 2
    :titlesonly:
    :glob:

.. admonition:: Last Updated

   Last Updated 2026/06/22

..   *
