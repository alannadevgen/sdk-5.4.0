# graalsystems.ActivityApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_activity**](ActivityApi.md#create_activity) | **POST** /activities | Create a new activity
[**create_comment_for_activity**](ActivityApi.md#create_comment_for_activity) | **POST** /activities/{activity_id}/comments | Insert a user comment for a given activity
[**create_reaction_for_activity**](ActivityApi.md#create_reaction_for_activity) | **POST** /activities/{activity_id}/reactions | Insert the reaction of an user to a given activity
[**delete_comment_from_activity**](ActivityApi.md#delete_comment_from_activity) | **DELETE** /activities/{activity_id}/comments/{comment_id} | Delete the comment of an user for a given activity
[**delete_reaction_from_activity**](ActivityApi.md#delete_reaction_from_activity) | **DELETE** /activities/{activity_id}/reactions/{reaction_id} | Delete users&#39; reactions for a given activity
[**get_activities_from_timeline**](ActivityApi.md#get_activities_from_timeline) | **GET** /activities | Get all activities from timeline
[**get_activities_summary**](ActivityApi.md#get_activities_summary) | **GET** /activities/{resource_id}/summary | Get a count of all the activities for a resource
[**get_comments_from_activity**](ActivityApi.md#get_comments_from_activity) | **GET** /activities/{activity_id}/comments | Get all the comments for a given activity
[**get_creation_date**](ActivityApi.md#get_creation_date) | **GET** /resources/{resource_id}/years | Get a list of defined years for a resource
[**get_reactions_from_activity**](ActivityApi.md#get_reactions_from_activity) | **GET** /activities/{activity_id}/reactions | Get all user reactions for a given activity
[**update_comment_for_activity**](ActivityApi.md#update_comment_for_activity) | **PUT** /activities/{activity_id}/comments/{comment_id} | Update the comment of an user for a given activity


# **create_activity**
> Activity create_activity(x_tenant, activity)

Create a new activity

An user can create a new activity in the platform. Activities represent events or tasks that users can participate in. Each activity may have a name, description, date and time.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.activity import Activity
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity = Activity(
        data={},
        id="id_example",
        time=dateutil_parser('1970-01-01T00:00:00.00Z'),
        reaction_count=[
            Reaction(
                id="id_example",
                count=1,
                users=[
                    User1(None),
                ],
            ),
        ],
    ) # Activity | 

    # example passing only required values which don't have defaults set
    try:
        # Create a new activity
        api_response = api_instance.create_activity(x_tenant, activity)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->create_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity** | [**Activity**](Activity.md)|  |

### Return type

[**Activity**](Activity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Activity Created |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_comment_for_activity**
> [CommentActivity] create_comment_for_activity(x_tenant, activity_id, comment)

Insert a user comment for a given activity

Create a new comment for an activity.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.comment_activity import CommentActivity
from graalsystems.model.comment import Comment
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 
    comment = Comment(
        comment="comment_example",
    ) # Comment | 

    # example passing only required values which don't have defaults set
    try:
        # Insert a user comment for a given activity
        api_response = api_instance.create_comment_for_activity(x_tenant, activity_id, comment)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->create_comment_for_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |
 **comment** | [**Comment**](Comment.md)|  |

### Return type

[**[CommentActivity]**](CommentActivity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_reaction_for_activity**
> [ReactionCount] create_reaction_for_activity(x_tenant, activity_id, reaction)

Insert the reaction of an user to a given activity

Insert a user's reaction to an activity. Each reaction increments the reaction counter and adds the user to the list of users who used that reaction.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.reaction import Reaction
from graalsystems.model.reaction_count import ReactionCount
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 
    reaction = Reaction(
        id="id_example",
        count=1,
        users=[
            User1(None),
        ],
    ) # Reaction | 

    # example passing only required values which don't have defaults set
    try:
        # Insert the reaction of an user to a given activity
        api_response = api_instance.create_reaction_for_activity(x_tenant, activity_id, reaction)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->create_reaction_for_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |
 **reaction** | [**Reaction**](Reaction.md)|  |

### Return type

[**[ReactionCount]**](ReactionCount.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Reaction successfully inserted |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_comment_from_activity**
> delete_comment_from_activity(x_tenant, activity_id, comment_id)

Delete the comment of an user for a given activity

Delete an user's comment to an activity.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 
    comment_id = "comment_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete the comment of an user for a given activity
        api_instance.delete_comment_from_activity(x_tenant, activity_id, comment_id)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->delete_comment_from_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |
 **comment_id** | **str**|  |

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
**204** | Comment successfully deleted |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_reaction_from_activity**
> delete_reaction_from_activity(x_tenant, activity_id, reaction_id)

Delete users' reactions for a given activity

Delete a user's reaction to an activity. Each reaction decrements (or deletes) the reaction counter and removes the user from the list of users who have used that reaction.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 
    reaction_id = "reaction_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Delete users' reactions for a given activity
        api_instance.delete_reaction_from_activity(x_tenant, activity_id, reaction_id)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->delete_reaction_from_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |
 **reaction_id** | **str**|  |

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
**204** | Reaction successfully deleted |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_activities_from_timeline**
> [Activity] get_activities_from_timeline(x_tenant, resource_id, resource_type)

Get all activities from timeline

Return timeline for specific resources.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.activity import Activity
from graalsystems.model.resource_type import ResourceType
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    resource_id = "resource_id_example" # str | 
    resource_type = ResourceType("catalog") # ResourceType | 
    x_cursor = "x-cursor_example" # str |  (optional)
    activity_type = "activity_type_example" # str |  (optional)
    batch_size = 10 # int |  (optional) if omitted the server will use the default value of 10
    aggregated = False # bool |  (optional) if omitted the server will use the default value of False

    # example passing only required values which don't have defaults set
    try:
        # Get all activities from timeline
        api_response = api_instance.get_activities_from_timeline(x_tenant, resource_id, resource_type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_activities_from_timeline: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get all activities from timeline
        api_response = api_instance.get_activities_from_timeline(x_tenant, resource_id, resource_type, x_cursor=x_cursor, activity_type=activity_type, batch_size=batch_size, aggregated=aggregated)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_activities_from_timeline: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **resource_id** | **str**|  |
 **resource_type** | **ResourceType**|  |
 **x_cursor** | **str**|  | [optional]
 **activity_type** | **str**|  | [optional]
 **batch_size** | **int**|  | [optional] if omitted the server will use the default value of 10
 **aggregated** | **bool**|  | [optional] if omitted the server will use the default value of False

### Return type

[**[Activity]**](Activity.md)

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

# **get_activities_summary**
> TimelineCountResponse get_activities_summary(x_tenant, resource_id, resource_type)

Get a count of all the activities for a resource

For each resource (within a defined tenant), retrieve the number of activities per day.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.timeline_count_response import TimelineCountResponse
from graalsystems.model.resource_type import ResourceType
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    resource_id = "resource_id_example" # str | 
    resource_type = ResourceType("catalog") # ResourceType | 
    year = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Get a count of all the activities for a resource
        api_response = api_instance.get_activities_summary(x_tenant, resource_id, resource_type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_activities_summary: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Get a count of all the activities for a resource
        api_response = api_instance.get_activities_summary(x_tenant, resource_id, resource_type, year=year)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_activities_summary: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **resource_id** | **str**|  |
 **resource_type** | **ResourceType**|  |
 **year** | **int**|  | [optional]

### Return type

[**TimelineCountResponse**](TimelineCountResponse.md)

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

# **get_comments_from_activity**
> [CommentActivity] get_comments_from_activity(x_tenant, activity_id)

Get all the comments for a given activity

For each activity (within a defined tenant), retrieve all the comment information. This information is made up of the comments of the activity with the users who wrote the comments.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.comment_activity import CommentActivity
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get all the comments for a given activity
        api_response = api_instance.get_comments_from_activity(x_tenant, activity_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_comments_from_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |

### Return type

[**[CommentActivity]**](CommentActivity.md)

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

# **get_creation_date**
> [int] get_creation_date(x_tenant, resource_id, resource_type)

Get a list of defined years for a resource

For each resource (within a defined tenant), get a list of defined years.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.resource_type import ResourceType
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    resource_id = "resource_id_example" # str | 
    resource_type = ResourceType("catalog") # ResourceType | 

    # example passing only required values which don't have defaults set
    try:
        # Get a list of defined years for a resource
        api_response = api_instance.get_creation_date(x_tenant, resource_id, resource_type)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_creation_date: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **resource_id** | **str**|  |
 **resource_type** | **ResourceType**|  |

### Return type

**[int]**

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

# **get_reactions_from_activity**
> [Reaction] get_reactions_from_activity(x_tenant, activity_id)

Get all user reactions for a given activity

For each activity (within a defined tenant), retrieve all the reaction information. This information is made up of the names of the reactions and the list of the users who have used the given reaction.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.reaction import Reaction
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Get all user reactions for a given activity
        api_response = api_instance.get_reactions_from_activity(x_tenant, activity_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->get_reactions_from_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |

### Return type

[**[Reaction]**](Reaction.md)

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

# **update_comment_for_activity**
> [CommentActivity] update_comment_for_activity(x_tenant, activity_id, comment_id)

Update the comment of an user for a given activity

Update an user's comment to an activity.

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import activity_api
from graalsystems.model.comment_activity import CommentActivity
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
    api_instance = activity_api.ActivityApi(api_client)
    x_tenant = "x-tenant_example" # str | 
    activity_id = "activity_id_example" # str | 
    comment_id = "comment_id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Update the comment of an user for a given activity
        api_response = api_instance.update_comment_for_activity(x_tenant, activity_id, comment_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling ActivityApi->update_comment_for_activity: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **activity_id** | **str**|  |
 **comment_id** | **str**|  |

### Return type

[**[CommentActivity]**](CommentActivity.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Successful Response |  -  |
**422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

