# graalsystems.PaymentmethodApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_payment_method**](PaymentmethodApi.md#create_payment_method) | **POST** /paymentmethods | Create an payment method
[**delete_payment_method_by_id**](PaymentmethodApi.md#delete_payment_method_by_id) | **DELETE** /paymentmethods/{paymentMethodId} | Delete a payment method by its id
[**find_favorite_or_random_valid_payment_method**](PaymentmethodApi.md#find_favorite_or_random_valid_payment_method) | **GET** /paymentmethods?favorite|random | Retrieve the favorite payment method and a random valid
[**find_payment_method_by_id**](PaymentmethodApi.md#find_payment_method_by_id) | **GET** /paymentmethods/{paymentMethodId} | Find paymentmethod by Id
[**find_payment_methods**](PaymentmethodApi.md#find_payment_methods) | **GET** /paymentmethods | Retrieve all payment methods
[**update_payment_method**](PaymentmethodApi.md#update_payment_method) | **PATCH** /paymentmethods/{paymentMethodId} | Update a payment method


# **create_payment_method**
> PaymentMethod create_payment_method(x_tenant, payment_method)

Create an payment method

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import paymentmethod_api
from graalsystems.model.payment_method import PaymentMethod
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
    api_instance = paymentmethod_api.PaymentmethodApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    payment_method = PaymentMethod(
        id="id_example",
        details=Details1(),
        provider="provider_example",
        status="status_example",
        remote_payment_method_id="remote_payment_method_id_example",
        favorite=True,
        metadata={
            "key": {},
        },
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
    ) # PaymentMethod | The paymentmethod to be created

    # example passing only required values which don't have defaults set
    try:
        # Create an payment method
        api_response = api_instance.create_payment_method(x_tenant, payment_method)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PaymentmethodApi->create_payment_method: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **payment_method** | [**PaymentMethod**](PaymentMethod.md)| The paymentmethod to be created |

### Return type

[**PaymentMethod**](PaymentMethod.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.paymentmethod+json
 - **Accept**: application/vnd.graal.systems.v1.paymentmethod+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_payment_method_by_id**
> delete_payment_method_by_id(x_tenant, payment_method_id)

Delete a payment method by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import paymentmethod_api
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
    api_instance = paymentmethod_api.PaymentmethodApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    payment_method_id = "paymentMethodId_example" # str | Id of the PaymentMethod

    # example passing only required values which don't have defaults set
    try:
        # Delete a payment method by its id
        api_instance.delete_payment_method_by_id(x_tenant, payment_method_id)
    except graalsystems.ApiException as e:
        print("Exception when calling PaymentmethodApi->delete_payment_method_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **payment_method_id** | **str**| Id of the PaymentMethod |

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
**404** | PaymentMethod not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_favorite_or_random_valid_payment_method**
> PaymentMethod find_favorite_or_random_valid_payment_method(x_tenant)

Retrieve the favorite payment method and a random valid

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import paymentmethod_api
from graalsystems.model.payment_method import PaymentMethod
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
    api_instance = paymentmethod_api.PaymentmethodApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve the favorite payment method and a random valid
        api_response = api_instance.find_favorite_or_random_valid_payment_method(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PaymentmethodApi->find_favorite_or_random_valid_payment_method: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**PaymentMethod**](PaymentMethod.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.paymentmethod+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_payment_method_by_id**
> PaymentMethod find_payment_method_by_id(x_tenant, payment_method_id)

Find paymentmethod by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import paymentmethod_api
from graalsystems.model.payment_method import PaymentMethod
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
    api_instance = paymentmethod_api.PaymentmethodApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    payment_method_id = "paymentMethodId_example" # str | Id of the payment method

    # example passing only required values which don't have defaults set
    try:
        # Find paymentmethod by Id
        api_response = api_instance.find_payment_method_by_id(x_tenant, payment_method_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PaymentmethodApi->find_payment_method_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **payment_method_id** | **str**| Id of the payment method |

### Return type

[**PaymentMethod**](PaymentMethod.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.paymentmethod+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | PaymentMethod not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_payment_methods**
> [PaymentMethod] find_payment_methods(x_tenant)

Retrieve all payment methods

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import paymentmethod_api
from graalsystems.model.payment_method import PaymentMethod
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
    api_instance = paymentmethod_api.PaymentmethodApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all payment methods
        api_response = api_instance.find_payment_methods(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PaymentmethodApi->find_payment_methods: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[PaymentMethod]**](PaymentMethod.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.paymentmethod+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_payment_method**
> PaymentMethod update_payment_method(x_tenant, payment_method_id, patch)

Update a payment method

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import paymentmethod_api
from graalsystems.model.payment_method import PaymentMethod
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
    api_instance = paymentmethod_api.PaymentmethodApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    payment_method_id = "paymentMethodId_example" # str | Id of the PaymentMethod
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
        # Update a payment method
        api_response = api_instance.update_payment_method(x_tenant, payment_method_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PaymentmethodApi->update_payment_method: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **payment_method_id** | **str**| Id of the PaymentMethod |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**PaymentMethod**](PaymentMethod.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.paymentmethod+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Usage not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

