## Electricity Trade
The model allows for the trade of electricity between regions. 

## Canadian Trade 

The map below shows available electricity trading paths for each Canadian Region. The red 'X' indicates a modeled central trading station for each region. The red dashed line then indicate available trade paths and approximate distances between each trading station. While the model does not utilize the distances between the trading station, our input data requires it. Capital cost numbers based on capacity could not be found. However, there is ample literature on average cost for transmission lines based on distances. Therefore, we found approximate distances to build new transmission lines and used this number to calculate capital costs. 

The Atlantic region had two options for trade distances. We could either use a distance that ends in New Brunswick, or a distance that ends in Newfoundland and Labrador. We approximated the distance to end in closer to New Brunswick and Nova Scotia as their annual demand is greater then that of Newfoundland and Labrador.  

<img src="https://i.postimg.cc/3xPZMG2w/Canadian-Trading.png" data-canonical-src="https://i.postimg.cc/3xPZMG2w/Canadian-Trading.png" width="525" height="450" />

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

Based on the [St. Clair curve](https://www.researchgate.net/figure/The-St-Clair-curve-as-based-on-the-results-of-14-retrieved-from-15-is-used-to_fig3_318692193), the transmission line load limit reduces as the distance increases. This is due to the increase in resistance and additional power losses. Using this curve and the estimated distance between each region, the load-ability and cost per power is calculated and presented in the table below.

| Start Region | End Region | Distance (km) |  Load-Ability (GW)  |      Cost/Power ($/GW)     |
|--------------|------------|---------------|---------------------|----------------------------|
| West         | Mid West   | 795           | 0.75 x 0.9 = 0.675  | 795 x 3 / 0.675 = 3,533    |
| Mid West     | Ontario    | 952           | 0.63 x 0.9 = 0.567  | 952 x 3 / 0.567 = 5,037    |
| Ontario      | Quebec     | 1,138         | 0.625 x 0.9 = 0.563 | 1,138 x 3 / 0.563 = 6,064  |
| Quebec       | Atlantic   | 913           | 0.635 x 0.9 = 0.572 | 913 x 3 / 0.572 = 4,788    |

### Fixed Costs 
The Fixed Cost for transmission used in our model will be 0.0054$M/GW. The cost is collected from [Transmission Rate Projection](https://www.aeso.ca/assets/Uploads/AESO-2021-TRP-Fact-Sheet-FINAL.pdf).

### Variable Costs

## Efficiency 

## International Trade Locations
Th Center for Strategies and International Studies published [this figure](https://www.csis.org/analysis/mapping-us-canada-energy-relationship) which highlights Canadian and USA trade locations. In total there are 25 trade locations that have been incorporated. 

| Start Region    | End Region | Distance (km) |
|-----------------|------------|---------------|
| Canada West     | USA North West     | |
| Canada West     | USA Mountain North | |
| Canada Mid West | USA Central East   | |
| Canada Mid West | USA Mid West       | |
| Canada Ontario  | USA Mid West       | |
| Canada Ontario  | USA New York       | |
| Canada Quebec   | USA New York       | |
| Canada Quebec   | USA New England    | |
| Canada Atlantic | USA New England    | |