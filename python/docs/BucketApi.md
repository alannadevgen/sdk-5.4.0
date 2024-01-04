# graalsystems.BucketApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_bucket**](BucketApi.md#create_bucket) | **POST** /buckets | Create a bucket
[**delete_bucket_by_id**](BucketApi.md#delete_bucket_by_id) | **DELETE** /buckets/{bucketId} | Delete a bucket by an id
[**find_bucket_by_id**](BucketApi.md#find_bucket_by_id) | **GET** /buckets/{bucketId} | Find bucket by Id
[**find_buckets**](BucketApi.md#find_buckets) | **GET** /buckets | Retrieve all buckets
[**update_bucket**](BucketApi.md#update_bucket) | **PATCH** /buckets/{bucketId} | Update a bucket


# **create_bucket**
> Bucket create_bucket(x_tenant, bucket)

Create a bucket

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bucket_api
from graalsystems.model.bucket import Bucket
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
    api_instance = bucket_api.BucketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket = Bucket(
        id="id_example",
        name="name_example",
        description="description_example",
        scope="scope_example",
        locked=True,
        uri=Uri(),
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
        labels={
            "key": "key_example",
        },
    ) # Bucket | The bucket to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a bucket
        api_response = api_instance.create_bucket(x_tenant, bucket)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BucketApi->create_bucket: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket** | [**Bucket**](Bucket.md)| The bucket to be created |

### Return type

[**Bucket**](Bucket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.bucket+json
 - **Accept**: application/vnd.graal.systems.v1.bucket+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_bucket_by_id**
> delete_bucket_by_id(x_tenant, bucket_id)

Delete a bucket by an id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bucket_api
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
    api_instance = bucket_api.BucketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket

    # example passing only required values which don't have defaults set
    try:
        # Delete a bucket by an id
        api_instance.delete_bucket_by_id(x_tenant, bucket_id)
    except graalsystems.ApiException as e:
        print("Exception when calling BucketApi->delete_bucket_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |

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
**404** | Bucket not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_bucket_by_id**
> Bucket find_bucket_by_id(x_tenant, bucket_id)

Find bucket by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bucket_api
from graalsystems.model.bucket import Bucket
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
    api_instance = bucket_api.BucketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket

    # example passing only required values which don't have defaults set
    try:
        # Find bucket by Id
        api_response = api_instance.find_bucket_by_id(x_tenant, bucket_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BucketApi->find_bucket_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |

### Return type

[**Bucket**](Bucket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.bucket+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Bucket not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_buckets**
> [Bucket] find_buckets(x_tenant)

Retrieve all buckets

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bucket_api
from graalsystems.model.bucket import Bucket
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
    api_instance = bucket_api.BucketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all buckets
        api_response = api_instance.find_buckets(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BucketApi->find_buckets: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Bucket]**](Bucket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.bucket+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_bucket**
> Bucket update_bucket(x_tenant, bucket_id, patch)

Update a bucket

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import bucket_api
from graalsystems.model.bucket import Bucket
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
    api_instance = bucket_api.BucketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    bucket_id = "bucketId_example" # str | Id of the bucket
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
        # Update a bucket
        api_response = api_instance.update_bucket(x_tenant, bucket_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling BucketApi->update_bucket: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **bucket_id** | **str**| Id of the bucket |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Bucket**](Bucket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.bucket+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Bucket not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

