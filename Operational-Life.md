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
| Hydrogen Storage Tank           | 30             | [Energy Efficiency & Renewable Energy](https://www.energy.gov/eere/fuelcells/doe-technical-targets-hydrogen-delivery)|
| Transmission Lines           | 100             | [How do electricity transmission lines withstand a lifetime of exposure to the elements?](https://engineering.mit.edu/engage/ask-an-engineer/how-do-electricity-transmission-lines-withstand-a-lifetime-of-exposure-to-the-elements/#:~:text=As%20long%20as%20electrical%20transmission,wrapped%20around%20steel%2Dreinforced%20cores.)|

### Hydro
We opted to use the operational life from the NREL because it estimated it to be 100 years. We want to impose the assumption that Hydro plants will not be shut down in the model, and instead maintained indefinitely. We set this assumption because Canada is very reliant on Hydro, and it is a renewable source. 

### Fuel Cells
The [Office of Energy Efficiency and Renewable Energy](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power) released a report for [Technical Targets for Fuel Cell Systems for Stationary Applications](https://www.energy.gov/eere/fuelcells/doe-technical-targets-fuel-cell-systems-stationary-combined-heat-and-power). In this report, the projected 2020 lifetime for a **stationary** fuel cell is 80,000hrs. We estimate this to be 10years. This lifetime is **not** representative of fuel cells used in the transportation industry.

Fuel Cells' operational life and duty cycle are dependent on various variables such as operation and temperature. In our model, we will use an operational life of 15 years (1.5 times the 80,000hrs) because of the limited operation of the fuel cell (66.7%). The references used for fuel cell life and duty cycle are [Degradation in PEM Fuel Cells and Mitigation Strategies Using System Design and Control](https://www.researchgate.net/publication/325048195_Degradation_in_PEM_Fuel_Cells_and_Mitigation_Strategies_Using_System_Design_and_Control),[Lifetime Prediction of a Polymer Electrolyte Membrane Fuel Cell under Automotive Load Cycling Using a Physically-Based Catalyst Degradation Model](https://www.researchgate.net/publication/326915743_Lifetime_Prediction_of_a_Polymer_Electrolyte_Membrane_Fuel_Cell_under_Automotive_Load_Cycling_Using_a_Physically-Based_Catalyst_Degradation_Model),[Estimating the end-of-life of PEM fuel cells: Guidelines and metrics](https://hal.archives-ouvertes.fr/hal-02380401/document), [Proton Exchange Membrane Fuel Cell](https://www.sciencedirect.com/topics/engineering/proton-exchange-membrane-fuel-cell),[Fuel Cells, Hydrogen and Fuel Cell Technologies Office](https://www.energy.gov/eere/fuelcells/fuel-cells),[BU-210: How does the Fuel Cell Work?](https://batteryuniversity.com/learn/article/fuel_cell_technology), [Status of Fuel Cells and the Challenges Facing Fuel Cell Technology Today](https://pubs.acs.org/doi/pdf/10.1021/bk-2010-1040.ch001?src=recsys), [Degradation in PEM Fuel Cells and Mitigation Strategies Using System Design and Control](https://www.intechopen.com/books/proton-exchange-membrane-fuel-cell/degradation-in-pem-fuel-cells-and-mitigation-strategies-using-system-design-and-control), [Degradation in PEM Fuel Cells and Mitigation Strategies Using System Design and Control](https://cdn.intechopen.com/pdfs/58665.pdf) & [A review of small stationary fuel cell performance](https://www.researchgate.net/publication/228692607_A_review_of_small_stationary_fuel_cell_performance)

### Power to Gas
The [Hydrogen Program](https://www.hydrogen.energy.gov/) released a report for [DOE Hydrogen and Fuel Cells Program Record](https://www.hydrogen.energy.gov/pdfs/19009_h2_production_cost_pem_electrolysis_2019.pdf). Based on this report which is dated February 3, 2020, the lifetime of the P2G is 20 years. 

### Hydrogen Storage Tank
The [Your storage mix: can Power-to-Gas (P2G) fit in?](https://nrc.canada.ca/en/stories/your-storage-mix-can-power-gas-p2g-fit) from the [Government of Canada](https://www.canada.ca/en.html) mentions that once the hydrogen gas has been generated, it can be stored almost indefinitely in hydrogen storage tanks. Hence, a large value "999999" is used for the operational life of storage in our model.

## Assumptions 
* The operational life for all technologies is the same for all regions
* Hydro stations will **not** be shut down throughout the model run 
* EIA Power Plant Assumptions for operational life have been compared with other sources to confirm accuracy. A tested example was the natural gas operational life which is 35 years and matches with [Combined-Cycle Plant Life Assessments](https://sargentlundy.com/wp-content/uploads/2017/05/Combined-Cycle-PowerPlant-LifeAssessment.pdf) and [Life Cycle Assessment of a Combined-Cycle Gas Turbine with a Focus on the Chemicals Used in Water Conditioning](https://www.mdpi.com/2071-1050/11/10/2912/htm).