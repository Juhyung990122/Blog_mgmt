---
title: keyduck개발일지17
date: 2021-06-20 20:45:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---


## 🌟키덕 개발일지 - 17

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 리뷰 R기능 구현
- 리뷰 테스트코드 작성


### 🎯에러로그 및 메모
1. Test 어노테이션 차이에 따른 예외처리 방식차이<br>

Test 어노테이션에는 두가지가 있는데,<br>
각 어노테이션마다 예외처리방식이 다르며 다음과 같습니다.<br>

- import org.junit.jupiter.api.Test;
```java
@Test
void 테스트(){
    //given
    //then

 Assertions.assertThrows(IllegalArgumentException.class
}

```


- import org.junit.Test;

```java
@Test(expected= 예외.class)
void 테스트(){
try{
    성공케이스
} catch(예외 e){
    System.out.println(e.getCause());
    throw e.getCause();
}
}
```
개인적으로는 후자가 더 읽기 좋아서 <br>
키덕도 이와같이 사용하고 있습니다.<br>
<br>

2. 디테일은 id로 찾게끔 수정할 것.<br>

시나리오상 처음에 전체유저,키보드 목록을 띄워줬다가<br>
개별디테일로 들어가는 방식이라 클라이언트에서 id값 정보를 가지고 있습니다.<br>
따라서 디테일 객체 조회시 model이나 email를 url 파라미터로 넣었던 것을<br>
요청 바디에 id값을 넣는 방식으로 수정할 예정입니다.<br>
<br>

3. No tests found for given includes:<br>

**문제 :** 테스트환경설정 오류입니다.<br>
**해결 :** Preference > Gradle(혹은 Maven) > Test환경설정을 IntelliJ IDEA로 변경 <br> 
