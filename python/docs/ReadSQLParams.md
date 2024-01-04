# ReadSQLParams


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**object** | **bool, date, datetime, dict, float, int, list, str, none_type** | Define parameters to read from a SQL server (URL,                 database, table, port, user, password). | 
**connector** | **bool, date, datetime, dict, float, int, list, str, none_type** | Type of connector (SQL or database connector) | 
**type** | **str** | Type SQL server. | [optional]  if omitted the server will use the default value of "sql"
**structure** | **[{str: (str,)}]** | List of dictionaries representing the columns (name and type). For each dictionnary the         &#39;name&#39; represents the column name and the &#39;type&#39; their corresponding type. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


