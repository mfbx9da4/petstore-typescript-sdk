# FindPetsByTagsRequest

## Example Usage

```typescript
import { FindPetsByTagsRequest } from "petstore-sdk/models/operations";

let value: FindPetsByTagsRequest = {
  tags: [
    "<value 1>",
    "<value 2>",
    "<value 3>",
  ],
};
```

## Fields

| Field              | Type               | Required           | Description        |
| ------------------ | ------------------ | ------------------ | ------------------ |
| `tags`             | *string*[]         | :heavy_check_mark: | Tags to filter by  |