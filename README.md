# ![LOGO](logo.png) Application Insights Data Plane **flow**ground Connector

## Description

A generated **flow**ground connector for the Application Insights Data Plane API (version 2018-04-20).

Generated from: https://api.apis.guru/v2/specs/azure.com/applicationinsights-swagger/2018-04-20/swagger.json<br/>
Generated at: 2019-05-07T17:37:15+03:00

## API Description

This API exposes AI metric & event information and associated metadata

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Get OData metadata

> Gets OData EDMX metadata describing the event data model

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `apiVersion` - _required_ - Client API version.

### Execute OData query

> Executes an OData query for events

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `eventType` - _required_ - The type of events to query; either a standard event type (`traces`, `customEvents`, `pageViews`, `requests`, `dependencies`, `exceptions`, `availabilityResults`) or `$all` to query across all event types.
    Possible values: $all, traces, customEvents, pageViews, browserTimings, requests, dependencies, exceptions, availabilityResults, performanceCounters, customMetrics.
* `timespan` - _optional_ - Optional. The timespan over which to retrieve events. This is an ISO8601 time period value.  This timespan is applied in addition to any that are specified in the Odata expression.
* `$filter` - _optional_ - An expression used to filter the returned events
* `$search` - _optional_ - A free-text search expression to match for whether a particular event should be returned
* `$orderby` - _optional_ - A comma-separated list of properties with \"asc\" (the default) or \"desc\" to control the order of returned events
* `$select` - _optional_ - Limits the properties to just those requested on each returned event
* `$skip` - _optional_ - The number of items to skip over before returning events
* `$top` - _optional_ - The number of events to return
* `$format` - _optional_ - Format for the returned events
* `$count` - _optional_ - Request a count of matching items included with the returned events
* `$apply` - _optional_ - An expression used for aggregation over returned events
* `apiVersion` - _required_ - Client API version.

### Get an event

> Gets the data for a single event

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `eventType` - _required_ - The type of events to query; either a standard event type (`traces`, `customEvents`, `pageViews`, `requests`, `dependencies`, `exceptions`, `availabilityResults`) or `$all` to query across all event types.
    Possible values: $all, traces, customEvents, pageViews, browserTimings, requests, dependencies, exceptions, availabilityResults, performanceCounters, customMetrics.
* `timespan` - _optional_ - Optional. The timespan over which to retrieve events. This is an ISO8601 time period value.  This timespan is applied in addition to any that are specified in the Odata expression.
* `eventId` - _required_ - ID of event.
* `apiVersion` - _required_ - Client API version.

### Retrieve metric metadata

> Gets metadata describing the available metrics

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `apiVersion` - _required_ - Client API version.

### Retrieve metric data

> Gets metric values for a single metric

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `metricId` - _required_ - ID of the metric. This is either a standard AI metric, or an application-specific custom metric.
    Possible values: requests/count, requests/duration, requests/failed, users/count, users/authenticated, pageViews/count, pageViews/duration, client/processingDuration, client/receiveDuration, client/networkDuration, client/sendDuration, client/totalDuration, dependencies/count, dependencies/failed, dependencies/duration, exceptions/count, exceptions/browser, exceptions/server, sessions/count, performanceCounters/requestExecutionTime, performanceCounters/requestsPerSecond, performanceCounters/requestsInQueue, performanceCounters/memoryAvailableBytes, performanceCounters/exceptionsPerSecond, performanceCounters/processCpuPercentage, performanceCounters/processIOBytesPerSecond, performanceCounters/processPrivateBytes, performanceCounters/processorCpuPercentage, availabilityResults/availabilityPercentage, availabilityResults/duration, billing/telemetryCount, customEvents/count.
* `timespan` - _optional_ - The timespan over which to retrieve metric values. This is an ISO8601 time period value. If timespan is omitted, a default time range of `PT12H` ("last 12 hours") is used. The actual timespan that is queried may be adjusted by the server based. In all cases, the actual time span used for the query is included in the response.
* `interval` - _optional_ - The time interval to use when retrieving metric values. This is an ISO8601 duration. If interval is omitted, the metric value is aggregated across the entire timespan. If interval is supplied, the server may adjust the interval to a more appropriate size based on the timespan used for the query. In all cases, the actual interval used for the query is included in the response.
* `aggregation` - _optional_ - The aggregation to use when computing the metric values. To retrieve more than one aggregation at a time, separate them with a comma. If no aggregation is specified, then the default aggregation for the metric is used.
* `segment` - _optional_ - The name of the dimension to segment the metric values by. This dimension must be applicable to the metric you are retrieving. To segment by more than one dimension at a time, separate them with a comma (,). In this case, the metric data will be segmented in the order the dimensions are listed in the parameter.
* `top` - _optional_ - The number of segments to return.  This value is only valid when segment is specified.
* `orderby` - _optional_ - The aggregation function and direction to sort the segments by.  This value is only valid when segment is specified.
* `filter` - _optional_ - An expression used to filter the results.  This value should be a valid OData filter expression where the keys of each clause should be applicable dimensions for the metric you are retrieving.
* `apiVersion` - _required_ - Client API version.

### Execute an Analytics query

> Executes an Analytics query for data

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `query` - _required_ - The Analytics query. Learn more about the [Analytics query syntax](https://azure.microsoft.com/documentation/articles/app-insights-analytics-reference/)
* `timespan` - _optional_ - Optional. The timespan over which to query data. This is an ISO8601 time period value.  This timespan is applied in addition to any that are specified in the query expression.
* `apiVersion` - _required_ - Client API version.

### Execute an Analytics query

> Executes an Analytics query for data. [Here](https://dev.applicationinsights.io/documentation/Using-the-API/Query) is an example for using POST with an Analytics query.

#### Input Parameters
* `subscriptionId` - _required_ - Gets subscription credentials which uniquely identify Microsoft Azure subscription. The subscription ID forms part of the URI for every service call.
* `resourceGroupName` - _required_ - The name of the resource group to get. The name is case insensitive.
* `applicationName` - _required_ - Name of the Application Insights application.
* `apiVersion` - _required_ - Client API version.

## License

**flow**ground :- Telekom iPaaS / azure-com-applicationinsights-swagger-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
