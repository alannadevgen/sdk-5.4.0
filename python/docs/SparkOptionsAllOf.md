# SparkOptionsAllOf


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** |  | [optional]  if omitted the server will use the default value of "spark"
**libraries** | **[str]** |  | [optional] 
**conf** | **{str: ({str: (bool, date, datetime, dict, float, int, list, str, none_type)},)}** |  | [optional] 
**main_library** | [**Library**](Library.md) |  | [optional] 
**py_files** | [**[Library]**](Library.md) |  | [optional] 
**main_class_name** | **str** |  | [optional] 
**loggers** | **[str]** |  | [optional] 
**executor_instance_type** | **str** |  | [optional] 
**driver_instance_type** | **str** |  | [optional] 
**number_executors** | **float** |  | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


