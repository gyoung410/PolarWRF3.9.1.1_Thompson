Polar WRF 3.8.1 README
February 6 2016

Here are the required files for polar optimized version of WRF version 3.8.1 developed by the Polar Meteorology Group of the Byrd Polar and Climate Research Center at The Ohio State University. Additional support is available at http://polarmet.osu.edu/hines/PWRF/ .
The files are supplements to WRF-ARW version 3.8.1 available from
NCAR at http://www.mmm.ucar.edu/wrf/users/download/. Latest additions are fixes for time-changing sea ice fraction in the dyn_em subdirectory  and options for polar clouds in module_mp_morr_two_moment.F.PWRF3.8.1.

Latest news: Tests with WRF 3.8.1 and PWRF 3.8.1 indicate there may be significant differences in results from those of 3.7.1. Tests for the late summer/early fall Arctic suggest that the WSM  microphysics options for 3.8.1 produce much less liquid cloud mass than 3.7.1, with impacts 
on the shortwave and longwave radiation and temperature. The Morrison microphysics used with 3.8.1 may also produce less cloud liquid, though the change is less dramatic. The cause of the change is unclear, but appears to be unrelated to a bug and bugfix reported for cloud 
fraction at http://www2.mmm.ucar.edu/wrf/users/wrfv3.8/known-prob-3.8.1.html during November 2016.

Potential issue: If you run with the fix for sea ice fraction updating 
during a run, you may need to run with a slightly smaller timestep (75-80%) because of issues between sea surface temperature, skin temperature, and sea ice consistency.

Some users are reporting compiler issues with PWRF 3.8.1 on some machines � these appear to be related to the files on the dyn_em subdirectory. Those files are needed for restarts, but should not be needed if you don�t use restarts. If you have these issues you can try running without compiling the files on dyn_em � but that will not allow restarts to be properly initiated.

A second Polar WRF workshop was presented in June 2016 in conjuction with 
the Antarctic Meteorological Observation, Modeling and Forecasting Workshop 
in Columbus, Ohio, USA. The first Polar WRF Workshop was during November 2011. 
The Polar WRF workshop includes both Arctic and Antarctic applications of Polar WRF. 

----------------------------------------------------------------------------------------
Included in this tar file are the files:

files
README.PWRF.3.8.1
README.PWRF.3.7.1
README.additional
README.PWRF.3.6.1
README.PWRF.3.3.1
README.PWRF.3.2
README.PWRF.3.1.1

phys/
	module_sf_noahlsm.F.PWRF3.8.1
	module_sf_noahlsm_glacial_only.F.PWRF3.8.1
	module_sf_noahdrv.F.PWRF3.8.1
	module_surface_driver.F.PWRF3.8.1
	module_sf_noah_seaice.F.PWRF3.8.1
	module_sf_noah_seaice_drv.F.PWRF3.8.1
	module_mp_morr_two_moment.F.PWRF3.8.1

dyn_em/
	module_first_rk_step_part1.F.PWRF3.8.1
	module_big_step_utilities_em.F.PWRF3.8.1
	module_initialize_real.F.PWRF3.8.1

run/
	LANDUSE.TBL.PWRF3.8.1
	VEGPARM.TBL.PWRF3.8.1

share/
	module_soil_pre.F.PWRF3.8.1

WPS/
 	moved ...
	Additional support is available at http://polarmet.osu.edu/hines/PWRF/ .

These files [except for the README and WPS files] are to replace the files on 
the relative directories minus the ".PWRF3.8.1" in the listed names.

This can be done, for example, by the following renaming and linking:

mv PWRF3.8.1 [your source directory]/WRFV3	{ the directory where WRF version 3.8.1 is installed
cd [your source directory]/WRFV3
mv share/module_soil_pre.F share/module_soil_pre.F-unpolar
mv run/LANDUSE.TBL run/LANDUSE.TBL-unpolar
mv run/VEGPARM.TBL run/LANDUSE.TBL-unpolar  	{store the previous versions
mv dyn_em/module_first_rk_step_part1.F dyn_em/module_first_rk_step_part1.F-unpolar
mv dyn_em/module_big_step_utilities_em.F dyn_em/module_big_step_utilities_em.F-unpolar
mv dyn_em/module_initialize_real.F dyn_em/module_initialize_real.F-unpolar
mv phys/module_sf_noahlsm.F phys/module_sf_noahlsm.F-unpolar
mv phys/module_sf_noahdrv.F phys/module_sf_noahdrv.F-unpolar
mv phys/module_surface_driver.F phys/module_surface_driver.F-unpolar
mv phys/module_sf_noahlsm_glacial_only.F phys/module_sf_noahlsm_glacial_only.F-unpolar
mv phys/module_sf_noah_seaice.F phys/module_sf_noah_seaice.F-unpolar
mv phys/module_sf_noah_seaice_drv.F phys/module_sf_noah_seaice_drv.F-unpolar
mv phys/module_mp_morr_two_moment.F phys/module_mp_morr_two_moment.F-unpolar
ln -s [source directory]/WRFV3/PWRF3.8.1/share/module_soil_pre.F.PWRF3.8.1 share/module_soil_pre.F
ln -s [source directory]/WRFV3/PWRF3.8.1/run/LANDUSE.TBL.PWRF3.8.1 run/LANDUSE.TBL
ln -s [source directory]/WRFV3/PWRF3.8.1/run/VEGPARM.TBL.PWRF3.8.1 run/VEGPARM.TBL
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_sf_noahlsm.F.PWRF3.8.1 phys/module_sf_noahlsm.F
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_sf_noahdrv.F.PWRF3.8.1 phys/module_sf_noahdrv.F
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_surface_driver.F.PWRF3.8.1 phys/module_surface_driver.F
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_sf_noahlsm_glacial_only.F.PWRF3.8.1 phys/module_sf_noahlsm_glacial_only.F
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_sf_noah_seaice.F.PWRF3.8.1 phys/module_sf_noah_seaice.F
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_sf_noah_seaice_drv.F.PWRF3.8.1 phys/module_sf_noah_seaice_drv.F
ln -s [source directory]/WRFV3/PWRF3.8.1/phys/module_mp_morr_two_moment.F.PWRF3.8.1 phys/module_mp_morr_two_moment.F
ln -s [source directory]/WRFV3/PWRF3.8.1/dyn_em/module_first_rk_step_part1.F.PWRF3.8.1 dyn_em/module_first_rk_step_part1.F
ln -s [source directory]/WRFV3/PWRF3.8.1/dyn_em/module_big_step_utilities_em.F.PWRF3.8.1 dyn_em/module_big_step_utilities_em.F
ln -s [source directory]/WRFV3/PWRF3.8.1/dyn_em/module_initialize_real.F.PWRF3.8.1 dyn_em/module_initialize_real.F

...
do this for all the Polar WRF supplemental fortran files
...
---------------------------------------------------------------------------
some additional information on recent versions of Polar WRF:

Starting with WRF 3.5, the thickness, snow depth upon, and albedo of sea ice can 
be be specified through input. This removes the need for several Polar WRF options
in the compiler directives (such as #define BPRC_SI_DEPTH) that were included at the tops
of WRF subroutines. A number of Polar WRF options can still be implemented by compiler directives.
(see older versions of Polar WRF RERADME files). A bugfixed version of Registry.EM_COMMON 
is also included for use of sea ice specifications in restart runs. In the planning stages,
but not yet ready is a web page from which users can download Arctic and Antarctic values of
sea ice concentration, sea ice thickness, snow depth on sea ice, and sea ice albedo (Arctic).

To run with polar options it's best to have the flags enabled for sea ice, sea ice albedo and sea ice thickness:
		:FLAG_SNOWSI = 1 ;
		:FLAG_ALBSI = 1 ;
		:FLAG_ICEDEPTH = 1 ;
in the met_em.d01.YYYY-MM-DD_HH:00:00.nc files (output of WPS)

sea ice concentration should be stored under the variable SEAICE in the met files
sea ice thickness should be stored under the variable ICEDEPTH in the met files
sea ice albedo should be stored under the variable ALBSI in the met files
sea depth on sea ice should be stored under the variable SNOWSI in the met files

In the &physics block of namelist.input

 SEAICE_THICKNESS_OPT = 1,
 SEAICE_THICKNESS_DEFAULT = 3.,
 SEAICE_SNOWDEPTH_OPT = 1,
 SEAICE_SNOWDEPTH_MAX = 1.0,
 SEAICE_SNOWDEPTH_MIN = 0.001,
 SEAICE_ALBEDO_OPT = 2,
 SEAICE_ALBEDO_DEFAULT = 0.82

will enable the input sea ice thickness, enable the input snow depth on sea ice,
and enable the input sea ice albedo. The maximum snow depth on sea ice will be 1 m, 
and the minimum is 0.001 m.

If you wish to specify sea ice thickness at a constant given value use

 SEAICE_THICKNESS_OPT = 0,
 SEAICE_THICKNESS_DEFAULT = [input value in meters]

If you wish to use snow depth on sea ice at a specified constant value use

 SEAICE_SNOWDEPTH_OPT = 1,
 SEAICE_SNOWDEPTH_MAX = [input value in meters]
 SEAICE_SNOWDEPTH_MIN = [input value in meters]

sst_update = 1, 
will hopefully allow sea surface specifications to be updated during a run.

List of files for running and compiling Polar WRF 3.7.1:

dyn_em/module_big_step_utilities_em.F.PWRF3.7.1
dyn_em/module_first_rk_step_part1.F.PWRF3.7.1
dyn_em/module_initialize_real.F.PWRF3.7.1

phys/module_mp_morr_two_moment.F.PWRF3.7.1
phys/module_sf_noah_seaice.F.PWRF3.7.1
phys/module_sf_noah_seaice_drv.F.PWRF3.7.1
phys/module_sf_noahlsm.F.PWRF3.7.1
phys/module_sf_noahlsm_glacial_only.F.PWRF3.7.1
phys/module_sf_noahdrv.F.PWRF3.7.1

run/VEGPARM.TBL.PWRF3.7.1
run/LANDUSE.TBL.PWRF3.7.1

share/module_soil_pre.F.PWRF3.7.1

These files must replace (renamed to)

dyn_em/module_big_step_utilities_em.F
dyn_em/module_first_rk_step_part1.F
dyn_em/module_initialize_real.F

phys/module_mp_morr_two_moment.F
phys/module_sf_noah_seaice.F
phys/module_sf_noah_seaice_drv.F
phys/module_sf_noahlsm.F
phys/module_sf_noahlsm_glacial_only.F
phys/module_sf_noahdrv.F

run/VEGPARM.TBL
run/LANDUSE.TBL

share/module_soil_pre.F


---------------------------------------------------------------------------
Key options:   (namelist options)

if you wish to use FRACTIONAL SEA ICE, please set "fractional_seaice = 1"
 in the physics section of namelist input. This is a standard option in 
 recent versions of WRF, however, it isn't implemented unless you set the flag.
 You should also set "sst_update  = 1" if you want sea surface temperature 
 and sea ice specifications to update during a run. This is especially important
 during long runs. Lesheng Bai has included a fix into PWRF 3.6.1 so that the sea
 ice does update during a run if you direct it to do so. 

An allowance for specified variable "seaice_thickness" can also be set the physics section 
of the namelist input file. You need to give the values for the SEA ICE THICKNESS. This can 
be done through the WPS supplemental files, thus the sea ice thickness will be in the 
standard data input file along with sea surface temperature and other variables.
Sea ice thickness datasets are increasingly becoming available. We have one for Arctic
System Reanalysis period 2000-2012 and have some updates into 2014. We also have a snow
depth on sea ice dataset for these years, thanks to the PIOMAS project at the University 
of Washington. If you are doing a future scenario, you might consider obtaining forecast
sea ice fields from a global or hemispheric climate model. There are even some Southern
Hemisphere sea ice thickness datasets that are possible to find.

If you want that option on set sst_update = 1, 		(this is an enabling flag)

Also consider SEAICE_SNOWDEPTH_OPT, SEAICE_SNOWDEPTH_MAX, SEAICE_SNOWDEPTH_MIN, 
SEAICE_ALBEDO_OPT and SEAICE_ALBEDO_DEFAULT.

----------------------------------------------------------------
compiler options: (these options are at the beginning of subroutine files and must be set
   consistent between the files)

#define BPRC_SI_TEMPERATURE (Soil initialization - module_soil_pre.F)
	Only use input xice/seaice variable to define sea ice locations.
	Otherwise TSK (skin temperature) can be used to determine 
	where sea ice is.
		default is option on

#define BPRC_EXTREME_CHECK (Noah LSM driver)
 	This option enables checks on reasonable value ranges for 
	model variables such as T1 (surface temperature), PSFC 
	(surface pressure), and STC (soil temperature). This is
	a holdover from Polar WRF 3.0.1 and now put as an option.
	It has some value in diagnosing errors, which may be located 
	quicker with this option. Generally not needed in runs that are
	proceeding smoothly.
		default is option off

#define ICEZO_SMALL (Noah LSM driver, and Noah glacial ice routine)
	This option reduces the surface roughness (Z0, ZNT, and Z0BRD) 
	to 0.1 mm over permanent ice. Recent results suggest the surface 
	boundary layer wind speed is too high over Antarctica, so this
	option is not currently recommended.
		default is option off

#define BPRC_MODS (Noah LSM, Noah driver, Noah glacial ice, Noah sea ice and surface driver)
	also module_big_step_utilities_em.F, and module_first_rk_step_part1.F
	This option sets snow emissivity to 0.98. It also reduces
	the maximum snow thickness over permanent ice to "4 times DSOIL" for 	
	purpose of calculating ground heat flux for permanent ice.
	An addition beginning with Polar WRF 3.2 is a wrapper routine for 
	the MYNN surface layer of the PBL. This enables the MYNN
	surface atmospheric layer scheme to run separately for 
	the ice and liquid components of pack ice grid points, similar
	to those for the MYJ and YSU surface layer atmospheric schemes.
	Now sets snow density to relative value of 0.35 based upon Yen (1981)
	Antarctic observations. It also changes the thermal conductivity of sea ice.
        There is a bugfix for time updates during a run of sea ice properties.
		default is option on

#define ORGANIC_TUNDRA (Noah LSM)
	This option sets the thermal conductivity for the upper soil
	layer to 0.25 W m-2 K-1 for Tundra (landuse 20, 21, 22, or 23)
	prior to any averaging with snow thermal conductivity. The
	motivation for this option is Mike Barlage's work with Noah
	in preparation for the Arctic System Reanalysis and the Hines et al. 
	(2010) test of Polar WRF 3.0.1.1 for Arctic land. A peat or "organic"
	layer seems to work well for the soil type along the North Slope 
	of Alaska. The effect there is too reduce the conductivity by an order
	of magnitude resulting in warmer winter soil temperatures, cooler 
	summer soil temperatures, slightly colder atmospheric temperatures
	during winter, and reduced ground heat flux. I don't know how well 
	this works for other Arctic environments. 
		default is option off

#define ALTERNATE_SFCT (Noah LSM, Noah glacial ice, and Noah sea ice)
	This option now lets the user decide to use Polar WRF's 
	method based upon direct calculation of the surface 
	energy balance .. or the classic WRF method for determining
	the surface temperature over snow in SUBROUTINE SNOPAC.
	Previously, it was found that that the Polar WRF direct
	calculation produced better results over Greenland and
	Antarctic ice sheets (option on). Which method produces better 
 	results over sea ice and Arctic land is uncertain. User's may 
	wish to test with the option on and off for best results in
	their cases. (This may be an important question).
	Only surface temperature over snow is impacted. This option has
	not been tested with recent version of PWRF.
		default is option off

There are also Polar WRF modifications to the surface properties 
in LANDUSE.TBL and VEGPARM.TBL

Quantities such as sea ice thickness, snow depth on sea ice, and sea ice albedo 
can be input through auxillary WPS programs. For Arctic sea ice albedo there
is an algorithm for seasonal evolution is based upon a prescribed seasonal cycle modulated
by Mark Anderson's snow melt on sea ice data (also Stockholm University's sea ice melt
and freeze dates). We also suggest users consider the ORGANIC_TUNDRA
option if that is appropriate for the soil in your domain, 
and for users to experiment with ALTERNATE_SFCT.

Future possibilities:

We wish to put sea ice quantities such as concentration, thickness, snow depth 
and albedo in WPS intermediate format for input to WPS metgrid.exe on a website.
The CLM sea ice can be modified for specified variable sea ice thickness. 
Optimizations for the Noah MP scheme can be considered. Some modifications for 
tundra soil moisture made by the University of Oslo could be made to the Noah LSM.
The prognostic sea ice albedo formulation could also be improved. We welcome 
any contributions toward these goals, or other optimizations.

---------------------------------------------------------------------------
Old Notes:

The in file "module_mp_morr_two_moment.F" (not included here) is normally set 
for typical id-latitude CCN values. The parameter INUC can be set at 0
(mid-latitude aerosols) or 1 (M-PACE study - Oct. 2004, clean atmosphere).

The subdirectory WPS section includes an optional feature for inputing
NSIDC sea ice (AMSR-E, bootstrap, and AMSR-E/SSMI from Chapman) through 
the WPS preprocessing.

You may wish to edit the parameter tables "LANDUSE.TBL" and "VEGPARM.TBL" to
better reflect the surface values of quantities such as seasonal albedo and
emissitivy for your study.

WRF3.1.1 (and later versions) have improved snow albedo compared to earlier 
versions. 

Tests suggest that Polar WRF 3.1.1 simulations have colder near-surface
atmospheric temperatures and smaller magnitude ground heat fluxes
for mid-winter cases in comparison to Polar WRF 3.0.1.1.

These routines are designed for WRF version 3.2 If you try to use them  
with another version of WRF you are likely to run into incompatibility 
problems.

As a favor, we ask that you reference the journal articles on Polar WRF in 
your publications that make use of Polar WRF. We would also like to hear from 
users of Polar WRF on the basic plans for the model's use.  Comments on 
the applicability and results of Polar WRF are encouraged, as user input 
helps improve the product. If you have improvements for Polar WRF, please 
share them so we can all benefit in a sense of a community model.

Testing of Polar WRF 3.2 has suggested the following:

Winter and summer temperatures are reasonable over the Arctic Ocean
during summer and winter and along the North Slope of Alaska. 

There is a warm bias for near surface temperature during winter over Greenland.

Realistic simulation of near surface temperature requires a reduction in the
summer albedo over Greenland. An albedo of 0.835 is a typical observed value.

The diurnal cycle of summer temperature of Greenland is larger than that 
observed.

There is a dry bias in the near surface atmosphere.

A negative near-surface wind speed bias with earlier versions of Polar WRF
is not found in tests of Polar WRF 3.2. There may be a slight positive bias
now.

The YSU PBL does not give good results.

The RRTMG radiation schemes give the best results. It has been suggested,
however, that version 3.2 has some issues in the upper atmosphere. Stay 
tuned for further developments.

The MYNN and QNSE PBL schemes may be slight improvements over
the MYJ scheme.

More study may be required of the heat transfer through sea ice and
associated surface energy balance. Use of the Warren et al (1999) 
climatological snow on sea ice dataset is not recommended at this time.

Pending are tests over Anatctica and implementation into AMPS, along with
additional ASR testing.

Writeups on Polar WRF can be obtained from the sources:

The OSU Polar Meteorology Group's Polar WRF web page:
http://polarmet.osu.edu/PolarMet/pwrf.html

Journal Publicationsi on Polar WRF:

Wilson, A.B., D.H. Bromwich, and K.M. Hines, 2011: 
Testing of Polar Weather Research and Forecasting (WRF) Model on the 
Arctic System Reanalysis Domain. Part I. Surface and Upper Air Analysis.
J. Geophys. Res., in preparation.

Hines, K.M., D.H. Bromwich, D.H., L.-S. Bai, M. Barlage, and A.G. Slater, 
2010: Development and Testing of Polar WRF. Part III. Arctic Land. 
J. Climate, in press. 

Bromwich, D.H., K.M. Hines, and L.-S. Bai, 2009: Development and Testing
of Polar WRF: 2. Arctic Ocean. J. Geophys. Res., 114, D08122, 
doi:10.1029/2008JD010300.

Hines, K.M., and D.H. Bromwich, 2008: Development and Testing of Polar WRF.
Part I. Greenland Ice Sheet Meteorology. Mon. Wea. Rev., 136, 1971-1989,
doi: 10.1175/2007MWR2112.1.

If you can add to the list of Polar WRF publications, that's great!

-------------------------------------------------------------------------------
Added August 26 2010:
Dan Steinhoff has added the modified subroutines for WRF 3.2.1. Polar WRF can now be
run with WRF 3.2.1, a version which includes bugfixes on the version 3.2 WRF release.
The new files are denoted by the suffix ".PWRF3.2.1". This is only done for files
that differ between versions 3.2 and 3.2.1.


