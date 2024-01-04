# graalsystems.IdentityProviderApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_identity_provider**](IdentityProviderApi.md#create_identity_provider) | **POST** /identity-providers | Create a user
[**delete_identity_provider_by_id**](IdentityProviderApi.md#delete_identity_provider_by_id) | **DELETE** /identity-providers/{identityProviderId} | Delete a user by an id
[**find_identity_provider_by_id**](IdentityProviderApi.md#find_identity_provider_by_id) | **GET** /identity-providers/{identityProviderId} | Find user by Id
[**find_identity_providers**](IdentityProviderApi.md#find_identity_providers) | **GET** /identity-providers | Retrieve all identity providers
[**update_identity_provider**](IdentityProviderApi.md#update_identity_provider) | **PATCH** /identity-providers/{identityProviderId} | Update a user


# **create_identity_provider**
> IdentityProvider create_identity_provider(x_tenant, identity_provider)

Create a user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_provider_api
from graalsystems.model.identity_provider import IdentityProvider
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
    api_instance = identity_provider_api.IdentityProviderApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_provider = IdentityProvider(
        id="id_example",
        type="type_example",
        name="name_example",
        tenant_id="tenant_id_example",
        client_id="client_id_example",
        client_secret="client_secret_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # IdentityProvider | The user to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a user
        api_response = api_instance.create_identity_provider(x_tenant, identity_provider)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityProviderApi->create_identity_provider: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_provider** | [**IdentityProvider**](IdentityProvider.md)| The user to be created |

### Return type

[**IdentityProvider**](IdentityProvider.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.identity-provider+json
 - **Accept**: application/vnd.graal.systems.v1.identity-provider+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_identity_provider_by_id**
> delete_identity_provider_by_id(x_tenant, identity_provider_id)

Delete a user by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_provider_api
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
    api_instance = identity_provider_api.IdentityProviderApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_provider_id = "identityProviderId_example" # str | Id of the user

    # example passing only required values which don't have defaults set
    try:
        # Delete a user by an id
        api_instance.delete_identity_provider_by_id(x_tenant, identity_provider_id)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityProviderApi->delete_identity_provider_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_provider_id** | **str**| Id of the user |

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
**404** | IdentityProvider not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_identity_provider_by_id**
> IdentityProvider find_identity_provider_by_id(x_tenant, identity_provider_id)

Find user by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_provider_api
from graalsystems.model.identity_provider import IdentityProvider
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
    api_instance = identity_provider_api.IdentityProviderApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_provider_id = "identityProviderId_example" # str | Id of the user

    # example passing only required values which don't have defaults set
    try:
        # Find user by Id
        api_response = api_instance.find_identity_provider_by_id(x_tenant, identity_provider_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityProviderApi->find_identity_provider_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_provider_id** | **str**| Id of the user |

### Return type

[**IdentityProvider**](IdentityProvider.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.identity-provider+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | IdentityProvider not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_identity_providers**
> [IdentityProvider] find_identity_providers(x_tenant)

Retrieve all identity providers

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_provider_api
from graalsystems.model.identity_provider import IdentityProvider
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
    api_instance = identity_provider_api.IdentityProviderApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all identity providers
        api_response = api_instance.find_identity_providers(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityProviderApi->find_identity_providers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[IdentityProvider]**](IdentityProvider.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.identity-provider+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_identity_provider**
> IdentityProvider update_identity_provider(x_tenant, identity_provider_id, patch)

Update a user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_provider_api
from graalsystems.model.identity_provider import IdentityProvider
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
    api_instance = identity_provider_api.IdentityProviderApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_provider_id = "identityProviderId_example" # str | Id of the user
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
        # Update a user
        api_response = api_instance.update_identity_provider(x_tenant, identity_provider_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityProviderApi->update_identity_provider: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_provider_id** | **str**| Id of the user |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**IdentityProvider**](IdentityProvider.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.identity-provider+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | IdentityProvider not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

