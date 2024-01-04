# NotNullFilter

Filter values that are not null.  Attributes ---------- type : RelationalOperatorType     Type of the filter. right : str     Optional value for right side of the filter.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**left** | **str** | Left operator for filter. | 
**right** | **str** |  | [optional] 
**type** | **str** | Operator for NOT NULL filter. | [optional]  if omitted the server will use the default value of "not_null"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


