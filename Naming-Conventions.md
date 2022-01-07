# Code Types

All technologies and commodities are constructed following standard naming conventions defined in this page. Unless custom parameters are being inputted into the model, all naming will be built using the [configuration file](https://github.com/DeltaE/Canada-U.S.-ElecTrade/blob/main/scripts/config.yaml) and pre-processing scripts. The purpose of using standard naming conventions is to aid in identifying where parameters fit into the model and help with post-processing. 

## Technology Classifications 

The technology classification is always defined by the first three letters of the name. 
* **PWR** represent energy conversion technologies
* **MIN** represent non-renewable resource mining technologies (coal, gas, ect...) 
* **RNW** represent renewable resource mining technologies (solar, water, ect...)
* **TRN** represent technologies that facilitate energy trade between regions  

## Commodity Classifications 

The energy carrier of the commodity is always 

## Geographical Region 



# Technology Codes

## Renewable Mining Technologies

Renewable commodities (solar, wind, water...) enter the model through renewable mining technologies. They are tagged using a 9 digit identifier 

### Mining Type 

x x x _ _ _ _ _ _ 



## Mining Technologies
Primary fuels (coal, gas, water ...) enter the model through mining technologies. These technologies are 9 or 11 digits long

### Mining Type 
x x x _ _ _ _ _ _ 

**RNW** for renewable resource

**MIN** for fossil fuel

### Commodity 
_ _ _ x x x _ _ _ 

Fuel that the mining technology **outputs** (ie. SPV, GAS, HYD...)



All power generation technologies convert a primary fuel source (coal, gas, water ...) into electricity. These commodities enter the model through mining technologies. These technologies are **nine** digits long



# Commodity Codes 

##

# Example

A schematic showing an example of the naming conventions is shown below [(source)](https://viewer.diagrams.net/?tags=%7B%7D&highlight=0000ff&edit=_blank&layers=1&nav=1&title=Flowchart#Uhttps%3A%2F%2Fdrive.google.com%2Fuc%3Fid%3D1fZjU6k_STVasVjSb2CXGet2QzmjS8dkd%26export%3Ddownload)

![](https://i.ibb.co/J7bN8bZ/Flowchart-drawio.png)

