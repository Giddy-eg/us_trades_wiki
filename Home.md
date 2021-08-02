# Model Overview
## Purpose
The Role of U.S.-Canada Electricity Trade in North American Decarbonization Pathways

## Timeslicing 

### Seasons
The model is broken into four seasons, as summarized below. Each season starts/ends on the firs/last day of the month (ie. They do not start/end mid-month like in reality) 

| Season | Abbreviation | Months Included | 
|--------|--------------|--------------------|
| Winter | W            | January, February, December|
| Spring | SP           | April, May, March|
| Summer | S            | July, August, June|
| Fall   | F            | October, November, September|

### Seasonal Days
Each season in the model is represented by a single 24 hour day to simplify processing and solving. This results in 96 timeslices for each year. Representing each season as a full 24 hour day allows us to capture parameters that are sensitive to time of the day, such as solar, wind, and energy loads. This seasonal 24 timeslicing methodology is similar to Jayadev et al. paper on [US energy infrastructure planning](https://www.sciencedirect.com/science/article/abs/pii/S0306261919319543)

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
##Canada


| Model Region | Abbreviation | Provinces Included | 
|--------------|--------------|--------------------|
| West         | WS           | BC, Alberta |
| Mid-West     | MW           | Saskatchewan, Manitoba |
| Quebec       | QC           | Quebec |
| Ontario      | OT           | Ontario |
| Atlantic     | AT           | New Brunswick, Nova Scotia, PEI, Newfoundland Labrador |

#U.S.

|    Model Region   | Abbreviation | States Included                   | 
|-------------------|--------------|-----------------------------------|
| North West        | NW           | WA, OR                            |
| California        | CA           | CA                                |
| Mountain North    | MN	   | MT, ID, WY, NV, UT, CO            |
| Southwest         | SW           | AZ, NM                            |
| Central           | CE           | ND, SD, NE, KS, OK                |
| Texas             | TX           | TX                                |
| Midwest           | MW           | MN, WI, IA, IL, IN, MI, MO        | 
| Arkansas-Louisiana| AL           |AR, LA                             |
| Mid-Atlantic      | MA           | OH, PA, WV, KY, VA, NJ, DE, MD, DC|
| Southeast         | SE           | TN, NC, SC, MS, AL, GA            |
| Florida           | FL           | FL                                |
| New York          | NY           | NY                                |
| New England       | NE           | VT, NH, ME, MA, CT, RI            |
*U.S. Abbreviation [Link](https://pe.usps.com/text/pub28/28apb.htm)


## Technologies
### Power Generators

| Technology                           | Abbreviation |
|--------------------------------------|--------------|
| Coal                                 | COA | 
| Coal Carbon Capture and Sequestration| COC | 
| Combined Cycle Natural Gas           | CCG | 
| Combustion Turbine Natural Gas       | CTG |
| Hydro Power                          | HYD |
| Onshore Wind                         | WND | 
| Solar                                | SPV |
| Nuclear                              | URN | 
| Biomass                              | BIO | 

### Storage

| Technology          | Abbreviation |
|---------------------|--------------|
| | | 

### Fuels

| Fuel         | Abbreviation |
|--------------|--------------|
| Electricity  | ELC | 
| Hydro        | HYD |
| Solar        | SPV |
| Wind         | WND |
| Biomass      | BIO |
| Coal         | COA |
| Natural Gas  | GAS |
| Uranium      | URN |


## Units
Below is a table highlighting the input units for each parameter in the model 

| Parameter                                    | Units in Model    |
| -------------------------------------------  |:-----------------:|
| AccumulatedAnnualDemand 		       |      		   |
| AnnualEmissionLimit      		       |            	   |
| AnnualExogenousEmission 		       |            	   |
| AvailabilityFactor      		       | na    		   |
| CapacityFactor      			       | na                |
| CapacityOfOneTechnologyUnit     	       |      		   |
| CapitalCost      			       | M$/GW             |
| CapitalCostStorage 			       | M$/GW             |
| DiscountRate      			       |      		   |
| DiscountRateStorage      		       |           	   |
| EmissionActivityRatio 		       | MTon CO2 / PJ     |
| EmissionPenalty      			       | M$/MTon CO2       |
| FixedCost     		               | M$/GW             |
| InputActivityRatio 			       | na                |
| MinStorageCharge      		       |      		   |
| ModelPeriodEmissionLimit    		       |           	   |
| ModelPeriodExogenousEmission		       |           	   |
| OperationalLife    			       | Years             |
| OperationalLifeStorage    		       | Years             |
| OutputActivityRatio 			       | na                |
| Reserve Margin      			       | GW                |
| ResidualCapacity     			       | GW                |
| ResidualStorageCapacity 		       | GW                |
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
| Variable Cost      			       | M$/PJ             |