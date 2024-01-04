# graalsystems.UsageApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_usage**](UsageApi.md#create_usage) | **POST** /usages | Create an usage
[**find_usages**](UsageApi.md#find_usages) | **GET** /usages | Retrieve all usages


# **create_usage**
> Usage create_usage(x_tenant, usage)

Create an usage

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import usage_api
from graalsystems.model.usage import Usage
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
    api_instance = usage_api.UsageApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    usage = Usage(
        product_type="INSTANCE",
        quantity=3.14,
        product_reference="product_reference_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        dimensions={
            "key": "key_example",
        },
    ) # Usage | The usage to be created

    # example passing only required values which don't have defaults set
    try:
        # Create an usage
        api_response = api_instance.create_usage(x_tenant, usage)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UsageApi->create_usage: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **usage** | [**Usage**](Usage.md)| The usage to be created |

### Return type

[**Usage**](Usage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.usage+json
 - **Accept**: application/vnd.graal.systems.v1.usage+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_usages**
> [Usage] find_usages(x_tenant)

Retrieve all usages

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import usage_api
from graalsystems.model.usage import Usage
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
    api_instance = usage_api.UsageApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    _from = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)
    to = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)
    _for = "for_example" # str |  (optional)
    params = {
        "key": "key_example",
    } # {str: (str,)} |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all usages
        api_response = api_instance.find_usages(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UsageApi->find_usages: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all usages
        api_response = api_instance.find_usages(x_tenant, _from=_from, to=to, _for=_for, params=params)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UsageApi->find_usages: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **_from** | **datetime**|  | [optional]
 **to** | **datetime**|  | [optional]
 **_for** | **str**|  | [optional]
 **params** | **{str: (str,)}**|  | [optional]

### Return type

[**[Usage]**](Usage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.usage+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

