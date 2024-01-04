# graalsystems.GraphApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_graph**](GraphApi.md#create_graph) | **POST** /graphs | Create graph
[**delete_graph_by_id**](GraphApi.md#delete_graph_by_id) | **DELETE** /graphs/{graphId} | Delete a graph by an id
[**find_graph_by_id**](GraphApi.md#find_graph_by_id) | **GET** /graphs/{graphId} | Find graph by Id
[**find_graphs**](GraphApi.md#find_graphs) | **GET** /graphs | Retrieve all graphs
[**update_graph**](GraphApi.md#update_graph) | **PATCH** /graphs/{graphId} | Update a graph


# **create_graph**
> Graph create_graph(x_tenant, graph)

Create graph

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import graph_api
from graalsystems.model.graph import Graph
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = graalsystems.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: internal
configuration = graalsystems.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with graalsystems.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = graph_api.GraphApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    graph = Graph(
        id="id_example",
        name="name_example",
        description="description_example",
        version="version_example",
        owner="owner_example",
        type="type_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        labels={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
    ) # Graph | The graph to be created

    # example passing only required values which don't have defaults set
    try:
        # Create graph
        api_response = api_instance.create_graph(x_tenant, graph)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling GraphApi->create_graph: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **graph** | [**Graph**](Graph.md)| The graph to be created |

### Return type

[**Graph**](Graph.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.graph+json
 - **Accept**: application/vnd.graal.systems.v1.graph+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_graph_by_id**
> delete_graph_by_id(x_tenant, graph_id)

Delete a graph by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import graph_api
from graalsystems.model.error import Error
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = graalsystems.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: internal
configuration = graalsystems.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with graalsystems.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = graph_api.GraphApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    graph_id = "graphId_example" # str | Id of the graph

    # example passing only required values which don't have defaults set
    try:
        # Delete a graph by an id
        api_instance.delete_graph_by_id(x_tenant, graph_id)
    except graalsystems.ApiException as e:
        print("Exception when calling GraphApi->delete_graph_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **graph_id** | **str**| Id of the graph |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**400** | Bad Request |  -  |
**404** | Graph not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_graph_by_id**
> Graph find_graph_by_id(x_tenant, graph_id)

Find graph by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import graph_api
from graalsystems.model.graph import Graph
from graalsystems.model.error import Error
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = graalsystems.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: internal
configuration = graalsystems.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with graalsystems.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = graph_api.GraphApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    graph_id = "graphId_example" # str | Id of the graph

    # example passing only required values which don't have defaults set
    try:
        # Find graph by Id
        api_response = api_instance.find_graph_by_id(x_tenant, graph_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling GraphApi->find_graph_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **graph_id** | **str**| Id of the graph |

### Return type

[**Graph**](Graph.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.graph+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Graph not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_graphs**
> GraphPage find_graphs(x_tenant)

Retrieve all graphs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import graph_api
from graalsystems.model.graph_page import GraphPage
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = graalsystems.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: internal
configuration = graalsystems.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with graalsystems.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = graph_api.GraphApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200
    owner = "owner_example" # str |  (optional)
    type = "type_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all graphs
        api_response = api_instance.find_graphs(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling GraphApi->find_graphs: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all graphs
        api_response = api_instance.find_graphs(x_tenant, page=page, size=size, owner=owner, type=type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling GraphApi->find_graphs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200
 **owner** | **str**|  | [optional]
 **type** | **str**|  | [optional]

### Return type

[**GraphPage**](GraphPage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.graph+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_graph**
> Graph update_graph(x_tenant, graph_id, patch)

Update a graph

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import graph_api
from graalsystems.model.graph import Graph
from graalsystems.model.patch import Patch
from graalsystems.model.error import Error
from pprint import pprint
# Defining the host is optional and defaults to http://localhost
# See configuration.py for a list of all supported configuration parameters.
configuration = graalsystems.Configuration(
    host = "http://localhost"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: internal
configuration = graalsystems.Configuration(
    host = "http://localhost"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with graalsystems.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = graph_api.GraphApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    graph_id = "graphId_example" # str | Id of the graph
    patch = [
        Patch(
            op="add",
            _from="_from_example",
            path="path_example",
            value={},
        ),
    ] # [Patch] | The patch

    # example passing only required values which don't have defaults set
    try:
        # Update a graph
        api_response = api_instance.update_graph(x_tenant, graph_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling GraphApi->update_graph: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **graph_id** | **str**| Id of the graph |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Graph**](Graph.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.graph+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

