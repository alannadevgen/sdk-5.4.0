# graalsystems.LayerApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_layer**](LayerApi.md#create_layer) | **POST** /layers | Create a layer
[**delete_layer_by_id**](LayerApi.md#delete_layer_by_id) | **DELETE** /layers/{name} | Delete a layer by an id
[**find_layer_by_id**](LayerApi.md#find_layer_by_id) | **GET** /layers/{name} | Find layer by Id
[**find_layers**](LayerApi.md#find_layers) | **GET** /layers | Retrieve all layers
[**update_layer**](LayerApi.md#update_layer) | **PATCH** /layers/{name} | Update a layer


# **create_layer**
> Layer create_layer(x_tenant, layer)

Create a layer

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import layer_api
from graalsystems.model.layer import Layer
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
    api_instance = layer_api.LayerApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer = Layer(
        id="id_example",
        technical_name="technical_name_example",
        name="name_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Layer | The layer to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a layer
        api_response = api_instance.create_layer(x_tenant, layer)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LayerApi->create_layer: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer** | [**Layer**](Layer.md)| The layer to be created |

### Return type

[**Layer**](Layer.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.layer+json
 - **Accept**: application/vnd.graal.systems.v1.layer+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_layer_by_id**
> delete_layer_by_id(x_tenant, name)

Delete a layer by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import layer_api
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
    api_instance = layer_api.LayerApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    name = "name_example" # str | Id of the layer

    # example passing only required values which don't have defaults set
    try:
        # Delete a layer by an id
        api_instance.delete_layer_by_id(x_tenant, name)
    except graalsystems.ApiException as e:
        print("Exception when calling LayerApi->delete_layer_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **name** | **str**| Id of the layer |

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
**404** | Layer not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_layer_by_id**
> Layer find_layer_by_id(x_tenant, name)

Find layer by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import layer_api
from graalsystems.model.layer import Layer
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
    api_instance = layer_api.LayerApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    name = "name_example" # str | Id of the layer

    # example passing only required values which don't have defaults set
    try:
        # Find layer by Id
        api_response = api_instance.find_layer_by_id(x_tenant, name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LayerApi->find_layer_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **name** | **str**| Id of the layer |

### Return type

[**Layer**](Layer.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.layer+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Layer not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_layers**
> [Layer] find_layers(x_tenant)

Retrieve all layers

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import layer_api
from graalsystems.model.layer import Layer
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
    api_instance = layer_api.LayerApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all layers
        api_response = api_instance.find_layers(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LayerApi->find_layers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Layer]**](Layer.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.layer+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_layer**
> Layer update_layer(x_tenant, name, patch)

Update a layer

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import layer_api
from graalsystems.model.layer import Layer
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
    api_instance = layer_api.LayerApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    name = "name_example" # str | Id of the layer
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
        # Update a layer
        api_response = api_instance.update_layer(x_tenant, name, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LayerApi->update_layer: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **name** | **str**| Id of the layer |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Layer**](Layer.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.layer+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Layer not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

