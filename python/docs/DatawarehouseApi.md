# graalsystems.DatawarehouseApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_data_warehouse**](DatawarehouseApi.md#create_data_warehouse) | **POST** /datawarehouses | Create datawarehouse
[**delete_data_warehouse_by_id**](DatawarehouseApi.md#delete_data_warehouse_by_id) | **DELETE** /datawarehouses/{datawarehouseId} | Delete a datawarehouse by an id
[**find_changes**](DatawarehouseApi.md#find_changes) | **GET** /datawarehouses/{datawarehouseId}/changes | Find changes by datawarehouse id
[**find_data_warehouse_by_id**](DatawarehouseApi.md#find_data_warehouse_by_id) | **GET** /datawarehouses/{datawarehouseId} | Find datawarehouse by Id
[**find_data_warehouses**](DatawarehouseApi.md#find_data_warehouses) | **GET** /datawarehouses | Retrieve all datawarehouses
[**find_tables**](DatawarehouseApi.md#find_tables) | **GET** /datawarehouses/{datawarehouseId}/tables | Find tables by datawarehouse id
[**get_logs_for_datawarehouse**](DatawarehouseApi.md#get_logs_for_datawarehouse) | **GET** /datawarehouses/{datawarehouseId}/logs | Get logs
[**update_data_warehouse**](DatawarehouseApi.md#update_data_warehouse) | **PATCH** /datawarehouses/{datawarehouseId} | Update a datawarehouse


# **create_data_warehouse**
> DataWarehouse create_data_warehouse(x_tenant, data_warehouse)

Create datawarehouse

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
from graalsystems.model.data_warehouse import DataWarehouse
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    data_warehouse = DataWarehouse(
        id="id_example",
        name="name_example",
        type="type_example",
        description="description_example",
        version="version_example",
        options=DataWarehouseOptions(),
        owner="owner_example",
        password="password_example",
        username="username_example",
        identity_id="identity_id_example",
        infrastructure_id="infrastructure_id_example",
        public_url="public_url_example",
        status="status_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        labels={
            "key": "key_example",
        },
        metadata={
            "key": {},
        },
    ) # DataWarehouse | The datawarehouse to be created

    # example passing only required values which don't have defaults set
    try:
        # Create datawarehouse
        api_response = api_instance.create_data_warehouse(x_tenant, data_warehouse)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->create_data_warehouse: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **data_warehouse** | [**DataWarehouse**](DataWarehouse.md)| The datawarehouse to be created |

### Return type

[**DataWarehouse**](DataWarehouse.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.datawarehouse+json
 - **Accept**: application/vnd.graal.systems.v1.datawarehouse+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_data_warehouse_by_id**
> delete_data_warehouse_by_id(x_tenant, datawarehouse_id)

Delete a datawarehouse by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    datawarehouse_id = "datawarehouseId_example" # str | Id of the datawarehouse

    # example passing only required values which don't have defaults set
    try:
        # Delete a datawarehouse by an id
        api_instance.delete_data_warehouse_by_id(x_tenant, datawarehouse_id)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->delete_data_warehouse_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **datawarehouse_id** | **str**| Id of the datawarehouse |

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
**404** | DataWarehouse not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_changes**
> ChangePage find_changes(x_tenant, datawarehouse_id)

Find changes by datawarehouse id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
from graalsystems.model.change_page import ChangePage
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    datawarehouse_id = "datawarehouseId_example" # str | Id of the datawarehouse
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Find changes by datawarehouse id
        api_response = api_instance.find_changes(x_tenant, datawarehouse_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_changes: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Find changes by datawarehouse id
        api_response = api_instance.find_changes(x_tenant, datawarehouse_id, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_changes: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **datawarehouse_id** | **str**| Id of the datawarehouse |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**ChangePage**](ChangePage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.change+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_data_warehouse_by_id**
> DataWarehouse find_data_warehouse_by_id(x_tenant, datawarehouse_id)

Find datawarehouse by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
from graalsystems.model.data_warehouse import DataWarehouse
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    datawarehouse_id = "datawarehouseId_example" # str | Id of the datawarehouse

    # example passing only required values which don't have defaults set
    try:
        # Find datawarehouse by Id
        api_response = api_instance.find_data_warehouse_by_id(x_tenant, datawarehouse_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_data_warehouse_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **datawarehouse_id** | **str**| Id of the datawarehouse |

### Return type

[**DataWarehouse**](DataWarehouse.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.datawarehouse+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | DataWarehouse not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_data_warehouses**
> DataWarehousePage find_data_warehouses(x_tenant)

Retrieve all datawarehouses

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
from graalsystems.model.data_warehouse_page import DataWarehousePage
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all datawarehouses
        api_response = api_instance.find_data_warehouses(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_data_warehouses: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all datawarehouses
        api_response = api_instance.find_data_warehouses(x_tenant, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_data_warehouses: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**DataWarehousePage**](DataWarehousePage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.datawarehouse+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_tables**
> [Table] find_tables(x_tenant, datawarehouse_id)

Find tables by datawarehouse id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
from graalsystems.model.table import Table
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    datawarehouse_id = "datawarehouseId_example" # str | Id of the datawarehouse
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Find tables by datawarehouse id
        api_response = api_instance.find_tables(x_tenant, datawarehouse_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_tables: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Find tables by datawarehouse id
        api_response = api_instance.find_tables(x_tenant, datawarehouse_id, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->find_tables: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **datawarehouse_id** | **str**| Id of the datawarehouse |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**[Table]**](Table.md)

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

# **get_logs_for_datawarehouse**
> [LogEntry] get_logs_for_datawarehouse(x_tenant, datawarehouse_id)

Get logs

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    datawarehouse_id = "datawarehouseId_example" # str | Id of the datawarehouse
    cursor = "cursor_example" # str | The cursor (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get logs
        api_response = api_instance.get_logs_for_datawarehouse(x_tenant, datawarehouse_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->get_logs_for_datawarehouse: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get logs
        api_response = api_instance.get_logs_for_datawarehouse(x_tenant, datawarehouse_id, cursor=cursor)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->get_logs_for_datawarehouse: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **datawarehouse_id** | **str**| Id of the datawarehouse |
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

# **update_data_warehouse**
> DataWarehouse update_data_warehouse(x_tenant, datawarehouse_id, patch)

Update a datawarehouse

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import datawarehouse_api
from graalsystems.model.data_warehouse import DataWarehouse
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
    api_instance = datawarehouse_api.DatawarehouseApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    datawarehouse_id = "datawarehouseId_example" # str | Id of the datawarehouse
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
        # Update a datawarehouse
        api_response = api_instance.update_data_warehouse(x_tenant, datawarehouse_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DatawarehouseApi->update_data_warehouse: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **datawarehouse_id** | **str**| Id of the datawarehouse |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**DataWarehouse**](DataWarehouse.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.datawarehouse+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

