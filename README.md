ALICE Release Validation
========================

This repository contains the scripts used to trigger the Release Validation
procedure for the ALICE experiment's software.

The ALICE Release Validation runs a reconstruction and several calibration and
physics passes to simulate the actual workflow. It is run on a dedicated cluster
based on [Mesos](http://mesos.apache.org/).

Job control is done via [Makeflow](http://ccl.cse.nd.edu/software/makeflow/) and
job submission uses [Work Queue](http://ccl.cse.nd.edu/software/workqueue).
Spawning of Work Queue workers is controlled by our
[Mesos Work Queue framework](https://github.com/alisw/mesos-workqueue).
