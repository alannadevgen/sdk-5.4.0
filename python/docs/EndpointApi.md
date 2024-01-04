# graalsystems.EndpointApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**call_proxy_infer**](EndpointApi.md#call_proxy_infer) | **POST** /projects/{projectId}/endpoints/{endpointId}/proxy/infer | Call proxy infer
[**call_proxy_metadata**](EndpointApi.md#call_proxy_metadata) | **GET** /projects/{projectId}/endpoints/{endpointId}/proxy/metadata | Call proxy metadata
[**create_endpoint_for_project**](EndpointApi.md#create_endpoint_for_project) | **POST** /projects/{projectId}/endpoints | Create endpoint
[**delete_endpoint_by_id_and_project_id**](EndpointApi.md#delete_endpoint_by_id_and_project_id) | **DELETE** /projects/{projectId}/endpoints/{endpointId} | Delete an endpoint by an id
[**find_endpoint_by_id_and_project_id**](EndpointApi.md#find_endpoint_by_id_and_project_id) | **GET** /projects/{projectId}/endpoints/{endpointId} | Find endpoint by Id
[**find_endpoints_by_project_id**](EndpointApi.md#find_endpoints_by_project_id) | **GET** /projects/{projectId}/endpoints | Retrieve all endpoints
[**get_logs_for_endpoint**](EndpointApi.md#get_logs_for_endpoint) | **GET** /projects/{projectId}/endpoints/{endpointId}/logs | Get logs
[**update_endpoint_by_id_and_project_id**](EndpointApi.md#update_endpoint_by_id_and_project_id) | **PATCH** /projects/{projectId}/endpoints/{endpointId} | Update an endpoint


# **call_proxy_infer**
> call_proxy_infer(x_tenant, project_id, endpoint_id)

Call proxy infer

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint_id = "endpointId_example" # str | Id of the endpoint
    body = {} # {str: (bool, date, datetime, dict, float, int, list, str, none_type)} |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Call proxy infer
        api_instance.call_proxy_infer(x_tenant, project_id, endpoint_id)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->call_proxy_infer: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Call proxy infer
        api_instance.call_proxy_infer(x_tenant, project_id, endpoint_id, body=body)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->call_proxy_infer: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint_id** | **str**| Id of the endpoint |
 **body** | **{str: (bool, date, datetime, dict, float, int, list, str, none_type)}**|  | [optional]

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**404** | Endpoint not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **call_proxy_metadata**
> call_proxy_metadata(x_tenant, project_id, endpoint_id)

Call proxy metadata

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint_id = "endpointId_example" # str | Id of the endpoint

    # example passing only required values which don't have defaults set
    try:
        # Call proxy metadata
        api_instance.call_proxy_metadata(x_tenant, project_id, endpoint_id)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->call_proxy_metadata: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint_id** | **str**| Id of the endpoint |

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
**200** | Successful operation |  -  |
**404** | Endpoint not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_endpoint_for_project**
> Endpoint create_endpoint_for_project(x_tenant, project_id, endpoint)

Create endpoint

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
from graalsystems.model.endpoint import Endpoint
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint = Endpoint(
        id="id_example",
        name="name_example",
        description="description_example",
        version="version_example",
        type="type_example",
        library=FileLibrary(None),
        uri=Uri(),
        instance_type="instance_type_example",
        owner="owner_example",
        infrastructure_id="infrastructure_id_example",
        device_id="device_id_example",
        public_url="public_url_example",
        status="status_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        labels={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
    ) # Endpoint | The endpoint to be created

    # example passing only required values which don't have defaults set
    try:
        # Create endpoint
        api_response = api_instance.create_endpoint_for_project(x_tenant, project_id, endpoint)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->create_endpoint_for_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint** | [**Endpoint**](Endpoint.md)| The endpoint to be created |

### Return type

[**Endpoint**](Endpoint.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.endpoint+json
 - **Accept**: application/vnd.graal.systems.v1.endpoint+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_endpoint_by_id_and_project_id**
> delete_endpoint_by_id_and_project_id(x_tenant, project_id, endpoint_id)

Delete an endpoint by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint_id = "endpointId_example" # str | Id of the endpoint

    # example passing only required values which don't have defaults set
    try:
        # Delete an endpoint by an id
        api_instance.delete_endpoint_by_id_and_project_id(x_tenant, project_id, endpoint_id)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->delete_endpoint_by_id_and_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint_id** | **str**| Id of the endpoint |

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
**404** | Endpoint not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_endpoint_by_id_and_project_id**
> Endpoint find_endpoint_by_id_and_project_id(x_tenant, project_id, endpoint_id)

Find endpoint by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
from graalsystems.model.endpoint import Endpoint
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint_id = "endpointId_example" # str | Id of the endpoint

    # example passing only required values which don't have defaults set
    try:
        # Find endpoint by Id
        api_response = api_instance.find_endpoint_by_id_and_project_id(x_tenant, project_id, endpoint_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->find_endpoint_by_id_and_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint_id** | **str**| Id of the endpoint |

### Return type

[**Endpoint**](Endpoint.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.endpoint+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Endpoint not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_endpoints_by_project_id**
> EndpointPage find_endpoints_by_project_id(x_tenant, project_id)

Retrieve all endpoints

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
from graalsystems.model.endpoint_page import EndpointPage
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all endpoints
        api_response = api_instance.find_endpoints_by_project_id(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->find_endpoints_by_project_id: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all endpoints
        api_response = api_instance.find_endpoints_by_project_id(x_tenant, project_id, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->find_endpoints_by_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**EndpointPage**](EndpointPage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.endpoint+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_logs_for_endpoint**
> [LogEntry] get_logs_for_endpoint(x_tenant, project_id, endpoint_id)

Get logs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
from graalsystems.model.log_entry import LogEntry
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint_id = "endpointId_example" # str | Id of the endpoint
    cursor = "cursor_example" # str | The cursor (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get logs
        api_response = api_instance.get_logs_for_endpoint(x_tenant, project_id, endpoint_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->get_logs_for_endpoint: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get logs
        api_response = api_instance.get_logs_for_endpoint(x_tenant, project_id, endpoint_id, cursor=cursor)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->get_logs_for_endpoint: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint_id** | **str**| Id of the endpoint |
 **cursor** | **str**| The cursor | [optional]

### Return type

[**[LogEntry]**](LogEntry.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.log+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  * X-Cursor - Current cursor <br>  |
**400** | Bad Request |  -  |
**404** | Run of job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_endpoint_by_id_and_project_id**
> Endpoint update_endpoint_by_id_and_project_id(x_tenant, project_id, endpoint_id, patch)

Update an endpoint

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import endpoint_api
from graalsystems.model.endpoint import Endpoint
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
    api_instance = endpoint_api.EndpointApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    endpoint_id = "endpointId_example" # str | Id of the endpoint
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
        # Update an endpoint
        api_response = api_instance.update_endpoint_by_id_and_project_id(x_tenant, project_id, endpoint_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EndpointApi->update_endpoint_by_id_and_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **endpoint_id** | **str**| Id of the endpoint |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Endpoint**](Endpoint.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.endpoint+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

