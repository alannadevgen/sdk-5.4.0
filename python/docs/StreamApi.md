# graalsystems.StreamApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_stream**](StreamApi.md#create_stream) | **POST** /streams | Create a stream
[**delete_stream_by_id**](StreamApi.md#delete_stream_by_id) | **DELETE** /streams/{streamId} | Delete a stream by an id
[**find_stream_by_id**](StreamApi.md#find_stream_by_id) | **GET** /streams/{streamId} | Find stream by Id
[**find_streams**](StreamApi.md#find_streams) | **GET** /streams | Retrieve all streams
[**update_stream**](StreamApi.md#update_stream) | **PATCH** /streams/{streamId} | Update a stream


# **create_stream**
> Stream create_stream(x_tenant, stream)

Create a stream

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stream_api
from graalsystems.model.stream import Stream
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
    api_instance = stream_api.StreamApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    stream = Stream(
        id="id_example",
        name="name_example",
        description="description_example",
        scope="scope_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
    ) # Stream | The stream to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a stream
        api_response = api_instance.create_stream(x_tenant, stream)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StreamApi->create_stream: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **stream** | [**Stream**](Stream.md)| The stream to be created |

### Return type

[**Stream**](Stream.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.stream+json
 - **Accept**: application/vnd.graal.systems.v1.stream+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_stream_by_id**
> delete_stream_by_id(x_tenant, stream_id)

Delete a stream by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stream_api
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
    api_instance = stream_api.StreamApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    stream_id = "streamId_example" # str | Id of the stream

    # example passing only required values which don't have defaults set
    try:
        # Delete a stream by an id
        api_instance.delete_stream_by_id(x_tenant, stream_id)
    except graalsystems.ApiException as e:
        print("Exception when calling StreamApi->delete_stream_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **stream_id** | **str**| Id of the stream |

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
**404** | Stream not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_stream_by_id**
> Stream find_stream_by_id(x_tenant, stream_id)

Find stream by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stream_api
from graalsystems.model.stream import Stream
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
    api_instance = stream_api.StreamApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    stream_id = "streamId_example" # str | Id of the stream

    # example passing only required values which don't have defaults set
    try:
        # Find stream by Id
        api_response = api_instance.find_stream_by_id(x_tenant, stream_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StreamApi->find_stream_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **stream_id** | **str**| Id of the stream |

### Return type

[**Stream**](Stream.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.stream+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Stream not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_streams**
> [Stream] find_streams(x_tenant)

Retrieve all streams

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stream_api
from graalsystems.model.stream import Stream
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
    api_instance = stream_api.StreamApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all streams
        api_response = api_instance.find_streams(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StreamApi->find_streams: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Stream]**](Stream.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.stream+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_stream**
> Stream update_stream(x_tenant, stream_id, patch)

Update a stream

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stream_api
from graalsystems.model.stream import Stream
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
    api_instance = stream_api.StreamApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    stream_id = "streamId_example" # str | Id of the stream
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
        # Update a stream
        api_response = api_instance.update_stream(x_tenant, stream_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StreamApi->update_stream: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **stream_id** | **str**| Id of the stream |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Stream**](Stream.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.stream+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Stream not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

