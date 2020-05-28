---
layout: default
title: Sort-foreach
parent: Firebase
grand_parent: Manual
nav_order: 2
---

# [Firebase] Java sort(), for each 사용법

## sort()

- 오름차순 : `Arrays.sort()`

- 내림차순 : `Collections.reverseOrder()`

  `Arrays.sort(arr, Collections.reverseOrder());` 

  → int 의 경우 integer로 바꿔줘야 한다.

- Collections 으로 ArrayList 정렬하기 

  `ArrayList list = new ArrayList();`

   `Collections.sort(list);`

<br/>

## for each

### 구조

```java
for(type var: iterate){
	body-of-loop
}
```

### 예시

```java
String[] num = {..};
for(String number: num){
	System.out.println(number);
}
```