---
layout: page
title: Vocabulary
section: vocabulary
order: 1
style: page-doel
lang: en
home: false
voc: true
---

### Student <a id="Student"></a> ([example](./examples/#Student))
Students are representations of a student. Students have a set of mandatory and optional properties. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the Student.
| **type** | JSON-LD type | valid JSON-LD representation of the Student type. In most cases, this will simply be the string `Student`. An array including `Student` and other string elements that are either URLs or compact IRIs within the current context are allowed.
| <a id="givenName"></a>**givenName** | [givenName](http://schema.org/givenName) | The givenName aka firstName of the student.
| <a id="familyName"></a>**familyName** |[familyName](http://schema.org/familyName) | The familyname of the student.
| <a id="gender"></a>gender |[GenderType](http://schema.org/GenderType) | The gender of the student.
| <a id="subjects"></a>**subjects** | Array of [Subject](#Subject)s | The subjects the student is taking this year.
| <a id="courses"></a>**courses** | Array of [Course](#Course)s | The list of all courses the user is currently taking.
| <a id="groups"></a>**groups** | Array of [Group](#Group)s | The list of coursegroups the user is part of.

</div>

### Subject <a id="Subject"></a> ([example](./examples/#Subject))
Subjects are representations of a subject. Subjects have a set of mandatory and optional properties. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the Subject.
| **type** | JSON-LD type | Subject
| <a id="name"></a>**name** | [name](http://schema.org/name) | The name of the subject.
| <a id="teachers"></a>**teachers** | Array of [Teacher](#Teacher)s | The list of teachers for this subject.
| <a id="credits"></a>**credits** | [Number](http://schema.org/Number) | The amount of credits for this subject.

</div>

### Course <a id="Course"></a> ([example](./examples/#Course))
Courses are representations of a course. Courses have a set of mandatory properties. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| -------- | ------------- | -----------
| **id** | IRI | Unique IRI for the Course.
| **type** | JSON-LD type | Course
| <a id="name"></a>**name** | [name](http://schema.org/name) | The name of the course.
| <a id="groups"></a>**groups** | Array of [Group](#Group)s | The list of groups of students for this course.

</div>

### Group <a id="Group"></a> ([example](./examples/#Group))
Groups are used to divide students into groups like for example at exercise sessions. Groups have a set of mandatory properties and optional fields. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the Group.
| **type** | JSON-LD type | Group
| <a id="name"></a>**name** | [name](http://schema.org/name) | The name of the group.
| <a id="description"></a>description | [description](http://schema.org/description) | A description of this group
| <a id="amount"></a>amount |[Number](http://schema.org/Number) | The amount of students in the group

</div>


### Teacher <a id="Teacher"></a> ([example](./examples/#Teacher))
Teachers are representations of a teacher. Teachers have a set of mandatory and optional properties. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the Teacher.
| **type** | JSON-LD type | Teacher
| <a id="givenName"></a>**givenName** | [givenName](http://schema.org/givenName) | The givenName aka firstName of the teacher.
| <a id="familyName"></a>**familyName** |[familyName](http://schema.org/familyName) | The familyname of the teacher.
| <a id="gender"></a>gender |[GenderType](http://schema.org/GenderType) | The gender of the teacher.
| <a id="honorificPrefix"></a>honorificPrefix | [honorificPrefix](http://schema.org/honorificPrefix) | An honorific prefix preceding a Person's name such as Dr/Mrs/Mr.
| <a id="honorificPrefix"></a>honorificSuffix | [honorificSuffix](http://schema.org/honorificSuffix) | An honorific suffix preceding a Person's name such as M.D. /PhD/MSCSW.

</div>

### CourseEvent <a id="CourseEvent"></a> ([example](./examples/#CourseEvent))
CourseEvents are representations of a class session of a course. CourseEvents have a set of mandatory properties. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the Course.
| **type** | JSON-LD type | Course
| <a id="title"></a>**title** | [name](http://schema.org/title) | The title of the course event.
| <a id="startDate"></a>**startDate** | [Date](http://schema.org/Date) | The startDate of the course event.
| <a id="endDate"></a>**startDate** | [Date](http://schema.org/Date) | The endDate of the course event.
| <a id="teachers"></a>**teachers** | Array of [Teacher](#Teacher)s | The list of teachers teaching this course.
| <a id="groups"></a>**groups** | Array of [Group](#Group)s | The list of groups of students that should attend this course.
| <a id="course"></a>**course** | [Course](#Course) | The course to which this event belongs.
| <a id="required"></a>required | [Boolean](http://schema.org/Boolean) | Whether this event is required to attend.

</div>

### DiversityGroup <a id="DiversityGroup"></a> ([example](./examples/#DiversityGroup))
DiversityGroups are representations of a community groups a student can be part of, like for example male/female. DiversityGroups have a set of mandatory properties. Fields marked **in bold letters** are mandatory.

<div class="table-wrapper" markdown="1">
{:.doc-table}
| Property | Expected Type | Description
| ----------- | ----------------- | -----------
| **id** | IRI | Unique IRI for the DiversityGroup.
| **type** | JSON-LD type | DiversityGroup
| <a id="name"></a>**name** | [name](http://schema.org/name) | The name of the diversity group.
| <a id="description"></a>description | [description](http://schema.org/description) | A description of this diversity group
| <a id="amount"></a>amount |[Number](http://schema.org/Number) | The amount of students at the institution that are part of this group

</div>