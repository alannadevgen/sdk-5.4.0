# graalsystems.HistoryApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_resource_history_for_user**](HistoryApi.md#add_resource_history_for_user) | **POST** /history | Add history for user
[**add_search_history_for_user**](HistoryApi.md#add_search_history_for_user) | **POST** /search/history | Add search history for user
[**get_resource_history**](HistoryApi.md#get_resource_history) | **GET** /history | Get resource history for user
[**get_search_history**](HistoryApi.md#get_search_history) | **GET** /search/history | Search history for user


# **add_resource_history_for_user**
> add_resource_history_for_user(x_tenant, type, id)

Add history for user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import history_api
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
    api_instance = history_api.HistoryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    type = "type_example" # str | The type of resource
    id = "id_example" # str | The id of resource

    # example passing only required values which don't have defaults set
    try:
        # Add history for user
        api_instance.add_resource_history_for_user(x_tenant, type, id)
    except graalsystems.ApiException as e:
        print("Exception when calling HistoryApi->add_resource_history_for_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **type** | **str**| The type of resource |
 **id** | **str**| The id of resource |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **add_search_history_for_user**
> [SearchHistory] add_search_history_for_user(x_tenant, search_history)

Add search history for user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import history_api
from graalsystems.model.search_history import SearchHistory
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
    api_instance = history_api.HistoryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    search_history = SearchHistory(
        id="id_example",
        term="term_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
    ) # SearchHistory | The search history to be created

    # example passing only required values which don't have defaults set
    try:
        # Add search history for user
        api_response = api_instance.add_search_history_for_user(x_tenant, search_history)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling HistoryApi->add_search_history_for_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **search_history** | [**SearchHistory**](SearchHistory.md)| The search history to be created |

### Return type

[**[SearchHistory]**](SearchHistory.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.searchhistory+json
 - **Accept**: application/vnd.graal.systems.v1.searchhistory+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_resource_history**
> [Result] get_resource_history(x_tenant)

Get resource history for user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import history_api
from graalsystems.model.result import Result
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
    api_instance = history_api.HistoryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get resource history for user
        api_response = api_instance.get_resource_history(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling HistoryApi->get_resource_history: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Result]**](Result.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.result+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_search_history**
> [SearchHistory] get_search_history(x_tenant)

Search history for user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import history_api
from graalsystems.model.search_history import SearchHistory
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
    api_instance = history_api.HistoryApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Search history for user
        api_response = api_instance.get_search_history(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling HistoryApi->get_search_history: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[SearchHistory]**](SearchHistory.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.searchhistory+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

