## Variance in Data
Researching the operational life of various technologies proved to be difficult as sources often disagreed on appropriate values. For example, the [2017 EIA Annual Energy Outlook Report](https://www.eia.gov/outlooks/aeo/assumptions/pdf/0554(2017).pdf) which provides our Input Activity Ratios has significantly lower values compared to the [NREL 2020 Annual Technology Baseline](https://atb.nrel.gov/electricity/2020/definitions.php) which provides our costs. 

We have currently implemented the majority of service life values provided by the [EIA Power Plant Assumptions](https://www.eia.gov/outlooks/aeo/assumptions/). Other references collected for this model provided numbers that closely aligned with the NREL values.  For further information about different government agency power plant operational lifetimes, Table 11 in this [Cost and Performance Assumptions for Modeling Electricity Generation Technologies](https://www.nrel.gov/docs/fy11osti/48595.pdf) created by NREL gives an overview of operational life variation. 

Due to the variability in operational life values from reputable sources, it will be good to perform a sensitivity analysis to further understand how the operational life effects renewable investment, emissions, and system cost. 

## Sources
The following table shows the operational life values used 
| Technology                      | Operational Life (Years) | Source |
|---------------------------------|--------------------------|--------|
| Coal                            | 45 			     | EIA Power Plant Assumptions |
| Coal Carbon Capture             | 45 			     | EIA Power Plant Assumptions |
| Natural Gas Combined Cycle      | 35 			     | EIA Power Plant Assumptions |
| Natural Gas Combustion Turbine  | 35 			     | EIA Power Plant Assumptions |
| Nuclear      	                  | 60 			     | EIA Power Plant Assumptions |
| Wind         	                  | 30 			     | EIA Power Plant Assumptions |             
| Solar        	                  | 30 			     | EIA Power Plant Assumptions |
| Hydro        	                  | 100 	             | [NREL 2020 Annual Technology Baseline](https://atb.nrel.gov/electricity/2020/definitions.php) |
| Biomass     	                  | 45 			     | EIA Power Plant Assumptions |
| Oil          	                  |      		     |  |
| Power to Gas                    | 20			     | [DOE Hydrogen and Fuel Cells Program Record](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf) |
| Hydrogen Fuel Cell              | 10			     | [Office of Energy Efficiency and Renewable Energy](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power) |

### Hydro
We opted to use the operational life from the NREL because it estimated it to be 100 years. We want to impose the assumption that Hydro plants will not be shut down in the model, and instead maintained indefinitely. We set this assumption because Canada is very reliant on Hydro, and it is a renewable source. 

### Fuel Cells
The [Office of Energy Efficiency and Renewable Energy](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power) released a report for [Technical Targets for Fuel Cell Systems for Stationary Applications](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power). In this report, the projected 2020 lifetime for a **stationary** fuel cell is 80,000hrs. We estimate this to be 10years. This lifetime is **not** representative of fuel cells used in the transportation industry

### Power to Gas
The [Hydrogen Program](https://www.hydrogen.energy.gov/) released a report for [DOE Hydrogen and Fuel Cells Program Record](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf). Based on this report which is dated February 3, 2020, the lifetime of the P2G is 20 years. 

## Assumptions 
* The operational life for all technologies is the same for all regions
* Hydro stations will **not** be shut down throughout the model run 