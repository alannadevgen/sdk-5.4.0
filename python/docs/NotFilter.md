# NotFilter

Filter values that are not equal to a given value.  Attributes ---------- type : RelationalOperatorType     Type of the filter. condition : union_filter     Union of all relational filters.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**condition** | **bool, date, datetime, dict, float, int, list, str, none_type** | Condition for NOT filter. | 
**type** | **str** | Operator for NOT filter. | [optional]  if omitted the server will use the default value of "not"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


