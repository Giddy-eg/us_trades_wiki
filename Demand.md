# Total Annual Demand
Canadian Provincial Energy Demands for 2005 to 2050 are documented by the [Canadian Energy Regulator](https://apps.cer-rec.gc.ca/ftrppndc/dflt.aspx?GoCTemplateCulture=en-CA) in their "Canada's Energy Future 2020: Energy Supply and Demand Projections to 2050" Report. 

# Demand Profile 
The yearly demand profile for each province is calculated by looking at hourly loads provided by the following sources. 

| Province              | Source |
|-----------------------|--------|
| British Columbia      | [BC Hydro](https://www.bchydro.com/energy-in-bc/operations/transmission/transmission-system/balancing-authority-load-data/historical-transmission-data.html) |
| Alberta               | [AESO](http://ets.aeso.ca/) |
| Saskatchewan          |  |
| Manitoba              |  |
| Ontario               | [IESO](http://reports.ieso.ca/public/Demand/) |
| Quebec                |  |
| New Brunswick         | [NB Power](http://tso.nbpower.com/Public/en/system_information_archive.aspx) |
| Nova Scotia           | [NS Power](https://www.nspower.ca/oasis/monthly-reports/hourly-total-net-nova-scotia-load) |
| PEI                   |  |
| Newfoundland Labrador |  |

## Daylight Savings 
Daylight saving is dealt with in the following manor: 
* If an hour is removed, the line item from the source is reported as zero (ie. 3am has a load of 0). In this case we take the same hourly demand from the previous day and map it to the missing hour. 
* If an hour is added, the line item in the source is doubled up (ie. two 3am load values). In this case we take the average between these values. 
