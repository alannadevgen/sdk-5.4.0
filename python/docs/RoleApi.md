# graalsystems.RoleApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_role**](RoleApi.md#create_role) | **POST** /roles | Create a role
[**delete_role_by_id**](RoleApi.md#delete_role_by_id) | **DELETE** /roles/{roleId} | Delete an role by an id
[**find_current_roles**](RoleApi.md#find_current_roles) | **GET** /me/roles | Retrieve all roles for the current user
[**find_permissions_by_role_id**](RoleApi.md#find_permissions_by_role_id) | **GET** /roles/{roleId}/permissions | Find permissions by role id
[**find_role_by_id**](RoleApi.md#find_role_by_id) | **GET** /roles/{roleId} | Find role by Id
[**find_roles**](RoleApi.md#find_roles) | **GET** /roles | Retrieve all roles


# **create_role**
> Role create_role(x_tenant, role)

Create a role

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import role_api
from graalsystems.model.role import Role
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
    api_instance = role_api.RoleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    role = Role(
        id="id_example",
        name="name_example",
        type="type_example",
        tenant_id="tenant_id_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Role | The role to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a role
        api_response = api_instance.create_role(x_tenant, role)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RoleApi->create_role: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **role** | [**Role**](Role.md)| The role to be created |

### Return type

[**Role**](Role.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.role+json
 - **Accept**: application/vnd.graal.systems.v1.role+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_role_by_id**
> delete_role_by_id(x_tenant, role_id)

Delete an role by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import role_api
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
    api_instance = role_api.RoleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    role_id = "roleId_example" # str | Id of the role

    # example passing only required values which don't have defaults set
    try:
        # Delete an role by an id
        api_instance.delete_role_by_id(x_tenant, role_id)
    except graalsystems.ApiException as e:
        print("Exception when calling RoleApi->delete_role_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **role_id** | **str**| Id of the role |

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

# **find_current_roles**
> [RoleAndAssignment] find_current_roles(x_tenant)

Retrieve all roles for the current user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import role_api
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
    api_instance = role_api.RoleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all roles for the current user
        api_response = api_instance.find_current_roles(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RoleApi->find_current_roles: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

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

# **find_permissions_by_role_id**
> [str] find_permissions_by_role_id(x_tenant, role_id)

Find permissions by role id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import role_api
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
    api_instance = role_api.RoleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    role_id = "roleId_example" # str | Id of the role

    # example passing only required values which don't have defaults set
    try:
        # Find permissions by role id
        api_response = api_instance.find_permissions_by_role_id(x_tenant, role_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RoleApi->find_permissions_by_role_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **role_id** | **str**| Id of the role |

### Return type

**[str]**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Role not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_role_by_id**
> Role find_role_by_id(x_tenant, role_id)

Find role by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import role_api
from graalsystems.model.role import Role
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
    api_instance = role_api.RoleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    role_id = "roleId_example" # str | Id of the role

    # example passing only required values which don't have defaults set
    try:
        # Find role by Id
        api_response = api_instance.find_role_by_id(x_tenant, role_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RoleApi->find_role_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **role_id** | **str**| Id of the role |

### Return type

[**Role**](Role.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.role+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Role not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_roles**
> [Role] find_roles(x_tenant)

Retrieve all roles

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import role_api
from graalsystems.model.role import Role
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
    api_instance = role_api.RoleApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all roles
        api_response = api_instance.find_roles(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RoleApi->find_roles: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Role]**](Role.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.role+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

