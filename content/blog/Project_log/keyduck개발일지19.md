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
