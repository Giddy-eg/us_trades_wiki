## Electricity Trade
The model allows for the trade of electricity between regions. 

## Canadian Trade 

The map below shows available electricity trading paths for each Canadian Region. The red 'X' indicates a modeled central trading station for the model to trade electricity. The red dashed line then indicates the approximated distance between each trading station. For the Atlantic region, the trading station was placed closer to New Brunswick and Nova Scotia as their annual demand is greater then that of Newfoundland and Labrador. The only purpose of the modeled central trading station is to indicate approximate distances new transmission lines will have to be built. This is further discussed in the capital cost section 

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

### Fixed Costs 
The Fixed Cost for transmission used in our model will be 0.0054$M/GW. The cost is collected from [Transmission Rate Projection](https://www.aeso.ca/assets/Uploads/AESO-2021-TRP-Fact-Sheet-FINAL.pdf).

### Variable Costs

## Efficiency 