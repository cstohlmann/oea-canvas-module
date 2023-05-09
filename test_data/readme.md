# Test data

This module includes artificially generated data which matches the format of [Canvas API Resources](https://canvas.instructure.com/doc/api/all_resources.html).
- x tables formatted in JSONs, as described in the Canvas data dictionary. Assets can be adapted to integrate ingestion/refinement functionality for more, different or less tables.

<strong>Note:</strong> This module contains one set of test data - for mock higher education data. This module does not currently contain test data formatted as a K-12 institution.

## Data dictionary

### [HEd Canvas Tables](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/test_data/hed_test_data)

See full details on the [Canvas API Resources](https://canvas.instructure.com/doc/api/all_resources.html)

| Domain | Table Name | Description |
|-----------|-----------|-----------|
| Activity/Assignments | [assignment_groups](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/assignment_groups) | Stores rules associated with an assignment group. |
| Activity/Assignments | [assignments](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/assignments) | Stores attributes for assignments. There is one record in this table for each assignment. |
| Academic Groups | [courses](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/courses) | Stores attributes for a course. |
| Affiliations | [enrollments](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/enrollments) | The relationship between a user and a class. That is, a list of users enrolled in a specific course and section. |
| Activity/Assignments | [scores](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/scores) | Stores assignment group and course grades for students enrolled in a course. |
| People | [users](https://data-access-platform-api.s3.amazonaws.com/index.html#tag/users) | Stores attributes for users. |
|  |  |  |
|  |  |  |
