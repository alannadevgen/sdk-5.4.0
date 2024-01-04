# graalsystems.LibraryApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_library_by_id**](LibraryApi.md#delete_library_by_id) | **DELETE** /libraries/{libraryId} | Delete a library by an id
[**download_library**](LibraryApi.md#download_library) | **GET** /libraries/{libraryId} | Download library by Id
[**find_libraries**](LibraryApi.md#find_libraries) | **GET** /libraries | List all libraries
[**find_metadata**](LibraryApi.md#find_metadata) | **GET** /libraries/{libraryId}?metadata | Get library metadata by Id
[**upload_library**](LibraryApi.md#upload_library) | **POST** /libraries | Upload a library


# **delete_library_by_id**
> delete_library_by_id(x_tenant, library_id)

Delete a library by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import library_api
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
    api_instance = library_api.LibraryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    library_id = "libraryId_example" # str | Id of the library

    # example passing only required values which don't have defaults set
    try:
        # Delete a library by an id
        api_instance.delete_library_by_id(x_tenant, library_id)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->delete_library_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **library_id** | **str**| Id of the library |

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
**404** | Library not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **download_library**
> file_type download_library(x_tenant, library_id)

Download library by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import library_api
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
    api_instance = library_api.LibraryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    library_id = "libraryId_example" # str | Id of the library

    # example passing only required values which don't have defaults set
    try:
        # Download library by Id
        api_response = api_instance.download_library(x_tenant, library_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->download_library: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **library_id** | **str**| Id of the library |

### Return type

**file_type**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Library not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_libraries**
> [BlobMetadata] find_libraries(x_tenant)

List all libraries

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import library_api
from graalsystems.model.blob_metadata import BlobMetadata
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
    api_instance = library_api.LibraryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    id = [
        "id_example",
    ] # [str] | Id of the library (optional)

    # example passing only required values which don't have defaults set
    try:
        # List all libraries
        api_response = api_instance.find_libraries(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->find_libraries: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # List all libraries
        api_response = api_instance.find_libraries(x_tenant, id=id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->find_libraries: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **id** | **[str]**| Id of the library | [optional]

### Return type

[**[BlobMetadata]**](BlobMetadata.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.blobmetadata+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_metadata**
> BlobMetadata find_metadata(x_tenant, library_id)

Get library metadata by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import library_api
from graalsystems.model.blob_metadata import BlobMetadata
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
    api_instance = library_api.LibraryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    library_id = "libraryId_example" # str | Id of the library

    # example passing only required values which don't have defaults set
    try:
        # Get library metadata by Id
        api_response = api_instance.find_metadata(x_tenant, library_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->find_metadata: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **library_id** | **str**| Id of the library |

### Return type

[**BlobMetadata**](BlobMetadata.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.blobmetadata+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Library not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **upload_library**
> [BlobMetadata] upload_library(x_tenant)

Upload a library

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import library_api
from graalsystems.model.blob_metadata import BlobMetadata
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
    api_instance = library_api.LibraryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    filename = [
        open('/path/to/file', 'rb'),
    ] # [file_type] |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Upload a library
        api_response = api_instance.upload_library(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->upload_library: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Upload a library
        api_response = api_instance.upload_library(x_tenant, filename=filename)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling LibraryApi->upload_library: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **filename** | **[file_type]**|  | [optional]

### Return type

[**[BlobMetadata]**](BlobMetadata.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/vnd.graal.systems.v1.blobmetadata+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

