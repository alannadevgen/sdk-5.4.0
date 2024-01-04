# WorkflowActivity

Object JobActivity.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actor** | [**User1**](User1.md) |  | 
**target** | [**Workflow1**](Workflow1.md) |  | 
**verb** | **str** |  | 
**data** | **{str: (bool, date, datetime, dict, float, int, list, str, none_type)}** |  | [optional] 
**id** | **str** |  | [optional] 
**time** | **datetime** |  | [optional] 
**reaction_count** | [**[Reaction]**](Reaction.md) |  | [optional] 
**type** | **str** |  | [optional]  if omitted the server will use the default value of "workflow"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


