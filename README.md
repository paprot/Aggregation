# Aggregation
Aggregation


NoSQL
=====

Zadanie 2
-----
**Agregacje**


```javascript
db.impor.aggregate([
  {$project: { _id: 0, userId: 1 } },
  {$group: { _id: "$userId" } },
  {$group: { _id: null, count: { $sum: 1 } } }
])
```

```javascript
{ "_id" : null, "count" : 35684 }
```
    
Najpopularniejsze programy telewizyjne:

```javascript
db.impor.aggregate([
 
  {$group: { _id: "$title", count: { $sum: 1 } } },
  {$sort: { count: -1 } },
  {$limit: 10 }
])
```

```javascript
{ "_id" : "True Blood", "count" : 29579 }
{ "_id" : "Glee", "count" : 21674 }
{ "_id" : "Dexter", "count" : 15529 }
{ "_id" : "The Big Bang Theory", "count" : 15446 }
{ "_id" : "Fringe", "count" : 14604 }
{ "_id" : "Doctor Who", "count" : 13129 }
{ "_id" : "Pretty Little Liars", "count" : 11959 }
{ "_id" : "Weeds", "count" : 11820 }
{ "_id" : "House", "count" : 11599 }
{ "_id" : "Family Guy", "count" : 11565 }
```

Ilość wszystkich akcji:

```javascript
db.impor.aggregate([
  {$project: { _id: 0, action: 1 } },
  {$group: { _id: null, count: { $sum: 1 } } }
])
```

```javascript

```

N

```javascript
db.impor.aggregate([
  {$project: { _id: 0, action: 1 } },
  {$group: { _id: "$action", count: { $sum: 1 } } },
  {$sort: { count: 1 } },
  {$limit: 10 }
])
```

```javascript
{ "_id" : "Reply", "count" : 4 }
{ "_id" : null, "count" : 15 }
{ "_id" : "Looked", "count" : 79 }
{ "_id" : "Comment", "count" : 573 }
{ "_id" : "Saved", "count" : 26651 }
{ "_id" : "Favorited", "count" : 55125 }
{ "_id" : "Unwanted", "count" : 67974 }
{ "_id" : "Disliked", "count" : 105496 }
{ "_id" : "Checkin", "count" : 1225866 }
{ "_id" : "Liked", "count" : 1538217 }
```

**Java**

