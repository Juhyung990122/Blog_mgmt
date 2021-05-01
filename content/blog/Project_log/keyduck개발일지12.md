---
title: keyduck개발일지12
date: 2021-05-01 17:05:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 12

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
    - addKeyboard 기능 추가
    - addKeyboard 테스팅
    - swagger 권한 추가 

### 🎯에러로그 및 메모
1. swagger 접속오류
    **문제 :** webconfig내의 권한 조건을 통과하지 못해서 생긴 에러였습니다.
    **해결 :** antMatchers()에 스웨거 관련 url을 넣어 해결하였습니다. 