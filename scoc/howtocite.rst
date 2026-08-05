
.. Review the README on instructions to contribute.
.. Review the style guide to keep a consistent approach to the documentation.
.. Static objects, such as figures, should be stored in the _static directory. Review the _static/README on instructions to contribute.
.. Do not remove the comments that describe each section. They are included to provide guidance to contributors.
.. Do not remove other content provided in the templates, such as a section. Instead, comment out the content and include comments to explain the situation. For example:
    - If a section within the template is not needed, comment out the section title and label reference. Do not delete the expected section title, reference or related comments provided from the template.
    - If a file cannot include a title (surrounded by ampersands (#)), comment out the title from the template and include a comment explaining why this is implemented (in addition to applying the ``title`` directive).

.. This is the label that can be used for cross referencing this file.
.. Recommended title label format is "Directory Name"-"Title Name" -- Spaces should be replaced by hyphens.
.. _SCOC-Community:
.. Each section should include a label for cross referencing to a given area.
.. Recommended format for all labels is "Title Name"-"Section Name" -- Spaces should be replaced by hyphens.
.. To reference a label that isn't associated with an reST object such as a title or figure, you must include the link and explicit title using the syntax :ref:`link text <label-name>`.
.. A warning will alert you of identical labels during the linkcheck process.

#######################
How to cite the LSST survey strategy 
#######################

The process of designing the LSST survey strategy is described in 

`Optimization of the Observing Cadence for the Rubin Observatory Legacy Survey of Space and Time: A Pioneering Process of Community-focused Experimental Design Federica B. Bianco et al 2022 ApJS 258 1  <https://iopscience.iop.org/article/10.3847/1538-4365/ac3e72>`_ DOI 10.3847/1538-4365/ac3e72


::

  @article{Bianco_2022, doi = {10.3847/1538-4365/ac3e72},
  url = {https://doi.org/10.3847/1538-4365/ac3e72},
  year = {2021},
  month = {dec},
  publisher = {The American Astronomical Society},
  volume = {258},
  number = {1},
  pages = {1},
  author = {Bianco, Federica B. and Ivezić, Željko and Jones, R. Lynne and Graham, Melissa L. and Marshall, Phil and Saha, Abhijit and Strauss, Michael A. and Yoachim, Peter and Ribeiro, Tiago and Anguita, Timo and Bauer, A. E. and Bauer, Franz E. and Bellm, Eric C. and Blum, Robert D. and Brandt, William N. and Brough, Sarah and Catelan, Márcio and Clarkson, William I. and Connolly, Andrew J. and Gawiser, Eric and Gizis, John E. and Hložek, Renée and Kaviraj, Sugata and Liu, Charles T. and Lochner, Michelle and Mahabal, Ashish A. and Mandelbaum, Rachel and McGehee, Peregrine and   Neilsen Jr., Eric H. and Olsen, Knut A. G. and Peiris, Hiranya V. and Rhodes, Jason and Richards, Gordon T. and Ridgway, Stephen and Schwamb, Megan E. and Scolnic, Dan and Shemmer, Ohad and Slater, Colin T. and Slosar, Anže and Smartt, Stephen J. and Strader, Jay and Street, Rachel and Trilling, David E. and Verma, Aprajita and Vivas, A. K. and Wechsler, Risa H. and Willman, Beth},
  title = {Optimization of the Observing Cadence for the Rubin Observatory Legacy Survey of Space and Time: A Pioneering Process of Community-focused Experimental Design},
  journal = {The Astrophysical Journal Supplement Series}
  }





The survey strategy itself is described in  PSTNs technical documents, all with citable with an associated DOI: the most recent survey strategy PSTNs are `PSTN-056 <https://pstn-056.lsst.io>`_ which describes the survey strategy in detail (DOI 10.71929/rubin/2585402) and `PSTN-057 <https://pstn-057.lsst.io>`_ (DOI 10.71929/rubin/3395070) which describes updates to PSTN-056 specifically relevant to the first years of LSST.  

::

  @TechReport{PSTN-056,
    author = "{Rubin's Survey Cadence Optimization Committee} and Bianco, Federica B. and Jones, R. Lynne and Anguita, Timo and Bauer, Franz E. and Edwards, Louise O. V. and Jha, Saurabh W. and Mandelbaum, Rachel and Miller, Adam A. and Olsen, Knut and Slater, Colin T. and Smartt, Stephen J. and Strader, Jay and Street, Rachel A. and Volk, Kathryn and Yoachim, Peter",
    title = "{Survey Cadence Optimization Committee’s Phase 3 Recommendations}",
    institution = "{NSF-DOE Vera C. Rubin Observatory}",
    year = "2025",
    month = "January",
    handle = "PSTN-056",
    type = "{Project Science Technical Note}",
    number = "PSTN-056",
    doi = "10.71929/rubin/2585402",
    url = "https://pstn-056.lsst.io/"
  }

::

  @TechReport{PSTN-057,
    author = "{{The Rubin Observatory Survey Cadence Optimization Committee}}",
    title = "{Survey Cadence Optimization Committee’s Survey Start Recommendations}",
    institution = "{NSF-DOE Vera C. Rubin Observatory}",
    year = "2026",
    month = "July",
    handle = "PSTN-057",
    type = "{Project Science Technical Note}",
    number = "PSTN-057",
    url = "https://pstn-057.lsst.io/"
  }

References for all Rubin and LSST documents are available at https://github.com/lsst/lsst-texmf
