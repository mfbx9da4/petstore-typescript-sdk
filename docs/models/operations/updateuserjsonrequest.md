# UpdateUserJsonRequest

## Example Usage

```typescript
import { UpdateUserJsonRequest } from "petstore-sdk/models/operations";

let value: UpdateUserJsonRequest = {
  username: "Skye_Shanahan-Dicki61",
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `username`                                         | *string*                                           | :heavy_check_mark:                                 | name that need to be deleted                       |
| `body`                                             | [components.User](../../models/components/user.md) | :heavy_minus_sign:                                 | Update an existent user in the store               |