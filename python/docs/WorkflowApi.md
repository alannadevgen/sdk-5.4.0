# graalsystems.WorkflowApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_workflow_by_id**](WorkflowApi.md#delete_workflow_by_id) | **DELETE** /workflows/{workflowId} | Delete a workflow by its id
[**find_run_by_workflow_id_and_run_id**](WorkflowApi.md#find_run_by_workflow_id_and_run_id) | **GET** /workflows/{workflowId}/runs/{runId} | Find the run by a workflowId and a runId
[**find_workflow_by_id**](WorkflowApi.md#find_workflow_by_id) | **GET** /workflows/{workflowId} | Find workflow by Id
[**find_workflows**](WorkflowApi.md#find_workflows) | **GET** /workflows | Retrieve all workflows
[**get_stats_by_workflow_id**](WorkflowApi.md#get_stats_by_workflow_id) | **GET** /workflows/{workflowId}/stats | Find the stats for a workflow
[**update_workflow**](WorkflowApi.md#update_workflow) | **PATCH** /workflows/{workflowId} | Update a workflow


# **delete_workflow_by_id**
> delete_workflow_by_id(x_tenant, workflow_id)

Delete a workflow by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import workflow_api
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
    api_instance = workflow_api.WorkflowApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the workflow

    # example passing only required values which don't have defaults set
    try:
        # Delete a workflow by its id
        api_instance.delete_workflow_by_id(x_tenant, workflow_id)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->delete_workflow_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the workflow |

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
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_run_by_workflow_id_and_run_id**
> WorkflowRun find_run_by_workflow_id_and_run_id(x_tenant, workflow_id, run_id)

Find the run by a workflowId and a runId

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import workflow_api
from graalsystems.model.workflow_run import WorkflowRun
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
    api_instance = workflow_api.WorkflowApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Find the run by a workflowId and a runId
        api_response = api_instance.find_run_by_workflow_id_and_run_id(x_tenant, workflow_id, run_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->find_run_by_workflow_id_and_run_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |
 **run_id** | **str**| Id of the Run |

### Return type

[**WorkflowRun**](WorkflowRun.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.workflowrun+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Run of workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_workflow_by_id**
> Workflow find_workflow_by_id(x_tenant, workflow_id)

Find workflow by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import workflow_api
from graalsystems.model.workflow import Workflow
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
    api_instance = workflow_api.WorkflowApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the workflow

    # example passing only required values which don't have defaults set
    try:
        # Find workflow by Id
        api_response = api_instance.find_workflow_by_id(x_tenant, workflow_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->find_workflow_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the workflow |

### Return type

[**Workflow**](Workflow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.workflow+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_workflows**
> WorkflowPage find_workflows(x_tenant)

Retrieve all workflows

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import workflow_api
from graalsystems.model.workflow_page import WorkflowPage
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
    api_instance = workflow_api.WorkflowApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all workflows
        api_response = api_instance.find_workflows(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->find_workflows: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all workflows
        api_response = api_instance.find_workflows(x_tenant, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->find_workflows: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**WorkflowPage**](WorkflowPage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.workflow+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_stats_by_workflow_id**
> RunStats get_stats_by_workflow_id(x_tenant, workflow_id)

Find the stats for a workflow

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import workflow_api
from graalsystems.model.run_stats import RunStats
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
    api_instance = workflow_api.WorkflowApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow

    # example passing only required values which don't have defaults set
    try:
        # Find the stats for a workflow
        api_response = api_instance.get_stats_by_workflow_id(x_tenant, workflow_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->get_stats_by_workflow_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |

### Return type

[**RunStats**](RunStats.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.stats+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_workflow**
> Workflow update_workflow(x_tenant, workflow_id, patch)

Update a workflow

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import workflow_api
from graalsystems.model.workflow import Workflow
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
    api_instance = workflow_api.WorkflowApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the workflow
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
        # Update a workflow
        api_response = api_instance.update_workflow(x_tenant, workflow_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling WorkflowApi->update_workflow: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the workflow |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Workflow**](Workflow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.workflow+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

