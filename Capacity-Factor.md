# Scripts and Data Files Referenced
* `CapacityFactor.py`
* dataSources/CapacityFactor
* dataSources/ResidualCapacity.csv

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
[Government of Canda](https://www.nrcan.gc.ca/science-data/data-analysis/energy-data-analysis/energy-facts/electricity-facts/20068#L1)