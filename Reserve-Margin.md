The North American Electric Reliability Corporation (NERC) provides guidelines on how to assign reserve margins. On [this page](https://www.nerc.com/pa/RAPA/ri/Pages/PlanningReserveMargin.aspx), they define reserve margin as the amount of generation capacity available to meet expected demand in planning horizon.

Specifically, NERC calls out:
> NERC's Reference Reserve Margin is equivalent to the Target Reserve Margin Level provided by the Regional/subregional’s own specific margin based on load, generation, and transmission characteristics as well as regulatory requirements. If not provided, NERC assigned 15 percent Reserve Margin for predominately thermal systems and 10 percent for predominately hydro systems.

From this we assumed reserve margins for each province based on if their generation is hydro dominated or thermal dominated. We determined the prominant energy generator using Figure 24 in [this Canadian Energy Regulator Site](https://www.cer-rec.gc.ca/en/data-analysis/canada-energy-future/2019/results/index.html). The notable exception was Prince Edward island which is wind dominated. We assumed a 15% reserve margin for PEI. 

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
