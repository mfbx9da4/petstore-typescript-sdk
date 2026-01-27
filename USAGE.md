<!-- Start SDK Example Usage [usage] -->
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
<!-- End SDK Example Usage [usage] -->