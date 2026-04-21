.. image:: https://img.shields.io/badge/dmtn--339-lsst.io-brightgreen.svg
   :target: https://dmtn-339.lsst.io
.. image:: https://github.com/lsst-dm/dmtn-339/workflows/CI/badge.svg
   :target: https://github.com/lsst-dm/dmtn-339/actions/

######################################################
Challenges serializing Rubin Observatory data products
######################################################

DMTN-339
========

At the NSF-DOE Vera C. Rubin Observatory the image-based data products include data models that are not described by any existing FITS standard. These include spatially-varying point-spread functions, complex World Coordinate System models, provenance information, and shutter motion profiles. For DP1 these data models were written using generic C++ storage APIs resulting in files that can only easily be read using our software. For DP2 we have changed our approach so as to write FITS files that are more accessible by the community and can be accessed more efficiently from object stores. In this presentation we will describe our new approach to serializing data models and how it compares with the existing files, and our approach for improving object store access to individual extensions and integration with the Butler. We will also discuss whether we can expand our file format support to include alternatives such as HDF5, Zarr, and ASDF.

Links
=====

- Live drafts: https://dmtn-339.lsst.io
- GitHub: https://github.com/lsst-dm/dmtn-339

Build
=====

This repository includes lsst-texmf_ as a Git submodule.
Clone this repository::

    git clone --recurse-submodules https://github.com/lsst-dm/dmtn-339

Compile the PDF::

    make

Clean built files::

    make clean

Updating acronyms
-----------------

A table of the technote's acronyms and their definitions are maintained in the `acronyms.tex` file, which is committed as part of this repository.
To update the acronyms table in ``acronyms.tex``::

    make acronyms.tex

*Note: this command requires that this repository was cloned as a submodule.*

The acronyms discovery code scans the LaTeX source for probable acronyms.
You can ensure that certain strings aren't treated as acronyms by adding them to the `skipacronyms.txt <./skipacronyms.txt>`_ file.

The lsst-texmf_ repository centrally maintains definitions for LSST acronyms.
You can also add new acronym definitions, or override the definitions of acronyms, by editing the `myacronyms.txt <./myacronyms.txt>`_ file.

Updating lsst-texmf
-------------------

`lsst-texmf`_ includes BibTeX files, the ``lsstdoc`` class file, and acronym definitions, among other essential tooling for LSST's LaTeX documentation projects.
To update to a newer version of `lsst-texmf`_, you can update the submodule in this repository::

   git submodule update --init --recursive

Commit, then push, the updated submodule.

.. _lsst-texmf: https://github.com/lsst/lsst-texmf
