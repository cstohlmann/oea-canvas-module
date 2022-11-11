# Documentation

See the [main Module readme](https://github.com/microsoft/OpenEduAnalytics/tree/main/modules/module_catalog/Canvas) for complete documentation of this module and technical assets. Some useful links are listed below for easy access.

| Resource | Description |
| --- | --- | 
| [Canvas LMS REST API documentation](https://canvas.instructure.com/doc/api/index.html) | Summary and details of various resources that can be accessed through the Canvas LMS API. |
| [Canvas API Endpoint Attributes](https://canvas.instructure.com/doc/api/file.endpoint_attributes.html) | Reference page of the Canvas API endpoint attributes. |
| [Canvas API IDs](https://canvas.instructure.com/doc/api/file.object_ids.html) | Reference page for specifications on the Canvas API Object IDs, SIS IDs, and special IDs. |
| [Canvas API - All Resources](https://canvas.instructure.com/doc/api/all_resources.html) | Reference page for a comprehensive table of all resources that can be queried through the Canvas API. |

## Potentially Useful/Main Tables

### User-Related Tables

| User Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: Names and Role](https://canvas.instructure.com/doc/api/names_and_role.html#method.lti/ims/names_and_roles.course_index) | Details on the Canvas "Names and Role" resource table. | ```GET /api/lti/courses/:course_id/names_and_roles``` | [ ] | [x] |
| [Canvas Resource: List Courses for a User](https://canvas.instructure.com/doc/api/all_resources.html#method.courses.user_index) | Details on how to get a list of courses for a particular user. | ```GET /api/v1/users/:user_id/courses``` | [x] | [x?] |
| [Canvas Resource: List Users in Course](https://canvas.instructure.com/doc/api/courses.html#method.courses.users) | Details on how to get a list of all users for a particular course. | ```GET /api/v1/courses/:course_id/users``` | [ ] | [x?] |
| [Canvas Resource: Get Bulk User Progress](https://canvas.instructure.com/doc/api/all_resources.html#method.courses.bulk_user_progress) | Details on how to get progress info for all users enrolled in a particular course. | ```GET /api/v1/courses/:course_id/bulk_user_progress``` | [ ] | [ ] | 

### Section-Related Tables

| Section Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List Course Sections](https://canvas.instructure.com/doc/api/all_resources.html#method.sections.index) | Details on how to get a paginated list of sections for a particular course. | ```GET /api/v1/courses/:course_id/sections```| [ ] | [x] |

### Course-Related Tables

| Course Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List Your Courses](https://canvas.instructure.com/doc/api/all_resources.html#method.courses.index) | Details on how to get a paginated list of active courses for the current user. | ```GET /api/v1/courses``` | [x] | [x]... prob |
| [Canvas Resource: List All Courses](https://canvas.instructure.com/doc/api/all_resources.html#method.search.all_courses) | Details on how to get a paginated list of all courses visible in the public index. | ```GET /api/v1/search/all_courses``` | [ ] | [ ] |

### Quiz-Related Tables

| Quiz Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List Quizzes in a Course](https://canvas.instructure.com/doc/api/all_resources.html#method.quizzes/quizzes_api.index) | Details on how to get a paginated list of quizzes in a particular course. | ```GET /api/v1/courses/:course_id/quizzes``` | [ ] | [?] |
| [Canvas Resource: Get All Quiz Submissions](https://canvas.instructure.com/doc/api/all_resources.html#method.quizzes/quiz_submissions_api.index) | Details on how to get a list of all submissions for a particular quiz. | ```GET /api/v1/courses/:course_id/quizzes/:quiz_id/submissions``` | [ ] | [?] |

### Activity-Stream-Related Tables

| Activity Stream Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List the Activity Stream](https://canvas.instructure.com/doc/api/all_resources.html#method.users.activity_stream) | Details on how to get a paginated list of the current user's global activity stream. | ```GET /api/v1/users/activity_stream``` | [ ] | [x?] |
| [Canvas Resource: Activity Stream Summary](https://canvas.instructure.com/doc/api/all_resources.html#method.users.activity_stream_summary) | Details on how to get a summary list of the current user's global activity stream. | ```GET /api/v1/users/self/activity_stream/summary``` | [ ] | [?] |

### Assignment-Related Tables

| Assignment Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List Assignments for a User](https://canvas.instructure.com/doc/api/assignments.html#method.assignments_api.user_index) | Details on how to get a paginated list of assignments for the specified user if the current user has rights to view. | ```GET /api/v1/users/:user_id/courses/:course_id/assignments``` | [x] | [?] |

### Calendar-Related Tables

| Calendar Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List Calendar Events](https://canvas.instructure.com/doc/api/calendar_events.html#method.calendar_events_api.index) | Details on how to get a paginated list of calendar events or assignments for the current user. | ```GET /api/v1/calendar_events``` | [x] | [?] |
| [Canvas Resource: List Calendar Events for a User](https://canvas.instructure.com/doc/api/calendar_events.html#method.calendar_events_api.user_index) | Details on the how to get a paginated list of calendar events or assignments for the specified user. <strong>Note:</strong> context_codes[] as a param -> calendar events of a particular course(s). | ```GET /api/v1/users/:user_id/calendar_events``` | [x] | [?] |

### Announcements-Related Tables

| Announcement Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: List Announcements](https://canvas.instructure.com/doc/api/announcements.html) | Details on how to get a paginated list of announcements for given courses and date range. <strong>Note:</strong> pass context_codes[] as a param -> get all announcements for the given courses. | ```GET /api/v1/announcements``` | [x] | [?] |

### Analytics-Related Tables

| Analytic Tables | Description | API Call | Microsoft-Documented as Valuable | Tables to start with |
| --- | --- | --- | --- | --- |
| [Canvas Resource: Get User-in-a-Course-Level Participation Data](https://canvas.instructure.com/doc/api/all_resources.html#method.analytics_api.student_in_course_participation) | Details on how to get a page view of hits grouped by hour, and participation details through the entire history of the course. | ```GET /api/v1/courses/:course_id/analytics/users/:student_id/activity``` | [ ] | [x] |

