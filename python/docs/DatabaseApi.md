# graalsystems.DatabaseApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_database**](DatabaseApi.md#create_database) | **POST** /layers/{layer_name}/databases | Create a database
[**delete_database_by_id**](DatabaseApi.md#delete_database_by_id) | **DELETE** /layers/{layer_name}/databases/{database_name} | Delete a database by an id
[**find_database_by_id**](DatabaseApi.md#find_database_by_id) | **GET** /layers/{layer_name}/databases/{database_name} | Find database by Id
[**find_databases**](DatabaseApi.md#find_databases) | **GET** /layers/{layer_name}/databases | Retrieve all databases
[**update_database**](DatabaseApi.md#update_database) | **PATCH** /layers/{layer_name}/databases/{database_name} | Update a database


# **create_database**
> Database create_database(x_tenant, layer_name, database)

Create a database

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import database_api
from graalsystems.model.database import Database
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
    api_instance = database_api.DatabaseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Name of the layer
    database = Database(
        id="id_example",
        technical_name="technical_name_example",
        name="name_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Database | The database to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a database
        api_response = api_instance.create_database(x_tenant, layer_name, database)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatabaseApi->create_database: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Name of the layer |
 **database** | [**Database**](Database.md)| The database to be created |

### Return type

[**Database**](Database.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.database+json
 - **Accept**: application/vnd.graal.systems.v1.database+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_database_by_id**
> delete_database_by_id(x_tenant, layer_name, database_name)

Delete a database by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import database_api
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
    api_instance = database_api.DatabaseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Id of the layer
    database_name = "database_name_example" # str | Id of the database

    # example passing only required values which don't have defaults set
    try:
        # Delete a database by an id
        api_instance.delete_database_by_id(x_tenant, layer_name, database_name)
    except graalsystems.ApiException as e:
        print("Exception when calling DatabaseApi->delete_database_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Id of the layer |
 **database_name** | **str**| Id of the database |

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
**404** | Database not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_database_by_id**
> Database find_database_by_id(x_tenant, layer_name, database_name)

Find database by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import database_api
from graalsystems.model.database import Database
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
    api_instance = database_api.DatabaseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Id of the layer
    database_name = "database_name_example" # str | Id of the database

    # example passing only required values which don't have defaults set
    try:
        # Find database by Id
        api_response = api_instance.find_database_by_id(x_tenant, layer_name, database_name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatabaseApi->find_database_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Id of the layer |
 **database_name** | **str**| Id of the database |

### Return type

[**Database**](Database.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.database+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Database not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_databases**
> [Database] find_databases(x_tenant, layer_name)

Retrieve all databases

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import database_api
from graalsystems.model.database import Database
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
    api_instance = database_api.DatabaseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Name of the layer

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all databases
        api_response = api_instance.find_databases(x_tenant, layer_name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatabaseApi->find_databases: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Name of the layer |

### Return type

[**[Database]**](Database.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.database+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_database**
> Database update_database(x_tenant, layer_name, database_name, patch)

Update a database

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import database_api
from graalsystems.model.database import Database
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
    api_instance = database_api.DatabaseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Id of the layer
    database_name = "database_name_example" # str | Id of the database
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
        # Update a database
        api_response = api_instance.update_database(x_tenant, layer_name, database_name, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatabaseApi->update_database: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Id of the layer |
 **database_name** | **str**| Id of the database |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Database**](Database.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.database+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Database not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

