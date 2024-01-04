# graalsystems.NotificationApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_notification**](NotificationApi.md#create_notification) | **POST** /notifications | Create a notification
[**find_notifications**](NotificationApi.md#find_notifications) | **GET** /notifications | Retrieve all notifications


# **create_notification**
> Notification1 create_notification(notification1)

Create a notification

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import notification_api
from graalsystems.model.notification1 import Notification1
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
    api_instance = notification_api.NotificationApi(api_client)
    notification1 = Notification1(
        id="id_example",
        title="title_example",
        description="description_example",
        infos="infos_example",
        severity="info",
        tags=[
            "tags_example",
        ],
    ) # Notification1 | The notification to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a notification
        api_response = api_instance.create_notification(notification1)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling NotificationApi->create_notification: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **notification1** | [**Notification1**](Notification1.md)| The notification to be created |

### Return type

[**Notification1**](Notification1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.notification+json
 - **Accept**: application/vnd.graal.systems.v1.notification+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_notifications**
> [Notification1] find_notifications(x_tenant)

Retrieve all notifications

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import notification_api
from graalsystems.model.notification1 import Notification1
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
    api_instance = notification_api.NotificationApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all notifications
        api_response = api_instance.find_notifications(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling NotificationApi->find_notifications: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Notification1]**](Notification1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.notification+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

