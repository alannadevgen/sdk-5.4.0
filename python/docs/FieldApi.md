# graalsystems.FieldApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_field**](FieldApi.md#create_field) | **POST** /layers/{layer_name}/databases/{database_name}/tables/{table_name}/fields | Create a field
[**find_fields**](FieldApi.md#find_fields) | **GET** /layers/{layer_name}/databases/{database_name}/tables/{table_name}/fields | Retrieve all fields


# **create_field**
> Field create_field(x_tenant, layer_name, database_name, table_name, field)

Create a field

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import field_api
from graalsystems.model.field import Field
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
    api_instance = field_api.FieldApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Name of the layer
    database_name = "database_name_example" # str | Name of the database
    table_name = "table_name_example" # str | Name of the table
    field = Field(
        id="id_example",
        technical_name="technical_name_example",
        name="name_example",
        description="description_example",
        type="type_example",
        nullable=True,
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Field | The field to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a field
        api_response = api_instance.create_field(x_tenant, layer_name, database_name, table_name, field)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FieldApi->create_field: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Name of the layer |
 **database_name** | **str**| Name of the database |
 **table_name** | **str**| Name of the table |
 **field** | [**Field**](Field.md)| The field to be created |

### Return type

[**Field**](Field.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.field+json
 - **Accept**: application/vnd.graal.systems.v1.field+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_fields**
> [Field] find_fields(x_tenant, layer_name, database_name, table_name)

Retrieve all fields

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import field_api
from graalsystems.model.field import Field
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
    api_instance = field_api.FieldApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    layer_name = "layer_name_example" # str | Name of the layer
    database_name = "database_name_example" # str | Name of the database
    table_name = "table_name_example" # str | Name of the table

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all fields
        api_response = api_instance.find_fields(x_tenant, layer_name, database_name, table_name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FieldApi->find_fields: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **layer_name** | **str**| Name of the layer |
 **database_name** | **str**| Name of the database |
 **table_name** | **str**| Name of the table |

### Return type

[**[Field]**](Field.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.field+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

