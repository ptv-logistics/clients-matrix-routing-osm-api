
# MatrixResponse


## Properties

Name | Type
------------ | -------------
`percentageOfDirectDistanceRelations` | number
`distances` | Array&lt;number&gt;
`travelTimes` | Array&lt;number&gt;
`directDistanceFlags` | Array&lt;boolean&gt;
`warnings` | [Array&lt;Warning&gt;](Warning.md)

## Example

```typescript
import type { MatrixResponse } from ''

// TODO: Update the object below with actual values
const example = {
  "percentageOfDirectDistanceRelations": null,
  "distances": null,
  "travelTimes": null,
  "directDistanceFlags": null,
  "warnings": null,
} satisfies MatrixResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MatrixResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


