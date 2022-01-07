# Project Overview 

Mitigating climate change will require Canada and the United States to significantly decarbonize their economies. Expanding electricity trade capacity between these countries could help each system decarbonize in a more cost-effective manner. Greater electricity trade would enable both countries to leverage the most favorable low- and zero-carbon resources though utilizing geographical advantages seen in specific regions. A long-term electricity system model can be implemented to study and quantitatively investigate the most economical pathways to reach full decarbonization.  

# Model Overview 

This section will provide the user with general background information on the model. Included is background information on the modelling framework, the temporal and spatial resolution, and the technologies and commodities included. 

## Modelling Framework 

The Open Source Energy Modeling System ([OSeMOSYS](https://osemosys.readthedocs.io/en/latest/)) is a fully open-source modelling framework designed to support long-run energy planning studies. It is a deterministic, linear, least-cost optimization modelling framework that can cover all, or any subset of, energy sectors. Moreover, OSeMOSYS supports easy user configuration and has an active online community in the form of a [Google Group](https://groups.google.com/g/osemosys) to help troubleshoot the models. The reputability and open-source community surrounding OSeMOSYS makes it an ideal candidate to support our research question. 

## Spatial Resolution

Our model supports analysis of all Canadian provinces (no territories) and the continental US States. The default spatial groupings are shown below (following standard [abbreviations](https://www.ncbi.nlm.nih.gov/books/NBK7254/)). Users are free to create their own spatial groupings via the configuration file, with spatial resolution as fine as individual provinces/states supported.

### Canadian Regions

| Model Region | Abbreviation | Provinces Included | 
|--------------|--------------|--------------------|
| West         | WS           | BC, AB |
| Mid-West     | MW           | SK, MB |
| Quebec       | QC           | QC |
| Ontario      | OT           | ON |
| Atlantic     | AT           | NB, NS, PE, NL |

### U.S. Regions

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

## Temporal Resolution 

Our model investigates decarbonization pathways, therefore, we can expect increasing shares of variable renewable energy sources being added to the system. Capturing the time-varying generation profiles of these sources is critical to accurately evaluate energy planning questions. However, since this is a long-term planning study, finding a tradeoff between a fine temporal resolution and a computationally tractable model is paramount. As such, a representative days time slicing structure is implemented. 

### Seasons

The model is broken into four seasons, as summarized below, with each season starting/ending on the first/last day of the month. Each season represents a single 24 hour day in the model -- resulting in 96 equally sized time slices per year. Representing each season as a full 24 hour day allows us to capture parameters that are sensitive to time of the day, such as solar, wind, and energy loads.

| Season | Abbreviation | Months Included | 
|--------|--------------|--------------------|
| Winter | W            | January, February, December|
| Spring | SP           | April, May, March|
| Summer | S            | July, August, June|
| Fall   | F            | October, November, September|

### Time Zones

A "Model Time" is implemented to account for time zone differences. The Pacific Time Zone is referenced as "Time Zero" and data is shifted for each time zone accordingly. This allows time zone differences to be included in how the model uses transmission. The table below summarizes the time shifts per province and states. 

| Time Zone | Time Shift | Provinces Included | States Included | 
|-----------|------------|--------------------|-----------------|
| PDT       | 0          | BC                 | WA, OR, CA, NV |
| MDT       | +1         | AB                 | MT, ID, WY, UT, CO, AZ, NM |
| CDT       | +2         | SK, MB             | ND, SD, NE, KS, OK, TX, MN, IA, MO, AR, LA, WI, IL, TN, MS, AL|
| EDT       | +3         | ON, QC             | MI, IN, KY, GA, FL, OH, SC, NC, WV, VA, PA NY, VT, ME, NH, MA, CT, RI, NJ, DE, MD, DC |
| ADT       | +4         | NB, NS, PE, NL     | None |

Canada is represented using 5 time zones. In reality, there are 6 time zones. Newfoundland operates on a time zone 30min ahead of the Atlantic time zone, which does not accommodate the hourly time slice structure. Therefore, we group all Newfoundland and Labrador data into the Atlantic time zone. Moreover, Saskatchewan does not observe daylight savings time while the rest of Canada does. Therefore, during the summer Saskatchewan's time matches Alberta, while during the winter its time matches Manitoba. To simplify data processing, we have grouped Saskatchewan into the Central Time Zone with Manitoba. 

## Technologies

All power generating stations in OSeMOSYS are represented by technologies. Technologies can convert between energy carriers based on user defined efficiencies. The electricity generation technologies can broadly be categorized as thermal, variable renewable, and non-variable renewable generation and are summarized below. 

| Technology                           | Abbreviation | Type    |
|--------------------------------------|--------------|---------|
| Coal                                 | COA          | Thermal |
| Coal Carbon Capture and Sequestration| COC          | Thermal |
| Combined Cycle Natural Gas           | CCG          | Thermal |
| Combustion Turbine Natural Gas       | CTG          | Thermal |
| Hydro Power                          | HYD          | Renewable |
| Onshore Wind                         | WND          | Variable Renewable |
| Solar                                | SPV          | Variable Renewable |
| Nuclear                              | URN          | Thermal |
| Biomass                              | BIO          | Renewable |

## Commodities

Each technology operates on a commodity to generate electricity. Different technologies can share commodities (such as open and combined cycle natural gas power plants) as shown in the Reference Energy System below. 

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

## Reference Energy System 

Below is a schematic showing the flow of energy for any arbitrary region in the model. The transmission and distribution technologies connect supply and demand between regions. 

![](https://i.ibb.co/hMnD5JN/res.png)

## Naming Conventions

See this page for an overview of the naming conventions 

## Units

The table below summarizes the input unit values for each parameter 

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