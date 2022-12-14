# Test data for the Tamanu RISPACS integration

Please note that all this is test data and these are not real people or real procedures.
## Patients (patient*.fhir.json)
Example inventory:
- Basic Patient: [**patient1.fhir.json**](patient1.fhir.json): Ryan Ashwood
- Merged Patient: [**patient.merged.fhir.json**](patient.merged.fhir.json): Johnothan Purcey
- Mergee Patient: [**patient.mergee.fhir.json**](patient.mergee.fhir.json): John Purcey
- Mergee Second Removed Patient: [**patient.mergedBelow.fhir.json**](patient.mergedBelow.fhir.json): Jane Purcey


The flow is this:
- Jane      --merged into--> Johnothan
- Johnothan --merged into--> John



| Active | Title |       Name       |   VRS Id   |     DoB    |   Sex  | Phone   | Address       | Merged?                                              |
|--------|-------|:----------------:|:----------:|:----------:|:------:|---------|---------------|------------------------------------------------------|
| True   | Mr    | Ryan Ashwood     | UTOE353558 | 1968-10-28 | Male   | 7018569 | City: Lautoka | NULL                                                 |
| False  | NULL  | Johnothan Purcey | QLKE835509 | 1980-04-27 | Male   | 9639954 | NULL          | Replaced by John Purcey<br>See also Jane Purcey      |
| True   | Mr    | John Purcey      | WVNF173345 | 1980-04-27 | Male   | 8041123 | City: Nadi    | Replaces Johnothan Purcey<br>Replaces Jane Purcey    |
| False  | NULL  | Jane Purcey      | ZAVN19458  | 1983-09-03 | Female | 8682308 | NULL          | Replaced by John Purcey<br>See also Johnothan Purcey |


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