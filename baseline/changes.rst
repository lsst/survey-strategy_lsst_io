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

Full metric outputs for recent simulations are available at
`USDF MAF <https://usdf-maf.slac.stanford.edu>`_.

v5.0.0
======
These simulations incorporate additional information from commissioning.
In particular, visits are now single-snaps of 1x30s in grizy, with 1x38s visits
in u band. The readout time is increased to 3.07s, although this will generally
be absorbed into the expected slew time. The slew performance of the observatory
model has been reduced in the v5 simulations, as the slew performance of the
observatory at the start of commissioning is yet to be fully determined. By using
a conservative estimate for the slew performance, we can hold some contingency
in case the performance does not improve quite as much as we expect it to.

The DDF strategy is significantly changed in these simulations. The tension
between deep nightly coadds, frequent time sampling, and a limited amount of
total visits available has led to a compromise "ocean" strategy. In the
ocean DDF strategy, DDF coverage is split into "shallow" and "deep" seasons.
In the shallow seasons, sequences are quite short and the overall depth is much
reduced from previous DDF sequences (although it is still deeper than WFD depths
in a single night). In the deep seasons, sequences are significantly longer and
more frequent than in previous simulations. Most of the total DDF coverage occurs
during the deep season for a DDF. Every DDF has at least one deep season.

v4.3.1
======
These simulations use the same strategy as 4.0, however, the start time of the survey
simulation is updated to better match current expectations of the start of the survey.
The simulation now starts in November of 2025 (compared to May 2025 in v4.0). This
does result in random changes in some metrics; a series of simulations with variable
start dates (in addition to the usual series with different weather) is also provided
to help quantify the effect of this stochastity.

Additional small differences will be noted from a correction to the template acquisition
criteria -- instead of expiring templates after 300 days, we now (more correctly) assume
they will expire after 365 days. This has the effect of spreading visits out more evenly
throughout year one, and is noticeable in u and g bands within that first year.

There are minor schema updates; "band" is added to align with general Rubin use of "filter"
vs. "band" ('filter' is still in place, but may start to look like the physical filter names).
And "scripted_id" has been dropped and the information added to the end of the "scheduler_note"
where relevant (i.e. the DD scheduler_notes now are longer and include integers).

`v4.3 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs4.3/tree/main/baseline>`_.

`v4.3 metric updates <https://github.com/lsst-pst/survey_strategy/blob/main/fbs_4.3/v4.3_Update.ipynb>`_.

v4.0
====
This represents an official update to the baseline survey strategy.
These simulations should be very similar to v3.6, with a few minor bugfixes
related to handling the additional downtime during year that would increase
the overall number of observations during year one very slightly.

`v4.0 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs4.0/tree/main/baseline>`_.

`v4.0 metric updates <https://github.com/lsst-pst/survey_strategy/blob/main/fbs_4.0/v4.0_Update.ipynb>`_.

v3.6
====
These simulations are updated versions of the v3.5 simulations, but standardized with
additional downtime in year 1. This additional downtime is the survey scheduling team's
attempt to represent expected observatory efficiency throughout year one. The actual downtime
is likely to vary significantly depending on results during commissioning.
In addition, ToOs are included in every simulation, which lowers the overall efficiency
of observations slightly.

The DDF dither pattern was modified in v3.6 to reduce the dither to 0.2 degrees
instead of 0.7 degrees. This significantly improves the cadence within the DDFs.

The near-sun microsurvey was modified to skip attempted observations when the moon
is close to the desired portion of sky. This removed the instances of the near-sun twilight
survey observing a single field more than ten or twenty times in during a single twilight.

`v3.6 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs3.6/tree/main/baseline>`_.

`v3.6 metric updates <https://github.com/lsst-pst/survey_strategy/blob/main/fbs_3.6/v3.6_Update.ipynb>`_.

v3.5
====
The v3.5 simulations represent early versions of the phase 3 recommendations. The changes include:

* uniform rolling (pauses in rolling cadence for year 4 and year 7 data releases)
* exposure time changes in u band (38s) and other bandpasses reduced to 29 seconds
* readout time changed to 2.4 seconds
* bluer filter balance in LMC/SMC
* updated footprint in galactic plane, including directing visits toward the Roman deep field
* DDF scheduling updated, leading to more observations per DDF in year one

Notable in the changes above are the slight reduction in amount of time spent in
rolling cadence -- uniform rolling includes 3 cycles (6 years) of rolling cadence
while v3.1 to v3.4 included 4 cycles (8 years) of rolling cadence. One of the simulations
included in the v3.5 release does illustrate 4 years of rolling cadence.

Another notable difference is the shift in exposure times per bandpass. This is equivalent
to shifting the survey back towards the u-band depths per visit that were present before
the mirror coating and throughputs update in v3.3.

There was a minor bugfix introduced, to reduce the number of non-paired
visits per night. There was also a bugfix added to ensure that morning twilight
near-sun microsurvey visits include r band when appropriate.

Some simulations in v3.5 include ToOs, as indicated in their filename.
Some simulations in v3.5 include additional downtime in year one - this additional
downtime was adopted as standard at v3.6.

`v3.5 configuration <https://github.com/lsst-sims/sims_featureScheduler_runs3.5/tree/main/baseline>`_.

`v3.5 metric updates <https://github.com/lsst-pst/survey_strategy/blob/main/fbs_3.5/v3.5_Update.ipynb>`_.

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


.. admonition:: Last Updated

   Last Updated 2025/07/28