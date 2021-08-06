# Total Annual Demand
Canadian Provincial Energy Demands for 2005 to 2050 are documented by the [Canadian Energy Regulator](https://apps.cer-rec.gc.ca/ftrppndc/dflt.aspx?GoCTemplateCulture=en-CA) in their Canadian Energy Future 2020: Energy Supply and Demand Projections Report. We retrieve data from the "End Use Demand" Appendix. Regional demands are found by summing provincial demands together

United States annual demand is provided by the Unites States Energy Information Administration ([EIA](https://www.eia.gov/)). State specific annual demands for 2019 and 2020 are found from [this source](https://www.eia.gov/electricity/gridmonitor/dashboard/electric_overview/US48/US48). A standard reference case growth rate as described from [this source](https://www.eia.gov/outlooks/aeo/electricity/sub-topic-01.php) is applied to all states. 

System-level electricity demand is forecasted to steadily increase over the model horizon with both countries following similar year-over-year trends. There is a slight dip in demand from 2019 to 2021 in both countries. This is likely due to the Covid-19 pandemic affecting electricity consumption habits, as discussed by the EIA [here](https://www.eia.gov/outlooks/steo/report/electricity.php). 

![](https://lh3.googleusercontent.com/keep-bbsk/AGk0z-O3VOZQVpVWR9yD6PjIcwPxt_Ny5lVXxnCwZR_GTMAJoJDq5OkJrU77hHt4nsaj9fxgr-7PJYfbpW5_obpOOztWSwHcobDdq_1OsEg)

# Demand Profile 
In Canada, hourly provincial load profiles are supplied by provincial electric utility companies and system operators. However, not all provincial utility companies freely provide hourly demand data. In these cases, we assume the profile of the neighboring province with the most similar annual demand. The table below documents Canadian provincial demand profile sources.  

| Province              | Source |
|-----------------------|--------|
| British Columbia      | [BC Hydro](https://www.bchydro.com/energy-in-bc/operations/transmission/transmission-system/balancing-authority-load-data/historical-transmission-data.html) |
| Alberta               | [AESO](http://ets.aeso.ca/) |
| Saskatchewan          | Used Alberta Load Profile |
| Manitoba              | Used Alberta Load Profile |
| Ontario               | [IESO](http://reports.ieso.ca/public/Demand/) |
| Quebec                | Used Ontario Load Profile |
| New Brunswick         | [NB Power](http://tso.nbpower.com/Public/en/system_information_archive.aspx) |
| Nova Scotia           | [NS Power](https://www.nspower.ca/oasis/monthly-reports/hourly-total-net-nova-scotia-load) |
| PEI                   | Used Nova Scotia Load Profile |
| Newfoundland Labrador | Used Nova Scotia Load Profile |

## Daylight Savings 
Daylight savings is dealt with in the following manor: 
* If an hour is removed, the line item from the source is either omitted or reported as zero (ie. 3am has a load of 0). In this case we take the demand from the previous hour and map it to the missing hour. 
* If an hour is added, the line item in the source is doubled up (ie. two 3am load values). In this case we take the average between these values. 
* See note on Saskatchewan daylight savings time [here](https://github.com/DeltaE/Canada-U.S.-ElecTrade/wiki#time-zones)
