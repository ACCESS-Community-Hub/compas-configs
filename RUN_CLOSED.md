## Closed basin
Closed basin with 25km grid spacing, 22 layers and sloping bottom in N-S direction (50 - 100m).
Forced with a constant westerly wind

See section 12.7 of the EMS manual

For more on COMPAS see https://research.csiro.au/cem/software/ems/hydro/unstructured-compas/

### EMS
Pulic release:https://github.com/csiro-coasts/EMS/tree/master

### Workflow for gadi
1. Clone repo
2. To build:
  - `module load netcdf/4.7.3 gcc/12.2.0 metis/5.1.0`
  - `cd EMS`
  - `conf/configure --enable-omp --with-metis=${METIS_ROOT} --libdir=${METIS_ROOT}/lib/GNU`
  - `make`
     - This will generate 2 executables:
         - `model/hd/shoc`
         - `model/hd-us/compas`
3. Run all the examples together (see below for one-at-a-time each)
  - `cd model/tests/hd-us/closed`
  - `./run_closed`
  
This builds EMS (both SHOC and COMPAS) and runs the closed basin examples:
* **SHOC** quad grid
* **COMPAS** on quad grid
* **COMPAS** on hex grid

### Forcing and input files

All the forcing files are contained in the `closed` test direcotory, the bash script `run_closed` generates the input netcdf files needed to run each of the tests.

**todo**: Move forcing/input files to a shared location

### Visualise model results with emsarray

todo

