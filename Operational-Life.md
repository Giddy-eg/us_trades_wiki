## Variance in Data
Researching the operational life of various technologies proved to be difficult as sources often disagreed on appropriate values. For example, the [2017 EIA Annual Energy Outlook Report](https://www.eia.gov/outlooks/aeo/assumptions/pdf/0554(2017).pdf) which provides our Input Activity Ratios has significantly lower values compared to the [NREL 2020 Annual Technology Baseline](https://atb.nrel.gov/electricity/2020/definitions.php) which provides our costs. 

We have currently implemented the [NREL 2020 Annual Technology Baseline](https://atb.nrel.gov/electricity/2020/definitions.php) operations life values, which are listed as Technical Life. Other references collected for this model provided numbers that closely aligned with the NREL values.  For further information about different government agency power plant operational lifetimes, Table 11 in this [Cost and Performance Assumptions for Modeling Electricity Generation Technologies](https://www.nrel.gov/docs/fy11osti/48595.pdf) created by NREL gives an overview of operational life variation. 

Due to the variability in operational life values from reputable sources, it will be good to perform a sensitivity analysis to further understand how the operational life effects renewable investment, emissions, and system cost. 

## Sources
The following table shows the operational life values used 
| Technology          | Operational Life (Years) | Source |
|---------------------|--------------------------|--------|
| Coal                | 45 			 |  |
| Coal Carbon Capture | 45 			 |  |
| Natural Gas         | 35 			 |  |
| Nuclear      	      | 60 			 |  |
| Wind         	      | 30 			 |  |             
| Solar        	      | 30 			 |  |
| Biomass     	      | 45 			 |  |
| Oil          	      | 10   			 |  |
| Power to Gas        | 10 			 |  |
| Hydrogen Fuel Cell  | 10			 | [Office of Energy Efficiency and Renewable Energy](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power) |

### Fuel Cells
The [Office of Energy Efficiency and Renewable Energy](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power) released a report for [Technical Targets for Fuel Cell Systems for Stationary Applications](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power). In this report, the projected 2020 lifetime for a **stationary** fuel cell is 80,000hrs. We estimate this to be 10years. This lifetime is **not** representative of fuel cells used in the transportation industry

### Power to Gas
**Not seeing where our Power to Gas Operational life is coming from**

## Assumptions 
* The operational life for all technologies is the same for all regions