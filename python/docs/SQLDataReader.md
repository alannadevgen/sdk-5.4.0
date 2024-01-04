# SQLDataReader


## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **str** | URL to connect to the SQL server. | 
**db** | **str** | Name of the database in the SQL server. | 
**table** | **str** | Name of the table in the database. | 
**user** | **str** | Username to connect to the SQL server. | 
**password** | **str** | Password to connect to the SQL server. | 
**port** | **str** | Port to connect to the SQL server. | [optional]  if omitted the server will use the default value of "5432"
**schema_db** | **str** | Logical structure defining the organization,         relationships, and attributes of the database. The public schema is the         default schema where all the new tables are created. | [optional]  if omitted the server will use the default value of "public"
**type** | **str** | Type of database connection | [optional]  if omitted the server will use the default value of "jdbc"
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


