# graalsystems.ProjectApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_job_for_project**](ProjectApi.md#create_job_for_project) | **POST** /projects/{projectId}/jobs | Create job
[**create_project**](ProjectApi.md#create_project) | **POST** /projects | Create a project
[**create_workflow_for_project**](ProjectApi.md#create_workflow_for_project) | **POST** /projects/{projectId}/workflows | Create workflows
[**delete_project_by_id**](ProjectApi.md#delete_project_by_id) | **DELETE** /projects/{projectId} | Delete a project by an id
[**find_banner_by_project_id**](ProjectApi.md#find_banner_by_project_id) | **GET** /projects/{projectId}/banner | Get banner
[**find_jobs_by_project_id**](ProjectApi.md#find_jobs_by_project_id) | **GET** /projects/{projectId}/jobs | Retrieve all jobs for a project
[**find_latest_runs_by_project_id**](ProjectApi.md#find_latest_runs_by_project_id) | **GET** /projects/{projectId}/runs | Retrieve all jobs for a project
[**find_project_by_id**](ProjectApi.md#find_project_by_id) | **GET** /projects/{projectId} | Find project by Id
[**find_projects**](ProjectApi.md#find_projects) | **GET** /projects | Retrieve all projects
[**find_workflows_by_project_id**](ProjectApi.md#find_workflows_by_project_id) | **GET** /projects/{projectId}/workflows | Retrieve all workflows for a project
[**get_metrics_for_project**](ProjectApi.md#get_metrics_for_project) | **GET** /projects/{projectId}/metrics | Find the metrics for a project
[**get_stats_by_project_id**](ProjectApi.md#get_stats_by_project_id) | **GET** /projects/{projectId}/stats | Find the stats for a project
[**update_project**](ProjectApi.md#update_project) | **PATCH** /projects/{projectId} | Update a project
[**upload_banner**](ProjectApi.md#upload_banner) | **POST** /projects/{projectId}/banner | Upload a new banner


# **create_job_for_project**
> Job create_job_for_project(x_tenant, project_id, job)

Create job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.job import Job
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    job = Job(
        id="id_example",
        name="name_example",
        description="description_example",
        project_id="project_id_example",
        identity_id="identity_id_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        timeout_seconds=1,
        max_retries=1,
        secrets=[
            "secrets_example",
        ],
        libraries=[
            Library(),
        ],
        options=Options(),
        schedule=Schedule(),
        notifications=Notifications(
            on_start=[
                Notification(),
            ],
            on_success=[
                Notification(),
            ],
            on_failure=[
                Notification(),
            ],
        ),
        parameters=[
            "parameters_example",
        ],
        labels={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
    ) # Job | The job to be created

    # example passing only required values which don't have defaults set
    try:
        # Create job
        api_response = api_instance.create_job_for_project(x_tenant, project_id, job)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->create_job_for_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **job** | [**Job**](Job.md)| The job to be created |

### Return type

[**Job**](Job.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.job+json
 - **Accept**: application/vnd.graal.systems.v1.job+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_project**
> Project create_project(x_tenant, project)

Create a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.project import Project
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project = Project(
        id="id_example",
        name="name_example",
        banner="banner_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
        labels={
            "key": "key_example",
        },
        locked=True,
        favorite=True,
        badge="badge_example",
    ) # Project | The project to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a project
        api_response = api_instance.create_project(x_tenant, project)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->create_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project** | [**Project**](Project.md)| The project to be created |

### Return type

[**Project**](Project.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.project+json
 - **Accept**: application/vnd.graal.systems.v1.project+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_workflow_for_project**
> Workflow create_workflow_for_project(x_tenant, project_id, workflow)

Create workflows

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.workflow import Workflow
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    workflow = Workflow(
        id="id_example",
        name="name_example",
        description="description_example",
        project_id="project_id_example",
        identity_id="identity_id_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        tasks=[
            Task(),
        ],
        schedule=Schedule(),
        notifications=Notifications(
            on_start=[
                Notification(),
            ],
            on_success=[
                Notification(),
            ],
            on_failure=[
                Notification(),
            ],
        ),
        parameters=[
            "parameters_example",
        ],
        labels={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
    ) # Workflow | The workflows to be created

    # example passing only required values which don't have defaults set
    try:
        # Create workflows
        api_response = api_instance.create_workflow_for_project(x_tenant, project_id, workflow)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->create_workflow_for_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **workflow** | [**Workflow**](Workflow.md)| The workflows to be created |

### Return type

[**Workflow**](Workflow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.workflow+json
 - **Accept**: application/vnd.graal.systems.v1.workflow+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_project_by_id**
> delete_project_by_id(x_tenant, project_id)

Delete a project by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project

    # example passing only required values which don't have defaults set
    try:
        # Delete a project by an id
        api_instance.delete_project_by_id(x_tenant, project_id)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->delete_project_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |

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
**404** | Project not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_banner_by_project_id**
> file_type find_banner_by_project_id(x_tenant, project_id)

Get banner

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    size = "size_example" # str | Size of the banner (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get banner
        api_response = api_instance.find_banner_by_project_id(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_banner_by_project_id: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get banner
        api_response = api_instance.find_banner_by_project_id(x_tenant, project_id, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_banner_by_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **size** | **str**| Size of the banner | [optional]

### Return type

**file_type**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: image/*


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_jobs_by_project_id**
> [Job] find_jobs_by_project_id(x_tenant, project_id)

Retrieve all jobs for a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.job import Job
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    type = "type_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all jobs for a project
        api_response = api_instance.find_jobs_by_project_id(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_jobs_by_project_id: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all jobs for a project
        api_response = api_instance.find_jobs_by_project_id(x_tenant, project_id, type=type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_jobs_by_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **type** | **str**|  | [optional]

### Return type

[**[Job]**](Job.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.job+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_latest_runs_by_project_id**
> [RunWithJob] find_latest_runs_by_project_id(x_tenant, project_id, number)

Retrieve all jobs for a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.run_with_job import RunWithJob
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    number = 1 # int | Number of runs

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all jobs for a project
        api_response = api_instance.find_latest_runs_by_project_id(x_tenant, project_id, number)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_latest_runs_by_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **number** | **int**| Number of runs |

### Return type

[**[RunWithJob]**](RunWithJob.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.jobrun-with-job+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_project_by_id**
> Project find_project_by_id(x_tenant, project_id)

Find project by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.project import Project
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project

    # example passing only required values which don't have defaults set
    try:
        # Find project by Id
        api_response = api_instance.find_project_by_id(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_project_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |

### Return type

[**Project**](Project.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.project+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_projects**
> [Project] find_projects(x_tenant)

Retrieve all projects

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.project import Project
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all projects
        api_response = api_instance.find_projects(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_projects: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Project]**](Project.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.project+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_workflows_by_project_id**
> [Workflow] find_workflows_by_project_id(x_tenant, project_id)

Retrieve all workflows for a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all workflows for a project
        api_response = api_instance.find_workflows_by_project_id(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->find_workflows_by_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |

### Return type

[**[Workflow]**](Workflow.md)

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
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_metrics_for_project**
> [Metric] get_metrics_for_project(x_tenant, project_id, metric)

Find the metrics for a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    metric = "metric_example" # str | The metric name
    _from = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)
    to = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Find the metrics for a project
        api_response = api_instance.get_metrics_for_project(x_tenant, project_id, metric)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->get_metrics_for_project: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Find the metrics for a project
        api_response = api_instance.get_metrics_for_project(x_tenant, project_id, metric, _from=_from, to=to)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->get_metrics_for_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
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
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_stats_by_project_id**
> RunStats get_stats_by_project_id(x_tenant, project_id)

Find the stats for a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project

    # example passing only required values which don't have defaults set
    try:
        # Find the stats for a project
        api_response = api_instance.get_stats_by_project_id(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->get_stats_by_project_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |

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
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_project**
> Project update_project(x_tenant, project_id, patch)

Update a project

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
from graalsystems.model.project import Project
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
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
        # Update a project
        api_response = api_instance.update_project(x_tenant, project_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->update_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Project**](Project.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.project+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **upload_banner**
> upload_banner(x_tenant, project_id)

Upload a new banner

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import project_api
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
    api_instance = project_api.ProjectApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    project_id = "projectId_example" # str | Id of the project
    filename = [
        open('/path/to/file', 'rb'),
    ] # [file_type] |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Upload a new banner
        api_instance.upload_banner(x_tenant, project_id)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->upload_banner: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Upload a new banner
        api_instance.upload_banner(x_tenant, project_id, filename=filename)
    except graalsystems.ApiException as e:
        print("Exception when calling ProjectApi->upload_banner: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**| Id of the project |
 **filename** | **[file_type]**|  | [optional]

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: Not defined


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

