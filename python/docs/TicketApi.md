# graalsystems.TicketApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_ticket**](TicketApi.md#create_ticket) | **POST** /tickets | Create a ticket
[**delete_ticket_by_id**](TicketApi.md#delete_ticket_by_id) | **DELETE** /tickets/{ticketId} | Delete a ticket by its id
[**execute_action1**](TicketApi.md#execute_action1) | **POST** /tickets/{ticketId}/actions | Execute an action
[**find_ticket_by_id**](TicketApi.md#find_ticket_by_id) | **GET** /tickets/{ticketId} | Find ticket by Id
[**find_tickets**](TicketApi.md#find_tickets) | **GET** /tickets | Retrieve all tickets
[**update_ticket**](TicketApi.md#update_ticket) | **PATCH** /tickets/{ticketId} | Update a ticket


# **create_ticket**
> Ticket create_ticket(ticket)

Create a ticket

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import ticket_api
from graalsystems.model.ticket import Ticket
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
    api_instance = ticket_api.TicketApi(api_client)
    ticket = Ticket(
        id="id_example",
        tenant_id="tenant_id_example",
        status="OPEN",
        title="title_example",
        description="description_example",
        details=Details(),
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        metadata={
            "key": {},
        },
    ) # Ticket | The ticket to be created
    x_tenant = "X-Tenant_example" # str |  (optional)
    challenge = "challenge_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    try:
        # Create a ticket
        api_response = api_instance.create_ticket(ticket)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->create_ticket: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        # Create a ticket
        api_response = api_instance.create_ticket(ticket, x_tenant=x_tenant, challenge=challenge)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->create_ticket: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ticket** | [**Ticket**](Ticket.md)| The ticket to be created |
 **x_tenant** | **str**|  | [optional]
 **challenge** | **str**|  | [optional]

### Return type

[**Ticket**](Ticket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.ticket+json
 - **Accept**: application/vnd.graal.systems.v1.ticket+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_ticket_by_id**
> delete_ticket_by_id(x_tenant, ticket_id)

Delete a ticket by its id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import ticket_api
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
    api_instance = ticket_api.TicketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    ticket_id = "ticketId_example" # str | Id of the Ticket

    # example passing only required values which don't have defaults set
    try:
        # Delete a ticket by its id
        api_instance.delete_ticket_by_id(x_tenant, ticket_id)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->delete_ticket_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **ticket_id** | **str**| Id of the Ticket |

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
**404** | Ticket not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **execute_action1**
> execute_action1(x_tenant, ticket_id, action)

Execute an action

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import ticket_api
from graalsystems.model.action import Action
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
    api_instance = ticket_api.TicketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    ticket_id = "ticketId_example" # str | Id of the ticket
    action = Action(
        comment="comment_example",
        type="type_example",
        metadata={
            "key": {},
        },
    ) # Action | 

    # example passing only required values which don't have defaults set
    try:
        # Execute an action
        api_instance.execute_action1(x_tenant, ticket_id, action)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->execute_action1: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **ticket_id** | **str**| Id of the ticket |
 **action** | [**Action**](Action.md)|  |

### Return type

void (empty response body)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.action+json
 - **Accept**: Not defined


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_ticket_by_id**
> Ticket find_ticket_by_id(x_tenant, ticket_id)

Find ticket by Id

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import ticket_api
from graalsystems.model.ticket import Ticket
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
    api_instance = ticket_api.TicketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    ticket_id = "ticketId_example" # str | Id of the ticket

    # example passing only required values which don't have defaults set
    try:
        # Find ticket by Id
        api_response = api_instance.find_ticket_by_id(x_tenant, ticket_id)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->find_ticket_by_id: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **ticket_id** | **str**| Id of the ticket |

### Return type

[**Ticket**](Ticket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.ticket+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Ticket not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_tickets**
> [Ticket] find_tickets(x_tenant)

Retrieve all tickets

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import ticket_api
from graalsystems.model.ticket import Ticket
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
    api_instance = ticket_api.TicketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        # Retrieve all tickets
        api_response = api_instance.find_tickets(x_tenant)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->find_tickets: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |

### Return type

[**[Ticket]**](Ticket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/vnd.graal.systems.v1.ticket+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_ticket**
> Ticket update_ticket(x_tenant, ticket_id, patch)

Update a ticket

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import ticket_api
from graalsystems.model.ticket import Ticket
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
    api_instance = ticket_api.TicketApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    ticket_id = "ticketId_example" # str | Id of the Ticket
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
        # Update a ticket
        api_response = api_instance.update_ticket(x_tenant, ticket_id, patch)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling TicketApi->update_ticket: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **ticket_id** | **str**| Id of the Ticket |
 **patch** | [**[Patch]**](Patch.md)| The patch |

### Return type

[**Ticket**](Ticket.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/json-patch+json;charset=UTF-8
 - **Accept**: application/vnd.graal.systems.v1.ticket+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Ticket not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

