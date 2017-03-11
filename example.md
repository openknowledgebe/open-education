---
layout: page
title: Examples
section: vocabulary
order: 1
style: page-doel
lang: en
home: false
voc: false
example: true
---
### Models

All models are described below. The mandatory properties of a model are marked **in bold letters**.

Every model also has a minimal-form, which is a stripped down version of the full-form.

It is possible that a mandatory property is not part of the minimal-form.

Even an optional field can be part of the minimal-form.

### Subject <a id="Subject"></a> ([doc](../#Subject))
<div class="table-wrapper" markdown="1">
```javascript
{
   "@context": "https://w3id.org/university/v1",
   "id": "example.com/subject/1",
   "type": "Subject",
   "name": "Bachelor in Mathematics: fase 1",
   "credits": 60
}
```
</div>

### Course <a id="Course"></a> ([doc](../#Course))
<div class="table-wrapper" markdown="1">
```javascript
{
    "@context": "https://w3id.org/university/v1",
    "id": "example.com/course/1",
    "type": "Course",
    "name": "Algebra",
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
            "id": "example.com/group/1",
            "type": "Group",
            "name": "cws"
        }
    ]
}
```
</div>

### Group <a id="Group"></a> ([doc](../#Group))
<div class="table-wrapper" markdown="1">
```javascript
{
    "@context": "https://w3id.org/university/v1",
    "id": "example.com/group/1",
    "type": "Group",
    "name": "te",
    "description": "This is a sample group",
    "amount": 5
}
```
</div>



### Teacher <a id="Teacher"></a> ([doc](../#Teacher))
<div class="table-wrapper" markdown="1">
```javascript
{
    "@context": "https://w3id.org/university/v1",
    "id": "example.com/teacher/1",
    "type": "Teacher",
    "givenName": "Teach",
    "middleName": "",
    "familyName": "er",
    "gender": "Female",
    "honorificPrefix": "Dr",
    "honorificSuffix": "PhD"
}
```
</div>

### CourseEvent <a id="CourseEvent"></a> ([doc](../#CourseEvent))
<div class="table-wrapper" markdown="1">
```javascript
{
    "@context": "https://w3id.org/university/v1",
    "id": "example.com/event/1",
    "type": "CourseEvent",
    "title": "",
    "startDate": "2017-03-11T10:05:00+00:00",
    "endDate": "2017-03-11T12:05:00+00:00",
    "teachers": [
        {
            "id": "example.com/teacher/1",
            "type": "Teacher",
            "givenName": "Teach",
            "middleName": "",
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
        "name": ""
    },
    "required": false
}
```
</div>

### DiversityGroup <a id="DiversityGroup"></a> ([doc](..#DiversityGroup))
<div class="table-wrapper" markdown="1">
```javascript
not added
```
</div>


