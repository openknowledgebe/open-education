---
layout: page
title: Api
section: api
order: 1
style: page-doel
lang: en
home: false
api: true
---
### Models

All models are described below. The mandatory properties of a model are marked **in bold letters**.

Every model also has a minimal-form, which is a stripped down version of the full-form.

It is possible that a mandatory property is not part of the minimal-form.

Even an optional field can be part of the minimal-form.

#### Subject <a id="Subject"></a> ([example](./examples/#Subject))
Subjects are representations of a subject.

<div class="table-wrapper" markdown="1">
{:.doc-table4}
| Property | Expected Type | Minimal | Description
| ----------- | ----------------- | -----------
| **id** | IRI | x | Unique IRI for the Subject.
| **type** | JSON-LD type x | x | Subject
| <a id="name"></a>**name** | [name](http://schema.org/name) | x | The name of the subject.
| <a id="credits"></a>credits | [Number](http://schema.org/Number) | | The amount of credits for this subject.

</div>

#### Course <a id="Course"></a> ([example](./examples/#Course))
Courses are representations of a course.

<div class="table-wrapper" markdown="1">
{:.doc-table4}
| Property | Expected Type | Minimal | Description
| -------- | ------------- | -----------
| **id** | IRI | x | Unique IRI for the Course.
| **type** | JSON-LD type | x | Course
| <a id="name"></a>**name** | [name](http://schema.org/name) | x | The name of the course.
| <a id="teachers"></a>**teachers** | Array of minimal [Teacher](#Teacher)s | | The list of teachers for this course.
| <a id="groups"></a>**groups** | Array of minimal [Group](#Group)s | | The list of groups of students for this course.
| <a id="credits"></a>credits | [Number](http://schema.org/Number) | | The amount of credits for this course.

</div>

#### Group <a id="Group"></a> ([example](./examples/#Group))
Groups are used to divide students into groups like for example at exercise sessions.

<div class="table-wrapper" markdown="1">
{:.doc-table4}
| Property | Expected Type | Minimal | Description
| ----------- | ----------------- | -----------
| **id** | IRI | x | Unique IRI for the Group.
| **type** | JSON-LD type | x | Group
| <a id="name"></a>**name** | [name](http://schema.org/name) | x | The name of the group.
| <a id="description"></a>description | [description](http://schema.org/description) |  | A description of this group
| <a id="amount"></a>amount |[Number](http://schema.org/Number) |  | The amount of students in this group

</div>


#### Teacher <a id="Teacher"></a> ([example](./examples/#Teacher))
Teachers are representations of a teacher.

<div class="table-wrapper" markdown="1">
{:.doc-table4}
| Property | Expected Type | Minimal | Description
| ----------- | ----------------- | -----------
| **id** | IRI | x | Unique IRI for the Teacher.
| **type** | JSON-LD type | x | Teacher
| <a id="givenName"></a>**givenName** | [givenName](http://schema.org/givenName) | x | The givenName aka firstName of the teacher.
| <a id="middleName"></a>middleName |[additionalName](http://schema.org/additionalName) | x | The middleName of the teacher
| <a id="familyName"></a>**familyName** |[familyName](http://schema.org/familyName) | x | The familyname of the teacher.
| <a id="gender"></a>gender |[GenderType](http://schema.org/GenderType) | | The gender of the teacher. (Male or Female or a custom string)
| <a id="honorificPrefix"></a>honorificPrefix | [honorificPrefix](http://schema.org/honorificPrefix) | | An honorific prefix preceding a Person's name such as Dr/Mrs/Mr.
| <a id="honorificSuffix"></a>honorificSuffix | [honorificSuffix](http://schema.org/honorificSuffix) | | An honorific suffix preceding a Person's name such as M.D. /PhD/MSCSW.

</div>

#### CourseEvent <a id="CourseEvent"></a> ([example](./examples/#CourseEvent))
CourseEvents are representations of a class session of a course.

<div class="table-wrapper" markdown="1">
{:.doc-table4}
| Property | Expected Type | Minimal | Description
| ----------- | ----------------- | -----------
| **id** | IRI | x | Unique IRI for the CourseEvent.
| **type** | JSON-LD type | x | CourseEvent
| <a id="title"></a>**title** | [title](http://schema.org/title) | x | The title of the course event.
| <a id="startDate"></a>**startDate** | [Date](http://schema.org/startDate) | x | The startDate of the course event.
| <a id="endDate"></a>**endDate** | [Date](http://schema.org/endDate) | x | The endDate of the course event.
| <a id="teachers"></a>**teachers** | Array of minimal [Teachers](#Teacher) | | The list of teachers teaching this course.
| <a id="groups"></a>**groups** | Array of minimal [Groups](#Group) | | The list of groups of students that should attend this eve t.
| <a id="course"></a>**course** | minimal [Course](#Course) | | The course to which this event belongs.
| <a id="required"></a>required | [Boolean](http://schema.org/Boolean) | | Whether this event is required to attend.

</div>


#### DiversityGroup <a id="DiversityGroup"></a> ([example](./examples/#DiversityGroup))
DiversityGroups are representations of a community groups a student can be part of, like for example male/female.

<div class="table-wrapper" markdown="1">
{:.doc-table4}
| Property | Expected Type | Minimal |Description
| ----------- | ----------------- | -----------
| **id** | IRI | x | Unique IRI for the DiversityGroup.
| **type** | JSON-LD type | x | DiversityGroup
| <a id="name"></a>**name** | [name](http://schema.org/name) | x | The name of the diversity group.
| <a id="description"></a>description | [description](http://schema.org/description) |  | A description of this diversity group
| <a id="amount"></a>amount |[Number](http://schema.org/Number) |  | The amount of students at the institution that are part of this group

</div>


### Api
This part describes the API-endpoints.

#### Some general info

##### Authentication and Permissions
Some API-endpoints grant access to personal data, this data may only be accessed if the person has given permission. The authentication
and permission system should be using OAuth 2.0

##### Languages
All API-endpoints should be able to return data in English and in the regional language(Dutch or French). The language of the response should match the language in the Accept-Language Header.
If the Accept-Language header is different from English and Dutch, and the language is not supported, an English response should be send.

##### Response status
The following response status should be used.
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Value | Description | Usage
| ----------- | ----------------- |
| 200 | Ok | When the request is valid.
| 403 | Forbidden | When the required permissions aren't given by the student
| 500 | Internal Server Error | When something went wrong on the server

</div>

#### GET Models
All models described above are accessible by /ModelName (/Course for the Course model).

Request Headers:
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Name | Description
| ----------- | -----------------
| Accept-Language | The language of the response.

</div>

Request Params:
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Key | Description
| ----------- | -----------------
| **id** | The id of the wanted model instance

</div>

Response:

A json object with the fields described for the model. All mandatory fields have to be present.

#### GET /Student <a id="Student"></a>
Request Header:
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Name | Description
| ----------- | -----------------
| **Authorization** | The OAuth 2.0 authorization header.
| Accept-Language | The language of the response.

</div>

Response:
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the Student.
| **type** | JSON-LD type | valid JSON-LD representation of the Student type. In most cases, this will simply be the string `Student`. An array including `Student` and other string elements that are either URLs or compact IRIs within the current context are allowed.
| <a id="givenName"></a>**givenName** | [givenName](http://schema.org/givenName) | The givenName aka firstName of the student.
| <a id="middleName"></a>middleName |[additionalName](http://schema.org/additionalName) | The middleName of the student
| <a id="familyName"></a>**familyName** |[familyName](http://schema.org/familyName) | The familyname of the student.
| <a id="gender"></a>gender |[GenderType](http://schema.org/GenderType) | The gender of the student. (Male, Female or a custom string)
| <a id="subjects"></a>**subjects** | Array of minimal [Subject](#Subject)s | The subjects the student is taking this year.
| <a id="courses"></a>**courses** | Array of minimal [Course](#Course)s | The list of all courses the user is currently taking.
| <a id="groups"></a>**groups** | Array of minimal [Group](#Group)s | The list of coursegroups the user is part of.

</div>

Example:
<div class="table-wrapper" markdown="1">
```javascript
{
    "@context": "https://w3id.org/university/v1",
    "id": "example.com/student/1",
    "type": "Student",
    "givenName": "Jesse",
    "middleName": "",
    "familyName": "Hoobergs",
    "gender": "Male",
    "subjects": [
        {
            "id": "example.com/subject/1",
            "type": "Subject",
            "name": "Bachelor in Engineering Science: fase 1"
        }
    ],
    "courses": [
        {
            "id": "example.com/course/1",
            "type": "Course",
            "name": "Algebra"
        },
        {
            "id": "example.com/course/2",
            "type": "Course",
            "name": "Analyse"
        }
    ],
    "groups": [
        {
            "id": "example.com/group/1",
            "type": "Group",
            "name": "A-L"
        },
        {
            "id": "example.com/group/3",
            "type": "Group",
            "name": "A-Z"
        }
    ]
}
```
</div>

#### GET /Schedule <a id="Schedule"></a>
Request Header:
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Name | Description
| ----------- | -----------------
| **Authorization** | The OAuth 2.0 authorization header.
| Accept-Language | The language of the response.

</div>

Request Params:
<div class="table-wrapper" markdown="1">
{:.doc-table}
| Key | Description
| ----------- | -----------------
| **startDate** | All returned events will have a startDate equal to or after this data
| **endDate** | All returned events will have a startDate before this data
| filtered | Whether the response only contains the events for the groups he is part of

</div>

Response:
<div class="table-wrapper" markdown="1">
{:.doc-table}
Array of [CourseEvent](#CourseEvent)s with the events for this students subjects.

</div>

<div class="table-wrapper" markdown="1">
```javascript
[
    {
        "@context": "https://w3id.org/university/v1",       
         "id": "example.com/event/1",
         "type": "CourseEvent",
         "title": "Algebra: Excercise session 1",
         "startDate": "2017-03-11T10:05:00+00:00",
         "endDate": "2017-03-11T12:05:00+00:00",
         "teachers": [
             {
                 "id": "example.com/teacher/1",
                 "type": "Teacher",
                 "givenName": "Teach",
                 "familyName": "er"
             }
         ],
         "groups": [
             {
                 "id": "https://example.org/Group/1",
                 "type": "Group",
                 "name": "te"
             }
         ],
         "course": {
             "id": "example.com/course/10",
             "type": "Course",
             "name": "Algebra"
         },
         "required": false
    },
    {
        "@context": "https://w3id.org/university/v1",
        "id": "example.com/event/1",
        "type": "CourseEvent",
        "title": "Algebra: Excercise session 2",
        "startDate": "2017-03-18T10:05:00+00:00",
        "endDate": "2017-03-18T12:05:00+00:00",
        "teachers": [
            {
                "id": "example.com/teacher/1",
                "type": "Teacher",
                "givenName": "Teach",
                "middleName": "middle",
                "familyName": "er"
            }
        ],
        "groups": [
            {
                "id": "https://example.org/Group/1",
                "type": "Group",
                "name": "te"
            }
        ],
        "course": {
            "id": "example.com/course/10",
            "type": "Course",
            "name": "Algebra"
        },
        "required": true
    }
]
```
</div>