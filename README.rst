RUNWRF 
======
Job scripts for running WRF and pre/post-processors on NCI Facility
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

This branch holds the job scripts used to execute WRF and the pre-processing and post-processing stuff on the NCI Facility.

They are by and large PBS job scripts, which may call additional bash, Python, GrADS, etc. scripts to do the work. I use these to link in additional files required at run time (e.g. lookup tables, namelists, other input stuff). I also generally try to avoid running the model code in the directory where the code lives - I prefer to keep the model output separate from the code base. 

I try to include some useful commentary, plus catch the exit code from scripts to enable me to indicate if the main part of the job worked. If not, it'll report the error code in the job output file - basically reminding me to check the log files from the main executable.

Shell:
------
The job scripts are generally csh (or tcsh) scripts.

Listing:
--------

run_ideal_tc, run_wrf_tc: run the idealised TC example (test/em_tropical_cyclone)
