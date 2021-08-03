## Sources
## CANADA
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

## Assumptions 
* Capacity does **not** ramp down near the end of a stations life. The station goes from having full capacity in one year, to zero capacity after its retirement year
* Hydro stations are **not** decommissioned throughout our model run

## U.S.
The U.S. residual capacity data is collected from the 3_1_GeneratorYyyyy.xlsx in [EIA-860 data set](https://www.eia.gov/electricity/data/eia860/). For example, the excel file we are processing in 2019 EIA-860 data is 3_1_GeneratorY2019.xlsx. Three tabs are included in this generator dataset that we are considering are shown as follows.
* Operable: includes those generators which are currently operating, out of service or on standby;
* Proposed: includes those generators which are planned and not yet in operation; and
* Retired: only includes those retired generators which were reported in the most current data cycle.

### Estimated Retirement Year
Since only few power plants have the proposed retirement year listed in the data set, we estimate the retirement year of a power plant of a certain type of technology by operating year + technology lifetime. For example, a hydro electric power plant was operating since 1981 and the hydro electric has 100 years of operational life, the estimated retirement year is 2081. 

### Capacity for Technologies in Each Year
Residual capacity refers to the generation capacities that are already installed in the base year (operating year), which the model inherits by exogenous specification. After the base year, those residual capacity plants remain available, although some are assumed to totally or partially retire in particular years. To evaluate the residual capacity of a power plant, there are two cases we need to consider. 
* For those power plants which should retire but haven't, we reduce its capacity linearly after the proposed retirement year. For example, a power plant started to operate in 1971 with 40 years of the lifetime but hasn't retired (2019 > 2011), we retire 1/40 of the initial capacity linearly each year starting from the year 2011 till zero capacity.
* For those normally operating powerplants, for example, a power plant that started to operate in 2010 with the lifetime of 15 years (retirement year 2025 > 2019), we set this power plant to be retired in the year 2025, i.e., the capacity of this power plant before the retirement year is the initial capacity, but is 0 starting from the year 2025. 

### Capacity of Proposed Power Plants
Since power plants shown in the "Proposed" tab are still in plan or not operable, we assume there is the half chance of operating in the future and half chance not, so only half of the original capacity will be considered before the retirement year.

### Capacity of Retirement Power Plants
We reduce the regional capacity by a retired power plant's initial capacity starting from its retirement year.

Overall, the regional residual capacity for a type of technology T in the year Y is calculated by aggregating all power plants' capacity of technology T in the year Y in this region.