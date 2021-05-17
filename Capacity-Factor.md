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

## Fossil Fuel Technologies
The capacity factors for the following technologies were taken from the National Renewable Energy Laboratory [2020 Annual Technology Baseline](https://atb.nrel.gov/electricity/2020/data.php). This is the same source that provided costs for the same technologies. 

NREL provides a representative value for each technology category. This value is the one that most closely aligns with recently installed or anticipated near-term installations of electricity generation plants. We used the representative value capacity factor for each technology as it provides a reliable average baseline number for general geography. **We are making the assumption that the capacity factor for these technologies is independent of geography**

The first table below shows how we filtered the `dataSources/NREL_Costs` datasheet to retrieve the capacity factor. The second table gives the full description for each techdetail abbreviation. 

| Model Technology    | atbyear | core_metric_parameter | core_metric_case | crpyears | technology    | techdetail | scenario |
|---------------------|---------|-----------------------|------------------|----------|---------------|------------|----------|
| Coal                |  2020   | See Cost Section      | Market           | 20       | Coal          | IGCCHighCF | Moderate |
| Coal CCS            |  2020   | See Cost Section      | Market           | 20       | Coal          | IGCCHighCF | Moderate |
| Natural Gas CC      |  2020   | See Cost Section      | Market           | 20       | NaturalGas    | CCHighCF   | Moderate |
| Natural Gas CT      |  2020   | See Cost Section      | Market           | 20       | NaturalGas    | CTHighCF   | Moderate |
| Nuclear             |  2020   | See Cost Section      | Market           | 20       | Nuclear       | na         | Moderate |
| Biomass             |  2020   | See Cost Section      | Market           | 20       | Biopower      | Dedicated  | Moderate |


| Technology                     | Technology Detail          | Abbreviation |
|--------------------------------|----------------------------|--------------|
| Coal                           | EIA Coal-New - High CF     | IGCCHighCF   |
| Coal Carbon Capture            | Coal-CCS-30%-High CF       | CCS30HighCF  |
| Natural Gas Combined Cycle     | EIA Gas CC - High CF       | CCHighCF     |
| Natural Gas Combustion Turbine | Natural Gas EIA CT High CT | CTHighCF     |
| Nuclear                        | na                         | na           |
| Biopower                       | EIA Dedicated              | Dedicated    |