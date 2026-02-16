# Ghost flux


This is a fork from cosima version of panan01, with SIS2 ice thermodynamics altered to include a simple longwave ghost flux over sea ice. This branch uses this [forked version of SIS2](https://github.com/willaguiar/SIS2) where the ghost flux is implemented. The ghost flux is assigned as a set of parameters under SIS_input in panan, and applied globally, only constrained by latitudes. 
The relevant parameters for the ghost flux are:

`GHOST_LW_ICE_ON` : if True, applies the ghost flux. default = False


`GHOST_LW_ICE` : Ghost longwave flux applied to ice thermodynamics (W m-2). default = 0.0


`GHOST_LW_LAT_SOUTH` : Southern ghost flux boundary in degrees. default=-90, i.e., 90S


`GHOST_LW_LAT_NORTH` : Northern ghost flux boundary in degrees. default = -40, i.e., 40S


As you can see, this is a rather simplistic ghost flux application, as it applies a "geographically rectangular" longwave ghost flux. To reduce the possibility of a unrealistic squared ice border, the ghost flux is not applied to the most superficial layer of sea ice. Still, if the prescribed flux is too big you might end up with a unphysical square ice border. So try to apply reasonably high, but not unphysically high ghost flux values


by Wilton Aguiar


# MOM6 Pan-Antarctic Model

1/20° regional model south of 37°S. MOM6-SIS2 coupled configuration,
forced at the open boundary by one year of daily output from
ACCESS-OM2-01 RYF, and at the surface by JRA55v13 RYF. This repository
contains the model configurations, and the scripts required to
generate the input forcing.

For up to date diagnostics on the model output see the [mom6-panan-diagnostics](https://github.com/COSIMA/mom6-panan-diagnostics) repository.
