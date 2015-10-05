mcpsc_noc README file
=====================

The project provides an algorithmic skeletons library (rckskel) and
ports of three protein structure comparison methods to perform
multi-criteria protein structure comparison on the Intel SCC or a PC.

This README file provides basic details on building the submodules of this
project - rckskel and mcpsc. 'rckskel' is the algorithmic skeletons library
built on top of the Intel RCCE. 'mcpsc' is the submodule containing ports
of the protein structure comparison methods.

Building MCPSC without rckskle for PC
=====================================

It is possible to build the mcpsc submodule without rckskel support if the
user is interested in running it locally without the SCC. The following
cases are currently supported - one each for the supported methods and one
containing all (the mcpsc case).

PC only USM
-----------

* Build: make pc_test_usm
* Run: time ./mcpsc /[full_path_to_a_temp_dir]/ /[full_path_to_pdb]/ /[full_path_to_contact_maps]/

PC only TMalign
---------------

* Build: make pc_test_tmalign
* Run: time ./mcpsc /[full_path_to_a_temp_dir]/ /[full_path_to_pdb]/ /[full_path_to_contact_maps]/

PC only CE
----------

* Build: make pc_test_ce
* Run: time ./mcpsc /[full_path_to_a_temp_dir]/ /[full_path_to_pdb]/ /[full_path_to_contact_maps]/

MCPC all-to-all test
--------------------

* Build: make pc_test_all_v_all
* Run: time ./mcpsc /[full_path_to_a_temp_dir]/ /[full_path_to_pdb]/ /[full_path_to_contact_maps]/

Build MCPSC for SCC (requires rckskel)
============================================

Build rckskel
-------------

1. Setup path to RCCE by altering the file 'rckskel/RCCE_V1.0.13/common/symbols.in': RCCEROOT=[path_to_dir]/rckskel/RCCE_V1.0.13

2. From rckskel directory run scripts/setup_rcce.sh, on success this will create an archive libRCCE_bigflags_nongory_nopwrmgmt.a

3. From rckskel directory run make rckskel.a, on success this will create an archive rckskel.a

SCC all-to-all test
--------------------

* Build: make scc_test_all_v_all
* Run: time ./scripts/rccerun -nue 48 -f $HOSTFILE mcpsc /tmp/ $BASE_DIR/pdb/ $BASE_DIR/contact_maps/
