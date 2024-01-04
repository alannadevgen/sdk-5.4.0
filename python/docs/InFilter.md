# InFilter

Filter values that are in a list or a string.  Attributes ---------- type : RelationalOperatorType     Type of the filter.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**left** | **str** | Left operator for filter. | 
**right** | **bool, date, datetime, dict, float, int, list, str, none_type** |  | 
**type** | **str** | Operator for IN list/range filter. | [optional]  if omitted the server will use the default value of "in"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


