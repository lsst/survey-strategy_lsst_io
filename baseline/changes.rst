.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _Baseline-Changes:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

#######################
Updates to the baseline
#######################

.. This section should provide a brief, top-level description of the page.

Over time, the baseline survey strategy evolves due to changes in the
observatory, update in our weather predictions, details of the Feature Based
Scheduler code, and most importantly, due to changes in the survey strategy.

All of the updates below are (so far) pre-commissioning, pre-operations.

(Note: WFD = Wide Fast Deep; DDF = Deep Drilling Field).


v3.4
=====
Updates from v3.3 are minor, primarily in ``rubin_scheduler`` code updates.
There were improvements to generalize masking of unavailable areas on the sky,
as well as preventing scripted surveys such as the DDFs from executing too close
to twilight. Cross-platform repeatability was improved.
Metrics run on ``baseline_v3.4_10yrs.db`` should present very similar
results to ``baseline_v3.3_10yrs.db``.

`v3.4 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs3.4/tree/main/baseline>`_.

v3.3
====
Updates from v3.2 are significant, as the new 3xAg ('triple silver') throughput
curves were introduced in v3.3. As of v3.3, the throughput curves in use are
v1.9 of the `syseng_throughputs <https://github.com/lsst-pst/syseng_throughputs>`_
curves, while v3.2 used v1.7. While the actual
survey strategy itself does not change, metrics evaluated on v3.3 which depend on
five sigma limiting magnitudes will produce noticeably different results
than earlier simulations. Throughput improved in grizy bands, although decreased
in u band.

There were minor changes in the weighting of various basis functions in the
scheduler code. One of these also produced a noticeable change in
u-band visits over time, as a bug which caused u-band visits to briefly "pause"
after the end of year 1 was fixed. The result of this bug fix was slightly more
visits overall in u-band (about 15%) which helped compensate for the drop in
u-band sensitivity.

`v3.3 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs3.3/tree/main/baseline>`_.

v3.2
====
Updates from v3.0 are significant. The survey start date was updated to May 1, 2025,
in accordance with updated estimates of the survey timeline.

As the camera can only hold 5 filters at a
time, the scheduler plans to swap the u filter with either z or y band depending
on the lunar phase. Simulations prior to v3.2 swapped u-band with z-band at
~ +/-7 nights around new moon; as of v3.2, the u-band filter is swapped with y-band
instead. There was also a small update to the low-dust extinction WFD survey
footprint to include a small 'swathe' to match the southern most edge of the
Euclid footprint.

The near-sun twilight microsurvey underwent several changes, pushing observations
closer to the sun. This improved metrics related to discovery of interior-to-earth
asteroids. The use of a distribution of filters in the microsurvey was also updated
to be more uniform.

The 'triplets' (long blobs) survey mode was also modified; v3.0 triggered
this survey mode every 6 nights, multiple times within those nights.
As of v3.2, the 'triplet' mode is only triggered once at the start of a night,
but more frequently (every 3 nights). This results in the triplet observations
being acquired on more independent nights, although at more limited
times within each night.

There were additional changes in the underlying codebase, which should not
significantly change evaluations of the simulated survey.

`v3.2 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs3.2/tree/main/baseline>`_.

v3.1
====
This was an un-released set of simulations, for internal use only.

v3.0
====
Updates from the v2 series are significant. The v3 series of simulations responds to
recommendations from the SCOC in `PSTN-055 <https://pstn-055.lsst.io>`_.

Major survey strategy changes can be summarized as follows:

* Visits in u-band moved from 2x15s snaps to a single 1x30s exposure. Visits in other bandpasses remain at 2x15s. This improves u-band depth per visit by shifting these visits toward the sky-noise dominated rather than readnoise-dominated regime.

* The survey footprint was updated by a small addition to the WFD at the Virgo Cluster. The Galactic Plane coverage (in particular, the area covered at WFD levels) was significantly updated, to add coverage at a wider range of galactic longitudes and for some stellar clusters. The filter balance of the footprint in the Galactic Plane was modified to spend more time in bluer filters, but unchanged in other areas.

* Time spent in Deep Drilling Fields increased from slightly less than 5% of the overall survey time, to over 6.5% of the survey time. The COSMOS DDF now receives additional coverage, in order to reach the expected 10 year DDF depth within the first 3 years of the survey, serving as a pathfinder for later processing requirements.

* A 'triplet' survey mode was introduced, such that every 6 nights, pointings observed in pairs early in the night will acquire a later (2-7 hours later) third visit (in one of the same filters as the pair). While a small fraction of total observations, this provides opportunities for short-timescale time-domain science.

* A near-sun twilight microsurvey was introduced, taking observations within a band approximately +/-20 degrees of the ecliptic, during -12 to -15 degree twilight. These visits are only 15 seconds long but repeat 4 times within the short (about 20 minute) period of twilight, in order to enable discovery of interior-to-earth asteroids. The visits are at low solar elongation, high airmass towards the direction of the sun.

The overall effect of these changes is to fulfill additional science goals that were
not met previously, however an additional effect is to reduce the number of visits
per pointing in the WFD portion of the survey footprint.

`v3.0 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs3.0/tree/main/baseline>`_.



v2.0
====
Updates from the v1 series are significant. The v2 series of simulations responds to
recommendations from the SCOC in `PSTN-053 <https://pstn-053.lsst.io>`_.

Major survey strategy changes can be summarized as follows:

* The survey footprint is significantly updated, placing more area into the WFD portion of the survey footprint. The low-dust-extinction area is increased by approximately 15%, allowing more useful area for extragalactic science. To maintain coverage of important galactic plane areas, the survey footprint now includes 'dusty plane' areas, observed with a few hundred visits per pointing. Additional coverage of the Galactic Bulge, at WFD-level (~800 visits per pointing) has been introduced to enable time-domain science in this area. The overall survey footprint is increased, which results in fewer visits per pointing.

* To maintain and improve on the cadence of visits within the WFD, a ``rolling cadence`` is introduced. The ``rolling cadence`` splits the WFD survey footprint into 4 different bands, based on declination, then alternately "activates" 2 of these bands in successive seasons. When a band is "active" it receives more visits, then in the next season when it is "inactivate", it receives fewer visits. A pointing in the WFD would receive approximately 82 visits (825 visits over the survey, divided by 10 years) in a standard season -- in an "active" season it might receive 145, while in an "inactive" season, it would only receive about 20, depending on how 'strong' the rolling in the rolling cadence is.

The overall effect of these changes is to improve science metrics, but reduce the
number of visits per pointing in the WFD.

`v2.0 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs2.0/tree/main/baseline>`_.

