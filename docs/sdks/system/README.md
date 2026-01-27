# System

## Overview

### Available Operations

* [healthCheck](#healthcheck) - Health check endpoint.

## healthCheck

Returns the health status of the API.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="healthCheck" method="get" path="/health" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const result = await petstore.system.healthCheck();

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { systemHealthCheck } from "petstore-sdk/funcs/systemHealthCheck.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const res = await systemHealthCheck(petstore);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("systemHealthCheck failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.HealthCheckResponseBody](../../models/operations/healthcheckresponsebody.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |