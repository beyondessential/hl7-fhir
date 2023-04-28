# Test cases for OMNI-Lab Integration

Please note that all this is test data and these are not real people or real procedures.
## Patients (patient*.fhir.json)
Example:
- Patient with Ethnicity: [**patient-w-ethnicity.fhir.json**](patient-w-ethnicity.fhir.json): Jack Bouma



| Active | PatientAdditionalData.title |       Patient.firstName   | Patient.lastName |       Patient.displayId   |     Patient.dateOfBirth    |   Patient.sex  | PatientAdditionalData.primaryContactNumber   | PatientAdditionalData.cityTown       | Patient.PatientAdditionalData.ethnicityId                                             |
|--------|-------|:----------------:|:----------------:|:----------:|:----------:|:------:|---------|---------------|------------------------------------------------------|
| True   | Mr    | Jack |  Bouma     | PVXC755243 | 1959-02-19 | Male   | null | null | ethnicity-ITaukei


## Service Requests (serviceRequest*.fhir.json)
Example:
- Patient Jack Johnson Requiring full Chem 7 tests: [**serviceRequest.panel.with-detail.fhir.json**](serviceRequest.panel.with-detail.fhir.json)
- Patient Jack Johnson requiring a follow up for Sodium Tests: [**serviceRequest.panel.one-test.fhir.json**](serviceRequest.panel.one-test.fhir.json) 


| Test Case                             | LabRequest.display_id |         Encounter.patient_id         | Patient.first_name | Patient.last_name | LabRequest.status | LabRequest.sampleTime     | LabRequest.priority | LabRequest.LabTestPanelRequest.LabTestPanel.externalCode | LabRequest.LabTestType.externalCode                                                                                        | LabRequest.requester.id              | LabRequest.requester.displayName | LabRequest.notePage[n].date | LabRequest.notePage[n].noteItem[m].content                                         | LabRequest.encounter.id              |
|---------------------------------------|:---------------------:|:------------------------------------:|:------------------:|:-----------------:|-------------------|---------------------------|---------------------|----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|--------------------------------------|----------------------------------|-----------------------------|------------------------------------------------------------------------------------|--------------------------------------|
| serviceRequest.panel.with-detail.fhir | VTBZWN                | 1a5deca5-6b4c-4d65-89b7-803f85ad4e64 | Jack               | Johnson           | RESULTS_PENDING   | 2022-02-07T13:28:17+10:00 | urgent              | B0030                                                    | ['B00010','B00020','B00030','B00040','B00060','B00070','B00150',<br>'B00050','B00090','B00080','B00110','B00980','B00990'] | 0735bc54-449f-498b-a919-8142deb6095c | Doctor Doctor                    | 2022-02-07T14:13:17+10:00   | This patient requires a full Chem 7 test <br>\n\n<br> Showing signs of high Sodium | bdebdc5e-753e-45f5-8fd0-01c49bd88f9e |
| serviceRequest.panel.one-test.fhir    | CTZZWN                | 1a5deca5-6b4c-4d65-89b7-803f85ad4e64 | Jack               | Johnson           | PUBLISHED         | 2022-07-12T13:28:17+10:00 | stat                | B0110                                                    | ['B00010']                                                                                                                 | d6fa9c10-93e4-44e8-9d9c-edfc8dccd3f9 | Doctor Seuss                     | 2023-01-21T06:23:03+10:00   | Checking sodium again \n\n <br>after other tests came back clear                   | edf593f8-37dc-4c59-8c82-98700b94f26f |


## Encounters (encounter.fhir.json)
Example:
- An encounter for John Yossarian in the clinical treatment room: [**serviceRequest.panel.with-detail.fhir.json**](serviceRequest.panel.with-detail.fhir.json)

| Test Case      | has Encounter been discharged? | Encounter.encounterType |         Encounter.patient.id         | Encounter.patient.firstName | Encounter.patient.lastName | Encounter.[Location]location.name | Encounter.[Location]<br>location.id |
|----------------|:------------------------------:|:-----------------------:|:------------------------------------:|:---------------------------:|----------------------------|-----------------------------------|-------------------------------------|
| encounter.fhir | Yes                            | CLINIC                  | 4c176418-86a4-48b5-9a6c-798b0b13a1e4 | John                        | Yossarian                  | Clinical Treatment Room           | clinicalTreatmentRoom               |
