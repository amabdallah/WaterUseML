# 1. Water Rights (allocations) or permits

## get calls
Get/SiteSpecific_WaterRights_WaterUseML  


## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  


## Output  


Field   name| Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | WaterRights |  
ALLOCATION_Code | 10101010 | add
ALLOCATION_OWNER | John Smithh | add
APPLICATION_DATE | 1900 | add
PRIORITY_DATE | 1920 | add
LEGAL_STATUS | abc | add
END_DATE |   | add


# 2. AllocatedWaterRightPerSite 

## get calls
Get/SiteSpecific_AllocatedWaterRightSite_WaterUseML  


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
ALLOCATION_Code | 101010 |  
DiversionCode | 2E+07 |  
LU_BeneficialUse | Irrigation | add
LU_SourceType | Groundwater | add
SOURCE_NAME | 01/01s | add
LU_FreshSalineIndicator | Fresh |  
StartDate | 10000 | add
EndDate | 01/01s | add
Year | 31/12s | add
Month | 2010 | add
Day |   | add
VolumeAmount | 5000 | add
FlowAmount | 60000 | add



# 3. DivertedWaterRightPerSite 

## get calls
Get/SiteSpecific_DivertedWaterRightPerSite_WaterUseML  


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
ALLOCATION_Code | 101010 |  
DiversionCode | 20202020 |  
LU_BeneficialUse | Irrigation | add
LU_SourceType | Groundwater | add
SOURCE_NAME | 01/01s | add
LU_FreshSalineIndicator | Fresh |  
StartDate | 10000 | add
EndDate | 01/01s | add
Year | 31/12s | add
Month | 2010 | add
Day |   | add
VolumeAmount | 5000 | add
FlowAmount | 60000 | add



# 4. AllocatedWaterRightTotal 

## get calls
Get/SiteSpecific_AllocatedWaterRightTotal_WaterUseML  


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
ALLOCATION_Code | 101010 |  
DiversionCode | 20202020 |  
LU_BeneficialUse | Irrigation | add
LU_SourceType | Groundwater | add
SOURCE_NAME | 01/01s | add
LU_FreshSalineIndicator | Fresh |  
StartDate | 10000 | add
EndDate | 01/01s | add
Year | 31/12s | add
Month | 2010 | add
Day |   | add
VolumeAmount | 5000 | add
FlowAmount | 60000 | add



# 5. DivertedPerWaterRightTotal 

## get calls
Get/SiteSpecific_DivertedPerWaterRightTotal_WaterUseML  


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
ALLOCATION_Code | 101010 |  
DiversionCode | 20202020 |  
LU_BeneficialUse | Irrigation | add
LU_SourceType | Groundwater | add
SOURCE_NAME | 01/01s | add
LU_FreshSalineIndicator | Fresh |  
StartDate | 10000 | add
EndDate | 01/01s | add
Year | 31/12s | add
Month | 2010 | add
Day |   | add
VolumeAmount | 5000 | add
FlowAmount | 60000 | add



# 5. Site_RetunFlow 

## get calls
Get/SiteSpecific_Site_RetunFlow_WaterUseML  


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
ALLOCATION_Code | 101010 |  
StartDate | 10000 | add
EndDate | 01/01s | add
Year | 31/12s | add
Month | 2010 | add
Day |   | add
VolumeAmount | 5000 | add
FlowAmount | 60000 | add


