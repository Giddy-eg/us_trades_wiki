## US Energy Information Administration 
To determine the efficiencies for each technology,  the EIA [2017 Annual Energy Outlook](https://www.eia.gov/outlooks/aeo/) was referenced. Specifically, Table 8.2 in their Assumptions documentation titled [Cost and Performance Characteristics of New Generating Technologies](https://www.eia.gov/outlooks/aeo/assumptions/pdf/0554(2017).pdf) was used. 

Table 8.2 provided heat rates for technologies in Btu/kWh. EIA further explains in [this FAQ page](https://www.eia.gov/tools/faqs/faq.php?id=107&t=3) how to use heat rate to calculate power plant efficiency. 
> To express the efficiency of a generator or power plant as a percentage, divide the equivalent Btu content of a kWh of electricity (3,412 Btu) by the heat rate.

Below is a table summarizing the values extracted from Table 8.2 in the 2017 AEO Assumptions. **We have assumed that the efficiency of the technology does not change throughout the model**

| Model Technology                      | EIA Technology                          | Heat Rate [Btu/kWh] | Efficiency (%) |
|---------------------------------------|-----------------------------------------|---------------------|----------------|
| Coal                                  | Integrated Coal-Gasification Comb Cycle | 8,700               | 39.2           |
| Coal Carbon Capture and Sequestration | Coal with 30% CCS                       | 9,750               | 35.0           |
| Nuclear                               | Adv Nuclear                             | 10,459              | 32.6           |
| Natural Gas Combined Cycle            | Conv Gas/Oil Combined Cycle             | 6,600               | 51.7           |
| Natural Gas Combustion Turbine        | Conv Combustion Turbine                 | 9,600               | 35.5           |
| Biomass                               | Biomass                                 | 13,500              | 25.3           |

### Coal Heat Rate
The [2017 Annual Energy Outlook Assumptions](https://www.eia.gov/outlooks/aeo/assumptions/pdf/0554(2017).pdf) does not list the heat rate of coal. Instead it notes that 
> AEO 2017 assumes new coal plants without CCS cannot be built, due to emission standards for the new plants. These technologies exist in the modeling framework, but are not assumed available to be built in the projections

Therefore, the heat rate for coal was taken from the [2014 Annual Energy Outlook Assumptuions](https://www.eia.gov/outlooks/aeo/assumptions/pdf/0554(2014).pdf). Table 8.2 Cost and performance characteristics of new central station electricity generating technologies lists the heat rate for Integrated Coal-Gasification Combined Cycle. 

## Renewable Technologies
Updated in the [2021 AEO Assumptions Table 8.1](https://www.eia.gov/outlooks/aeo/assumptions/pdf/table_8.2.pdf) was is the note for hydropower, wind, and solar, no heat rate is reported because the power is generated without fuel combustion and no set British thermal unit conversion factors exists. This also matches up with our assumption of the technologies operating at 100 percent efficiency (ie. one unit of water can be converted into one unit of electricity). We used the 2017 report numbers instead of the 2021 report values because it gave more aggregated general heat rates for technologies. For example, 2017 gave one category for conventional natural gas combined cycles, while 2021 broke it down into single shaft and multi shaft combined cycles. This provided numbers with greater detail then we required. 

## Power to Gas Efficiency
The P2G efficiency for 2019-2050 came from [Hydrogen production by PEM water electrolysis](https://www.sciencedirect.com/science/article/pii/S2589299119300035) published December 2019.

## Fuel Cell Efficiency
The Fuel Cell efficiency came from [U.S. Department of Energy - Fuel Cell Technologies Office](https://www.energy.gov/sites/prod/files/2015/11/f27/fcto_fuel_cells_fact_sheet.pdf) and [Power Technology - Realising the hydrogen economy](https://www.power-technology.com/comment/standing-at-the-precipice-of-the-hydrogen-economy/#:~:text=A%20fuel%20cell%2C%20by%20contrast,to%2060%20per%20cent%20efficiency.&text=per%20cent%20efficiency.-,A%20fuel%20cell%2C%20by%20contrast%2C%20can%20mix%20hydrogen%20with%20air,to%2060%20per%20cent%20efficiency.).