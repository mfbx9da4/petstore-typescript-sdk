# Status

pet status in the store

## Example Usage

```typescript
import { Status } from "petstore-sdk/models/components";

let value: Status = "pending";
```

## Values

This is an open enum. Unrecognized values will be captured as the `Unrecognized<string>` branded type.

```typescript
"available" | "pending" | "sold" | Unrecognized<string>
```