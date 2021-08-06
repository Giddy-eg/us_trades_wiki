# Definition
We utilize two of OSeMOSYS' demand parameters: Specified Annual Demand and Specified Demand Profile. The annual demand determines a regions annual demand for each year over the model horizon. The demand profile then distributes the annual demand into time sliced demand. 

# Annual Demand
**Canadian** Provincial Energy Demands for 2005 to 2050 are documented by the [Canadian Energy Regulator](https://apps.cer-rec.gc.ca/ftrppndc/dflt.aspx?GoCTemplateCulture=en-CA) in their Canadian Energy Future 2020: Energy Supply and Demand Projections Report. We retrieve data from the "End Use Demand" Appendix. Regional demands are found by summing provincial demands together

**United States** annual demand is provided by the Unites States Energy Information Administration ([EIA](https://www.eia.gov/)). State specific annual demands for 2019 and 2020 are found from [this source](https://www.eia.gov/electricity/gridmonitor/dashboard/electric_overview/US48/US48). A standard reference case growth rate as described from [this source](https://www.eia.gov/outlooks/aeo/electricity/sub-topic-01.php) is applied to all states. 

System-level electricity demand is forecasted to steadily increase over the model horizon with both countries following similar year-over-year trends. There is a slight dip in demand from 2019 to 2021 in both countries. This is likely due to the Covid-19 pandemic affecting electricity consumption habits, as discussed by the EIA [here](https://www.eia.gov/outlooks/steo/report/electricity.php). 

![](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-O3VOZQVpVWR9yD6PjIcwPxt_Ny5lVXxnCwZR_GTMAJoJDq5OkJrU77hHt4nsaj9fxgr-7PJYfbpW5_obpOOztWSwHcobDdq_1OsEg)

# Demand Profile 
## Canada 
In Canada, hourly provincial load profiles are supplied by provincial electric utility companies and system operators. However, not all provincial utility companies freely provide hourly demand data. In these cases, we assume the profile of the neighboring province with the most similar annual demand. The table below documents Canadian provincial demand profile sources.  

| Province | Source |
|----------|--------|
| BC       | [BC Hydro](https://www.bchydro.com/energy-in-bc/operations/transmission/transmission-system/balancing-authority-load-data/historical-transmission-data.html) |
| AB       | [AESO](http://ets.aeso.ca/) |
| SK       | Used Alberta Load Profile |
| MB       | Used Alberta Load Profile |
| ON       | [IESO](http://reports.ieso.ca/public/Demand/) |
| QU       | Used Ontario Load Profile |
| NB       | [NB Power](http://tso.nbpower.com/Public/en/system_information_archive.aspx) |
| NS       | [NS Power](https://www.nspower.ca/oasis/monthly-reports/hourly-total-net-nova-scotia-load) |
| PE       | Used Nova Scotia Load Profile |
| NL       | Used Nova Scotia Load Profile |

### Daylight Savings 
Daylight savings is dealt with in the following manor: 
* If an hour is removed, the line item from the source is either omitted or reported as zero (ie. 3am has a load of 0). In this case we take the demand from the previous hour and map it to the missing hour. 
* If an hour is added, the line item in the source is doubled up (ie. two 3am load values). In this case we take the average between these values. 
* See note on Saskatchewan daylight savings time [here](https://github.com/DeltaE/Canada-U.S.-ElecTrade/wiki#time-zones)

## United States
We use the same United States profiles provided by [Jayadev et al.](https://www.sciencedirect.com/science/article/abs/pii/S0306261919319543)  in their [supplemental documentation](https://data.mendeley.com/datasets/cjcfw8b4xf/1). The table below highlights their references for for regional demand profiles. All years over the model horizon use the same 2017 demand profile. 

| States                                         | Source |
|------------------------------------------------|--------|
| TX                                             | [ERCOT](http://www.ercot.com/gridinfo/load/load_hist/) |
|                                                | [MISO](https://www.misoenergy.org/markets-and-operations/real-time--market-data/real-time-displays/) |
| NY                                             | [NYISO](https://www.nyiso.com/load-data) |
| IL, IN, KY, MD, MI, NJ, NC, OH, PA, TN, VA, WV | [PJM](https://dataminer2.pjm.com/feed/hrl_load_metered/definition) |
| CT, ME, MA, NH, RI, VT                         | [IESO](http://reports.ieso.ca/public/Demand/) |

### EIA Data
While the EIA reporting organizations do not line up with the generated regions by [Jayadev et al.](https://www.sciencedirect.com/science/article/abs/pii/S0306261919319543), their [hourly demand profiles](https://www.eia.gov/electricity/gridmonitor/dashboard/electric_overview/US48/US48) may be useful for cross referencing data in future work. 

## Demand Profile 
The aggregated demand profiles for each of the five time zones is shown in the graphs below

![](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-OtifYzdxeRXX-u5fncX1k998OSV0IOOHqnxWQBiktXVhUQ2Rhb6GwUxO1GbV8GtPATV-WRzYDhoZTdBOtEm6Vls_6dvesdQMsdu50)
