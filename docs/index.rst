====================================
Welcome to MPRAflow's documentation!
====================================


This pipeline processes sequencing data from Massively Parallel Reporter Assays (MPRA)
to create count tables for candidate sequences tested in the experiment.

Installation & Getting Started
    Instructions for the Installation of the program and some examples to get you started.

MPRAflow Workflows
    An overview of how MPRAflow works and documentation for the MPRAflow sub workflows.

MPRAflow Examples
    Muliple examples from the literature are listed for every sub workflow in MPRAflow.

Project Information
    More information on the project, including the changelog, list of contributing authors, and contribution instructions.


-------------
Quick Example
-------------

.. code-block:: bash

    nextflow run count.nf --dir "fastQFolder" --experiment-file "experiment.csv" --design "design.fa" --association "bc_map.pickle" --m 1 -resume --mpranalyze --outdir "output"


--------
Features
--------

:Association:
  This utility takes in library association sequencing data (FASTQ) and a design file (FASTA) to assign barcodes to the corresponding elements tested. Functionality includes filtering for quality and coverage of barcodes. This utility must be run before the COUNT utility.
:Count:
  This utility processes sequence data (FASTQ) of barcodes from the DNA and RNA fractions of the MPRA experiment and outputs count tables labeled with the element tested and a label provided in the design file. This utility can process multiple replicates and conditions in a parallelized manner. Based on a user specified flag, the pipeline will either output normalized activity for each tested sequence, or will combine the results into a single count matrix compatible with MPRAnalyze.
:Saturation mutagenesis:
  This workflow is about getting single variant effect from a target with multiple mutations generated by error-prone PCR. The workflow takes counts (e.g. from the count workflow), combines them with an association file (variants to barcodes) and uses a generalized linear model to to detect single variant effects.

--------
Feedback
--------

The best place to leave feedback, ask questions, and report bugs is the `MPRAflow Issue Tracker <https://github.com/shendurelab/MPRAflow/issues>`_.


Indices and tables
==================

* :ref:`genindex`
* :ref:`search`

.. toctree::
    :caption: Installation & Getting Started
    :name: getting-started
    :maxdepth: 1
    :hidden:

    quickstart
    install
    cluster


.. toctree::
    :caption: MPRAflow Workflows
    :name: mpraflow-workflows
    :maxdepth: 1
    :hidden:

    overview
    association
    count
    saturation_mutagenesis

.. toctree::
    :caption: MPRAflow Examples
    :name: mpraflow-examples
    :maxdepth: 2
    :hidden:

    association_example1
    count_example1
    count_example2
    saturation_mutagenesis_example1


.. toctree::
    :caption: Tips & Tricks
    :name: tips-tricks
    :maxdepth: 1
    :hidden:

    faq



.. toctree::
   :caption: Project Info
   :name: project-info
   :maxdepth: 1
   :hidden:

   contributing
   authors
   history
   license
   todo_list
