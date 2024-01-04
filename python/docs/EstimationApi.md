# graalsystems.EstimationApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_estimation**](EstimationApi.md#create_estimation) | **POST** /estimations | Create an estimation


# **create_estimation**
> Estimation create_estimation(x_tenant, estimation)

Create an estimation

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import estimation_api
from graalsystems.model.estimation import Estimation
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
    api_instance = estimation_api.EstimationApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    estimation = Estimation(
        currency="currency_example",
        amount="amount_example",
        requests=[
            Request(
                name="name_example",
                currency="currency_example",
                amount="amount_example",
                product_type="INSTANCE",
                product_reference="product_reference_example",
                quantity=3.14,
            ),
        ],
    ) # Estimation | The estimation to be calculated

    # example passing only required values which don't have defaults set
    try:
        # Create an estimation
        api_response = api_instance.create_estimation(x_tenant, estimation)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EstimationApi->create_estimation: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **estimation** | [**Estimation**](Estimation.md)| The estimation to be calculated |

### Return type

[**Estimation**](Estimation.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.estimation+json
 - **Accept**: application/vnd.graal.systems.v1.estimation+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

