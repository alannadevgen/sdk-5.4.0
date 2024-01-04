# ReadFileParams


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**connector** | **bool, date, datetime, dict, float, int, list, str, none_type** | Type of connector (local, S3, Azure). | 
**object** | **bool, date, datetime, dict, float, int, list, str, none_type** | Options for reading a file (header, file path, separator,         delimiter, ...). | 
**type** | **str** | Type of object file. | [optional]  if omitted the server will use the default value of "file"
**structure** | **[{str: (str,)}]** | List of dictionaries representing the columns         (name and type). For each dictionnary the &#39;name&#39; represents the column         name and the &#39;type&#39; their corresponding type. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


