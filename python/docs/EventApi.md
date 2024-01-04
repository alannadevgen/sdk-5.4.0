# graalsystems.EventApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_event_for_job_and_run**](EventApi.md#create_event_for_job_and_run) | **POST** /jobs/{jobId}/runs/{runId}/events | Add event for a run and a job
[**create_event_for_workflow_and_run**](EventApi.md#create_event_for_workflow_and_run) | **POST** /workflows/{workflowId}/runs/{runId}/events | Add event for a run and a workflow
[**find_events_by_job_id_and_run_id**](EventApi.md#find_events_by_job_id_and_run_id) | **GET** /jobs/{jobId}/runs/{runId}/events | Find the events related to a run
[**find_events_by_workflow_id_and_run_id**](EventApi.md#find_events_by_workflow_id_and_run_id) | **GET** /workflows/{workflowId}/runs/{runId}/events | Find the events related to a run


# **create_event_for_job_and_run**
> Event create_event_for_job_and_run(x_tenant, job_id, run_id, event)

Add event for a run and a job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import event_api
from graalsystems.model.event import Event
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
    api_instance = event_api.EventApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run
    event = Event(
        id="id_example",
        object_type="object_type_example",
        object_id="object_id_example",
        tenant_id="tenant_id_example",
        type="type_example",
        message="message_example",
        at=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Event | The event to be created

    # example passing only required values which don't have defaults set
    try:
        # Add event for a run and a job
        api_response = api_instance.create_event_for_job_and_run(x_tenant, job_id, run_id, event)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EventApi->create_event_for_job_and_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |
 **event** | [**Event**](Event.md)| The event to be created |

### Return type

[**Event**](Event.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.event+json
 - **Accept**: application/vnd.graal.systems.v1.event+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_event_for_workflow_and_run**
> Event create_event_for_workflow_and_run(x_tenant, workflow_id, run_id, event)

Add event for a run and a workflow

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import event_api
from graalsystems.model.event import Event
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
    api_instance = event_api.EventApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow
    run_id = "runId_example" # str | Id of the Run
    event = Event(
        id="id_example",
        object_type="object_type_example",
        object_id="object_id_example",
        tenant_id="tenant_id_example",
        type="type_example",
        message="message_example",
        at=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Event | The event to be created

    # example passing only required values which don't have defaults set
    try:
        # Add event for a run and a workflow
        api_response = api_instance.create_event_for_workflow_and_run(x_tenant, workflow_id, run_id, event)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EventApi->create_event_for_workflow_and_run: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |
 **run_id** | **str**| Id of the Run |
 **event** | [**Event**](Event.md)| The event to be created |

### Return type

[**Event**](Event.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.event+json
 - **Accept**: application/vnd.graal.systems.v1.event+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_events_by_job_id_and_run_id**
> [Event] find_events_by_job_id_and_run_id(x_tenant, job_id, run_id)

Find the events related to a run

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import event_api
from graalsystems.model.event import Event
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
    api_instance = event_api.EventApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Find the events related to a run
        api_response = api_instance.find_events_by_job_id_and_run_id(x_tenant, job_id, run_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EventApi->find_events_by_job_id_and_run_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **run_id** | **str**| Id of the Run |

### Return type

[**[Event]**](Event.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.event+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_events_by_workflow_id_and_run_id**
> [Event] find_events_by_workflow_id_and_run_id(x_tenant, workflow_id, run_id)

Find the events related to a run

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import event_api
from graalsystems.model.event import Event
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
    api_instance = event_api.EventApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    workflow_id = "workflowId_example" # str | Id of the Workflow
    run_id = "runId_example" # str | Id of the Run

    # example passing only required values which don't have defaults set
    try:
        # Find the events related to a run
        api_response = api_instance.find_events_by_workflow_id_and_run_id(x_tenant, workflow_id, run_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EventApi->find_events_by_workflow_id_and_run_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**| Id of the Workflow |
 **run_id** | **str**| Id of the Run |

### Return type

[**[Event]**](Event.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.event+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Workflow not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

