# DagUnverified

Creates a DAG (Directed Acyclic Graph) from a JSON file.  Attributes ---------- id : str     Identifier of the DAG. tasks : ListIntVisited     Tasks that make up the DAG.  Methods ------- check_dependencies(tasks)     Checks if the tasks dependencies are valid. check_circle(tasks)     Checks that there are no circular dependencies in the DAG. get_zipped_code(language: LanguageType)     Returns the requirements and code in a zipped folder. get_nodes(tasks)     Returns all the information of the DAG as a list of tasks. get_edges(tasks)     Get all two-by-two dependencies between tasks. to_graph(tasks)     Create a graph from the DAG with the edges and nodes.

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Identifier of the Directed Acyclic Graph (DAG). | 
**tasks** | **[bool, date, datetime, dict, float, int, list, str, none_type]** | List of tasks that compose the DAG. | 
**any string name** | **bool, date, datetime, dict, float, int, list, str, none_type** | any string name can be used but the value must be the correct type | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


