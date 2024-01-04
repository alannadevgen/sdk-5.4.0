# graalsystems.SecretApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_secret**](SecretApi.md#create_secret) | **POST** /secrets | Create a secret
[**delete_secret_by_id**](SecretApi.md#delete_secret_by_id) | **DELETE** /secrets/{secretId} | Delete a secret by an id
[**find_secret_by_id**](SecretApi.md#find_secret_by_id) | **GET** /secrets/{secretId} | Find secret by Id
[**find_secret_data_by_id**](SecretApi.md#find_secret_data_by_id) | **GET** /secrets/{secretId}?data | Find secret data by Id
[**find_secrets**](SecretApi.md#find_secrets) | **GET** /secrets | Retrieve all secrets
[**update_secret**](SecretApi.md#update_secret) | **PATCH** /secrets/{secretId} | Update a secret


# **create_secret**
> Secret create_secret(x_tenant, secret)

Create a secret

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import secret_api
from graalsystems.model.secret import Secret
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
    api_instance = secret_api.SecretApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    secret = Secret(
        id="id_example",
        data="data_example",
        name="name_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        labels={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
    ) # Secret | The secret to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a secret
        api_response = api_instance.create_secret(x_tenant, secret)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SecretApi->create_secret: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **secret** | [**Secret**](Secret.md)| The secret to be created |

### Return type

[**Secret**](Secret.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.secret+json
 - **Accept**: application/vnd.graal.systems.v1.secret+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_secret_by_id**
> delete_secret_by_id(x_tenant, secret_id)

Delete a secret by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import secret_api
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
    api_instance = secret_api.SecretApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    secret_id = "secretId_example" # str | Id of the secret

    # example passing only required values which don't have defaults set
    try:
        # Delete a secret by an id
        api_instance.delete_secret_by_id(x_tenant, secret_id)
    except graalsystems.ApiException as e:
        print("Exception when calling SecretApi->delete_secret_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **secret_id** | **str**| Id of the secret |

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
**404** | Secret not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_secret_by_id**
> Secret find_secret_by_id(x_tenant, secret_id)

Find secret by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import secret_api
from graalsystems.model.secret import Secret
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
    api_instance = secret_api.SecretApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    secret_id = "secretId_example" # str | Id of the secret

    # example passing only required values which don't have defaults set
    try:
        # Find secret by Id
        api_response = api_instance.find_secret_by_id(x_tenant, secret_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SecretApi->find_secret_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **secret_id** | **str**| Id of the secret |

### Return type

[**Secret**](Secret.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.secret+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Secret not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_secret_data_by_id**
> file_type find_secret_data_by_id(x_tenant, secret_id)

Find secret data by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import secret_api
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
    api_instance = secret_api.SecretApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    secret_id = "secretId_example" # str | Id of the secret

    # example passing only required values which don't have defaults set
    try:
        # Find secret data by Id
        api_response = api_instance.find_secret_data_by_id(x_tenant, secret_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SecretApi->find_secret_data_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **secret_id** | **str**| Id of the secret |

### Return type

**file_type**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Secret not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_secrets**
> [Secret] find_secrets(x_tenant)

Retrieve all secrets

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import secret_api
from graalsystems.model.secret import Secret
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
    api_instance = secret_api.SecretApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all secrets
        api_response = api_instance.find_secrets(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SecretApi->find_secrets: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Secret]**](Secret.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.secret+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_secret**
> Secret update_secret(x_tenant, secret_id, patch)

Update a secret

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import secret_api
from graalsystems.model.secret import Secret
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
    api_instance = secret_api.SecretApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    secret_id = "secretId_example" # str | Id of the secret
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
        # Update a secret
        api_response = api_instance.update_secret(x_tenant, secret_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SecretApi->update_secret: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **secret_id** | **str**| Id of the secret |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Secret**](Secret.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.secret+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Bucket not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

