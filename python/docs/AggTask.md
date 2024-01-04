# AggTask

Defines a task in a DAG.  Attributes ---------- id : str     Identifier of a task. params : Params     Parameters of a task.  Methods ------- accept(visitor)     Visit a task using a specified visitor. to_node()     Returns the information about the task (id and parameters). to_edge()     Gets all the dependencies of the task.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Identifier of the task. | 
**params** | **bool, date, datetime, dict, float, int, list, str, none_type** | Parameters of the aggregation task. | 
**dependency** | **[str]** | List of all dependencies of the task. | 
**type** | **str** | Type of the aggregation task. | [optional]  if omitted the server will use the default value of "aggregation"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


