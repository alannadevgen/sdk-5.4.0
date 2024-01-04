# graalsystems.MarketplaceApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**find_template_metadata**](MarketplaceApi.md#find_template_metadata) | **GET** /templates/{name}/versions/{version} | Get template metadata
[**find_template_versions**](MarketplaceApi.md#find_template_versions) | **GET** /templates/{name}/versions | Get template versions
[**find_templates**](MarketplaceApi.md#find_templates) | **GET** /templates | Get templates
[**generate_template**](MarketplaceApi.md#generate_template) | **POST** /renders/{name}/versions/{version} | Generate dag from a template


# **find_template_metadata**
> find_template_metadata(x_tenant, name, version)

Get template metadata

Get all the metadata from a template.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import marketplace_api
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
    api_instance = marketplace_api.MarketplaceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    name = "name_example" # str | 
    version = "version_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get template metadata
        api_instance.find_template_metadata(x_tenant, name, version)
    except graalsystems.ApiException as e:
        print("Exception when calling MarketplaceApi->find_template_metadata: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **name** | **str**|  |
 **version** | **str**|  |

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
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_template_versions**
> [str] find_template_versions(x_tenant, name)

Get template versions

Get the list of all available versions for a template.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import marketplace_api
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
    api_instance = marketplace_api.MarketplaceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    name = "name_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get template versions
        api_response = api_instance.find_template_versions(x_tenant, name)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling MarketplaceApi->find_template_versions: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **name** | **str**|  |

### Return type

**[str]**

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

# **find_templates**
> [{str: (str,)}] find_templates(x_tenant)

Get templates

Get the list of all available templates.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import marketplace_api
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
    api_instance = marketplace_api.MarketplaceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get templates
        api_response = api_instance.find_templates(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling MarketplaceApi->find_templates: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

**[{str: (str,)}]**

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **generate_template**
> generate_template(x_tenant, name, version, body)

Generate dag from a template

Generates the dag of a given template and fills it with parameters.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import marketplace_api
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
    api_instance = marketplace_api.MarketplaceApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    name = "name_example" # str | 
    version = "version_example" # str | 
    body = {} # {str: (bool, date, datetime, dict, float, int, list, str, none_type)} | 

    # example passing only required values which don't have defaults set
    try:
        # Generate dag from a template
        api_instance.generate_template(x_tenant, name, version, body)
    except graalsystems.ApiException as e:
        print("Exception when calling MarketplaceApi->generate_template: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **name** | **str**|  |
 **version** | **str**|  |
 **body** | **{str: (bool, date, datetime, dict, float, int, list, str, none_type)}**|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

