# graalsystems.SessionsApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_notebook**](SessionsApi.md#create_notebook) | **GET** /sessions/{session_id} | Check if the workspace is running and create a notebook
[**create_session**](SessionsApi.md#create_session) | **POST** /sessions | Create a new workspace and corresponding session
[**delete_session**](SessionsApi.md#delete_session) | **DELETE** /sessions/{session_id} | Delete a session
[**get_sessions**](SessionsApi.md#get_sessions) | **GET** /sessions | Get existing Sessions, used for live-coding.
[**run_session**](SessionsApi.md#run_session) | **POST** /sessions/{session_id} | Run a session


# **create_notebook**
> str create_notebook(x_tenant, session_id)

Check if the workspace is running and create a notebook

Check if the workspace is running and create a notebook.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import sessions_api
from graalsystems.model.http_validation_error import HTTPValidationError
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
    api_instance = sessions_api.SessionsApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    session_id = "session_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Check if the workspace is running and create a notebook
        api_response = api_instance.create_notebook(x_tenant, session_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->create_notebook: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **session_id** | **str**|  |

### Return type

**str**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_session**
> bool, date, datetime, dict, float, int, list, str, none_type create_session(x_tenant, workspace_name)

Create a new workspace and corresponding session

Generates a session from live-coding information.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import sessions_api
from graalsystems.model.http_validation_error import HTTPValidationError
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
    api_instance = sessions_api.SessionsApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    workspace_name = "workspace_name_example" # str | 
    infrastructure_id = "scaleway-frpar1" # str |  (optional) if omitted the server will use the default value of "scaleway-frpar1"
    instance_type = "Standard_General_G0_v1" # str |  (optional) if omitted the server will use the default value of "Standard_General_G0_v1"

    # example passing only required values which don't have defaults set
    try:
        # Create a new workspace and corresponding session
        api_response = api_instance.create_session(x_tenant, workspace_name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->create_session: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Create a new workspace and corresponding session
        api_response = api_instance.create_session(x_tenant, workspace_name, infrastructure_id=infrastructure_id, instance_type=instance_type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->create_session: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workspace_name** | **str**|  |
 **infrastructure_id** | **str**|  | [optional] if omitted the server will use the default value of "scaleway-frpar1"
 **instance_type** | **str**|  | [optional] if omitted the server will use the default value of "Standard_General_G0_v1"

### Return type

**bool, date, datetime, dict, float, int, list, str, none_type**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_session**
> str delete_session(x_tenant, session_id)

Delete a session

Delete a Session from a Zeppelin environment.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import sessions_api
from graalsystems.model.http_validation_error import HTTPValidationError
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
    api_instance = sessions_api.SessionsApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    session_id = "session_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete a session
        api_response = api_instance.delete_session(x_tenant, session_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->delete_session: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **session_id** | **str**|  |

### Return type

**str**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_sessions**
> [Session] get_sessions(x_tenant)

Get existing Sessions, used for live-coding.

Returns a list of session id that you can filter depending on their status.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import sessions_api
from graalsystems.model.session import Session
from graalsystems.model.http_validation_error import HTTPValidationError
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
    api_instance = sessions_api.SessionsApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    inactive = False # bool |  (optional) if omitted the server will use the default value of False
    expiration_time = 10 # int |  (optional) if omitted the server will use the default value of 10

    # example passing only required values which don't have defaults set
    try:
        # Get existing Sessions, used for live-coding.
        api_response = api_instance.get_sessions(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->get_sessions: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get existing Sessions, used for live-coding.
        api_response = api_instance.get_sessions(x_tenant, inactive=inactive, expiration_time=expiration_time)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->get_sessions: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **inactive** | **bool**|  | [optional] if omitted the server will use the default value of False
 **expiration_time** | **int**|  | [optional] if omitted the server will use the default value of 10

### Return type

[**[Session]**](Session.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **run_session**
> {str: (bool, date, datetime, dict, float, int, list, str, none_type)} run_session(x_tenant, session_id, dag_unverified)

Run a session

Run a Session in a Zeppelin environment.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import sessions_api
from graalsystems.model.dag_unverified import DagUnverified
from graalsystems.model.http_validation_error import HTTPValidationError
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
    api_instance = sessions_api.SessionsApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    session_id = "session_id_example" # str | 
    dag_unverified = DagUnverified(
        id="id_example",
        tasks=[
            None,
        ],
    ) # DagUnverified | 

    # example passing only required values which don't have defaults set
    try:
        # Run a session
        api_response = api_instance.run_session(x_tenant, session_id, dag_unverified)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling SessionsApi->run_session: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **session_id** | **str**|  |
 **dag_unverified** | [**DagUnverified**](DagUnverified.md)|  |

### Return type

**{str: (bool, date, datetime, dict, float, int, list, str, none_type)}**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

