# graalsystems.UserApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_user**](UserApi.md#create_user) | **POST** /users | Create a user
[**delete_user_by_id**](UserApi.md#delete_user_by_id) | **DELETE** /users/{userId} | Delete a user by an id
[**find_current_user**](UserApi.md#find_current_user) | **GET** /me | Just... me
[**find_logs_by_user_id**](UserApi.md#find_logs_by_user_id) | **GET** /users/{userId}/auditlogs | Find logs by a user id
[**find_roles_by_user_id**](UserApi.md#find_roles_by_user_id) | **GET** /users/{userId}/roles | Find roles by a user id
[**find_user_by_id**](UserApi.md#find_user_by_id) | **GET** /users/{userId} | Find user by Id
[**find_user_by_remote_user_id**](UserApi.md#find_user_by_remote_user_id) | **GET** /remote/users/{remote_user_id} | Find user by remote user id
[**find_users**](UserApi.md#find_users) | **GET** /users | Retrieve all users
[**get_audit_logs**](UserApi.md#get_audit_logs) | **GET** /auditlogs | Find logs
[**update_user**](UserApi.md#update_user) | **PATCH** /users/{userId} | Update a user


# **create_user**
> User create_user(x_tenant, user)

Create a user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.user import User
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    user = User(
        id="id_example",
        username="username_example",
        firstname="firstname_example",
        lastname="lastname_example",
        email="email_example",
        description="description_example",
        password="password_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
        locked=True,
    ) # User | The user to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a user
        api_response = api_instance.create_user(x_tenant, user)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->create_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user** | [**User**](User.md)| The user to be created |

### Return type

[**User**](User.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.user+json
 - **Accept**: application/vnd.graal.systems.v1.user+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_user_by_id**
> delete_user_by_id(x_tenant, user_id)

Delete a user by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    user_id = "userId_example" # str | Id of the user

    # example passing only required values which don't have defaults set
    try:
        # Delete a user by an id
        api_instance.delete_user_by_id(x_tenant, user_id)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->delete_user_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**| Id of the user |

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

# **find_current_user**
> User find_current_user(x_tenant)

Just... me

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.user import User
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Just... me
        api_response = api_instance.find_current_user(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->find_current_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**User**](User.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.user+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_logs_by_user_id**
> [AuditLog] find_logs_by_user_id(x_tenant, user_id)

Find logs by a user id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.audit_log import AuditLog
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    user_id = "userId_example" # str | Id of the user

    # example passing only required values which don't have defaults set
    try:
        # Find logs by a user id
        api_response = api_instance.find_logs_by_user_id(x_tenant, user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->find_logs_by_user_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**| Id of the user |

### Return type

[**[AuditLog]**](AuditLog.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.auditlog+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_roles_by_user_id**
> [RoleAndAssignment] find_roles_by_user_id(x_tenant, user_id)

Find roles by a user id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    user_id = "userId_example" # str | Id of the user

    # example passing only required values which don't have defaults set
    try:
        # Find roles by a user id
        api_response = api_instance.find_roles_by_user_id(x_tenant, user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->find_roles_by_user_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**| Id of the user |

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

# **find_user_by_id**
> User find_user_by_id(x_tenant, user_id)

Find user by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.user import User
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    user_id = "userId_example" # str | Id of the user

    # example passing only required values which don't have defaults set
    try:
        # Find user by Id
        api_response = api_instance.find_user_by_id(x_tenant, user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->find_user_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**| Id of the user |

### Return type

[**User**](User.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.user+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_user_by_remote_user_id**
> User find_user_by_remote_user_id(x_tenant, remote_user_id)

Find user by remote user id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.user import User
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    remote_user_id = "remote_user_id_example" # str | Remote id of the user

    # example passing only required values which don't have defaults set
    try:
        # Find user by remote user id
        api_response = api_instance.find_user_by_remote_user_id(x_tenant, remote_user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->find_user_by_remote_user_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **remote_user_id** | **str**| Remote id of the user |

### Return type

[**User**](User.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.user+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_users**
> [User] find_users(x_tenant)

Retrieve all users

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.user import User
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all users
        api_response = api_instance.find_users(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->find_users: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[User]**](User.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.user+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_audit_logs**
> [AuditLog] get_audit_logs(x_tenant)

Find logs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.audit_log import AuditLog
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Find logs
        api_response = api_instance.get_audit_logs(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->get_audit_logs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[AuditLog]**](AuditLog.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.auditlog+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_user**
> User update_user(x_tenant, user_id, patch)

Update a user

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import user_api
from graalsystems.model.user import User
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
    api_instance = user_api.UserApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    user_id = "userId_example" # str | Id of the user
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
        api_response = api_instance.update_user(x_tenant, user_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling UserApi->update_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**| Id of the user |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**User**](User.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.user+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | User not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

