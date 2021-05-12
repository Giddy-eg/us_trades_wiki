# Model Overview
## Purpose
The Role of U.S.-Canada Electricity Trade in North American Decarbonization Pathways

## Timeslicing 

### Seasons
The model is broken into four seasons, as summarized below. Each season starts/ends on the firs/last day of the month (ie. They do not start/end mid-month like in reality) 

| Season | Abbreviation | Months Included | 
|--------|--------------|--------------------|
| Winter | W            | January, February, March |
| Spring | SP           | April, May, June |
| Summer | S            | July, August, September |
| Fall   | F            | October, November, December |

### Time Zones
A "Model Time" is implemented to account for time zone differences. British Columbia is referenced as "Time Zero" and data is shifted for each time zone accordingly. This allows time zone differences to be included in how the model uses transmission. The table below summarizes the time shifts per province. An example on how to read this table is, the input demand at 2pm Local BC time is matched up with the input demand at 3pm Local Alberta Time. 

| Time Zone | Time Shift | Provinces Included | 
|-----------|------------|--------------------|
| PDT       | 0          | British Columbia |
| MDT       | +1         | Alberta |
| CDT       | +2         | Saskatchewan, Manitoba |
| EDT       | +3         | Ontario, Quebec |
| ADT       | +4         | New Brunswick, Nova Scotia, PEI, Newfoundland Labrador |

Our model represents Canada using 5 time zones. In reality, there are 6 time zones. Newfoundland operates on a time zone 30min ahead of the Atlantic time zone. Since our timeslicing is done on an hourly basis, it does not lend itself well to accommodate this. Therefore, we group all Newfoundland and Labrador data into the Atlantic time zone. 

Saskatchewan does not observe daylight savings time. Therefore, during the summer its time matches Alberta, and during the winter its time matches Manitoba. To simplify data processing, we have grouped Saskatchewan into the Central Time Zone with Manitoba. More information about Canadian time zones and daylight savings can be found [here](https://en.wikipedia.org/wiki/Daylight_saving_time_in_Canada)

## Regions 
The model currently includes the 10 Canadian provinces, with plans to add in the mainland United States in the future. The table below summarizes how the provinces were separated into modeled regions. 

| Model Region | Abbreviation | Provinces Included | 
|--------------|--------------|--------------------|
| West         | W            | BC, Alberta |
| Mid-West     | MW           | Saskatchewan, Manitoba |
| Mid-East     | ME           | Ontario, New Brunswick |
| East         | E            | Quebec, Nova Scotia, PEI, Newfoundland Labrador |

## Technologies
### Power Generators

| Technology          | Abbreviation |
|---------------------|--------------|
| Coal                | CL | 
| Natural Gas         | GS | 
| Hydro Power         | HYD |
| Onshore Wind        | WN | 
| Solar               | PV |
| Nuclear             | NUC | 
| Biomass             | BIO | 
| Oil                 | OI |
| Power to Gas        | P2G |
| Hydrogen Fuel Cells | FC | 

### Mining 

| Technology          | Abbreviation |
|---------------------|--------------|
| Coal                | MIN_CL | 
| Natural Gas         | MIN_GS | 
| Hydro Power         | MIN_HYD |
| Onshore Wind        | MIN_WN | 
| Solar               | MIN_PV |
| Nuclear             | MIN_NUC | 
| Biomass             | MIN_BIO | 
| Oil                 | MIN_OI |

### Storage

| Technology          | Abbreviation |
|---------------------|--------------|
| Hydrogen Storage    | TANK | 

### Fuels

| Fuel         | Abbreviation |
|--------------|--------------|
| Electricity  | ELC | 
| Hydrogen     | H2 |

## Units
Below is a table hihglighting the input units for each parameter in the model 

| Parameter                                    | Units in Model    |
| -------------------------------------------  |:-----------------:|
| AccumulatedAnnualDemand 		       |      		   |
| AnnualEmissionLimit      		       |            	   |
| AnnualExogenousEmission 		       |            	   |
| AvailabilityFactor      		       |      		   |
| CapacityFactor      			       | na                |
| CapacityOfOneTechnologyUnit     	       |      		   |
| CapitalCost      			       | $/GW              |
| CapitalCostStorage 			       | Update            |
| DiscountRate      			       |      		   |
| DiscountRateStorage      		       |           	   |
| EmissionActivityRatio 		       | Tonne CO2 / PJ    |
| EmissionPenalty      			       | $/Tonne CO2       |
| FixedCost     		               | $/GW              |
| InputActivityRatio 			       | na                |
| MinStorageCharge      		       |      		   |
| ModelPeriodEmissionLimit    		       |           	   |
| ModelPeriodExogenousEmission		       |           	   |
| OperationalLife    			       | Years             |
| OperationalLifeStorage    		       | Years             |
| OutputActivityRatio 			       | na                |
| Reserve Margin      			       | update            |
| ResidualCapacity     			       | GW                |
| ResidualStorageCapacity 		       |                   |
| SpecifiedAnnualDemand      		       | PJ                |
| SpecifiedDemandProfile 		       | na                |
| StorageLevelStart    			       |      		   |
| StorageMaxChargeRate     		       |           	   |
| StorageMaxDischargeRate 		       |           	   |
| TotalAnnualMaxCapacity      		       |      		   |
| TotalAnnualMaxCapacityInvestment             |           	   |
| TotalAnnualMinCapacity 	       	       | 	       	   |
| TotalAnnualMinCapacityInvestment             |      	   	   |
| TotalTechnologyAnnualActivityLowerLimit      |           	   |
| TotalTechnologyAnnualActivityUpperLimit      |           	   |
| TotalTechnologyModelPeriodActivityLowerLimit |           	   |
| TotalTechnologyModelPeriodActivityUpperLimit |           	   |
| Variable Cost      			       | $/PJ              |