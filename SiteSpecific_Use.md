
# 1. Site specific Public Supply Consumptive use

## get calls
Get/SiteSpecific_WaterSupply_Consumptive_WaterUseML  


## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output  


Field   name | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | WaterRights_supply | add
ALLOCATION_Code | 101010 | add
WATER_USER_NAME | John Smith | add
LU_BeneficialUse | Irrigation | add
LU_SourceType | Groundwater | add
SOURCE_NAME | 01/01s | add
LU_FreshSalineIndicator | Fresh |  
PopulationServed | 10000 | add
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 5000 | add



# 2. Site specific Thermoelectric Consumptive use

## get calls
Get/SiteSpecific_Thermoelectric_Consumptive_WaterUseML  


## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output   

Field   name | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_thermo_ConsUse | add
ALLOCATION_Code | 101010 | add
WATER_USER_NAME | John Smithh | add
LU_BeneficialUse | Thermo | add
POWER_GENERATED | 10000 | add
LU_SourceType | Groundwater | add
LU_FreshSalineIndicator | Fresh |  
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 5000 | add


# 3. Site specific Irrigation Consumptive use

## get calls
Get/SiteSpecific_Irrigation_Consumptive_WaterUseML  


## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output   



Field   name | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_Irrigation_ConsUse | add
ALLOCATION_Code | Thermo | add
WATER_USER_NAME | 101010 | add
LU_BeneficialUse | John Smith | add
LU_IrrigationMethod | Pivot | add
LU_CropType | Alfalafa | add
ACRES_IRRIGATED | 10000 | add
LU_SourceType | Groundwater | add
LU_FreshSalineIndicator | Fresh | add
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 5000 | add


