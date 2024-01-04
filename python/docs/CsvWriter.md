# CsvWriter


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **str** | Path to CSV file. | 
**separator** | **str** | Delimiter to use between columns. | [optional] 
**header** | **bool** | Is the first row the header? | [optional] 
**delimiter** | **str** | Alias for separator. | [optional] 
**compression** | **str** | Type of on-the-fly decompression to use. | [optional] 
**index** | **bool** | Is the first column an index? | [optional] 
**type** | **str** | Define file type for CSV. | [optional]  if omitted the server will use the default value of "csv"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


