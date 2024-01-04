# Job


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** |  | [optional] 
**name** | **str** |  | [optional] 
**description** | **str** |  | [optional] 
**project_id** | **str** |  | [optional] 
**identity_id** | **str** |  | [optional] 
**created** | **datetime** |  | [optional] 
**updated** | **datetime** |  | [optional] 
**timeout_seconds** | **int** |  | [optional] 
**max_retries** | **int** |  | [optional] 
**secrets** | **[str]** |  | [optional] 
**libraries** | [**[Library]**](Library.md) |  | [optional] 
**options** | [**Options**](Options.md) |  | [optional] 
**schedule** | [**Schedule**](Schedule.md) |  | [optional] 
**notifications** | [**Notifications**](Notifications.md) |  | [optional] 
**parameters** | **[str]** |  | [optional] 
**labels** | **{str: (str,)}** |  | [optional] 
**metadata** | **{str: ({str: (bool, date, datetime, dict, float, int, list, str, none_type)},)}** |  | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


