---
layout: default
title: Delete-update
parent: Firebase
grand_parent: Manual
nav_order: 1
---

# [Firebase] 데이터 삭제, 조회, 업데이트

## 데이터 삭제하기

### 문서 삭제하기

```java
FirebaseFirestore db = FirebaseFirestore.getInstance();
db.collection("users").document("userinfo")
	.delete()
	.addOnSuccessListener(new OnSuccessListener<Void>() {
		@Override
		public void onSuccess(Void aVoid){
		}		
	})
	.addOnFailureListener(new OnFailuereLisener() {
		@Override
		public void onFailure(@NonNull Exception e) {
		}
	});
}
```

### 문서 안에서 지정된 필드 삭제하기

```java
FirebaseFirestore db = FirebaseFirestore.getInstance();
DocumentReference docRef = db.collection("users".document("userinfo");

MAP<String, Object> updates = new HashMap<>();
updates.put("address", FieldValue.delete());

docRef.update(updates).addOnCompleteListener(new OnCompleteListener<Void>() {
	@Override
	public void onComplete(@NonNull Task<Void> task){
	}		
});
```

<br/>

## 데이터 조회하기

### 지정된 문서의 정보를 조회하기 - 객체로 반환하여 사용하기

```java
public class UserInfo
{
	private String name;
	private int age;
	...
	public String getName()
	{
		return name;
	}
	public void setName(String name)
	{
		this.name = name;
	}
	...
}
...
if(document.exists())
{
	UserInfo userInfo = document.toObject(UserInfo.class);
	Log.d("namjinha", "name = " + userInfo.getName());
}
```

### 쿼리로 조건에 맞는 문서의 정보를 조회하기

```java
db.collection("users")
.whereEqualTo("age", 25)
.get()
.addOnCompleteListener(new OnCompleteListener<QuerySnapshot>()
{
	if(task.isSuccessful())
	{
		for(QueryDocumentSnapshot document : task.getResult())
		{
			Log.d("namjinha", document.getId() + " => " + document.getData());
			UserInfo userInfo = document.toObject(UserInfo.class);
			Log.d("namjinha", "name = " + userInfo.getName());
		}
	}
});
```

`whereEqualTo()`

`whereGreaterThan ()`

`whereLessThan()`

`whereGreatThanOrEqualTo()`

`whereLessThanOrEqualTo()`

### 변경된 데이터를 실시간으로 확인하기

```java
final DocumentReference docRef = db.collection("users".document("userinfo");
docRef.addSnapshotListener(new EventListener<DocumentSnapshot>()
{
	@Override
	public void onEvent(@Nullable DocumentSnapshot snapshot,
											@Nullable FirebaseFirestoreException e)
	{
		if(e != null)
		{
			return;
		}
		if(snapshot != null && snapshot.exists())
		{
			Log.d("namjinha", "Current data: " + snapshot.getData());
		}
		else
		{
		}
	}
}
```

<br/>

## 데이터 업데이트

```java
DocumentReference tdb = db.collection("User").document(user.getUid())
    .collection("TotalDailyIntake").document(date);
tdb.update("totalCalories", FieldValue.increment(calories));
```

