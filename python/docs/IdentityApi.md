# graalsystems.IdentityApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_identity**](IdentityApi.md#create_identity) | **POST** /identities | Create a identity
[**delete_identity_by_id**](IdentityApi.md#delete_identity_by_id) | **DELETE** /identities/{identityId} | Delete an identity by an id
[**find_identities**](IdentityApi.md#find_identities) | **GET** /identities | Retrieve all identities
[**find_identity_by_id**](IdentityApi.md#find_identity_by_id) | **GET** /identities/{identityId} | Find identity by Id
[**find_roles_by_identity_id**](IdentityApi.md#find_roles_by_identity_id) | **GET** /identities/{identityId}/roles | Find roles by a identity id
[**update_identity**](IdentityApi.md#update_identity) | **PATCH** /identities/{identityId} | Update a identity


# **create_identity**
> Identity create_identity(x_tenant, identity)

Create a identity

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_api
from graalsystems.model.identity import Identity
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
    api_instance = identity_api.IdentityApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity = Identity(
        id="id_example",
        type="type_example",
        name="name_example",
        tenant_id="tenant_id_example",
        remote_identity_id="remote_identity_id_example",
        secret="secret_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
        locked=True,
    ) # Identity | The identity to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a identity
        api_response = api_instance.create_identity(x_tenant, identity)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityApi->create_identity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity** | [**Identity**](Identity.md)| The identity to be created |

### Return type

[**Identity**](Identity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.identity+json
 - **Accept**: application/vnd.graal.systems.v1.identity+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_identity_by_id**
> delete_identity_by_id(x_tenant, identity_id)

Delete an identity by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_api
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
    api_instance = identity_api.IdentityApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_id = "identityId_example" # str | Id of the identity

    # example passing only required values which don't have defaults set
    try:
        # Delete an identity by an id
        api_instance.delete_identity_by_id(x_tenant, identity_id)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityApi->delete_identity_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_id** | **str**| Id of the identity |

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
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_identities**
> [Identity] find_identities(x_tenant)

Retrieve all identities

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_api
from graalsystems.model.identity import Identity
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
    api_instance = identity_api.IdentityApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all identities
        api_response = api_instance.find_identities(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityApi->find_identities: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Identity]**](Identity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.identity+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_identity_by_id**
> Identity find_identity_by_id(x_tenant, identity_id)

Find identity by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_api
from graalsystems.model.identity import Identity
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
    api_instance = identity_api.IdentityApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_id = "identityId_example" # str | Id of the identity

    # example passing only required values which don't have defaults set
    try:
        # Find identity by Id
        api_response = api_instance.find_identity_by_id(x_tenant, identity_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityApi->find_identity_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_id** | **str**| Id of the identity |

### Return type

[**Identity**](Identity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.identity+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Identity not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_roles_by_identity_id**
> [RoleAndAssignment] find_roles_by_identity_id(x_tenant, identity_id)

Find roles by a identity id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_api
from graalsystems.model.role_and_assignment import RoleAndAssignment
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
    api_instance = identity_api.IdentityApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_id = "identityId_example" # str | Id of the identity

    # example passing only required values which don't have defaults set
    try:
        # Find roles by a identity id
        api_response = api_instance.find_roles_by_identity_id(x_tenant, identity_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityApi->find_roles_by_identity_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_id** | **str**| Id of the identity |

### Return type

[**[RoleAndAssignment]**](RoleAndAssignment.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.roleassignment+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_identity**
> Identity update_identity(x_tenant, identity_id, patch)

Update a identity

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import identity_api
from graalsystems.model.identity import Identity
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
    api_instance = identity_api.IdentityApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    identity_id = "identityId_example" # str | Id of the identity
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
        # Update a identity
        api_response = api_instance.update_identity(x_tenant, identity_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling IdentityApi->update_identity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **identity_id** | **str**| Id of the identity |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Identity**](Identity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.identity+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

