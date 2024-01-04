# graalsystems.JobApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_job_by_id**](JobApi.md#delete_job_by_id) | **DELETE** /jobs/{jobId} | Delete a job by its id
[**find_job_by_job_id**](JobApi.md#find_job_by_job_id) | **GET** /jobs/{jobId} | Find job by Id
[**find_jobs**](JobApi.md#find_jobs) | **GET** /jobs | Retrieve all jobs
[**get_metrics_for_job**](JobApi.md#get_metrics_for_job) | **GET** /jobs/{jobId}/metrics | Find the metrics for a job
[**get_stats_by_job_id**](JobApi.md#get_stats_by_job_id) | **GET** /jobs/{jobId}/stats | Find the stats for a job
[**update_job**](JobApi.md#update_job) | **PATCH** /jobs/{jobId} | Update a job


# **delete_job_by_id**
> delete_job_by_id(x_tenant, job_id)

Delete a job by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import job_api
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
    api_instance = job_api.JobApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job

    # example passing only required values which don't have defaults set
    try:
        # Delete a job by its id
        api_instance.delete_job_by_id(x_tenant, job_id)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->delete_job_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |

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
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_job_by_job_id**
> Job find_job_by_job_id(x_tenant, job_id)

Find job by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import job_api
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
    api_instance = job_api.JobApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job

    # example passing only required values which don't have defaults set
    try:
        # Find job by Id
        api_response = api_instance.find_job_by_job_id(x_tenant, job_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->find_job_by_job_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |

### Return type

[**Job**](Job.md)

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
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_jobs**
> [Job] find_jobs(x_tenant)

Retrieve all jobs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import job_api
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
    api_instance = job_api.JobApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    type = "type_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all jobs
        api_response = api_instance.find_jobs(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->find_jobs: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all jobs
        api_response = api_instance.find_jobs(x_tenant, type=type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->find_jobs: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **type** | **str**|  | [optional]

### Return type

[**[Job]**](Job.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.job+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_metrics_for_job**
> [Metric] get_metrics_for_job(x_tenant, job_id, metric)

Find the metrics for a job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import job_api
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
    api_instance = job_api.JobApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
    metric = "metric_example" # str | The metric name
    _from = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)
    to = dateutil_parser('1970-01-01T00:00:00.00Z') # datetime |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Find the metrics for a job
        api_response = api_instance.get_metrics_for_job(x_tenant, job_id, metric)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->get_metrics_for_job: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Find the metrics for a job
        api_response = api_instance.get_metrics_for_job(x_tenant, job_id, metric, _from=_from, to=to)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->get_metrics_for_job: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
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

# **get_stats_by_job_id**
> RunStats get_stats_by_job_id(x_tenant, job_id)

Find the stats for a job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import job_api
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
    api_instance = job_api.JobApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job

    # example passing only required values which don't have defaults set
    try:
        # Find the stats for a job
        api_response = api_instance.get_stats_by_job_id(x_tenant, job_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->get_stats_by_job_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |

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
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_job**
> Job update_job(x_tenant, job_id, patch)

Update a job

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import job_api
from graalsystems.model.job import Job
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
    api_instance = job_api.JobApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    job_id = "jobId_example" # str | Id of the Job
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
        # Update a job
        api_response = api_instance.update_job(x_tenant, job_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling JobApi->update_job: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**| Id of the Job |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Job**](Job.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.job+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

