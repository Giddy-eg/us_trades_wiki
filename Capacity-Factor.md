# Definition
Capacity Factors represent the capacity limit of a technology in each time slice. Both variable and non-variable generation sources have capacity factors. Ensuring that variable renewable technologies have accurate production profiles adjusted for season and time of day is imperative for obtaining credible results.

# Sources 

## Thermal Generation Technologies
Thermal generation facilities include coal power, gas power, and nuclear power. All **Canadian and United States** thermal generation capacity factors are taken from the National Renewable Energy Laboratory (NREL) [2020 Annual Technology Baseline](https://atb-archive.nrel.gov/electricity/2020/data.php). NREL provides a representative value for each technology category. This value is the one that most closely aligns with recently installed or anticipated near-term installations of electricity generation plants. We used the representative value capacity factor for each technology as it provides a reliable average baseline number for general geography. **We are making the assumption that the capacity factor for these technologies is independent of geography**

The table below shows how we filtered the NREL data to retrieve values for each technology. 

| Model Technology    | atbyear | core_metric_parameter | core_metric_case | crpyears | technology    | techdetail  | scenario |
|---------------------|---------|-----------------------|------------------|----------|---------------|-------------|----------|
| Coal                |  2020   | CF                    | Market           | 20       | Coal          | IGCCHighCF  | Moderate |
| Coal CCS            |  2020   | CF                    | Market           | 20       | Coal          | CCS90HighCF | Moderate |
| Natural Gas CC      |  2020   | CF                    | Market           | 20       | NaturalGas    | CCHighCF    | Moderate |
| Natural Gas CT      |  2020   | CF                    | Market           | 20       | NaturalGas    | CTHighCF    | Moderate |
| Nuclear             |  2020   | CF                    | Market           | 20       | Nuclear       | na          | Moderate |

**NOTE**: Canada used values reported from the 2020 report, while the United States used values reported from the 2017 report. 

## Non-Variable Renewable Generation Technologies 
Non-variable renewable energy generation technologies are dispatched to produce the electricity needed to satisfy demand, rather than dictated by weather conditions. In this grouping we include dammed hydropower and biomass.

Hydropower is given an availability factor value rather then a capacity factor value. The availability factor is the capacity limit of a technology over **a whole year** rather then over each time slice. Introducing an availability factor oppose to a capacity factor gives hydro flexible production functionality. **Canadian** hydropower availability factors are calculated using provincial hydro [residual capacity](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510002201&pickMembers%5B0%5D=1.1&pickMembers%5B1%5D=2.1&cubeTimeFrame.startYear=2017&cubeTimeFrame.endYear=2017&referencePeriods=20170101%2C20170101) and [generation](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510001501&pickMembers%5B0%5D=1.1&pickMembers%5B1%5D=2.1&cubeTimeFrame.startMonth=01&cubeTimeFrame.startYear=2017&cubeTimeFrame.endMonth=12&cubeTimeFrame.endYear=2017&referencePeriods=20170101%2C20171201) numbers. The availability factor was then calculated using the following formula: 

`Availability Factor = (Generation [Wh] * (1 year / 8760 hrs)) / Capacity [W]`

Biomass capacity factor values are taken from the NREL [2020 Annual Technology Baseline](https://atb-archive.nrel.gov/electricity/2020/data.php). This is the same report that provided the thermal generation station capacity factor values. Moreover, the representative value (as previously discussed) was used to filter the data. 

| Model Technology    | atbyear | core_metric_parameter | core_metric_case | crpyears | technology    | techdetail  | scenario |
|---------------------|---------|-----------------------|------------------|----------|---------------|-------------|----------|
| Biomass             |  2020   | CF                    | Market           | 20       | Biopower      | Dedicated   | Moderate |

**NOTE**: Canada used values reported from the 2020 report, while the United States used values reported from the 2017 report. 

## Variable Renewable Generation Technologies
We define variable renewable energy generation as any non-dispatchable generation source. The instantaneous production capacity of these sources varies over time depending on the weather. Included in this category are photovoltaic solar and onshore wind power. 

**Canadian** average provincial capacity factors for wind and solar resources are collected using [Renewables Ninja](https://www.renewables.ninja/). This software provides hourly power output from wind and solar farms located anywhere in the world. To find regional capacity factor values for variable-renewables, we calculate a weighted average based on provincial land area. Moreover, we assume that capacity factor values in 2019 are the same for all years in the model horizon. 

**United States** variable renewable capacity factors are estimated using the NREL System Advisor Model (SAM) according to [Jayadev et al.](https://www.sciencedirect.com/science/article/abs/pii/S0306261919319543)

Listed below are the input parameters for RenewableNinja to get Canadian provincial capacity factor values

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