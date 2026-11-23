# MatricesApi

All URIs are relative to *https://api.myptv.com/matrixrouting-osm/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**calculateMatrix**](MatricesApi.md#calculatematrix) | **POST** /matrices |  |
| [**cancelMatrixCalculation**](MatricesApi.md#cancelmatrixcalculation) | **DELETE** /matrices/{id} |  |
| [**getMatrix**](MatricesApi.md#getmatrix) | **GET** /matrices/{id} |  |
| [**getStatus**](MatricesApi.md#getstatus) | **GET** /matrices/status/{id} |  |
| [**startMatrixCalculation**](MatricesApi.md#startmatrixcalculation) | **POST** /matrices/async |  |



## calculateMatrix

> MatrixResponse calculateMatrix(locations, profile, results, options)



Creates a matrix by calculating distances and travel times between given origins and destinations.

### Example

```ts
import {
  Configuration,
  MatricesApi,
} from '';
import type { CalculateMatrixRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new MatricesApi(config);

  const body = {
    // Locations
    locations: ...,
    // string | A profile defines a vehicle by a set of attributes, matching typical transport situations. It must be the name of one of the [predefined profiles](../data-api/concepts/osm-profiles) such as _EUR_OSM_CAR_. (optional)
    profile: profile_example,
    // Array<Results> | Comma-separated list that defines which results will be returned.  * `DISTANCES`     Response includes information about the distances between start and destination locations.  * `TRAVEL_TIMES`     Response includes information about the travel times between start and destination locations.  * `DIRECT_DISTANCE_FLAGS`     Response includes flags describing if relations have been estimated by direct distance. (optional)
    results: ["TRAVEL_TIMES"],
    // Options | Matrix Routing-relevant options like the average speed for direct distance calculations. Use array notation like `options[averageSpeed]=60` to set options. (optional)
    options: ...,
  } satisfies CalculateMatrixRequest;

  try {
    const data = await api.calculateMatrix(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **locations** | [Locations](Locations.md) |  | |
| **profile** | `string` | A profile defines a vehicle by a set of attributes, matching typical transport situations. It must be the name of one of the [predefined profiles](../data-api/concepts/osm-profiles) such as _EUR_OSM_CAR_. | [Optional] [Defaults to `&#39;EUR_OSM_CAR&#39;`] |
| **results** | `Array<Results>` | Comma-separated list that defines which results will be returned.  * &#x60;DISTANCES&#x60;     Response includes information about the distances between start and destination locations.  * &#x60;TRAVEL_TIMES&#x60;     Response includes information about the travel times between start and destination locations.  * &#x60;DIRECT_DISTANCE_FLAGS&#x60;     Response includes flags describing if relations have been estimated by direct distance. | [Optional] |
| **options** | [](.md) | Matrix Routing-relevant options like the average speed for direct distance calculations. Use array notation like &#x60;options[averageSpeed]&#x3D;60&#x60; to set options. | [Optional] [Defaults to `undefined`] |

### Return type

[**MatrixResponse**](MatrixResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## cancelMatrixCalculation

> cancelMatrixCalculation(id)



Cancels a matrix calculation and deletes the calculated results specified by its ID. Results already calculated cannot be requested by its ID, anymore.

### Example

```ts
import {
  Configuration,
  MatricesApi,
} from '';
import type { CancelMatrixCalculationRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new MatricesApi(config);

  const body = {
    // string | The ID of a matrix calculation operation.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies CancelMatrixCalculationRequest;

  try {
    const data = await api.cancelMatrixCalculation(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The ID of a matrix calculation operation. | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMatrix

> MatrixResponse getMatrix(id)



Requests the results of a matrix calculation operation.

### Example

```ts
import {
  Configuration,
  MatricesApi,
} from '';
import type { GetMatrixRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new MatricesApi(config);

  const body = {
    // string | The ID of a matrix calculation operation.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetMatrixRequest;

  try {
    const data = await api.getMatrix(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The ID of a matrix calculation operation. | [Defaults to `undefined`] |

### Return type

[**MatrixResponse**](MatrixResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getStatus

> StatusResponse getStatus(id, maximumPollingPeriod)



Requests the status of a matrix calculation.

### Example

```ts
import {
  Configuration,
  MatricesApi,
} from '';
import type { GetStatusRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new MatricesApi(config);

  const body = {
    // string | The ID of a matrix calculation operation.
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // number | If the calculation is still running, this operation will be blocked and will not return before this period [ms] expires. If the calculation is completed, it will return immediately.  The default of 0 ms will cause the operation to return immediately in any case. Use a value > 0 to implement long polling to reduce the number of requests. See the [tutorial](https://developer.myptv.com/en/resources/tutorials/general/how-use-asynchronous-requests-ptv-developer-apis) on asynchronous requests for details.  (optional)
    maximumPollingPeriod: 56,
  } satisfies GetStatusRequest;

  try {
    const data = await api.getStatus(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **id** | `string` | The ID of a matrix calculation operation. | [Defaults to `undefined`] |
| **maximumPollingPeriod** | `number` | If the calculation is still running, this operation will be blocked and will not return before this period [ms] expires. If the calculation is completed, it will return immediately.  The default of 0 ms will cause the operation to return immediately in any case. Use a value &gt; 0 to implement long polling to reduce the number of requests. See the [tutorial](https://developer.myptv.com/en/resources/tutorials/general/how-use-asynchronous-requests-ptv-developer-apis) on asynchronous requests for details.  | [Optional] [Defaults to `0`] |

### Return type

[**StatusResponse**](StatusResponse.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## startMatrixCalculation

> MatrixIdentifier startMatrixCalculation(locations, profile, results, options)



Creates a matrix asynchronously by calculating distances and travel times between given origins and destinations.

### Example

```ts
import {
  Configuration,
  MatricesApi,
} from '';
import type { StartMatrixCalculationRequest } from '';

async function example() {
  console.log("🚀 Testing  SDK...");
  const config = new Configuration({ 
    // To configure API key authorization: apiKeyAuth
    apiKey: "YOUR API KEY",
  });
  const api = new MatricesApi(config);

  const body = {
    // Locations
    locations: ...,
    // string | A profile defines a vehicle by a set of attributes, matching typical transport situations. It must be the name of one of the [predefined profiles](../data-api/concepts/osm-profiles) such as _EUR_OSM_CAR_. (optional)
    profile: profile_example,
    // Array<Results> | Comma-separated list that defines which results will be returned.  * `DISTANCES`     Response includes information about the distances between start and destination locations.  * `TRAVEL_TIMES`     Response includes information about the travel times between start and destination locations.  * `DIRECT_DISTANCE_FLAGS`     Response includes flags describing if relations have been estimated by direct distance. (optional)
    results: ["TRAVEL_TIMES"],
    // Options | Matrix Routing-relevant options like the average speed for direct distance calculations. Use array notation like `options[averageSpeed]=60` to set options. (optional)
    options: ...,
  } satisfies StartMatrixCalculationRequest;

  try {
    const data = await api.startMatrixCalculation(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **locations** | [Locations](Locations.md) |  | |
| **profile** | `string` | A profile defines a vehicle by a set of attributes, matching typical transport situations. It must be the name of one of the [predefined profiles](../data-api/concepts/osm-profiles) such as _EUR_OSM_CAR_. | [Optional] [Defaults to `&#39;EUR_OSM_CAR&#39;`] |
| **results** | `Array<Results>` | Comma-separated list that defines which results will be returned.  * &#x60;DISTANCES&#x60;     Response includes information about the distances between start and destination locations.  * &#x60;TRAVEL_TIMES&#x60;     Response includes information about the travel times between start and destination locations.  * &#x60;DIRECT_DISTANCE_FLAGS&#x60;     Response includes flags describing if relations have been estimated by direct distance. | [Optional] |
| **options** | [](.md) | Matrix Routing-relevant options like the average speed for direct distance calculations. Use array notation like &#x60;options[averageSpeed]&#x3D;60&#x60; to set options. | [Optional] [Defaults to `undefined`] |

### Return type

[**MatrixIdentifier**](MatrixIdentifier.md)

### Authorization

[apiKeyAuth](../README.md#apiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Response on success. |  -  |
| **0** | Response on failure. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

