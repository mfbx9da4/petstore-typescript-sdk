# Store

## Overview

Access to Petstore orders

Find out more about our store
<https://swagger.io>

### Available Operations

* [getInventory](#getinventory) - Returns pet inventories by status.
* [placeOrderJson](#placeorderjson) - Place an order for a pet.
* [placeOrderRaw](#placeorderraw) - Place an order for a pet.
* [placeOrderForm](#placeorderform) - Place an order for a pet.
* [getOrderById](#getorderbyid) - Find purchase order by ID.
* [deleteOrder](#deleteorder) - Delete purchase order by identifier.

## getInventory

Returns a map of status codes to quantities.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getInventory" method="get" path="/store/inventory" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
});

async function run() {
  const result = await petstore.store.getInventory({
    apiKey: "<YOUR_API_KEY_HERE>",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { storeGetInventory } from "petstore-sdk/funcs/storeGetInventory.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
});

async function run() {
  const res = await storeGetInventory(petstore, {
    apiKey: "<YOUR_API_KEY_HERE>",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storeGetInventory failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `security`                                                                                                                                                                     | [operations.GetInventorySecurity](../../models/operations/getinventorysecurity.md)                                                                                             | :heavy_check_mark:                                                                                                                                                             | The security requirements to use for the request.                                                                                                                              |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[{ [k: string]: number }](../../models/.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |

## placeOrderJson

Place a new order in the store.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="placeOrder_json" method="post" path="/store/order" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const result = await petstore.store.placeOrderJson({
    id: 10,
    petId: 198772,
    quantity: 7,
    status: "approved",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { storePlaceOrderJson } from "petstore-sdk/funcs/storePlaceOrderJson.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const res = await storePlaceOrderJson(petstore, {
    id: 10,
    petId: 198772,
    quantity: 7,
    status: "approved",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storePlaceOrderJson failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [components.Order](../../models/components/order.md)                                                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Order](../../models/components/order.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |

## placeOrderRaw

Place a new order in the store.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="placeOrder_raw" method="post" path="/store/order" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const result = await petstore.store.placeOrderRaw(bytesToStream(new TextEncoder().encode("{\"id\":10,\"petId\":198772,\"quantity\":7,\"status\":\"approved\"}")));

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { storePlaceOrderRaw } from "petstore-sdk/funcs/storePlaceOrderRaw.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const res = await storePlaceOrderRaw(petstore, bytesToStream(new TextEncoder().encode("{\"id\":10,\"petId\":198772,\"quantity\":7,\"status\":\"approved\"}")));
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storePlaceOrderRaw failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [ReadableStream<Uint8Array>](../../models/order.md)                                                                                                                            | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Order](../../models/components/order.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |

## placeOrderForm

Place a new order in the store.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="placeOrder_form" method="post" path="/store/order" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const result = await petstore.store.placeOrderForm({
    id: 10,
    petId: 198772,
    quantity: 7,
    status: "approved",
  });

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { storePlaceOrderForm } from "petstore-sdk/funcs/storePlaceOrderForm.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const res = await storePlaceOrderForm(petstore, {
    id: 10,
    petId: 198772,
    quantity: 7,
    status: "approved",
  });
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storePlaceOrderForm failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `request`                                                                                                                                                                      | [components.Order](../../models/components/order.md)                                                                                                                           | :heavy_check_mark:                                                                                                                                                             | The request object to use for the request.                                                                                                                                     |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[components.Order](../../models/components/order.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |

## getOrderById

For valid response try integer IDs with value <= 5 or > 10. Other values will generate exceptions.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="getOrderById" method="get" path="/store/order/{orderId}" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const result = await petstore.store.getOrderById(728529);

  console.log(result);
}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { storeGetOrderById } from "petstore-sdk/funcs/storeGetOrderById.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const res = await storeGetOrderById(petstore, 728529);
  if (res.ok) {
    const { value: result } = res;
    console.log(result);
  } else {
    console.log("storeGetOrderById failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `orderId`                                                                                                                                                                      | *number*                                                                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | ID of order that needs to be fetched                                                                                                                                           |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<[operations.GetOrderByIdResponse](../../models/operations/getorderbyidresponse.md)\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |

## deleteOrder

For valid response try integer IDs with value < 1000. Anything above 1000 or non-integers will generate API errors.

### Example Usage

<!-- UsageSnippet language="typescript" operationID="deleteOrder" method="delete" path="/store/order/{orderId}" -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  await petstore.store.deleteOrder(690575);


}

run();
```

### Standalone function

The standalone function version of this method:

```typescript
import { PetstoreCore } from "petstore-sdk/core.js";
import { storeDeleteOrder } from "petstore-sdk/funcs/storeDeleteOrder.js";

// Use `PetstoreCore` for best tree-shaking performance.
// You can create one instance of it to use across an application.
const petstore = new PetstoreCore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const res = await storeDeleteOrder(petstore, 690575);
  if (res.ok) {
    const { value: result } = res;
    
  } else {
    console.log("storeDeleteOrder failed:", res.error);
  }
}

run();
```

### Parameters

| Parameter                                                                                                                                                                      | Type                                                                                                                                                                           | Required                                                                                                                                                                       | Description                                                                                                                                                                    |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `orderId`                                                                                                                                                                      | *number*                                                                                                                                                                       | :heavy_check_mark:                                                                                                                                                             | ID of the order that needs to be deleted                                                                                                                                       |
| `options`                                                                                                                                                                      | RequestOptions                                                                                                                                                                 | :heavy_minus_sign:                                                                                                                                                             | Used to set various options for making HTTP requests.                                                                                                                          |
| `options.fetchOptions`                                                                                                                                                         | [RequestInit](https://developer.mozilla.org/en-US/docs/Web/API/Request/Request#options)                                                                                        | :heavy_minus_sign:                                                                                                                                                             | Options that are passed to the underlying HTTP request. This can be used to inject extra headers for examples. All `Request` options, except `method` and `body`, are allowed. |
| `options.retries`                                                                                                                                                              | [RetryConfig](../../lib/utils/retryconfig.md)                                                                                                                                  | :heavy_minus_sign:                                                                                                                                                             | Enables retrying HTTP requests under certain failure conditions.                                                                                                               |

### Response

**Promise\<void\>**

### Errors

| Error Type                  | Status Code                 | Content Type                |
| --------------------------- | --------------------------- | --------------------------- |
| errors.PetstoreDefaultError | 4XX, 5XX                    | \*/\*                       |