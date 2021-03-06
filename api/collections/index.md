uid: pid-57cd7de46c8s9
type: documentation/page
created: 2016-09-05 14:15:00
modified: 2016-09-05 14:15:00
title: Collections
sort: 2

===

### /api/collections/listCollections

Get collection schema

```javascript
fetch('/api/collections/listCollections?token=xxtokenxx')
    .then(collections => collection.json())
    .then(collections => console.log(collections));
```

### /api/collections/collection/{collectionname}

Get collection schema

```javascript
fetch('/api/collections/collection/posts?token=xxtokenxx')
    .then(collection => collection.json())
    .then(collection => console.log(collection));
```

### /api/collections/get/{collectionname}

Get collection entries

```javascript
fetch('/api/collections/get/posts?token=xxtokenxx')
    .then(res => res.json())
    .then(res => console.log(res));
```

```javascript
fetch('/api/collections/get/posts?token=xxtokenxx', {
    method: 'post',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        filter: {published:true},
        limit: 10,
        skip: 5,
        sort: {_created:-1},
        populate: 1 // resolve linked collection items
    })
})
.then(res=>res.json())
.then(res => console.log(res));
```


### /api/collections/save/{collectionname}

Create / Update collection collection entries

```javascript
fetch('/api/collections/save/posts?token=xxtokenxx', {
    method: 'post',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        data: {...}
    })
})
.then(res=>res.json())
.then(entry => console.log(entry));
```


### /api/collections/remove/{collectionname}

Create / Update collection collection entries

```javascript
fetch('/api/collections/remove/posts?token=xxtokenxx', {
    method: 'post',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
        filter: {...}
    })
})
```