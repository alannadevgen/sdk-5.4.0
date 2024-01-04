# graalsystems.FollowApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_catalog_follower**](FollowApi.md#create_catalog_follower) | **POST** /catalogs/{catalog_id}/followers | Create Catalog Followers
[**create_database_follower**](FollowApi.md#create_database_follower) | **POST** /databases/{database_id}/followers | Create Database Followers
[**create_job_follower**](FollowApi.md#create_job_follower) | **POST** /jobs/{job_id}/followers | Create Job Followers
[**create_project_follower**](FollowApi.md#create_project_follower) | **POST** /projects/{project_id}/followers | Create Project Followers
[**create_table_follower**](FollowApi.md#create_table_follower) | **POST** /tables/{table_id}/followers | Create Table Followers
[**create_user_follower**](FollowApi.md#create_user_follower) | **POST** /users/{user_id}/followers | Create User Followers
[**create_workflow_follower**](FollowApi.md#create_workflow_follower) | **POST** /workflows/{workflow_id}/followers | Create Workflow Followers
[**delete_following_catalog**](FollowApi.md#delete_following_catalog) | **DELETE** /following/catalogs/{catalog_id} | Delete Following Catalog
[**delete_following_database**](FollowApi.md#delete_following_database) | **DELETE** /following/databases/{database_id} | Delete Following Database
[**delete_following_job**](FollowApi.md#delete_following_job) | **DELETE** /following/jobs/{job_id} | Delete Following Job
[**delete_following_project**](FollowApi.md#delete_following_project) | **DELETE** /following/projects/{project_id} | Delete Following Project
[**delete_following_table**](FollowApi.md#delete_following_table) | **DELETE** /following/tables/{table_id} | Delete Following Table
[**delete_following_user**](FollowApi.md#delete_following_user) | **DELETE** /following/users/{user_id} | Delete Following User
[**delete_following_workflow**](FollowApi.md#delete_following_workflow) | **DELETE** /following/workflows/{workflow_id} | Delete Following User
[**get_catalog_followers**](FollowApi.md#get_catalog_followers) | **GET** /catalogs/{catalog_id}/followers | Get Catalog Followers
[**get_database_followers**](FollowApi.md#get_database_followers) | **GET** /databases/{database_id}/followers | Get Database Followers
[**get_job_followers**](FollowApi.md#get_job_followers) | **GET** /jobs/{job_id}/followers | Get Job Followers
[**get_project_followers**](FollowApi.md#get_project_followers) | **GET** /projects/{project_id}/followers | Get Project Followers
[**get_table_followers**](FollowApi.md#get_table_followers) | **GET** /tables/{table_id}/followers | Get Table Followers
[**get_user_followers**](FollowApi.md#get_user_followers) | **GET** /users/{user_id}/followers | Get User Followers
[**get_user_following**](FollowApi.md#get_user_following) | **GET** /users/{user_id}/following | Get User Following
[**get_workflow_followers**](FollowApi.md#get_workflow_followers) | **GET** /workflows/{workflow_id}/followers | Get Workflow Followers


# **create_catalog_follower**
> Follow create_catalog_follower(x_tenant, catalog_id)

Create Catalog Followers

Create a new follow relationship between a catalog and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    catalog_id = "catalog_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create Catalog Followers
        api_response = api_instance.create_catalog_follower(x_tenant, catalog_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_catalog_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **catalog_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Exists |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_database_follower**
> Follow create_database_follower(x_tenant, database_id)

Create Database Followers

Create a new follow relationship between a database and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    database_id = "database_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create Database Followers
        api_response = api_instance.create_database_follower(x_tenant, database_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_database_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **database_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Exists |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_job_follower**
> Follow create_job_follower(x_tenant, job_id)

Create Job Followers

Create a new follow relationship between a job and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    job_id = "job_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create Job Followers
        api_response = api_instance.create_job_follower(x_tenant, job_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_job_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Exists |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_project_follower**
> Follow create_project_follower(x_tenant, project_id)

Create Project Followers

Create a new follow relationship between a project and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    project_id = "project_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create Project Followers
        api_response = api_instance.create_project_follower(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_project_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Exists |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_table_follower**
> Follow create_table_follower(x_tenant, table_id)

Create Table Followers

Create a new follow relationship between a table and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    table_id = "table_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create Table Followers
        api_response = api_instance.create_table_follower(x_tenant, table_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_table_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **table_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Exists |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_user_follower**
> Follow create_user_follower(x_tenant, user_id)

Create User Followers

Create a new follow relationship between a two users.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    user_id = "user_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create User Followers
        api_response = api_instance.create_user_follower(x_tenant, user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_user_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Created |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_workflow_follower**
> Follow create_workflow_follower(x_tenant, workflow_id)

Create Workflow Followers

Create a new follow relationship between a workflow and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.follow import Follow
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    workflow_id = "workflow_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Create Workflow Followers
        api_response = api_instance.create_workflow_follower(x_tenant, workflow_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->create_workflow_follower: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**|  |

### Return type

[**Follow**](Follow.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Already Exists |  -  |
**201** | Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_catalog**
> delete_following_catalog(x_tenant, catalog_id)

Delete Following Catalog

Delete the follow relationship between a catalog and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    catalog_id = "catalog_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following Catalog
        api_instance.delete_following_catalog(x_tenant, catalog_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_catalog: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **catalog_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_database**
> delete_following_database(x_tenant, database_id)

Delete Following Database

Delete the follow relationship between a database and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    database_id = "database_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following Database
        api_instance.delete_following_database(x_tenant, database_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_database: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **database_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_job**
> delete_following_job(x_tenant, job_id)

Delete Following Job

Delete the follow relationship between a job and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    job_id = "job_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following Job
        api_instance.delete_following_job(x_tenant, job_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_job: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_project**
> delete_following_project(x_tenant, project_id)

Delete Following Project

Delete the follow relationship between a project and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    project_id = "project_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following Project
        api_instance.delete_following_project(x_tenant, project_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_project: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_table**
> delete_following_table(x_tenant, table_id)

Delete Following Table

Delete the follow relationship between a table and an user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    table_id = "table_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following Table
        api_instance.delete_following_table(x_tenant, table_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_table: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **table_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_user**
> delete_following_user(x_tenant, user_id)

Delete Following User

Delete the follow relationship between two users.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    user_id = "user_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following User
        api_instance.delete_following_user(x_tenant, user_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_user: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_following_workflow**
> delete_following_workflow(x_tenant, workflow_id)

Delete Following User

Delete the follow relationship between a workflow and a user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    workflow_id = "workflow_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete Following User
        api_instance.delete_following_workflow(x_tenant, workflow_id)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->delete_following_workflow: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_catalog_followers**
> [User1] get_catalog_followers(x_tenant, catalog_id)

Get Catalog Followers

Route to GET all users following a given catalog.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    catalog_id = "catalog_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get Catalog Followers
        api_response = api_instance.get_catalog_followers(x_tenant, catalog_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_catalog_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **catalog_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

# **get_database_followers**
> [User1] get_database_followers(x_tenant, database_id)

Get Database Followers

Route to GET all users following a given database.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    database_id = "database_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get Database Followers
        api_response = api_instance.get_database_followers(x_tenant, database_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_database_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **database_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

# **get_job_followers**
> [User1] get_job_followers(x_tenant, job_id)

Get Job Followers

Route to GET all users following a given job.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    job_id = "job_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get Job Followers
        api_response = api_instance.get_job_followers(x_tenant, job_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_job_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **job_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

# **get_project_followers**
> [User1] get_project_followers(x_tenant, project_id)

Get Project Followers

Route to GET all users following a given project.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    project_id = "project_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get Project Followers
        api_response = api_instance.get_project_followers(x_tenant, project_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_project_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **project_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

# **get_table_followers**
> [User1] get_table_followers(x_tenant, table_id)

Get Table Followers

Route to GET all users following a given table.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    table_id = "table_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get Table Followers
        api_response = api_instance.get_table_followers(x_tenant, table_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_table_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **table_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

# **get_user_followers**
> [User1] get_user_followers(x_tenant, user_id)

Get User Followers

Route to GET all followers of a given user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    user_id = "user_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get User Followers
        api_response = api_instance.get_user_followers(x_tenant, user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_user_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

# **get_user_following**
> [bool, date, datetime, dict, float, int, list, str, none_type] get_user_following(x_tenant, user_id)

Get User Following

Route to GET all users following a given user.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
from graalsystems.model.project1 import Project1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    user_id = "user_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get User Following
        api_response = api_instance.get_user_following(x_tenant, user_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_user_following: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **user_id** | **str**|  |

### Return type

**[bool, date, datetime, dict, float, int, list, str, none_type]**

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

# **get_workflow_followers**
> [User1] get_workflow_followers(x_tenant, workflow_id)

Get Workflow Followers

Route to GET all users following a given workflow.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import follow_api
from graalsystems.model.user1 import User1
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
    api_instance = follow_api.FollowApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    workflow_id = "workflow_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get Workflow Followers
        api_response = api_instance.get_workflow_followers(x_tenant, workflow_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FollowApi->get_workflow_followers: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **workflow_id** | **str**|  |

### Return type

[**[User1]**](User1.md)

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

