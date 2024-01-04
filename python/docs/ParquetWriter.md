# ParquetWriter


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **str** | Path to PARQUET file. | 
**partition_by** | **[str]** | How to partition the dataset. | [optional] 
**mode** | **bool, date, datetime, dict, float, int, list, str, none_type** | How to write the file (append, overwrite) | [optional] 
**compression** | **str** | Type of on-the-fly compression to use. | [optional] 
**type** | **str** | Define file type for PARQUET. | [optional]  if omitted the server will use the default value of "parquet"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


