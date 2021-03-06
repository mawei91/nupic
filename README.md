Numenta Platform for Intelligent Computing (NuPIC)
=====

NuPIC is a library that provides the building blocks for online prediction systems.  The library contains the Cortical Learning Algorithm (CLA), but also the Online Prediction Framework (OPF) that allows clients to build prediction systems out of encoders, models, and metrics.

For more information, see [numenta.org](http://numenta.org).

OPF Basics
----------

__Encoders__ turn raw values into sparse distributed representations (SDRs).  A good encoder will capture the semantics of the data type in the SDR using overlapping bits for semantically similar values.

__Models__ take sequences of SDRs and make predictions.  The CLA is implemented as an OPF model.

__Metrics__ take input values and predictions and output scalar representations of the quality of the predictions.  Different metrics are suitable for different problems.

__Clients__ take input data and feed it through encoders, models, and metrics and store or report the resulting predictions or metric results.

Installation
------------

NuPIC requires Python 2.6, GCC, and Make.

Add the following to your .bashrc file. Change the paths as needed.

    # Installation path
    export NTA=$HOME/nta/eng
    # Target source/repo path. Defaults to $PWD
    export NUPIC=/path/to/repo
    # Convenience variable for temporary build files
    export BUILDDIR=$HOME/ntabuild
    # Number of jobs to run in parallel (optional)
    export MK_JOBS=3

    # Set up the rest of the necessary env variables. Must be done after
    # setting $NTA.
    source $NUPIC/env.sh

Build and install NuPIC:

    $NUPIC/build.sh

NuPIC should now be installed in $NTA!

Try it out!
-----------
Run the C++ tests:

    $NTA/bin/htmtest
    $NTA/bin/testeverything

You can run the examples using the OpfRunExperiment OPF client:

    python $NUPIC/examples/opf/bin/OpfRunExperiment.py $NUPIC/examples/opf/experiments/multistep/hotgym/
