# DBConnector

Connector for databases.  Attributes ---------- type : ConnectorType     Database type of connector. options : DBConnectorOptions     Options to connect to a database.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | Connector type for a database connector like SQL | [optional]  if omitted the server will use the default value of "DB"
**options** | **bool, date, datetime, dict, float, int, list, str, none_type** | Options to connect to a database. | [optional] 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


