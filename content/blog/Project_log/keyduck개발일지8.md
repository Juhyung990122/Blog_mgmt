---
title: Keyduck개발일지8
date: 2021-03-28 17:03:32
category: project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 8

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 회원관련 기능 예외처리 및 마무리

### 🎯에러로그 및 메모
1. There is no PasswordEncoder mapped for the id "null"<br>
    **문제 :** Spring security의 passwordEncoder가 업데이트 되면서 생긴 에러였습니다.<br>
    **해결 :** 패스워드 앞에 {id} 를 추가하면 된다는 자료를 보고 회원가입시 패스워드 인코딩과정과 로그인시 패스워드 일치여부판단할때 MemberLoginDto의 password앞에 "{noop}"을 붙여 해결했습니다.

