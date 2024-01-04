# graalsystems.ActionApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**execute_action**](ActionApi.md#execute_action) | **POST** /actions | Execute an action


# **execute_action**
> execute_action(x_tenant, action)

Execute an action

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import action_api
from graalsystems.model.action import Action
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
    api_instance = action_api.ActionApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    action = Action(
        comment="comment_example",
        type="type_example",
        metadata={
            "key": {},
        },
    ) # Action | 

    # example passing only required values which don't have defaults set
    try:
        # Execute an action
        api_instance.execute_action(x_tenant, action)
    except graalsystems.ApiException as e:
        print("Exception when calling ActionApi->execute_action: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **action** | [**Action**](Action.md)|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.action+json
 - **Accept**: Not defined


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

