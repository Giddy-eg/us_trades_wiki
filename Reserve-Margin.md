## NERC Reserve Margin

The North American Electric Reliability Corporation (NERC) provides guidelines on how to assign reserve margins. On [this page](https://www.nerc.com/pa/RAPA/ri/Pages/PlanningReserveMargin.aspx), they define reserve margin as the amount of generation capacity available to meet expected demand in planning horizon.

Specifically, NERC calls out:
> NERC's Reference Reserve Margin is equivalent to the Target Reserve Margin Level provided by the Regional/subregional’s own specific margin based on load, generation, and transmission characteristics as well as regulatory requirements. If not provided, NERC assigned 15 percent Reserve Margin for predominately thermal systems and 10 percent for predominately hydro systems.

From this we assumed reserve margins for each province based on if their generation is hydro dominated or thermal dominated. We determined the predominant energy generator using Figure 24 in [this Canadian Energy Regulator Site](https://www.cer-rec.gc.ca/en/data-analysis/canada-energy-future/2019/results/index.html). The notable exception was Prince Edward island which is wind dominated. We assumed a 15% reserve margin for PEI. 

| Province      | Reserve Margin (%) |
|---------------|:------------------:|
| BC            | 10                 |
| Alberta       | 15                 |
| Saskatchewan  | 15                 |
| Manitoba      | 10                 |
| Ontario       | 15                 |
| Quebec        | 10                 |
| New Brunswick | 15                 |
| Newfoundland  | 10                 |
| Nova Scotia   | 15                 |
| PEI           | 15                 |

## Regionalized Reserve Margin 
The model groups provinces into distinct regions, which is discussed in [this wiki page](https://github.com/DeltaE/Canada-U.S.-ElecTrade/wiki#regions). The provinces grouped into each region will **not** necessarily share the same reserve margin, as some will be 10% and other will be 15%. To account for this, a weighted reserve margin is calculated. The weighting is based on the provinces total demand, and uses the values found in `dataSources/ProvincialAnnualDemand.csv`

The regionalized reserve margin formula implemented is shown below:  

<img src="https://render.githubusercontent.com/render/math?math=(ReserveMargiun)_{Region} = \sum \frac{(Demand)_{Province}}{(Demand)_{Region}} (ReserveMargin)_{Province}">

## Peak Squishing
The regionalized reserve margin calculated above is applied to our timesliced max demand. This is **not** representative of the actual max demand. Based on our [models timeslicing approach](https://github.com/DeltaE/Canada-U.S.-ElecTrade/wiki#timeslicing), we have compressed each three month season into a single 24 hour day. The demand for this single day represents the average demand for the season. This means, if a large demand peak occurs due to unpredictable weather (or any other factor) it is **not** captured in our average seasonal day. 

To account for this, we add extra reserve margin to our previously calculated reserve margin. 