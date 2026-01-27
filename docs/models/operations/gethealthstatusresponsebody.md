# GetHealthStatusResponseBody

API is healthy

## Example Usage

```typescript
import { GetHealthStatusResponseBody } from "petstore-sdk/models/operations";

let value: GetHealthStatusResponseBody = {
  healthy: false,
  apiVersion: "1.0.29",
};
```

## Fields

| Field              | Type               | Required           | Description        | Example            |
| ------------------ | ------------------ | ------------------ | ------------------ | ------------------ |
| `healthy`          | *boolean*          | :heavy_check_mark: | N/A                |                    |
| `apiVersion`       | *string*           | :heavy_check_mark: | N/A                | 1.0.29             |
| `uptime`           | *number*           | :heavy_minus_sign: | Uptime in seconds  |                    |