# Test data for the Tamanu RISPACS integration

Please note that all this is test data and these are not real people or real procedures.


## Service Requests (serviceRequest*.fhir.json)
Example inventory:
- X-ray of left hand, left elbow and left forearm: [**serviceRequest.x-ray.fhir.json**](serviceRequest.x-ray.fhir.json)
- CT Scan of Sinuses + Brain post -IV contrast & CT Facial Bones post - IV contrast: [**serviceRequest.ct.fhir.json**](serviceRequest.ct.fhir.json) 

| Identifier |        Category        |    Subject   | Status | Priority | Code <br>(modality) |                                  Order Detail                                  |
|:----------:|:----------------------:|:------------:|:------:|:--------:|:-------------------:|:------------------------------------------------------------------------------:|
| VTBZWN     | 363679005<br>(Imaging) | Ryan Ashwood | active | urgent   | X-ray               | - Left Hand (2LHA)<br>- Left Elbow (2LEL)<br>- Left Forarm (2LFR)              |
| VRTDCN     | 363679005<br>(Imaging) | John Purcey  | active | routine  | CT Scan             | - CT Sinuses + Brain post -IV contrast<br>- CT Facial Bones post - IV contrast |

## Results of Service Requests (observation*.fhir.json)
Example inventory:
- Results to the X-ray of left hand, left elbow and left forearm: [**observation.x-ray.fhir.json**](observation.x-ray.fhir.json)
- Results to the CT Scan of Sinuses + Brain post -IV contrast & CT Facial Bones post - IV contrast: [**observation.ct.fhir.json**](observation.ct.fhir.json) 

|  Results of (basedOn)  | status | Accession Number |                                                    note                                                    |
|:----------------------:|:------:|:----------------:|:----------------------------------------------------------------------------------------------------------:|
| John Purcey's CT Scan  | final  | ABCD1234         | The clinician has discovered a buildup of brain fluid within the circumference of the right ocular cavity. |
| Ryan Ashwood's X-ray   | final  | WXYZ7890         | Hairline fracture along the left upper humerus                                                             |