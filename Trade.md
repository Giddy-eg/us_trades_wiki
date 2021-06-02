## Electricity Trade
The model allows for the trade of electricity between regions. 

## Canadian Trade 

The map below shows available electricity trading paths for each Canadian Region. The red 'X' indicates a modeled central trading station for each region. The red dashed line then indicate available trade paths and approximate distances between each trading station. While the model does not utilize the distances between the trading station, our input data requires it. Capital cost numbers based on capacity could not be found. However, there is ample literature on average cost for transmission lines based on distances. Therefore, we found approximate distances to build new transmission lines and used this number to calculate capital costs. 

The Atlantic region had two options for trade distances. We could either use a distance that ends in New Brunswick, or a distance that ends in Newfoundland and Labrador. We approximated the distance to end in closer to New Brunswick and Nova Scotia as their annual demand is greater then that of Newfoundland and Labrador.  

<img src="https://i.postimg.cc/3xPZMG2w/Canadian-Trading.png" data-canonical-src="https://i.postimg.cc/3xPZMG2w/Canadian-Trading.png" width="525" height="450" />

| Start Region | End Region | Distance (km) |
|--------------|------------|---------------|
| West         | Mid West   | 1200 |
| Mid West     | Ontario    | 1300 |
| Ontario      | Quebec     | 800 |
| Quebec       | Atlantic   | 700 |

## Costs

### Capital Costs  
The Capital Cost for transmission depends on several factors such as number of circuits, voltage ratings and distance. The current cost used in our model is considering 500kV, double circuits (3.0$M/km). The costs are collected from: 
* [Transmission Cost Estimation Guide](https://cdn.misoenergy.org/20190212%20PSC%20Item%2005a%20Transmission%20Cost%20Estimation%20Guide%20for%20MTEP%202019_for%20review317692.pdf) 
* [ELECTRICITY 101](https://electricity.ca/wp-content/uploads/2017/12/Electricity101_July-11_2018.pdf) 
* [CAPITAL COSTS FOR TRANSMISSION AND SUBSTATIONS](https://www.wecc.org/reliability/1210_bv_wecc_transcostreport_final.pdf).
* The load carrying capability of the transmission line is measured in terms of Surge Impedance Loading (SIL). The load-ability of a transmission line is 100% at 300 miles (482.8km). The load-ability of the 500kV transmission line at 100%(300 miles) is 900MW. Therefore the transmission capital cost per power is calculated below:
* 482.8km x $3M/km = $1,448.4M for 900MW @100% (0.9GW @100%)
==> $1,609.3M/GW

The transmission SIL measurement are located in [AMERICAN ELECTRIC POWER-Transmission Facts](https://web.ecs.baylor.edu/faculty/grady/_13_EE392J_2_Spring11_AEP_Transmission_Facts.pdf), [Transmission Lines Electricity's Highways](https://site.ieee.org/northern-canada-pesias/files/2013/01/Transmission-Lines-Presentation.pdf), [ENG 505 - ENERGY SURETY AND SYSTEMS-Electricity Transmission Systems](https://www.osti.gov/servlets/purl/1117566).

### Fixed Costs 
The Fixed Cost for transmission used in our model will be 0.0054$M/GW. The cost is collected from [Transmission Rate Projection](https://www.aeso.ca/assets/Uploads/AESO-2021-TRP-Fact-Sheet-FINAL.pdf).

### Variable Costs

## Efficiency 