# BetweenFilter

Filter values that are in a range/between two values.  Attributes ---------- type : RelationalOperatorType     Type of the filter. right : list     Values below and above.  Methods ------- get_value()     Get the value of the filter operator

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**left** | **str** | Left operator for filter. | 
**right** | **[str]** |  | 
**type** | **str** | Operator for BETWEEN filter (range). | [optional]  if omitted the server will use the default value of "between"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


