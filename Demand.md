# Total Annual Demand
Canadian Provincial Energy Demands for 2005 to 2050 are documented by the [Canadian Energy Regulator](https://apps.cer-rec.gc.ca/ftrppndc/dflt.aspx?GoCTemplateCulture=en-CA) in their "Canada's Energy Future 2020: Energy Supply and Demand Projections to 2050" Report. We retrieve data from the "End Use Demand" Appendix.

# Demand Profile 
The yearly demand profile for each province is calculated by looking at hourly loads provided by the following sources. 

| Province              | Source |
|-----------------------|--------|
| British Columbia      | [BC Hydro](https://www.bchydro.com/energy-in-bc/operations/transmission/transmission-system/balancing-authority-load-data/historical-transmission-data.html) |
| Alberta               | [AESO](http://ets.aeso.ca/) |
| Saskatchewan          | Used Alberta Load Profile |
| Manitoba              | Used Alberta Load Profile |
| Ontario               | [IESO](http://reports.ieso.ca/public/Demand/) |
| Quebec                | Used British Columbia Load Profile |
| New Brunswick         | [NB Power](http://tso.nbpower.com/Public/en/system_information_archive.aspx) |
| Nova Scotia           | [NS Power](https://www.nspower.ca/oasis/monthly-reports/hourly-total-net-nova-scotia-load) |
| PEI                   | Used Nova Scotia Load Profile |
| Newfoundland Labrador | Used Nova Scotia Load Profile |

## Missing Hourly Provincial Loads
Retrieving hourly load data for an entire year has not been done for Saskatchewan, Manitoba, Quebec, PEI and Newfoundland. This is due to the data not being easily accessible. To account for this, we have mapped the load profiles from similar provinces as described in the above table. 

To calculate the hourly load value (in Watts) for the missing provinces...
1.  Found the ratio between annual demands for the two provinces using the Total Annual Demand Source
*  Ratio = (Unknown Province Annual Demand) / (Known Province Annual Demand) 
2.  Multiplied the known provinces demand values by the ratio to find hourly load for the unknown province 
*  Hourly Load Unknown Province = Ratio * Hourly Load Known Province
3.  The resulting normalized load profile will be the same as the known provinces profile. However, when regions are built the raw load value (in Watts) will contribute to the weighted average load profile the appropriate amount 

# Missing Technology (Petroleum)
Petroleum data are not added in our model. Currently, less than 1% of Canadian electricity is produced from petroleum [Provincial and Territorial Energy Profiles – Canada](https://www.cer-rec.gc.ca/en/data-analysis/energy-markets/provincial-territorial-energy-profiles/provincial-territorial-energy-profiles-canada.html). The majority of electricity production in the country is through renewable and non-GHG emitting sources [Electricity facts](https://www.nrcan.gc.ca/science-data/data-analysis/energy-data-analysis/energy-facts/electricity-facts/20068). Therefore, electricity is produced from renewable and nuclear sources sources as a primary energy since it is captured from natural resources [About Electricity](https://www.nrcan.gc.ca/our-natural-resources/energy-sources-distribution/electricity-infrastructure/about-electricity/7359).

## Daylight Savings 
Daylight saving is dealt with in the following manor: 
* If an hour is removed, the line item from the source is either omitted or reported as zero (ie. 3am has a load of 0). In this case we take the demand from the previous hour and map it to the missing hour. 
* If an hour is added, the line item in the source is doubled up (ie. two 3am load values). In this case we take the average between these values. 
* See note on Saskatchewan daylight savings time [here](https://github.com/DeltaE/Canada-U.S.-ElecTrade/wiki#time-zones)
