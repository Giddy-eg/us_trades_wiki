# Definition
Three cost types are associated with all technologies in OSeMOSYS. These include capital costs, fixed operation and maintenance costs, and variable costs. If the technology uses a consumable fuel (coal, gas, uranium), the cost to purchase this fuel is built into the variable cost. 

# Sources

All generation technology costs for both countries are collected from the National Renewable Energy Laboratory [2020 Annual Technology Baseline](https://atb-archive.nrel.gov/electricity/2020/data.php). NREL provides a representative value for each technology category. This value is the one that most closely aligns with recently installed or anticipated near-term installations of electricity generation plants. We used the representative value capacity factor for each technology as it provides a reliable average baseline number for general geography.

The table below shows how we filtered the NREL data to retrieve values for each technology. 

| Model Technology    | atbyear | core_metric_parameter | core_metric_case | crpyears | technology    | techdetail  | Alias                      | scenario |
|---------------------|---------|-----------------------|------------------|----------|---------------|-------------|----------------------------|----------|
| Coal                |  2020   | Cost Type*            | Market           | 20       | Coal          | IGCCHighCF  | EIA Coal-New - High CF     | Moderate |
| Coal CCS            |  2020   | Cost Type*            | Market           | 20       | Coal          | CCS30HighCF | Coal-CCS-30%-High CF       | Moderate |
| Natural Gas CC      |  2020   | Cost Type*            | Market           | 20       | NaturalGas    | CCHighCF    | EIA Gas CC - High CF       | Moderate |
| Natural Gas CT**    |  2020   | Cost Type*            | Market           | 20       | NaturalGas    | CTHighCF    | Natural Gas EIA CT High CT | Moderate |
| Hydro Power         |  2020   | Cost Type*            | Market           | 20       | Hydropower    | NPD4        | Non-Powered Dams Class 4   | Moderate |
| Onshore Wind        |  2020   | Cost Type*            | Market           | 20       | LandbasedWind | LTRG4       | Wind Speed Class 4         | Moderate |
| Solar               |  2020   | Cost Type*            | Market           | 20       | UtilityPV     | KansasCity  | Kansas City                | Moderate |
| Nuclear             |  2020   | Cost Type*            | Market           | 20       | Nuclear       | na          | na                         | Moderate |
| Biomass             |  2020   | Cost Type*            | Market           | 20       | Biopower      | Dedicated   | EIA Dedicated              | Moderate | 

***Cost Type** will either be: CAPEX, Fixed O&M, Variable O&M, or Fuel

** **NOTE**: NREL did not explicitly provide a representative value for Natural Gas Combustion Turbine. From the raw data sheet, the representative value for Natural Gas Combustion Turbine was assumed to be "Natural Gas EIA CT High CF"

## Capital Cost
The capital expenditure value includes the general equipment and infrastructure, the electrical infrastructure and connections, the installation cost, the owners cost and the site cost. More information on included CAPEX costs can be found on [ATB Definitions Page](https://atb-archive.nrel.gov/electricity/2020/definitions.php) 

## Fixed Cost
The fixed operations and maintenance cost for all NREL technologies includes insurance, property taxes, site security, and project management fees for example. The complete list can be found on the [ATB Definitions Page](https://atb-archive.nrel.gov/electricity/2020/definitions.php)

## Variable Cost
The variable cost for all NREL technologies represents the cost of running the power plant, such as operation labor. Fuel costs represent the cost of purchasing consumable fuel for the plant. Summing these values together gives us the input variable cost for our model. More information on these values can be found on the [ATB Definitions Page](https://atb-archive.nrel.gov/electricity/2020/definitions.php)

# United States Location Variation
The ATB data doesn't include regional capital cost multipliers, so we applied the location variation data from [EIA Capital Cost Study](https://www.eia.gov/analysis/studies/powerplants/capitalcost/pdf/capital_cost_AEO2020.pdf) to the ATB cost data for the United States. The regional multipliers were the average location variation values of states within a certain region. 