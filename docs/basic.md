---
layout: default
title: Basic
parent: Front-end
grand_parent: Manual
nav_order: 1
---
# [Front-end] 프론트엔드의 기본

## 프론트엔드 기술

### HTML5

- Hyper Text Markup Language
- 웹 페이지 구축을 위한 뼈대가 되는 언어이다.

### CSS

- Cascading Style Sheet
- 웹 디자인을 완성시켜 주는 언어이다.

### JavaScript

<br/>

## 웹사이트 구조

header : 회사 로고와 목차

article : 메인 이미지, 본문 등

footer :사이트에 관한 주요 정보

<br/>

## HTML 문서 구조

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<meta http-equiv="X-UA-Compatible" content="ie=edge">
	<title>Document</title>
</head>
<body>
</body>
</html>
```

### <!DOCTYPE html>

문서의 타입 즉, 형식을 명시하기 위한 것으로 HTML 문서의 첫 번째 줄에 나와야 한다.

### <meta>

웹 문서 정보(작성자, 형식, 인코딩 방식)를 지정한다.

빈 태그로 종료 태그가 없다.

<br/>

## <head>와 <body> 태그

```html
<head>
	HTML 문서에 대한 정보, CSS 속성
<head>
<body>
	각종 HTML 태그 정보
	하단 부분에 자바스크립트
</body>
```

### <head> 내부에 넣을 수 있는 태그 이름

- meta : 웹 페이지에 추가 정보를 전달한다.
- title : 웹 페이지의 제목을 나타낸다.
- script : 웹 페이지에 스크립트를 추가한다.
- link : 다른 파일을 추가한다.
- style : 스타일 시트를 추가한다.
- base : 기본 경로를 지정한다.

```html
<meta name="keywords" content="Jeju, tourist"/>
```

검색엔진에서 해당 키워드와 관련된 내용을 검색할 경우 이런 키워드가 포함되어 있는 웹 페이지를 보여주게 된다.

```html
<meta name="description" content="JEJU The most beautiful Island in the World"/>
```

사이트에 대한 설명을 나타내 주는 곳이다.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

현재 사용하는 브라우저에서 보이는 크기를 1로 고정해 주는 역할을 한다.

initial-scale=2로 하게 되면 모바일 브라우저에서만 사이트의 글씨 크기가 2배로 확대되어 보인다.

```html
<meta http-equiv="X-UA-Compatible" content="ie=edge">
```

IE인 경우 가장 최신 브라우저 모드로 보이게끔 처리하는 것이다.

```html
<meta http-equiv="refresh" content="3;url=http://www.google.com/">
```

3초 후에 google.com으로 사이트가 리다이렉트해주게 된다.

3을 0으로 변경하면 바로 이동한다.

<br/>

## CSS 파일 적용 방법

1. 임베디드 방식

    ```html
    <style>
    	h1 {font-size: 32px; color: #ccc;}
    	...
    </style>
    ```

2. 별도의 파일을 호출하는 방식

    ```html
    <link rel="stylesheet" type="text/css" href="./css/style.css">
    ```

    일반적으로 가장 많이 사용하는 방법이다.

3. HTML 태그 내부에 직접 적용하는 방식

    ```html
    <h1 style="font-size:32px;color:#css;">About Jejudo</h1>
    ```

    가급적 사용하지 않기를 권한다.
