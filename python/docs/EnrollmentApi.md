# graalsystems.EnrollmentApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_enrollment**](EnrollmentApi.md#create_enrollment) | **POST** /enrollments | Create enrollment
[**delete_enrollment_by_id**](EnrollmentApi.md#delete_enrollment_by_id) | **DELETE** /enrollments/{enrollmentId} | Delete a enrollment by an id
[**find_enrollment_by_enrollment_id**](EnrollmentApi.md#find_enrollment_by_enrollment_id) | **GET** /enrollments/{enrollmentId} | Find enrollment by Id
[**find_enrollments**](EnrollmentApi.md#find_enrollments) | **GET** /enrollments | Retrieve all enrollment


# **create_enrollment**
> Enrollment create_enrollment(x_tenant, enrollment)

Create enrollment

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import enrollment_api
from graalsystems.model.enrollment import Enrollment
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
    api_instance = enrollment_api.EnrollmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    enrollment = Enrollment(
        id="id_example",
        platform_public_key="platform_public_key_example",
        device_certificate="device_certificate_example",
        description="description_example",
        metadata={
            "key": {},
        },
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
    ) # Enrollment | The enrollment to be created

    # example passing only required values which don't have defaults set
    try:
        # Create enrollment
        api_response = api_instance.create_enrollment(x_tenant, enrollment)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnrollmentApi->create_enrollment: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **enrollment** | [**Enrollment**](Enrollment.md)| The enrollment to be created |

### Return type

[**Enrollment**](Enrollment.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.enrollment+json
 - **Accept**: application/vnd.graal.systems.v1.enrollment+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_enrollment_by_id**
> delete_enrollment_by_id(x_tenant, enrollment_id)

Delete a enrollment by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import enrollment_api
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
    api_instance = enrollment_api.EnrollmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    enrollment_id = "enrollmentId_example" # str | Id of the enrollment

    # example passing only required values which don't have defaults set
    try:
        # Delete a enrollment by an id
        api_instance.delete_enrollment_by_id(x_tenant, enrollment_id)
    except graalsystems.ApiException as e:
        print("Exception when calling EnrollmentApi->delete_enrollment_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **enrollment_id** | **str**| Id of the enrollment |

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

# **find_enrollment_by_enrollment_id**
> Enrollment find_enrollment_by_enrollment_id(x_tenant, enrollment_id)

Find enrollment by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import enrollment_api
from graalsystems.model.enrollment import Enrollment
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
    api_instance = enrollment_api.EnrollmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    enrollment_id = "enrollmentId_example" # str | Id of the enrollment

    # example passing only required values which don't have defaults set
    try:
        # Find enrollment by Id
        api_response = api_instance.find_enrollment_by_enrollment_id(x_tenant, enrollment_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnrollmentApi->find_enrollment_by_enrollment_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **enrollment_id** | **str**| Id of the enrollment |

### Return type

[**Enrollment**](Enrollment.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.enrollment+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Enrollment not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_enrollments**
> EnrollmentPage find_enrollments(x_tenant)

Retrieve all enrollment

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import enrollment_api
from graalsystems.model.enrollment_page import EnrollmentPage
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
    api_instance = enrollment_api.EnrollmentApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    page = 0 # int |  (optional) if omitted the server will use the default value of 0
    size = 200 # int |  (optional) if omitted the server will use the default value of 200

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all enrollment
        api_response = api_instance.find_enrollments(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnrollmentApi->find_enrollments: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Retrieve all enrollment
        api_response = api_instance.find_enrollments(x_tenant, page=page, size=size)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling EnrollmentApi->find_enrollments: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **page** | **int**|  | [optional] if omitted the server will use the default value of 0
 **size** | **int**|  | [optional] if omitted the server will use the default value of 200

### Return type

[**EnrollmentPage**](EnrollmentPage.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.enrollment+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

