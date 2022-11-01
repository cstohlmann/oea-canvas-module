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

| User Tables | Description |
| --- | --- |
| [Canvas Resource: Names and Role](https://canvas.instructure.com/doc/api/names_and_role.html#method.lti/ims/names_and_roles.course_index) | Details on the Canvas "Names and Role" resource table. |
| [Canvas Resource: List Courses for a User](https://canvas.instructure.com/doc/api/all_resources.html#method.courses.user_index) | Details on the how to get a list of courses for a particular user. |
| [Canvas Resource: List Users in Course](https://canvas.instructure.com/doc/api/courses.html#method.courses.users) | Details on the how to get a list of all users for a particular course. |
| [Canvas Resource: Get Bulk User Progress](https://canvas.instructure.com/doc/api/all_resources.html#method.courses.bulk_user_progress) | Details on the how to get progress info for all users enrolled in a particular course. |

### Section-Related Tables

| Section Tables | Description |
| --- | --- |
| [Canvas Resource: List Course Sections](https://canvas.instructure.com/doc/api/all_resources.html#method.sections.index) | Details on the how to get a paginated list of sections for a particular course. |

### Course-Related Tables

| Course Tables | Description |
| --- | --- |
| [Canvas Resource: List Your Courses](https://canvas.instructure.com/doc/api/all_resources.html#method.courses.index) | Details on the how to get a paginated list of active courses for the current user. |
| [Canvas Resource: List All Courses](https://canvas.instructure.com/doc/api/all_resources.html#method.search.all_courses) | Details on the how to get a paginated list of all courses visible in the public index. |

### Quiz-Related Tables

| Quiz Tables | Description |
| --- | --- |
| [Canvas Resource: List Quizzes in a Course](https://canvas.instructure.com/doc/api/all_resources.html#method.quizzes/quizzes_api.index) | Details on the how to get a paginated list of quizzes in a particular course. |
| [Canvas Resource: Get All Quiz Submissions](https://canvas.instructure.com/doc/api/all_resources.html#method.quizzes/quiz_submissions_api.index) | Details on the how to get a list of all submissions for a particular quiz. |

### Activity-Stream-Related Tables

| Activity Stream Tables | Description |
| --- | --- |
| [Canvas Resource: List the Activity Stream](https://canvas.instructure.com/doc/api/all_resources.html#method.users.activity_stream) | Details on the how to get a paginated list of the current user's global activity stream. |
| [Canvas Resource: Activity Stream Summary](https://canvas.instructure.com/doc/api/all_resources.html#method.users.activity_stream_summary) | Details on the how to get a summary list of the current user's global activity stream. |
