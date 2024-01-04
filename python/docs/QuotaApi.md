# graalsystems.QuotaApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**find_quota_by_key**](QuotaApi.md#find_quota_by_key) | **GET** /quotas/{key} | Find quota by key
[**find_quotas**](QuotaApi.md#find_quotas) | **GET** /quotas | Retrieve all quotas


# **find_quota_by_key**
> Quota find_quota_by_key(x_tenant, key)

Find quota by key

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import quota_api
from graalsystems.model.quota import Quota
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
    api_instance = quota_api.QuotaApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    key = "key_example" # str | Key of the quota

    # example passing only required values which don't have defaults set
    try:
        # Find quota by key
        api_response = api_instance.find_quota_by_key(x_tenant, key)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling QuotaApi->find_quota_by_key: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **key** | **str**| Key of the quota |

### Return type

[**Quota**](Quota.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.quota+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Quota not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_quotas**
> [Quota] find_quotas(x_tenant)

Retrieve all quotas

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import quota_api
from graalsystems.model.quota import Quota
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
    api_instance = quota_api.QuotaApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all quotas
        api_response = api_instance.find_quotas(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling QuotaApi->find_quotas: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Quota]**](Quota.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.quota+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

