# graalsystems.EnvApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_capacity**](EnvApi.md#get_capacity) | **GET** /capacity | Retrieve the capacity
[**get_endpoints**](EnvApi.md#get_endpoints) | **GET** /env/endpoints | Find the endpoints for the current tenant
[**get_env**](EnvApi.md#get_env) | **GET** /env | Retrieve the current tenant
[**get_metrics_for_tenant**](EnvApi.md#get_metrics_for_tenant) | **GET** /env/metrics | Find the metrics for the current tenant


# **get_capacity**
> TargetInfo get_capacity(x_tenant)

Retrieve the capacity

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import env_api
from graalsystems.model.target_info import TargetInfo
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
    api_instance = env_api.EnvApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve the capacity
        api_response = api_instance.get_capacity(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnvApi->get_capacity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**TargetInfo**](TargetInfo.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.capacity+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_endpoints**
> {str: (str,)} get_endpoints(x_tenant)

Find the endpoints for the current tenant

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import env_api
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
    api_instance = env_api.EnvApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Find the endpoints for the current tenant
        api_response = api_instance.get_endpoints(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnvApi->get_endpoints: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

**{str: (str,)}**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_env**
> Tenant1 get_env(x_tenant)

Retrieve the current tenant

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import env_api
from graalsystems.model.tenant1 import Tenant1
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
    api_instance = env_api.EnvApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve the current tenant
        api_response = api_instance.get_env(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnvApi->get_env: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**Tenant1**](Tenant1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.env+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_metrics_for_tenant**
> [Metric] get_metrics_for_tenant(x_tenant, metric)

Find the metrics for the current tenant

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import env_api
from graalsystems.model.metric import Metric
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
    api_instance = env_api.EnvApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    metric = "metric_example" # str | The metric name
    _from = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)
    to = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Find the metrics for the current tenant
        api_response = api_instance.get_metrics_for_tenant(x_tenant, metric)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnvApi->get_metrics_for_tenant: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Find the metrics for the current tenant
        api_response = api_instance.get_metrics_for_tenant(x_tenant, metric, _from=_from, to=to)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnvApi->get_metrics_for_tenant: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **metric** | **str**| The metric name |
 **_from** | **datetime**|  | [optional]
 **to** | **datetime**|  | [optional]

### Return type

[**[Metric]**](Metric.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

