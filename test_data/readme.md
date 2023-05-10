# Test data

This module includes artificially generated data which matches the format of the [Canvas API Calls](https://canvas.instructure.com/doc/api/index.html).
- 18 tables formatted in JSONs, as described in the Canvas data dictionary. Assets can be adapted to integrate ingestion/refinement functionality for more, different or less tables.

<strong>Note:</strong> This module contains one set of test data - for mock higher education data. This module does not currently contain test data formatted as a K-12 institution.

## Data dictionary

### [HEd Canvas Tables](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas/test_data/hed_test_data)

See full details on all [Canvas API Resources](https://canvas.instructure.com/doc/api/all_resources.html).

| Domain | Table Name | Description | 
|-----------|-----------|-----------|
| People/Accounts | [accounts](https://canvas.instructure.com/doc/api/accounts.html) | User accounts associated IDs (i.e., Canvas accounts) |
| People/Accounts | [accounts_lti](https://canvas.instructure.com/doc/api/accounts_(lti).html) | User accounts associated IDs (i.e., LTI accounts) |
| Activity/Assignments | [assignments](https://canvas.instructure.com/doc/api/assignments.html) | Stores attributes for assignments. There is one record in this table for each assignment. |
| Activity/Assignments/Submission Results | [assignment_submissions](https://canvas.instructure.com/doc/api/submissions.html) | Holds assignment submission results within a given course or section for users. | 
| Activity/Assignments/Submission Results | [assignment_submission_summary](https://canvas.instructure.com/doc/api/submissions.html) | Holds summary of assignment submission results within a given course or section for users. | 
| Academic Groups | [courses](https://canvas.instructure.com/doc/api/courses.html) | Stores attributes for a course. |
| Affiliations | [course_memberships](https://canvas.instructure.com/doc/api/names_and_role.html) | The relationship between a user and a class. That is, a list of users enrolled in a specific course and section. Difference between this and enrollments is that this table contains the LTI mappings. | 
| Affiliations | [enrollments](https://canvas.instructure.com/doc/api/enrollments.html) | The relationship between a user and a class. That is, a list of users enrolled in a specific course and section. |
| Affiliations | [enrollment_terms](https://canvas.instructure.com/doc/api/enrollment_terms.html) | The relationship between a user and and their enrollment term. | 
| Activity/Modules | [modules](https://canvas.instructure.com/doc/api/modules.html) | List of modules (similar to lessons) in a course. |
| Activity/Modules | [module_items](https://canvas.instructure.com/doc/api/modules.html) | List of module items in a course. |
| Outcomes/Grade Results | [outcome_results](https://canvas.instructure.com/doc/api/outcome_results.html) | Holds assignment and/or quiz results within a given course for users. |
| Activity/Quizzes | [quizzes](https://canvas.instructure.com/doc/api/quizzes.html) | Stores attributes for quizzes. There is one record in this table for each quiz. | 
| Activity/Quizzes | [quiz_submissions](https://canvas.instructure.com/doc/api/quiz_submissions.html) | Stores attributes for quiz submissions. | 
| Outcomes/Grade Results | [result](https://canvas.instructure.com/doc/api/result.html) | Holds assignment and/or quiz results within a given course for users. | 
| Role | [role](https://canvas.instructure.com/doc/api/roles.html) | List of roles within an account. See list of Canvas roles [here](https://canvas.instructure.com/doc/api/file.canvas_roles.html). | 
| Academic Groups | [sections](https://canvas.instructure.com/doc/api/sections.html) | List of sections for a specific course. | 
| People | [users](https://canvas.instructure.com/doc/api/users.html) | Stores attributes for users. The latter API call is for user profiles (which contains LTI and SIS ) | 

For the specific API calls for tables, see the table below.

|Table Name | API Call |
|-----------|-----------|
| [accounts](https://canvas.instructure.com/doc/api/accounts.html) |```GET /api/v1/accounts``` |
| [accounts_lti](https://canvas.instructure.com/doc/api/accounts_(lti).html) | ```GET /api/lti/accounts/:account_id``` |
| [assignments](https://canvas.instructure.com/doc/api/assignments.html) | ```GET /api/v1/courses/:course_id/assignments``` and/or ```GET /api/v1/courses/:course_id/assignment_groups/:assignment_group_id/assignments``` |
| [assignment_submissions](https://canvas.instructure.com/doc/api/submissions.html) | ```GET /api/v1/courses/:course_id/assignments/:assignment_id/submissions``` and/or ```GET /api/v1/sections/:section_id/assignments/:assignment_id/submissions``` |
| [assignment_submission_summary](https://canvas.instructure.com/doc/api/submissions.html) | ```GET /api/v1/courses/:course_id/assignments/:assignment_id/submission_summary``` and/or ```GET /api/v1/sections/:section_id/assignments/:assignment_id/submission_summary``` |
| [courses](https://canvas.instructure.com/doc/api/courses.html) | ```GET /api/v1/courses``` |
| [course_memberships](https://canvas.instructure.com/doc/api/names_and_role.html) |```GET /api/lti/courses/:course_id/names_and_roles``` |
| [enrollments](https://canvas.instructure.com/doc/api/enrollments.html) | ```GET /api/v1/sections/:section_id/enrollments``` and/or ```GET /api/v1/courses/:course_id/enrollments``` |
| [enrollment_terms](https://canvas.instructure.com/doc/api/enrollment_terms.html) | ```GET /api/v1/accounts/:account_id/terms``` |
| [modules](https://canvas.instructure.com/doc/api/modules.html) | ```GET /api/v1/courses/:course_id/modules``` |
| [module_items](https://canvas.instructure.com/doc/api/modules.html) | ```GET /api/v1/courses/:course_id/modules/:module_id/items``` |
| [outcome_results](https://canvas.instructure.com/doc/api/outcome_results.html) | ```GET /api/v1/courses/:course_id/outcome_results``` |
| [quizzes](https://canvas.instructure.com/doc/api/quizzes.html) | ```GET /api/v1/courses/:course_id/quizzes```  |
| [quiz_submissions](https://canvas.instructure.com/doc/api/quiz_submissions.html) | ```GET /api/v1/courses/:course_id/quizzes/:quiz_id/submissions```  |
| [result](https://canvas.instructure.com/doc/api/result.html) | ```GET /api/lti/courses/:course_id/line_items/:line_item_id/results``` |
| [role](https://canvas.instructure.com/doc/api/roles.html) | ```GET /api/v1/accounts/:account_id/roles``` |
| [sections](https://canvas.instructure.com/doc/api/sections.html) | ```GET /api/v1/courses/:course_id/sections``` |
| [users](https://canvas.instructure.com/doc/api/users.html) | ```GET /api/v1/accounts/:account_id/users``` and/or ```GET /api/v1/users/:user_id/profile```|
