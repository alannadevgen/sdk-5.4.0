# graalsystems.BridgeApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_bridge**](BridgeApi.md#create_bridge) | **POST** /bridges | Create bridge
[**delete_bridge_by_id**](BridgeApi.md#delete_bridge_by_id) | **DELETE** /bridges/{bridgeId} | Delete a bridge by an id
[**find_bridge_by_id**](BridgeApi.md#find_bridge_by_id) | **GET** /bridges/{bridgeId} | Find bridge by Id
[**find_bridges**](BridgeApi.md#find_bridges) | **GET** /bridges | Retrieve all bridges


# **create_bridge**
> Bridge create_bridge(x_tenant, bridge)

Create bridge

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bridge_api
from graalsystems.model.bridge import Bridge
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
    api_instance = bridge_api.BridgeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bridge = Bridge(
        id="id_example",
        type="type_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        configuration={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
        locked=True,
    ) # Bridge | The bridge to be created

    # example passing only required values which don't have defaults set
    try:
        # Create bridge
        api_response = api_instance.create_bridge(x_tenant, bridge)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BridgeApi->create_bridge: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bridge** | [**Bridge**](Bridge.md)| The bridge to be created |

### Return type

[**Bridge**](Bridge.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.bridge+json
 - **Accept**: application/vnd.graal.systems.v1.bridge+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_bridge_by_id**
> delete_bridge_by_id(x_tenant, bridge_id)

Delete a bridge by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bridge_api
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
    api_instance = bridge_api.BridgeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bridge_id = "bridgeId_example" # str | Id of the bridge

    # example passing only required values which don't have defaults set
    try:
        # Delete a bridge by an id
        api_instance.delete_bridge_by_id(x_tenant, bridge_id)
    except graalsystems.ApiException as e:
        print("Exception when calling BridgeApi->delete_bridge_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bridge_id** | **str**| Id of the bridge |

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
**404** | Bridge not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_bridge_by_id**
> Bridge find_bridge_by_id(x_tenant, bridge_id)

Find bridge by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bridge_api
from graalsystems.model.bridge import Bridge
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
    api_instance = bridge_api.BridgeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bridge_id = "bridgeId_example" # str | Id of the bridge

    # example passing only required values which don't have defaults set
    try:
        # Find bridge by Id
        api_response = api_instance.find_bridge_by_id(x_tenant, bridge_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BridgeApi->find_bridge_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bridge_id** | **str**| Id of the bridge |

### Return type

[**Bridge**](Bridge.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.bridge+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Bridge not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_bridges**
> BridgePage find_bridges(x_tenant)

Retrieve all bridges

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bridge_api
from graalsystems.model.bridge_page import BridgePage
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
    api_instance = bridge_api.BridgeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all bridges
        api_response = api_instance.find_bridges(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BridgeApi->find_bridges: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all bridges
        api_response = api_instance.find_bridges(x_tenant, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BridgeApi->find_bridges: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**BridgePage**](BridgePage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.bridge+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

