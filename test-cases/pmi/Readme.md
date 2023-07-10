# Test data for the Tamanu PMI integration
Please note that all this is test data and these are not real people.

## Patients (patient*.fhir.json)
Example patients:
- Basic Patient: [**patient1.fhir.json**](patient1.fhir.json): Ryan Ashwood
    - Has had his NHN entered and so his Tamanu Id has been demoted to secondary
- Merged Patient: [**patient.merged.fhir.json**](patient.merged.fhir.json): Johnothan Purcey
    -  Has had his NHN entered and so his Tamanu Id has been demoted to secondary
- Mergee Patient: [**patient.mergee.fhir.json**](patient.mergee.fhir.json): John Purcey
     - Has no NHN entered so still using Tamanu Id as official
- Mergee Second Removed Patient: [**patient.mergedBelow.fhir.json**](patient.mergedBelow.fhir.json): Jane Purcey
    - Has no NHN entered so still using Tamanu Id as official


The flow is this:
- Jane      --merged into--> Johnothan
- Johnothan --merged into--> John



| Active | Title |       Name       | Tamanu Id  |   External Id (NHN)     |     DoB    |   Sex  | Phone   | Address       | Merged?                                              |
|--------|-------|:----------------:|:----------:|:-----------------------:|:----------:|:------:|---------|---------------|------------------------------------------------------|
| True   | Mr    | Ryan Ashwood     | UTOE353558 |        246801357        | 1968-10-28 | Male   | 7018569 | City: Lautoka | NULL                                                 |
| False  | NULL  | Johnothan Purcey | QLKE835509 |        753124680        | 1980-04-27 | Male   | 9639954 | NULL          | Replaced by John Purcey<br>See also Jane Purcey      |
| True   | Mr    | John Purcey      | WVNF173345 |            null         | 1980-04-27 | Male   | 8041123 | City: Nadi    | Replaces Johnothan Purcey<br>Replaces Jane Purcey    |
| False  | NULL  | Jane Purcey      | ZAVN19458  |            null         | 1983-09-03 | Female | 8682308 | NULL          | Replaced by John Purcey<br>See also Johnothan Purcey |
