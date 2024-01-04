# graalsystems.RunApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_run_for_job**](RunApi.md#create_run_for_job) | **POST** /jobs/{jobId}/runs | Create a run for a job
[**create_run_for_workflow**](RunApi.md#create_run_for_workflow) | **POST** /workflows/{workflowId}/runs | Create a run for a workflow
[**delete_run_by_job_id_and_run_id**](RunApi.md#delete_run_by_job_id_and_run_id) | **DELETE** /jobs/{jobId}/runs/{runId} | Delete a run by a jobId and a runId
[**delete_run_by_workflow_id_and_run_id**](RunApi.md#delete_run_by_workflow_id_and_run_id) | **DELETE** /workflows/{workflowId}/runs/{runId} | Delete a run by a workflowId and a runId
[**find_latest_runs**](RunApi.md#find_latest_runs) | **GET** /runs | Find the latest runs
[**find_run_by_job_id_and_run_id**](RunApi.md#find_run_by_job_id_and_run_id) | **GET** /jobs/{jobId}/runs/{runId} | Find the run by a jobId and a runId
[**find_runs_by_job_id**](RunApi.md#find_runs_by_job_id) | **GET** /jobs/{jobId}/runs | Find the runs for a job
[**find_runs_by_workflow_id**](RunApi.md#find_runs_by_workflow_id) | **GET** /workflows/{workflowId}/runs | Find the runs for a workflow
[**get_file**](RunApi.md#get_file) | **GET** /jobs/{jobId}/runs/{runId}/files/{filename} | Get file
[**get_logs**](RunApi.md#get_logs) | **GET** /jobs/{jobId}/runs/{runId}/logs | Get logs
[**get_metrics_for_run**](RunApi.md#get_metrics_for_run) | **GET** /jobs/{jobId}/runs/{runId}/metrics | Find the metrics for a run
[**get_run_files**](RunApi.md#get_run_files) | **GET** /jobs/{jobId}/runs/{runId}/files | Get files
[**update_run**](RunApi.md#update_run) | **PATCH** /jobs/{jobId}/runs/{runId} | Update a run


# **create_run_for_job**
> JobRun create_run_for_job(x_tenant, job_id, job_run)

Create a run for a job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.job_run import JobRun
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    job_run = JobRun(
        id="id_example",
        initiator="initiator_example",
        infrastructure_id="infrastructure_id_example",
        device_id="device_id_example",
        job_id="job_id_example",
        project_id="project_id_example",
        name="name_example",
        description="description_example",
        status="status_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        parameters=[
            "parameters_example",
        ],
        metadata={
            "key": {},
        },
    ) # JobRun | The run to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a run for a job
        api_response = api_instance.create_run_for_job(x_tenant, job_id, job_run)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->create_run_for_job: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **job_run** | [**JobRun**](JobRun.md)| The run to be created |

### Return type

[**JobRun**](JobRun.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.jobrun+json
 - **Accept**: application/vnd.graal.systems.v1.jobrun+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_run_for_workflow**
> Workflow create_run_for_workflow(x_tenant, workflow_id, workflow_run)

Create a run for a workflow

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.workflow import Workflow
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow
    workflow_run = WorkflowRun(
        id="id_example",
        infrastructure_id="infrastructure_id_example",
        device_id="device_id_example",
        workflow_id="workflow_id_example",
        project_id="project_id_example",
        name="name_example",
        description="description_example",
        status="status_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # WorkflowRun | The run to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a run for a workflow
        api_response = api_instance.create_run_for_workflow(x_tenant, workflow_id, workflow_run)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->create_run_for_workflow: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |
 **workflow_run** | [**WorkflowRun**](WorkflowRun.md)| The run to be created |

### Return type

[**Workflow**](Workflow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.workflowrun+json
 - **Accept**: application/vnd.graal.systems.v1.workflowrun+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_run_by_job_id_and_run_id**
> delete_run_by_job_id_and_run_id(x_tenant, job_id, run_id)

Delete a run by a jobId and a runId

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Delete a run by a jobId and a runId
        api_instance.delete_run_by_job_id_and_run_id(x_tenant, job_id, run_id)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->delete_run_by_job_id_and_run_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |

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
**404** | Run not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_run_by_workflow_id_and_run_id**
> delete_run_by_workflow_id_and_run_id(x_tenant, workflow_id, run_id)

Delete a run by a workflowId and a runId

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Delete a run by a workflowId and a runId
        api_instance.delete_run_by_workflow_id_and_run_id(x_tenant, workflow_id, run_id)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->delete_run_by_workflow_id_and_run_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |
 **run_id** | **str**| Id of the Run |

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
**404** | Run not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_latest_runs**
> [RunWithJob] find_latest_runs(x_tenant, number)

Find the latest runs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.run_with_job import RunWithJob
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    number = 1 # int | Number of runs

    # example passing only required values which don't have defaults set
    try:
        # Find the latest runs
        api_response = api_instance.find_latest_runs(x_tenant, number)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->find_latest_runs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **number** | **int**| Number of runs |

### Return type

[**[RunWithJob]**](RunWithJob.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.jobrun-with-job+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_run_by_job_id_and_run_id**
> JobRun find_run_by_job_id_and_run_id(x_tenant, job_id, run_id)

Find the run by a jobId and a runId

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.job_run import JobRun
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Find the run by a jobId and a runId
        api_response = api_instance.find_run_by_job_id_and_run_id(x_tenant, job_id, run_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->find_run_by_job_id_and_run_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |

### Return type

[**JobRun**](JobRun.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.jobrun+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Run of job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_runs_by_job_id**
> [JobRun] find_runs_by_job_id(x_tenant, job_id)

Find the runs for a job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.job_run import JobRun
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job

    # example passing only required values which don't have defaults set
    try:
        # Find the runs for a job
        api_response = api_instance.find_runs_by_job_id(x_tenant, job_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->find_runs_by_job_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |

### Return type

[**[JobRun]**](JobRun.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.jobrun+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_runs_by_workflow_id**
> [WorkflowRun] find_runs_by_workflow_id(x_tenant, workflow_id)

Find the runs for a workflow

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow

    # example passing only required values which don't have defaults set
    try:
        # Find the runs for a workflow
        api_response = api_instance.find_runs_by_workflow_id(x_tenant, workflow_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->find_runs_by_workflow_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |

### Return type

[**[WorkflowRun]**](WorkflowRun.md)

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
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_file**
> file_type get_file(x_tenant, job_id, run_id, filename)

Get file

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run
    filename = "filename_example" # str | Name of the file

    # example passing only required values which don't have defaults set
    try:
        # Get file
        api_response = api_instance.get_file(x_tenant, job_id, run_id, filename)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->get_file: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |
 **filename** | **str**| Name of the file |

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
**404** | Run of job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_logs**
> [LogEntry] get_logs(x_tenant, job_id, run_id)

Get logs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.log_entry import LogEntry
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run
    cursor = "cursor_example" # str | The cursor (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get logs
        api_response = api_instance.get_logs(x_tenant, job_id, run_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->get_logs: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get logs
        api_response = api_instance.get_logs(x_tenant, job_id, run_id, cursor=cursor)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->get_logs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |
 **cursor** | **str**| The cursor | [optional]

### Return type

[**[LogEntry]**](LogEntry.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.log+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  * X-Cursor - Current cursor <br>  |
**400** | Bad Request |  -  |
**404** | Run of job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_metrics_for_run**
> [Metric] get_metrics_for_run(x_tenant, job_id, run_id, metric)

Find the metrics for a run

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.metric import Metric
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run
    metric = "metric_example" # str | The metric name
    _from = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)
    to = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Find the metrics for a run
        api_response = api_instance.get_metrics_for_run(x_tenant, job_id, run_id, metric)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->get_metrics_for_run: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Find the metrics for a run
        api_response = api_instance.get_metrics_for_run(x_tenant, job_id, run_id, metric, _from=_from, to=to)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->get_metrics_for_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |
 **metric** | **str**| The metric name |
 **_from** | **datetime**|  | [optional]
 **to** | **datetime**|  | [optional]

### Return type

[**[Metric]**](Metric.md)

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
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_run_files**
> [str] get_run_files(x_tenant, job_id, run_id)

Get files

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Get files
        api_response = api_instance.get_run_files(x_tenant, job_id, run_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->get_run_files: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |

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
**404** | Run of job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_run**
> JobRun update_run(x_tenant, job_id, run_id, patch)

Update a run

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import run_api
from graalsystems.model.job_run import JobRun
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
    api_instance = run_api.RunApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run
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
        # Update a run
        api_response = api_instance.update_run(x_tenant, job_id, run_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling RunApi->update_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**JobRun**](JobRun.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.jobrun+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

