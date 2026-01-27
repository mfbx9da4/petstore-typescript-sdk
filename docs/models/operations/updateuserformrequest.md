# UpdateUserFormRequest

## Example Usage

```typescript
import { UpdateUserFormRequest } from "petstore-sdk/models/operations";

let value: UpdateUserFormRequest = {
  username: "Jairo_Glover19",
};
```

## Fields

| Field                                              | Type                                               | Required                                           | Description                                        |
| -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- | -------------------------------------------------- |
| `username`                                         | *string*                                           | :heavy_check_mark:                                 | name that need to be deleted                       |
| `body`                                             | [components.User](../../models/components/user.md) | :heavy_minus_sign:                                 | Update an existent user in the store               |