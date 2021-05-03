# Scripts and Data Files Referenced
* `CapacityFactor.py`
* dataSources/CapacityFactor

# Sources and Assumptions 
## Wind and Solar
### Source
[Renewables Ninja](https://www.renewables.ninja/)

### Assumptions
* The capacity factors in 2019 are the same for all model years (2019-2050)
* The capacity average factor for each province (calculated by RenewablesNinja) is an accurate representation of the Capacity Factor for the entire region
* The capacity factor for each modeled region is a weighted average based on provincial land area 

### Solar Input Parameters for RenewableNinja 
* Location - Canadian Province
* Dateset - MERRA-2 (global)
* Data Year - 2019
* Capacity - 1kW
* System Loss - 0.1
* Tracking - None
* Tilt - 35deg
* Azimuth - 180deg

### Wind Input Parameters for RenewableNinja 
* Location - Canadian Province
* Dateset - MERRA-2 (global)
* Data Year - 2019
* Capacity - 1kW
* Hub Height - 80m
* Turbine Model - Vestas V90 2000

## Hydro 
Had difficulty finding straight hydro capacity factor values for any province in Canada. Instead, we utilized our hydro residual capacity values and found provincial hydro generation numbers. The capacity factor was then calculated using the following formula: 

Capacity Factor = (Generation [Wh] * (1 year / 8760 hrs)) / Capacity [W]

### Sources 
* [Residual Capacity Source](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510002201&pickMembers%5B0%5D=1.1&pickMembers%5B1%5D=2.1&cubeTimeFrame.startYear=2017&cubeTimeFrame.endYear=2017&referencePeriods=20170101%2C20170101)
* [Generation Source](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510001501&pickMembers%5B0%5D=1.1&pickMembers%5B1%5D=2.1&cubeTimeFrame.startMonth=01&cubeTimeFrame.startYear=2017&cubeTimeFrame.endMonth=12&cubeTimeFrame.endYear=2017&referencePeriods=20170101%2C20171201)

### Assumptions
* The capacity factors in 2019 are the same for all model years (2019-2050) and model timesteps 