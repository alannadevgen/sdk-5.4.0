# graalsystems.StyleApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**find_style_by_tenant_id**](StyleApi.md#find_style_by_tenant_id) | **GET** /style | Find style by tenant id
[**update_style**](StyleApi.md#update_style) | **PATCH** /style | Update the current style


# **find_style_by_tenant_id**
> Style find_style_by_tenant_id(x_tenant)

Find style by tenant id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import style_api
from graalsystems.model.style import Style
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
    api_instance = style_api.StyleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Find style by tenant id
        api_response = api_instance.find_style_by_tenant_id(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StyleApi->find_style_by_tenant_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**Style**](Style.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.style+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_style**
> Style update_style(x_tenant, patch)

Update the current style

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import style_api
from graalsystems.model.style import Style
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
    api_instance = style_api.StyleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
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
        # Update the current style
        api_response = api_instance.update_style(x_tenant, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StyleApi->update_style: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Style**](Style.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.style+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Rule not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

