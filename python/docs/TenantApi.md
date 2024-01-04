# graalsystems.TenantApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_tenant**](TenantApi.md#create_tenant) | **POST** /tenants | Create a tenant
[**delete_tenant_by_id**](TenantApi.md#delete_tenant_by_id) | **DELETE** /tenants/{tenantId} | Delete a tenant by its id
[**find_realm_by_tenant_id**](TenantApi.md#find_realm_by_tenant_id) | **GET** /tenants/{tenantId}?attribute&#x3D;realm | Find realm by tenant id
[**find_tenant_by_id**](TenantApi.md#find_tenant_by_id) | **GET** /tenants/{tenantId} | Find tenant by Id
[**find_tenants**](TenantApi.md#find_tenants) | **GET** /tenants | Retrieve all tenants
[**update_tenant**](TenantApi.md#update_tenant) | **PATCH** /tenants/{tenantId} | Update a tenant


# **create_tenant**
> Tenant create_tenant(x_tenant, tenant)

Create a tenant

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import tenant_api
from graalsystems.model.tenant import Tenant
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
    api_instance = tenant_api.TenantApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    tenant = Tenant(
        id="id_example",
        name="name_example",
        type="type_example",
        sku="sku_example",
        email="email_example",
        realm="realm_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Tenant | The tenant to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a tenant
        api_response = api_instance.create_tenant(x_tenant, tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TenantApi->create_tenant: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **tenant** | [**Tenant**](Tenant.md)| The tenant to be created |

### Return type

[**Tenant**](Tenant.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.tenant+json
 - **Accept**: application/vnd.graal.systems.v1.tenant+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_tenant_by_id**
> delete_tenant_by_id(x_tenant, tenant_id)

Delete a tenant by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import tenant_api
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
    api_instance = tenant_api.TenantApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    tenant_id = "tenantId_example" # str | Id of the Tenant

    # example passing only required values which don't have defaults set
    try:
        # Delete a tenant by its id
        api_instance.delete_tenant_by_id(x_tenant, tenant_id)
    except graalsystems.ApiException as e:
        print("Exception when calling TenantApi->delete_tenant_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **tenant_id** | **str**| Id of the Tenant |

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
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_realm_by_tenant_id**
> Tenant find_realm_by_tenant_id(tenant_id)

Find realm by tenant id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import tenant_api
from graalsystems.model.tenant import Tenant
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
    api_instance = tenant_api.TenantApi(api_client)
    tenant_id = "tenantId_example" # str | Id of the tenant

    # example passing only required values which don't have defaults set
    try:
        # Find realm by tenant id
        api_response = api_instance.find_realm_by_tenant_id(tenant_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TenantApi->find_realm_by_tenant_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **tenant_id** | **str**| Id of the tenant |

### Return type

[**Tenant**](Tenant.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.tenant+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_tenant_by_id**
> Tenant find_tenant_by_id(x_tenant, tenant_id)

Find tenant by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import tenant_api
from graalsystems.model.tenant import Tenant
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
    api_instance = tenant_api.TenantApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    tenant_id = "tenantId_example" # str | Id of the tenant

    # example passing only required values which don't have defaults set
    try:
        # Find tenant by Id
        api_response = api_instance.find_tenant_by_id(x_tenant, tenant_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TenantApi->find_tenant_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **tenant_id** | **str**| Id of the tenant |

### Return type

[**Tenant**](Tenant.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.tenant+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_tenants**
> [Tenant] find_tenants(x_tenant)

Retrieve all tenants

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import tenant_api
from graalsystems.model.tenant import Tenant
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
    api_instance = tenant_api.TenantApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all tenants
        api_response = api_instance.find_tenants(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TenantApi->find_tenants: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Tenant]**](Tenant.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.tenant+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_tenant**
> Tenant update_tenant(x_tenant, tenant_id, patch)

Update a tenant

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import tenant_api
from graalsystems.model.tenant import Tenant
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
    api_instance = tenant_api.TenantApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    tenant_id = "tenantId_example" # str | Id of the Tenant
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
        # Update a tenant
        api_response = api_instance.update_tenant(x_tenant, tenant_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TenantApi->update_tenant: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **tenant_id** | **str**| Id of the Tenant |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Tenant**](Tenant.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.tenant+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Tenant not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

