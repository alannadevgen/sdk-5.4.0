# graalsystems.DeviceApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_device**](DeviceApi.md#create_device) | **POST** /devices | Create device
[**delete_device_by_id**](DeviceApi.md#delete_device_by_id) | **DELETE** /devices/{deviceId} | Delete a device by an id
[**find_device_by_device_id**](DeviceApi.md#find_device_by_device_id) | **GET** /devices/{deviceId} | Find device by Id
[**find_devices**](DeviceApi.md#find_devices) | **GET** /devices | Retrieve all device
[**update_device**](DeviceApi.md#update_device) | **PATCH** /devices/{deviceId} | Update an device


# **create_device**
> Device create_device(x_tenant)

Create device

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import device_api
from graalsystems.model.device import Device
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
    api_instance = device_api.DeviceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    filename = [
        open('/path/to/file', 'rb'),
    ] # [file_type] |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Create device
        api_response = api_instance.create_device(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->create_device: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Create device
        api_response = api_instance.create_device(x_tenant, filename=filename)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->create_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **filename** | **[file_type]**|  | [optional]

### Return type

[**Device**](Device.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: application/vnd.graal.systems.v1.device+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_device_by_id**
> delete_device_by_id(x_tenant, device_id)

Delete a device by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import device_api
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
    api_instance = device_api.DeviceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    device_id = "deviceId_example" # str | Id of the device

    # example passing only required values which don't have defaults set
    try:
        # Delete a device by an id
        api_instance.delete_device_by_id(x_tenant, device_id)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->delete_device_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **device_id** | **str**| Id of the device |

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

# **find_device_by_device_id**
> Device find_device_by_device_id(x_tenant, device_id)

Find device by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import device_api
from graalsystems.model.device import Device
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
    api_instance = device_api.DeviceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    device_id = "deviceId_example" # str | Id of the device

    # example passing only required values which don't have defaults set
    try:
        # Find device by Id
        api_response = api_instance.find_device_by_device_id(x_tenant, device_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->find_device_by_device_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **device_id** | **str**| Id of the device |

### Return type

[**Device**](Device.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.device+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Device not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_devices**
> DevicePage find_devices(x_tenant)

Retrieve all device

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import device_api
from graalsystems.model.device_page import DevicePage
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
    api_instance = device_api.DeviceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all device
        api_response = api_instance.find_devices(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->find_devices: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all device
        api_response = api_instance.find_devices(x_tenant, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->find_devices: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**DevicePage**](DevicePage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.device+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_device**
> Device update_device(x_tenant, device_id, patch)

Update an device

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import device_api
from graalsystems.model.device import Device
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
    api_instance = device_api.DeviceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    device_id = "deviceId_example" # str | Id of the device
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
        # Update an device
        api_response = api_instance.update_device(x_tenant, device_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling DeviceApi->update_device: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **device_id** | **str**| Id of the device |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Device**](Device.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.device+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Project not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

