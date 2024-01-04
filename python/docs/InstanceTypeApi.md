# graalsystems.InstanceTypeApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**find_instance_type_by_instance_type_id**](InstanceTypeApi.md#find_instance_type_by_instance_type_id) | **GET** /instance-types/{instance_type_id} | Find instance type by Id
[**find_instance_types**](InstanceTypeApi.md#find_instance_types) | **GET** /instance-types | Retrieve all instance types


# **find_instance_type_by_instance_type_id**
> InstanceType find_instance_type_by_instance_type_id(x_tenant, instance_type_id)

Find instance type by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import instance_type_api
from graalsystems.model.instance_type import InstanceType
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
    api_instance = instance_type_api.InstanceTypeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    instance_type_id = "instance_type_id_example" # str | Id of the instance type

    # example passing only required values which don't have defaults set
    try:
        # Find instance type by Id
        api_response = api_instance.find_instance_type_by_instance_type_id(x_tenant, instance_type_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling InstanceTypeApi->find_instance_type_by_instance_type_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **instance_type_id** | **str**| Id of the instance type |

### Return type

[**InstanceType**](InstanceType.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.instance-type+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Instance type not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_instance_types**
> [InstanceType] find_instance_types(x_tenant)

Retrieve all instance types

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import instance_type_api
from graalsystems.model.instance_type import InstanceType
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
    api_instance = instance_type_api.InstanceTypeApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all instance types
        api_response = api_instance.find_instance_types(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling InstanceTypeApi->find_instance_types: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[InstanceType]**](InstanceType.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.instance-type+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

