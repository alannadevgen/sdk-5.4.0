# graalsystems.StripeApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**stripe_create_setup_intent**](StripeApi.md#stripe_create_setup_intent) | **POST** /stripe/create-setup-intent | create setup intent on Stripe
[**stripe_public_key**](StripeApi.md#stripe_public_key) | **GET** /stripe/public-key | get Stripe public key


# **stripe_create_setup_intent**
> InlineResponse200 stripe_create_setup_intent(x_tenant)

create setup intent on Stripe

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stripe_api
from graalsystems.model.inline_response200 import InlineResponse200
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
    api_instance = stripe_api.StripeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # create setup intent on Stripe
        api_response = api_instance.stripe_create_setup_intent(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StripeApi->stripe_create_setup_intent: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**InlineResponse200**](InlineResponse200.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **stripe_public_key**
> InlineResponse2001 stripe_public_key(x_tenant)

get Stripe public key

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import stripe_api
from graalsystems.model.inline_response2001 import InlineResponse2001
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
    api_instance = stripe_api.StripeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # get Stripe public key
        api_response = api_instance.stripe_public_key(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling StripeApi->stripe_public_key: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**InlineResponse2001**](InlineResponse2001.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

