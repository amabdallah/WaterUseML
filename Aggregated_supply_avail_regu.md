
# 1. Aggregated water supply  

## get calls
Get/Agg_WaterSupply_WaterUseML  

## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output  

Field   name | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_supply | add
LU_WaterSupplyType | spring | add
WFS_FEATURE_REF | add fea | add
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 20000 | add



# 2.Aggregated water availability

## get call
Get/Agg_WaterAvailability_WaterUseML 

## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output  

Field   name | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_avail | add
LU_SourceType | Reservoir | add
LU_FreshSalineIndicator | Fresh | add
AvailabilityType | add | add
WFS_FEATURE_REF | add | add
LU_Metric | add meteric | add
StartDate | 01/01s | add
EndDate | 31/12s | add
Year | 2010 | add
Month |   | add
Amount | 20000 | add



# 3.Aggregated regulatory 

## get call
Get/Agg_regulatory_WaterUseML  

## Input to get calls  
- ReportAreaCode [WHERE]  
- VariableCode [WHAT]  

## Output    

Field   name | Example | Description
-- | -- | --
OrganizationCode | UDWR | add
ReportCode | 2010 | add
ReportAreaCode | 101010 | add
VariableCode | Agg_regulatory | add
REGULATORY_TYPE | abc | add
REGULATORY_STATUS | wxy | add
OVERSIGHT_AGENCY | UDWR | add
REGULATORY_DESCRIPTION | add desc here | add
WFS_FEATURE_REF | add feature here | add




