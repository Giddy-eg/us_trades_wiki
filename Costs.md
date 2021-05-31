
## National Renewable Energy Laboratory
In numerous situations, the capital costs, fixed costs and variable costs were taken from the National Renewable Energy Laboratory [2020 Annual Technology Baseline](https://atb.nrel.gov/electricity/2020/data.php). While this is a United States focused report, it provides lower, mid, and upper cost values for the majority of technologies in our model. Moreover, this data set was utilized by Jaydev et. Al in [U.S. electricity infrastructure of the future: Generation and transmission pathways through 2050](https://www.sciencedirect.com/science/article/abs/pii/S0306261919319543). 

Using the NREL data source provides us with reliable cost figures in one place. Although they are not Canada specific, thus introducing error, it saves significant data collection time and allows us to move forward with other modelling aspects. Once the model is in a more complete form, this data set can be updated to reflect Canadian Numbers. 

The following global parameters were applied to the NREL database. Notes on the `core_metric_parameter` column can be found in each cost section (Capital, Fixed, Variable) below. 

| Model Technology    | atbyear | core_metric_parameter | core_metric_case | crpyears | technology    | techdetail | scenario |
|---------------------|---------|-----------------------|------------------|----------|---------------|------------|----------|
| Coal                |  2020   | See Cost Section      | Market           | 20       | Coal          | IGCCHighCF | Moderate |
| Coal CCS            |  2020   | See Cost Section      | Market           | 20       | Coal          | IGCCHighCF | Moderate |
| Natural Gas CC      |  2020   | See Cost Section      | Market           | 20       | NaturalGas    | CCHighCF   | Moderate |
| Natural Gas CT      |  2020   | See Cost Section      | Market           | 20       | NaturalGas    | CTHighCF   | Moderate |
| Hydro Power         |  2020   | See Cost Section      | Market           | 20       | Hydropower    | NPD4       | Moderate |
| Onshore Wind        |  2020   | See Cost Section      | Market           | 20       | LandbasedWind | LTRG4      | Moderate |
| Solar               |  2020   | See Cost Section      | Market           | 20       | UtilityPV     | KansasCity | Moderate |
| Nuclear             |  2020   | See Cost Section      | Market           | 20       | Nuclear       | na         | Moderate |
| Biomass             |  2020   | See Cost Section      | Market           | 20       | Biopower      | Dedicated  | Moderate |

### Global Parameters 
- atbyear = 2020: Published data set year to take the cost values from  
- core_metric_case = Market: Financial Assumption that will only impact LCOE, which we are not using from this database. More information [here](https://atb.nrel.gov/electricity/2020/definitions.php)
- crpyears = 20: 
- scenario = Moderate: This is the business as usual scenario. The [NREL Defenition](https://atb.nrel.gov/electricity/2020/definitions.php) is "Innovations observed in today's marketplace become more widespread, and innovations that are nearly market-ready today come into the marketplace. Current levels of public and private R&D investment continue. This scenario may be considered the expected level of technology innovation."

### Database Standard Assumptions
The following are the standard assumptions provided by [NREL](https://atb.nrel.gov/electricity/2020/definitions.php)

- Labor cost: Labor costs are the average of union and nonunion labor rates
- Regional Cost Variation: Capital costs represent a national average benchmark. Regional variations are not applied.
- Materials Cost Index: Materials costs are given in 2018 U.S. dollars, using the Consumer Price Index (BLS, 2020) for dollar year conversions, unless otherwise noted.
- Scale of Industry: Technology costs assume fully mature and industrialized supply chain and manufacturing capacity for a given technology and economies of scale are reached.
- Policies and Regulations: Financial assumptions include current laws and regulatory regimes only.
- Inflation: All values are given in 2018 U.S. dollars, using the Consumer Price Index (BLS, 2020) for dollar year conversions. Projections use an inflation assumption of 2.5% per year

### Technology Details Category
Technology details indicate resource levels and specific technology subcategories. A range giving maximum and minimum values for each technology are filtered through the technology details column. 

NREL provides a representative value for each category. This value is the one that most closely aligns with recently installed or anticipated near-term installations of electricity generation plants. We used the representative value cost for each technology as it provides a reliable average baseline number for all geography. If costs are calculated based on region, then the technology details category can be used to find geographically accurate numbers. The representative value for each technology is shown in the table below. More information on how this number was calculated can be found on the [NREL ATO Webpage](https://atb.nrel.gov/electricity/2020/definitions.php)

| Technology                     | Technology Detail          | Abbreviation |
|--------------------------------|----------------------------|--------------|
| Coal                           | EIA Coal-New - High CF     | IGCCHighCF   |
| Coal Carbon Capture            | Coal-CCS-30%-High CF       | CCS30HighCF  |
| Hydropower                     | Non-Powered Dams Class 4   | NPD4         |
| Natural Gas Combined Cycle     | EIA Gas CC - High CF       | CCHighCF     |
| Natural Gas Combustion Turbine | Natural Gas EIA CT High CT | CTHighCF     |
| LandbasedWind                  | Wind Speed Class 4         | LTRG4        |
| Utility Scale PV               | Kansas City                | KansasCity   |
| Nuclear                        | na                         | na           |
| Biopower                       | EIA Dedicated              | Dedicated    |

NOTE: No nuclear range was represented in the ATB
NOTE: NREL did not explicitly provide a representative value for Natural Gas Combustion Turbine. From the raw data sheet, the representative value for Natural Gas Combustion Turbine was assumed to be "Natural Gas EIA CT High CF"

## Capital Cost
### NREL Database 
The capital cost for all NREL technologies was found by filtering the `core_metric_parameter` by Capital Expenditure (CAPEX). This capital expenditure figure includes the general equipment and infrastructure, the electrical infrastructure and connections, the installation cost, the owners cost and the site cost. More information on included CAPEX costs can be found on [NREL Definitions Page](https://atb.nrel.gov/electricity/2020/definitions.php) 

### Fuel Cells
The United States Office of Energy Efficiency and Renewable Energy published [Technical Targets for Stationary Fuel Cell Systems](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power). This listed the installation cost of combined heat and power fuel cell systems operating on natural gas. We assumed this number to be the capital cost for stationary hydrogen fuel cell systems. 

### Power to Gas
The Hydrogen Program from the [Energy.Gov](https://www.hydrogen.energy.gov/) published [Cost of Electrolytic Hydrogen Production with Existing Technology](https://www.hydrogen.energy.gov/pdfs/20004-cost-electrolytic-hydrogen-production.pdf) in the DOE Hydrogen and Fuel Cells Program Record on September 14, 2020. The document contains the current and future capital cost for P2G PEM which is used in our model.

### Hydrogen Storage Tank
The capital cost of Stationary Gaseous Hydrogen Storage Tanks was collected from [DOE Technical Targets for Hydrogen Delivery](https://www.energy.gov/eere/fuelcells/doe-technical-targets-hydrogen-delivery). The Total Electrical Usage ratio of 51.4 kWh/kg [Ref.](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf) was used to calculate the correct units ($/GW).

### Transmission 
The capital Cost for transmission depends on several factors such as number of circuits, voltage ratings and distance. The current cost used in our model will be 1.65$M/km. The costs are collected from [Transmission Cost Estimation Guide](https://cdn.misoenergy.org/20190212%20PSC%20Item%2005a%20Transmission%20Cost%20Estimation%20Guide%20for%20MTEP%202019_for%20review317692.pdf), [ELECTRICITY 101](https://electricity.ca/wp-content/uploads/2017/12/Electricity101_July-11_2018.pdf) & [CAPITAL COSTS FOR TRANSMISSION AND SUBSTATIONS](https://www.wecc.org/reliability/1210_bv_wecc_transcostreport_final.pdf).

## Fixed Cost
### NREL Database 
The fixed cost for all NREL technologies was found by filtering the `core_metric_parameter` by Fixed Operation and Maintence (Fixed O&M). This Operations and Maintenance figure includes insurance, property taxes, site security, and project management fees for example. The complete list can be found on the [NREL Definitions Page](https://atb.nrel.gov/electricity/2020/definitions.php)

### Fuel Cells 
The United States Office of Energy Efficiency and Renewable Energy published [Technical Targets for Stationary Fuel Cell Systems](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power). This listed the Annual maintenance cost equal to 2% of the equipment cost for combined heat and power fuel cell systems operating on natural gas. We assumed this number to be the fixed cost for stationary hydrogen fuel cell systems.

### Power to Gas
The PEM fixed costs are from the [Hydrogen Production Cost From PEM Electrolysis - 2019](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf) published in February 3, 2019 in the DOE Hydrogen and Fuel Cells Program Record. The 2019 and 2035 fixed cost for Distributed Capacity was collected and is used in our model. The Total Electrical Usage ratio of 51.4 kWh/kg [Ref.](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf) was used to calculate the correct units ($/GW).

### Transmission 
The Fixed Cost for transmission used in our model will be 0.0054$M/GW. The cost is collected from [Transmission Rate Projection](https://www.aeso.ca/assets/Uploads/AESO-2021-TRP-Fact-Sheet-FINAL.pdf).

## Variable Cost
### NREL Database 
The variable cost for all NREL technologies was found by filtering the `core_metric_parameter` by Variable Operation and Maintenance (Variable O&M) and Fuel. These values represent the cost of running the power plant, such as operation labor, and the cost of purchasing fuel for the plant. Summing these values together gives us the input variable cost for our model. More information on these values can be found on the [NREL Definitions Page](https://atb.nrel.gov/electricity/2020/definitions.php)

### Fuel Cells 

### Power to Gas
The variable cost for PEM was found in [Techno-economic Analysis of PEM Electrolysis for Hydrogen Production](https://www.energy.gov/sites/prod/files/2014/08/f18/fcto_2014_electrolytic_h2_wkshp_colella1.pdf) dated February 27, 2014. A conservative value was added to our model following this document and using the Total Electrical Usage ratio of 51.4 kWh/kg [Ref.](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf) to attain the correct units ($/PJ).