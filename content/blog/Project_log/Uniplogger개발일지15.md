---
title: '[Uniplogger]유니플로거 개발일지15'
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
- REST API 테스트 및 수정3 - 미사용필드 정리,rank default값 수정

### 🎯에러로그
**문제:** 필드 정리 이후 서버에 배포하자 삭제된 필드값이 없다는 column에러가 발생했습니다.<br>
**해결:** 우분투 서버에서 ./manage.py makemigrations와 ./manage.py migrate로 서버 내 DB에 변경사항을 반영해주었습니다.

