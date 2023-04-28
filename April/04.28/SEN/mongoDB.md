# MongoDB - studio 3T
**table 확인하기**
show collection




**조건 추출하기: find()**
- 비교 연산자
```jsx
// READ : documents : conditaion query
// level >= 4
db.info.find({level : {$gte : 4}});
```
```jsx
// subject : flask, nginx
db.info.find({subject : {$in['flask', 'nginx'}});
```
- 논리 연산자
```jsx
// (level > 5) && (subject == nginx)
db.info.find({$and: [{subject : 'nginx'}, {{level:{$gte : 5}}]});
```
- col만 선택 추출
projection
```jsx
// READ : documents : projection : select columns
// _id : 예외동장 : 따로 false 설정하지 않으면 무조건 출력
db.user.find({}, {name : true, age : true}); // 조건인지, 출력할 컬럼
// age 컬럼 제외하고 출력
db.user.find({}, {age : false}); // false로 해주면 출력하지 않음
// _id 제외하고 출력
db.user.find({}, {_id : false, name : true, age : true});
// _id를 제외한 컬럼에 true, false를 섞어서 사용할 수 없음
```

**정렬하기 : sort()**
```jsx
// 정렬 : sort()
// level : 오름차순 정렬 : 1
db.info.find().sort({level:1});
// level : 내림차순 정렬 : -1
db.info.find().sort({level:-1});
```

**데이터 원하는 만큼만 출력**
출력 데이터 갯수 제한 : limit()
```jsx
// level이 5이하인 것을 내림차순으로 정렬해서 3개만 출력
db.info.find({level : {$lte : 5}}).sort({level : -1}).limit(3);
```
데이터를 스킵해서 출력 : skip()
```jsx
db.info.find({level : {$lte : 5}}).sort({level : -1}).skip(4);
```

**데이터 수정하기**
```jsx
// UPDATE documents : update() : $set
dh.info.find();
//python > level == 5 document 1개만 수정
db.info.update({subject : 'python'}, {$set : {level : 5}});
// python > level == 4, mutil true를 활용하여 여러 개의 document 수정
db.info.update(
              {subject : 'python'},
              {$set : {level : 4}},
              {multi : true}
);
db.info.find();
```

**fuction 사용**
```jsx
// pagenation fuction : 몇페이지 게시글을 가져와라
db.info();
var pagenation = function(page, pageblock){
    return db.info.find().skip((page -1) * pageblock).limit(pageblock)
};
pagenation(2, 3); // 2 번째 

// creat : insert() : [{data1} {data2}]
// read : find() : (query, projection) : &gt, $and, $in
// update : update() : (query, update data, option) : %set
// delete : drop() : (query)





