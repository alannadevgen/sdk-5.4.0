# graalsystems.FirewallRulesApi

All URIs are relative to *http://localhost*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_firewall_rule**](FirewallRulesApi.md#create_firewall_rule) | **POST** /firewall/rules | Create a firewall rule


# **create_firewall_rule**
> FirewallRule create_firewall_rule(x_tenant, firewall_rule)

Create a firewall rule

### Example

* OAuth Authentication (internal):

```python
import time
import graalsystems
from graalsystems.api import firewall_rules_api
from graalsystems.model.firewall_rule import FirewallRule
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
    api_instance = firewall_rules_api.FirewallRulesApi(api_client)
    x_tenant = "X-Tenant_example" # str | 
    firewall_rule = FirewallRule(
        id="id_example",
        description="description_example",
        created=dateutil_parser('1970-01-01T00:00:00.00Z'),
        updated=dateutil_parser('1970-01-01T00:00:00.00Z'),
        type="ingress",
        protocol="protocol_example",
        ports="ports_example",
        source="source_example",
        target="target_example",
        metadata={
            "key": {},
        },
    ) # FirewallRule | The firewall rule to be created

    # example passing only required values which don't have defaults set
    try:
        # Create a firewall rule
        api_response = api_instance.create_firewall_rule(x_tenant, firewall_rule)
        pprint(api_response)
    except graalsystems.ApiException as e:
        print("Exception when calling FirewallRulesApi->create_firewall_rule: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **x_tenant** | **str**|  |
 **firewall_rule** | [**FirewallRule**](FirewallRule.md)| The firewall rule to be created |

### Return type

[**FirewallRule**](FirewallRule.md)

### Authorization

[internal](../README.md#internal)

### HTTP request headers

 - **Content-Type**: application/vnd.graal.systems.v1.firewall.rule+json
 - **Accept**: application/vnd.graal.systems.v1.firewall.rule+json, application/vnd.graal.systems.v1.error+json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful operation |  -  |
**400** | Bad Request |  -  |
**404** | Job not found |  -  |
**405** | Method Not Allowed |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

