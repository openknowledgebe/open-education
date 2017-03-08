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

### Subject <a id="Subject"></a> ([doc](../#Subject))
<div class="table-wrapper" markdown="1">
```javascript
{
   "@context": "http://jesseh.be/edu/",
   "id": "sub1",
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
    "@context": "http://jesseh.be/edu/",
    "id": "course1",
    "type": "Course",
    "name": "Mathem",
    "teachers": [
        {
            "id": "teach1",
            "type": "Teacher",
            "givenName": "Teach",
            "familyName": "er"
        }
    ],
    "groups": [
    {
        "id": "group1",
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
    "@context": "http://jesseh.be/edu/",
    "id": "https://example.org/Group/1",
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
    "@context": "http://jesseh.be/edu/",
    "id": "teach1",
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
not added
```
</div>

### DiversityGroup <a id="DiversityGroup"></a> ([doc](..#DiversityGroup))
<div class="table-wrapper" markdown="1">
```javascript
not added
```
</div>


