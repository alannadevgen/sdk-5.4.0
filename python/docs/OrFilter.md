# OrFilter

Filter values that verify at least one condition.  Attributes ---------- type : RelationalOperatorType     Type of the filter. conditions : union_filter     Union of all relational filters.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**conditions** | **[bool, date, datetime, dict, float, int, list, str, none_type]** | Condition for OR filter. | 
**type** | **str** | Operator for OR filter. | [optional]  if omitted the server will use the default value of "or"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


