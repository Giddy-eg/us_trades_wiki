## Coal
A shortlist of the coal fired generating facilities in Canada has been compiled in [this Wikipedia Table](https://en.wikipedia.org/wiki/Coal_in_Canada#cite_note-CBC1-42). Each of the individuals facilities page was referenced to find the the capacity, commission date and retirement data if applicable. The exact pages are listed in `dataSources/ResidualCapacitiesByProvince.csv`

### Capacity
In some cases, the capacity of each steam turbine unit was given. In these cases the capacities were summed to provide the residual capacity at its start data. In other cases, less information was available and only a general capacity of the power plant was provided. 

### Commission Date 
The commission date of the power plant is critical, as coal is starting to be phased out in Canada and we didn't want to introduce brand new residual capacity in the start year. On some Wikipedia pages, the commission year of each unit was given. In these cases, the average commission date across all the units was used as the stations commission date. In other cases, only a general commission date for the entire power plant was given. 

### Retirement 
As coal is a heavy emitter, these stations are beginning to be phased out. Some references included a decommissioning date which is transferred over into the model. In cases where a decommissioning date was not listed, the operational life was applied to the commission date to find set the retirement year. 

### Ramping Down of Capacity near Decommissioning 
Since these power plants often consist of numerous turbines or units, decommissioning them could mean a gradual reduction in capacity as individual units are removed. This is **not** taken into account in out model. Each power station has is full residual capacity until its decommissioning year. 

### Coal Conversion to Natural Gas
As coal is being phased in due to the high emission levels, some plants are being converted into natural gas facilities. In these cases, the capacity flips from being for a coal technology to a natural gas technology. Specifically this is found in the Alberta H.R. Milner Generating Facility and in the Alberta Genesee Generating Facility. 
