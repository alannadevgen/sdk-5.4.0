# graalsystems.TableApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_table**](TableApi.md#create_table) | **POST** /layers/{layer_name}/databases/{database_name}/tables | Create a table
[**delete_table_by_id**](TableApi.md#delete_table_by_id) | **DELETE** /layers/{layer_name}/databases/{database_name}/tables/{table_name} | Delete a table by an id
[**find_table_by_id**](TableApi.md#find_table_by_id) | **GET** /layers/{layer_name}/databases/{database_name}/tables/{table_name} | Find table by Id
[**find_tables1**](TableApi.md#find_tables1) | **GET** /layers/{layer_name}/databases/{database_name}/tables | Retrieve all tables
[**update_table**](TableApi.md#update_table) | **PATCH** /layers/{layer_name}/databases/{database_name}/tables/{table_name} | Update a table


# **create_table**
> Table1 create_table(x_tenant, layer_name, database_name, table1)

Create a table

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import table_api
from graalsystems.model.table1 import Table1
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
    api_instance = table_api.TableApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Name of the layer
    database_name = "database_name_example" # str | Name of the database
    table1 = Table1(
        id="id_example",
        technical_name="technical_name_example",
        name="name_example",
        uri="uri_example",
        public_uri="public_uri_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Table1 | The database to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a table
        api_response = api_instance.create_table(x_tenant, layer_name, database_name, table1)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TableApi->create_table: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Name of the layer |
 **database_name** | **str**| Name of the database |
 **table1** | [**Table1**](Table1.md)| The database to be created |

### Return type

[**Table1**](Table1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.table+json
 - **Accept**: application/vnd.graal.systems.v1.table+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_table_by_id**
> delete_table_by_id(x_tenant, layer_name, database_name, table_name)

Delete a table by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import table_api
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
    api_instance = table_api.TableApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Id of the layer
    database_name = "database_name_example" # str | Id of the database
    table_name = "table_name_example" # str | Id of the table

    # example passing only required values which don't have defaults set
    try:
        # Delete a table by an id
        api_instance.delete_table_by_id(x_tenant, layer_name, database_name, table_name)
    except graalsystems.ApiException as e:
        print("Exception when calling TableApi->delete_table_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Id of the layer |
 **database_name** | **str**| Id of the database |
 **table_name** | **str**| Id of the table |

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
**404** | Table not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_table_by_id**
> Table1 find_table_by_id(x_tenant, layer_name, database_name, table_name)

Find table by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import table_api
from graalsystems.model.table1 import Table1
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
    api_instance = table_api.TableApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Id of the layer
    database_name = "database_name_example" # str | Id of the database
    table_name = "table_name_example" # str | Id of the table

    # example passing only required values which don't have defaults set
    try:
        # Find table by Id
        api_response = api_instance.find_table_by_id(x_tenant, layer_name, database_name, table_name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TableApi->find_table_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Id of the layer |
 **database_name** | **str**| Id of the database |
 **table_name** | **str**| Id of the table |

### Return type

[**Table1**](Table1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.table+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Table not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_tables1**
> [Table1] find_tables1(x_tenant, layer_name, database_name)

Retrieve all tables

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import table_api
from graalsystems.model.table1 import Table1
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
    api_instance = table_api.TableApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Name of the layer
    database_name = "database_name_example" # str | Name of the database

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all tables
        api_response = api_instance.find_tables1(x_tenant, layer_name, database_name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TableApi->find_tables1: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Name of the layer |
 **database_name** | **str**| Name of the database |

### Return type

[**[Table1]**](Table1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.table+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_table**
> Table1 update_table(x_tenant, layer_name, database_name, table_name, patch)

Update a table

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import table_api
from graalsystems.model.table1 import Table1
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
    api_instance = table_api.TableApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Id of the layer
    database_name = "database_name_example" # str | Id of the database
    table_name = "table_name_example" # str | Id of the table
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
        # Update a table
        api_response = api_instance.update_table(x_tenant, layer_name, database_name, table_name, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TableApi->update_table: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Id of the layer |
 **database_name** | **str**| Id of the database |
 **table_name** | **str**| Id of the table |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Table1**](Table1.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.table+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Table not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

