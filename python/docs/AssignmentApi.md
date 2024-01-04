# graalsystems.AssignmentApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_role_assignment**](AssignmentApi.md#create_role_assignment) | **POST** /assignments | Create a assignment
[**delete_role_assignment_by_id**](AssignmentApi.md#delete_role_assignment_by_id) | **DELETE** /assignments/{assignmentId} | Delete an assignment by an id
[**find_role_assignment_by_id**](AssignmentApi.md#find_role_assignment_by_id) | **GET** /assignments/{assignmentId} | Find assignment by Id
[**find_role_assignments**](AssignmentApi.md#find_role_assignments) | **GET** /assignments | Retrieve all assignments for a resource


# **create_role_assignment**
> RoleAssignment create_role_assignment(x_tenant, role_assignment)

Create a assignment

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import assignment_api
from graalsystems.model.role_assignment import RoleAssignment
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
    api_instance = assignment_api.AssignmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    role_assignment = RoleAssignment(
        id="id_example",
        resource_id="resource_id_example",
        resource_type="resource_type_example",
        principal_type="principal_type_example",
        principal_id="principal_id_example",
        role_id="role_id_example",
        tenant_id="tenant_id_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # RoleAssignment | The assignment to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a assignment
        api_response = api_instance.create_role_assignment(x_tenant, role_assignment)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling AssignmentApi->create_role_assignment: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **role_assignment** | [**RoleAssignment**](RoleAssignment.md)| The assignment to be created |

### Return type

[**RoleAssignment**](RoleAssignment.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.assignment+json
 - **Accept**: application/vnd.graal.systems.v1.assignment+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_role_assignment_by_id**
> delete_role_assignment_by_id(x_tenant, assignment_id)

Delete an assignment by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import assignment_api
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
    api_instance = assignment_api.AssignmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    assignment_id = "assignmentId_example" # str | Id of the assignment

    # example passing only required values which don't have defaults set
    try:
        # Delete an assignment by an id
        api_instance.delete_role_assignment_by_id(x_tenant, assignment_id)
    except graalsystems.ApiException as e:
        print("Exception when calling AssignmentApi->delete_role_assignment_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **assignment_id** | **str**| Id of the assignment |

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

# **find_role_assignment_by_id**
> RoleAssignment find_role_assignment_by_id(x_tenant, assignment_id)

Find assignment by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import assignment_api
from graalsystems.model.role_assignment import RoleAssignment
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
    api_instance = assignment_api.AssignmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    assignment_id = "assignmentId_example" # str | Id of the assignment

    # example passing only required values which don't have defaults set
    try:
        # Find assignment by Id
        api_response = api_instance.find_role_assignment_by_id(x_tenant, assignment_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling AssignmentApi->find_role_assignment_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **assignment_id** | **str**| Id of the assignment |

### Return type

[**RoleAssignment**](RoleAssignment.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.assignment+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | RoleAssignment not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_role_assignments**
> [RoleAndPrincipalAndAssignment] find_role_assignments(x_tenant)

Retrieve all assignments for a resource

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import assignment_api
from graalsystems.model.role_and_principal_and_assignment import RoleAndPrincipalAndAssignment
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
    api_instance = assignment_api.AssignmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    resource_type = "resource_type_example" # str |  (optional)
    resource_id = "resource_id_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all assignments for a resource
        api_response = api_instance.find_role_assignments(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling AssignmentApi->find_role_assignments: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all assignments for a resource
        api_response = api_instance.find_role_assignments(x_tenant, resource_type=resource_type, resource_id=resource_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling AssignmentApi->find_role_assignments: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **resource_type** | **str**|  | [optional]
 **resource_id** | **str**|  | [optional]

### Return type

[**[RoleAndPrincipalAndAssignment]**](RoleAndPrincipalAndAssignment.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.roleprincipalassignment+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

