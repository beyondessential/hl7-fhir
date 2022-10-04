## Patients (patient*.fhir.json)
Here is an inventory of files:
- Basic Patient: **patient1.fhir.json**: Ryan Ashwood
- Merged Patient: **patient.merged.fhir.json**: Johnothan Purcey
- Mergee Patient: **patient.mergee.fhir.json**: John Purcey
- Mergee Second Removed Patient: **patient.mergedBelow.fhir.json**: Jane Purcey


The flow is this:
- Jane      --merged into--> Johnothan
- Johnothan --merged into--> John



| Active | Title |       Name       |   VRS Id   | RTA    |     DoB    |   Sex  | Phone   | Address       | Merged?                                              |
|--------|-------|:----------------:|:----------:|--------|:----------:|:------:|---------|---------------|------------------------------------------------------|
| True   | Mr    | Ryan Ashwood     | UTOE353558 | NULL   | 1968-10-28 | Male   | 7018569 | City: Lautoka | NULL                                                 |
| False  | Mr    | Johnothan Purcey | QLKE835509 | 656985 | 1980-04-27 | Male   | 9639954 | City: Suva    | Replaced by John Purcey<br>See also Jane Purcey      |
| True   | Mr    | John Purcey      | WVNF173345 | NULL   | 1980-04-27 | Male   | 8041123 | City: Nadi    | Replaces Johnothan Purcey<br>Replaces Jane Purcey    |
| False  | Miss  | Jane Purcey      | ZAVN19458  | NULL   | 1983-09-03 | Female | 8682308 | City: Lautoka | Replaced by John Purcey<br>See also Johnothan Purcey |


## Service Requests

