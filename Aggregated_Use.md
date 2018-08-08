
# 1. Irrigation or Aggriculture 

Aggregated Irrigation Consumptive use or withdrawal WaterUseML calls and their output

## get calls
Get/Agg_Irrigation_Consumptive_WaterUseML  
Get/Agg_Irrigation_Withdrawal_WaterUseML  

## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output  
 
Field   name | Example | Description  
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_Irrigation_ConsUse, Agg_Irrigation_withdrawal | add
LU_BeneficialUse | Irrigation | add
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


# 2. Thermoelectric    

## get calls 
Get/Agg_Thermoelectric_Consumptive_WaterUseML  
Get/Agg_Thermoelectric_Withdrawal_WaterUseML 


## Input to get calls   
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  


## Output
Field | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_Irrigation_ConsUse | add
LU_BeneficialUse | Thermo | add
POWER_GENERATED_megawhat | 1000 | add
LU_SourceType | Groundwater | add
LU_FreshSalineIndicator | Fresh | add
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 5000 | add




# 3. Public Supply    

## get calls  
Get/Agg_community_Consumptive_WaterUseML  
Get/Agg_community_Withdrawal_WaterUseML  

## Input to get calls   
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output   

Field   name | Example | Description
-- | -- | --
ReportCode | UDWR | add
ReportAreaCode | 2010 | add
VariableCode | 101010 | add
LU_BeneficialUse | Agg_community_ConsUse | add
LU_SourceType | Groundwater | add
LU_FreshSalineIndicator | Fresh | add
PopulationServed | 10000 | add
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 5000 | add

