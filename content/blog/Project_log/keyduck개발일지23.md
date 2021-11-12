---
title: keyduck개발일지23
date: 2021-11-12 21:41:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 23

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개
기계식 키보드 안내 및 구매 정보제공 웹서비스 

### 🎯진행내역
- 멤버 테스트 코드 리팩토링

### 🎯에러로그 및 메모
1. given, when ,that 절 구분
2. request 객체로 입력값 관리
    기존 : 스트링으로 관리
    이유 : 스트링으로 관리하면 오타발생이나 값이 바뀌었을떄 파악하기 어렵기 때문에
    객체를 따로 생성하여 request를 관리하는 방법으로 변경하였습니다.
3. memberRepository MockBean 으로 등록
    기존 : repository를 직접 bean으로 등록
    이유 : Mockbean을 통해 껍데기만 가져오고, 리턴값을 직접 설정하여 실제 DB에 영향이 없게끔 하였습니다.
    
