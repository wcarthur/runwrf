RUNWRF 
======

Job scripts for running WRF and pre/post-processors on NCI Facility
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This repository holds the job scripts used to execute WRF and the pre-processing and post-processing stuff on the NCI Facility.

They are by and large PBS job scripts, which may call additional bash, Python, GrADS, etc. scripts to do the work. I use these to link in additional files required at run time (e.g. lookup tables, namelists, other input stuff). I also generally try to avoid running the model code in the directory where the code lives - I prefer to keep the model output separate from the code base. 

I try to include some useful commentary, plus catch the exit code from scripts to enable me to indicate if the main part of the job worked. If not, it'll report the error code in the job output file - basically reminding me to check the log files from the main executable.

Shell:
------
The job scripts are generally bash scripts. 

Listing:
--------

run_tc_setup.csh: link required files for the idealised TC example
run_ideal_tc, run_wrf_tc: run the idealised TC example (test/em_tropical_cyclone)
run_ideal_les, run_wrf_les: run an idealised large-eddy simulation example (test/em_les)
run_wps: Run WPS and prepare required input data for a real simulation
run_wrf_real: linke required files and execute wrf.exe for a real simulation (need to run `run_wps` first)
