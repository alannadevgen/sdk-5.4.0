# RandomForest

Define a logical operator for train a model.  Attributes ---------- type : str     Type of model (Random Forest, ...).  Methods ------- accept(visitor)     Enables the visitor to visit the task.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**test_size** | **float** | Represent the proportion of the dataset to include in the test split. [0, 1.0] | 
**predict_column** | **str** | The column of the dataset to predict. | 
**features_column** | **[str]** | The features columns . | 
**number_trees** | **int** | The number of trees in the forest. | 
**max_depth** | **int** | The maximum depth of the tree. | 
**model** | **str** | Random Forest model. | [optional]  if omitted the server will use the default value of "random_forest"
**seed** | **int** | Seed to set in order to have reproducible results. | [optional]  if omitted the server will use the default value of 42
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


