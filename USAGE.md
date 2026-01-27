<!-- Start SDK Example Usage [usage] -->
```typescript
import { Petstore } from "petstore-sdk";

const petstore = new Petstore({
  serverURL: "https://api.example.com",
  petstoreAuth: "<YOUR_PETSTORE_AUTH_HERE>",
});

async function run() {
  const result = await petstore.pet.updatePetJson({
    id: 10,
    name: "doggie",
    category: {
      id: 1,
      name: "Dogs",
    },
    photoUrls: [
      "<value 1>",
    ],
  });

  console.log(result);
}

run();

```
<!-- End SDK Example Usage [usage] -->