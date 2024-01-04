# graalsystems.SubscriptionApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_subscription**](SubscriptionApi.md#create_subscription) | **POST** /subscriptions | Create an subscription
[**delete_subscription_by_id**](SubscriptionApi.md#delete_subscription_by_id) | **DELETE** /subscriptions/{subscriptionId} | Delete a subscription by its id
[**find_subscription**](SubscriptionApi.md#find_subscription) | **GET** /subscriptions | Retrieve all subscription
[**find_subscription_by_id**](SubscriptionApi.md#find_subscription_by_id) | **GET** /subscriptions/{subscriptionId} | Find subscription by Id
[**update_subscription**](SubscriptionApi.md#update_subscription) | **PATCH** /subscriptions/{subscriptionId} | Update a subscription


# **create_subscription**
> Subscription create_subscription(x_tenant, subscription)

Create an subscription

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import subscription_api
from graalsystems.model.subscription import Subscription
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
    api_instance = subscription_api.SubscriptionApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    subscription = Subscription(
        id="id_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        status="status_example",
        company=Company(None),
        contact=Contact(None),
    ) # Subscription | The subscription to be created

    # example passing only required values which don't have defaults set
    try:
        # Create an subscription
        api_response = api_instance.create_subscription(x_tenant, subscription)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SubscriptionApi->create_subscription: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **subscription** | [**Subscription**](Subscription.md)| The subscription to be created |

### Return type

[**Subscription**](Subscription.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.subscription+json
 - **Accept**: application/vnd.graal.systems.v1.subscription+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_subscription_by_id**
> delete_subscription_by_id(x_tenant, subscription_id)

Delete a subscription by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import subscription_api
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
    api_instance = subscription_api.SubscriptionApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    subscription_id = "subscriptionId_example" # str | Id of the Subscription

    # example passing only required values which don't have defaults set
    try:
        # Delete a subscription by its id
        api_instance.delete_subscription_by_id(x_tenant, subscription_id)
    except graalsystems.ApiException as e:
        print("Exception when calling SubscriptionApi->delete_subscription_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **subscription_id** | **str**| Id of the Subscription |

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
**404** | Subscription not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_subscription**
> [Subscription] find_subscription(x_tenant)

Retrieve all subscription

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import subscription_api
from graalsystems.model.subscription import Subscription
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
    api_instance = subscription_api.SubscriptionApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all subscription
        api_response = api_instance.find_subscription(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SubscriptionApi->find_subscription: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Subscription]**](Subscription.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.subscription+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_subscription_by_id**
> Subscription find_subscription_by_id(x_tenant, subscription_id)

Find subscription by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import subscription_api
from graalsystems.model.subscription import Subscription
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
    api_instance = subscription_api.SubscriptionApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    subscription_id = "subscriptionId_example" # str | Id of the subscription

    # example passing only required values which don't have defaults set
    try:
        # Find subscription by Id
        api_response = api_instance.find_subscription_by_id(x_tenant, subscription_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SubscriptionApi->find_subscription_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **subscription_id** | **str**| Id of the subscription |

### Return type

[**Subscription**](Subscription.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.subscription+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Subscription not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_subscription**
> Subscription update_subscription(x_tenant, subscription_id, patch)

Update a subscription

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import subscription_api
from graalsystems.model.subscription import Subscription
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
    api_instance = subscription_api.SubscriptionApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    subscription_id = "subscriptionId_example" # str | Id of the Subscription
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
        # Update a subscription
        api_response = api_instance.update_subscription(x_tenant, subscription_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SubscriptionApi->update_subscription: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **subscription_id** | **str**| Id of the Subscription |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Subscription**](Subscription.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.subscription+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Usage not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

