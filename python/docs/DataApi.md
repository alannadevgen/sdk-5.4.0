# graalsystems.DataApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_files**](DataApi.md#delete_files) | **DELETE** /buckets/{bucketId}/data | Delete files
[**download_file**](DataApi.md#download_file) | **GET** /buckets/{bucketId}/data?download | Download data by path
[**get_data_files**](DataApi.md#get_data_files) | **GET** /buckets/{bucketId}/data | Get files
[**upload_file**](DataApi.md#upload_file) | **POST** /buckets/{bucketId}/data | Upload a file


# **delete_files**
> delete_files(x_tenant, bucket_id, path)

Delete files

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import data_api
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
    api_instance = data_api.DataApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket
    path = [
        "path_example",
    ] # [str] | path

    # example passing only required values which don't have defaults set
    try:
        # Delete files
        api_instance.delete_files(x_tenant, bucket_id, path)
    except graalsystems.ApiException as e:
        print("Exception when calling DataApi->delete_files: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |
 **path** | **[str]**| path |

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
**404** | File not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **download_file**
> file_type download_file(x_tenant, bucket_id, path)

Download data by path

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import data_api
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
    api_instance = data_api.DataApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket
    path = "path_example" # str | path

    # example passing only required values which don't have defaults set
    try:
        # Download data by path
        api_response = api_instance.download_file(x_tenant, bucket_id, path)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DataApi->download_file: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |
 **path** | **str**| path |

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
**404** | File not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_data_files**
> [FileOrDirectory] get_data_files(x_tenant, bucket_id, path)

Get files

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import data_api
from graalsystems.model.file_or_directory import FileOrDirectory
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
    api_instance = data_api.DataApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket
    path = "path_example" # str | path

    # example passing only required values which don't have defaults set
    try:
        # Get files
        api_response = api_instance.get_data_files(x_tenant, bucket_id, path)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DataApi->get_data_files: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |
 **path** | **str**| path |

### Return type

[**[FileOrDirectory]**](FileOrDirectory.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.file+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | File not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **upload_file**
> upload_file(x_tenant, bucket_id)

Upload a file

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import data_api
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
    api_instance = data_api.DataApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket
    path = "path_example" # str | path (optional)
    filename = [
        open('/path/to/file', 'rb'),
    ] # [file_type] |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Upload a file
        api_instance.upload_file(x_tenant, bucket_id)
    except graalsystems.ApiException as e:
        print("Exception when calling DataApi->upload_file: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Upload a file
        api_instance.upload_file(x_tenant, bucket_id, path=path, filename=filename)
    except graalsystems.ApiException as e:
        print("Exception when calling DataApi->upload_file: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |
 **path** | **str**| path | [optional]
 **filename** | **[file_type]**|  | [optional]

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: Not defined


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

