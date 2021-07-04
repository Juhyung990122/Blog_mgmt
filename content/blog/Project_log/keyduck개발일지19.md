---
title: keyduck개발일지18
date: 2021-07-03 23:45:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---


## 🌟키덕 개발일지 - 19

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 리뷰 테스트코드 수정


### 🎯에러로그 및 메모
1. @Before, @After
    반복적인 testKeyboard와 testMember 생성과정을 메소드 내에 쓰기보다는 Before와 After 어노테이션을 사용하여 분리하였습니다. 해당 어노테이션은 메소드가 실행될때마다 실행되며 추후 @BeforeAll, @AfterAll로 변경할 예정입니다.(된다면...)
<br>

2. 테스트객체 삭제..
    리뷰테스트쪽에서 review 추가 테스트 부분에 데이터가 추가되고 테스트가 끝나는데 테스트데이터를 디비에 남겨두고 싶지않아서 삭제방법을 고민해보고있습니다. 처음엔 .andrReturn을 통해 결과데이터를 MvcResult로 받아서 String으로 변환한뒤 키보드와 멤버정보를 빼와서 
    그걸 통해 객체조회 및 삭제를 진행하려 했으나 스트링에서 키보드 멤버정보 빼오기가 애매해서 실패했습니다ㅜㅠ 이에 해시맵을 활용하는 방향으로 로직을 바꿀까 합니다.. 근데 될까는 모르겠어요.