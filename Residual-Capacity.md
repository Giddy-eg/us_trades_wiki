## Sources
### Canada Energy Regulator 
Originally, residual capacities were extracted from this [Statistics Canada Site](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510002201&pickMembers%5B0%5D=1.1&pickMembers%5B1%5D=2.1&cubeTimeFrame.startYear=2017&cubeTimeFrame.endYear=2017&referencePeriods=20170101%2C20170101). This provided reliable Canadian Government backed existing capacity numbers for a variety of technologies separated by provinces. The issue with this data set is that the aggregation method used is more coarse then what our model needs. For example, the values group all steam turbine fuels into one technology, instead of breaking it down into coal, natural gas, oil, ect. The second issue is that these numbers do not provide commissioning dates. Therefore, we would either have to assume general commission dates which could effect capacity investment in the future. 

### Wikipedia
Although Wikipedia sources need to be carefully verified, due to its open-source nature, it can act as a fantastic resource to compile a large amount of data quickly. Currently, the majority of our residual capacities and commissioning dates come from Wikipedia pages (each reference can be found in the file `dataSources/ResidualCapacitiesByProvince.csv`). The total capacity numbers were cross-referenced against this [Statistics Canada Site](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510002201&pickMembers%5B0%5D=1.1&pickMembers%5B1%5D=2.1&cubeTimeFrame.startYear=2017&cubeTimeFrame.endYear=2017&referencePeriods=20170101%2C20170101), this [Canadian Energy Regulator Site](https://www.cer-rec.gc.ca/en/data-analysis/canada-energy-future/2019/results/index.html) and this [Energy Rates Site](https://energyrates.ca/the-main-electricity-sources-in-canada-by-province/). This insured our assumption of trusting Wikipedia compiled numbers are in the correct ballpark when comparing percentage generation by source and aggregating multiple sources. 

It needs to be noted, we have **not** yet verified the sources Wikipedia is extracting its information from.

## Coal
### Retirement 
As coal is a heavy emitter, numerous coal power plants are beginning to be phased out. Some references included a decommissioning date which is transferred over into the model. In cases where a decommissioning date was not listed, the operational life was applied to the commission date to find set the retirement year. 

### Coal Conversion to Natural Gas
As coal is being phased out due to the high emission levels, some plants are being converted into natural gas facilities. In these cases, the capacity flips from being for a coal technology to a natural gas technology. Specifically this is found in the Alberta H.R. Milner Generating Facility and in the Alberta Genesee Generating Facility. 

## Hydro 
We assume that all hydro stations are going to be maintained throughout the model run. Therefore, we used the more reliable [Canadian Energy Regulator](https://www.cer-rec.gc.ca/en/data-analysis/canada-energy-future/2019/results/index.html) residual capacity for hydro power. 

## Wind and Solar
The Wikipedia sources (listed in `dataSources/ResidualCapacitiesByProvince.csv`) usually provide commission dates for existing facilities and planned facilities. However, in some cases these dates could not be found. In cases where an existing plants commissioning date could not be found, it was estimated to be commissioned in 2010. In cases where planned facilities commissioning dates could not be found, they were estimated to open in 2025. 

## Natural Gas  
In the model we include two types of natural gas power plants, a combined cycle and a combustion turbine. In cases where there were insufficient information on the power plant to classify it as one or the other, it was assumed to be a combined cycle

## Biomass
All biomass capacities and commissioning data currently comes from Wikipedia as shown in `dataSources/ResidualCapacitiesByProvince.csv`. If the commissioning date of a facility could not be found it was assumed to be commissioned in 2010. 

## Trade
The residual capacity (installed capacity) for each province is collected from the [Government of Canada](https://www.nrcan.gc.ca/our-natural-resources/electricity-infrastructure/electricity-canada/canadas-electric-reliability-fra/newfoundland-and-labradors-electric-reliability-framework/18834) website. The provinces' values are added based on the model's regions. Thereafter, the electricity exports from each region to the U.S. are collected from [Statistics Canada](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=2510002101). The difference between each region's residual capacity and the U.S. exports are attained and divided into halves for regions with eastern and western neighboring regions.

## Assumptions 
* Capacity does **not** ramp down near the end of a stations life. The station goes from having full capacity in one year, to zero capacity after its retirement year
* Hydro stations are **not** decommissioned throughout our model run
