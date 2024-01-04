# graalsystems.MessageApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**send_message**](MessageApi.md#send_message) | **POST** /messages | Send an message


# **send_message**
> send_message(x_tenant, message)

Send an message

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import message_api
from graalsystems.model.message import Message
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
    api_instance = message_api.MessageApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    message = Message(
        to="to_example",
        _from="_from_example",
        subject="subject_example",
        body="body_example",
        importance="importance_example",
        vars={
            "key": "key_example",
        },
    ) # Message | The message to be created

    # example passing only required values which don't have defaults set
    try:
        # Send an message
        api_instance.send_message(x_tenant, message)
    except graalsystems.ApiException as e:
        print("Exception when calling MessageApi->send_message: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **message** | [**Message**](Message.md)| The message to be created |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.message+json
 - **Accept**: Not defined


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

