# Test data for the Tamanu PACS integration
Purpose: To receive a url for an external viewer

Method: POST
Location: `https://[base_url]`

## Bundled Results (bundle.results*.fhir.json)
Here Imaging Study is bundled with an Endpoint  
Example Bundled results:
- Basic Results with link to viewer: [**bundle.results.fhir.json**](bundle.results.fhir.json): 

Variables are:

| ImagingStudy(Status) | ImagingStudy(Identifier) |       ImagingStudy(endpointId)       |  Endpoint(id)  |   Endpoint(address)     |
|--------|-------|:----------------:|:----------:|:-----------------------:|
| final   | ABCD1234    | 00a2c05b-f980-48a8-aec0-3d4fe0122f324     | 00a2c05b-f980-48a8-aec0-3d4fe0122f324 |        https://voyager.io/viewer/ABCD1234         
