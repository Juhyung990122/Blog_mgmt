---
title: '[Uniplogger]유니플로거 개발일지17'
date: 2020-11-03 23:43:10
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

### 🎯깃허브 링크 
개인연습 : https://github.com/Juhyung990122/Yapp_temp
팀 : https://github.com/Yapp-17th/iOS_2_Backend

### 🎯프로젝트 소개 
조깅을 하며 쓰레기를 줍는 '플로깅'에 재미요소를 가미하여 
일상에서 환경운동에 동참할 수 있도록 돕는 앱서비스입니다.

### 🎯진행내역
- push알림 구현 및 수정

### 🎯에러로그
1. django push notification 라이브러리 작동안됨.<br>
    **문제:**회원가입과 로그인쪽에서 사용하는 jwt와 충돌이 났었습니다.<br>
    **해결:** FCM으로 구현하였습니다.

2. push알림이 주기적으로 발송되지 않음.<br>
lastlogined를 기점으로 3일 7일간격으로 와야하는 푸시알림이 오지 않았습니다.<br>
    **문제:** lastlogined값 설정에 auto_add가 True로 되어있어서 lastlogined 날짜가 자동적으로 갱신되어왔습니다.<br>
    **해결:** auto_add를 False로 바꾸고, 현재시간을 반영해주는 users/update_lastlogined/를 활용하여 접속시간을 갱신합니다. 
