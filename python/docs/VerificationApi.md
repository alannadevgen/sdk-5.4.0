# graalsystems.VerificationApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_verification**](VerificationApi.md#create_verification) | **POST** /verifications | Create a verification
[**find_verification_by_code**](VerificationApi.md#find_verification_by_code) | **GET** /verifications | Find a verification by code


# **create_verification**
> create_verification(type, value)

Create a verification

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import verification_api
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
    api_instance = verification_api.VerificationApi(api_client)
    type = "type_example" # str | 
    value = "value_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create a verification
        api_instance.create_verification(type, value)
    except graalsystems.ApiException as e:
        print("Exception when calling VerificationApi->create_verification: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**|  |
 **value** | **str**|  |

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
**201** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_verification_by_code**
> InlineResponse2002 find_verification_by_code(type, value, code)

Find a verification by code

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import verification_api
from graalsystems.model.inline_response2002 import InlineResponse2002
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
    api_instance = verification_api.VerificationApi(api_client)
    type = "type_example" # str | 
    value = "value_example" # str | 
    code = "code_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Find a verification by code
        api_response = api_instance.find_verification_by_code(type, value, code)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling VerificationApi->find_verification_by_code: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**|  |
 **value** | **str**|  |
 **code** | **str**|  |

### Return type

[**InlineResponse2002**](InlineResponse2002.md)

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

