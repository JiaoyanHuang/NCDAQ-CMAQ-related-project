Joey Huang huangj1311@gmail.com 20191227

[MOVES_script](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/MOVES.md)

[MOVES_post_plots](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/MOVESdata.md)

[spatial_allocator](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/NA_MA_spatial_allocator_tools.md) R version

[EMF](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/EMF.md)

[WRF_installation](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/WRF%20and%20WPS%20installation.MD)

[CMAQ_installation](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/CMAQ(v5.3)%20system%20installation%20NCDAQ.md)

[2016_EMP](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/2016%20emission%20platform.MD)

[run_CMAQ](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/run_CMAQ(v5.3)_benchmark.md)

[CMAQ_prep_post_analysis](https://github.com/JiaoyanHuang/NCDAQ-related-projects/blob/master/doc/PREP_POST_data_process.md)

https://www.cmascenter.org


# CMAQ related topics

All the installations are based on follwoing settings:

```
[jhuang@ncaqc2017 apps]$ which ifort
/storage/highspeed/apps/intel/compilers_and_libraries_2017.4.196/linux/bin/intel64/ifort
[jhuang@ncaqc2017 apps]$ which icc
/storage/highspeed/apps/intel/compilers_and_libraries_2017.4.196/linux/bin/intel64/icc
[jhuang@ncaqc2017 apps]$ which icpc
/storage/highspeed/apps/intel/compilers_and_libraries_2017.4.196/linux/bin/intel64/icpc
[jhuang@ncaqc2017 apps]$ which mpirun
/storage/highspeed/apps/mvapich2-2.2_ifc17/bin/mpirun
```

if you have any quesiton please post question to 

https://forum.cmascenter.org/

## Tools

### netcdf
### ioapi
please see https://github.com/JiaoyanHuang/NCDAQ-CMAQ-related-project/blob/master/CMAQ(v5.3)%20system%20installation%20NCDAQ.md

located in 
```
/storage/highspeed/apps/ioapi-3.2_20190925
/storage/highspeed/apps/netcdf-c-4.7.0-intel17
/storage/highspeed/apps/netcdf-fortran-4.4.5-intel17
```
m3tools or ioapi functions can be found in:

https://www.cmascenter.org/ioapi/documentation/all_versions/html/AA.html

netcdf functions or questions can check here:

https://www.unidata.ucar.edu/software/netcdf/

## CMAQ
I built mulitple version of CMAQ for different usages, since not all versions of CMAQ include 
Integrated Source Apportionment Method (ISAM):https://www.airqualitymodeling.org/index.php/CMAQv5.0.2_Integrated_Source_Apportionment

Decoupled Direct Method in 3 Dimensions (DDM-3D):https://www.airqualitymodeling.org/index.php/CMAQ_version_5.2_DDM_Technical_Documentation

Advanced Plume Treatment (APT):https://www.airqualitymodeling.org/index.php/CMAQv5.0.2-APT

ISAM and DDM are instrumental models for CMAQ source apportionment, the difference between these two are DDM can give us more detail information
about contribution the A precursor from B sources to C pollutant. ISAM can only provide contribution from B sources to C pollutant.

APT is a CMAQ advanced plume treatment model for CMAQ, Randy wish to understand of the contributions for landing and takeoff contribution in downwind area of airports.

### CMAQv5.0.2
CMAQ 5.0.2, CMAQ ISAM, CMAQ DDM have been built in 
```
/storage/highspeed/Models/aq/CMAQ/CMAQv5.0.2
```
However, there is an evalution issue, we have to update intel fortran compiler to 2018:

https://forum.cmascenter.org/t/cmaq-benchmark-differences/475

CMAQ APT has been built and an issued found related to SCICHEM (dispersion model) files:
```
 indir:
 /storage/highspeed/Models/aq/CMAQ/CMAQv5.0.2/data/apt/CMAQv5.0.2/data/scichemin
 p
 outdir:
 /storage/highspeed/Models/aq/CMAQ/CMAQv5.0.2/data/apt/CMAQv5.0.2/data/cctm/2005
 179
 rstdir:


 ******ERROR******
 Routine=init_scichem
 Error opening SCICHEM log output file
 File=/storage/highspeed/Models/aq/CMAQ/CMAQv5.0.2/data/apt/CMAQv5.0.2/data/cctm
 /2005179/cmaqapt50.log
```

please contact Prakash Karamchandani at Ramboll (pkaramchandani@ramboll.com)
### CMAQv5.2
CMAQ 5.2 and CMAQ DDM have been built in

```
/storage/highspeed/Models/aq/CMAQ/CMAQ_v5.2
```
evalutions are OK.

### CMAQv5.3

CMAQ 5.3 and CMAQ ISAM have been built in
```
/storage/highspeed/Models/aq/CMAQ/CMAQ_v5.3
```
evalutions are OK.

## SMOKE

### SMOKE4.7
```
/storage/highspeed/apps/SMOKEv4.7
```

## NEI2016
```
/storage/highspeed/JH/EMP_2016/newftp.epa.gov/air/emismod/2016/v1/2016emissions/2016fh_16j
/storage/highspeed/JH/EMP_2016_beta/newftp.epa.gov/air/emismod/2016/beta
```
ftp://newftp.epa.gov/air/emismod/2016/

https://www.epa.gov/sites/production/files/2019-09/documents/2016v7.2_regionalhaze_emismod_tsd_508.pdf

2016 EMP related files can be downloaded from 
https://views.cira.colostate.edu/iwdw/RequestData/Default.aspx

by 20191030 EMP v1, MCIP, BC, IC for 12US2 are ready. 

20191120 EMP v1 pre merge data are ready on NCDAQ cluster with some minor errors (cannot adjust please see https://forum.cmascenter.org/t/2016-emission-platform-v1-adjust-sectors/1126).

