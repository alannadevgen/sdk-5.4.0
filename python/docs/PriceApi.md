# graalsystems.PriceApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_price**](PriceApi.md#create_price) | **POST** /prices | Create an price
[**delete_price_by_id**](PriceApi.md#delete_price_by_id) | **DELETE** /prices/{priceId} | Delete a price by its id
[**find_price_by_id**](PriceApi.md#find_price_by_id) | **GET** /prices/{priceId} | Find price by Id
[**find_prices**](PriceApi.md#find_prices) | **GET** /prices | Retrieve all prices
[**update_price**](PriceApi.md#update_price) | **PATCH** /prices/{priceId} | Update a price


# **create_price**
> Price create_price(price)

Create an price

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import price_api
from graalsystems.model.price import Price
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
    api_instance = price_api.PriceApi(api_client)
    price = Price(
        id="id_example",
        currency="currency_example",
        amount="amount_example",
        product_type="product_type_example",
        product_reference="product_reference_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Price | The price to be created

    # example passing only required values which don't have defaults set
    try:
        # Create an price
        api_response = api_instance.create_price(price)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PriceApi->create_price: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **price** | [**Price**](Price.md)| The price to be created |

### Return type

[**Price**](Price.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.price+json
 - **Accept**: application/vnd.graal.systems.v1.price+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_price_by_id**
> delete_price_by_id(x_tenant, price_id)

Delete a price by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import price_api
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
    api_instance = price_api.PriceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    price_id = "priceId_example" # str | Id of the Price

    # example passing only required values which don't have defaults set
    try:
        # Delete a price by its id
        api_instance.delete_price_by_id(x_tenant, price_id)
    except graalsystems.ApiException as e:
        print("Exception when calling PriceApi->delete_price_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **price_id** | **str**| Id of the Price |

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
**404** | Price not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_price_by_id**
> Price find_price_by_id(x_tenant, price_id)

Find price by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import price_api
from graalsystems.model.price import Price
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
    api_instance = price_api.PriceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    price_id = "priceId_example" # str | Id of the price

    # example passing only required values which don't have defaults set
    try:
        # Find price by Id
        api_response = api_instance.find_price_by_id(x_tenant, price_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PriceApi->find_price_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **price_id** | **str**| Id of the price |

### Return type

[**Price**](Price.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.price+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Price not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_prices**
> [Price] find_prices(x_tenant)

Retrieve all prices

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import price_api
from graalsystems.model.price import Price
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
    api_instance = price_api.PriceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all prices
        api_response = api_instance.find_prices(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PriceApi->find_prices: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Price]**](Price.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.price+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_price**
> Price update_price(x_tenant, price_id, patch)

Update a price

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import price_api
from graalsystems.model.price import Price
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
    api_instance = price_api.PriceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    price_id = "priceId_example" # str | Id of the Price
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
        # Update a price
        api_response = api_instance.update_price(x_tenant, price_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling PriceApi->update_price: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **price_id** | **str**| Id of the Price |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Price**](Price.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.price+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Price not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

