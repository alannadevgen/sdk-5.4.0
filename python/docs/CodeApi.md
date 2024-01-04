# graalsystems.CodeApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**download_code**](CodeApi.md#download_code) | **POST** /code?download | Download code
[**verify_code**](CodeApi.md#verify_code) | **POST** /code?verify | Verify code


# **download_code**
> file_type download_code(x_tenant)

Download code

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import code_api
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
    api_instance = code_api.CodeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    source = "source_example" # str |  (optional)
    destination = "destination_example" # str |  (optional)
    filename = [
        open('/path/to/file', 'rb'),
    ] # [file_type] |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Download code
        api_response = api_instance.download_code(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling CodeApi->download_code: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Download code
        api_response = api_instance.download_code(x_tenant, source=source, destination=destination, filename=filename)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling CodeApi->download_code: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **source** | **str**|  | [optional]
 **destination** | **str**|  | [optional]
 **filename** | **[file_type]**|  | [optional]

### Return type

**file_type**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: */*


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **verify_code**
> verify_code(x_tenant)

Verify code

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import code_api
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
    api_instance = code_api.CodeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    source = "source_example" # str |  (optional)
    destination = "destination_example" # str |  (optional)
    filename = [
        open('/path/to/file', 'rb'),
    ] # [file_type] |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Verify code
        api_instance.verify_code(x_tenant)
    except graalsystems.ApiException as e:
        print("Exception when calling CodeApi->verify_code: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Verify code
        api_instance.verify_code(x_tenant, source=source, destination=destination, filename=filename)
    except graalsystems.ApiException as e:
        print("Exception when calling CodeApi->verify_code: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **source** | **str**|  | [optional]
 **destination** | **str**|  | [optional]
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
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

