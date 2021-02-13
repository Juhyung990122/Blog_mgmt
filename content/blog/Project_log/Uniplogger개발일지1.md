---
title: '[Uniplogger] 유니플로거 개발일지1'
date: 2020-09-22 01:52:05
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟유니플로거 개발일지 - 1 

### 🎯깃허브 링크 
개인연습 : https://github.com/Juhyung990122/Yapp_temp
팀 : https://github.com/Yapp-17th/iOS_2_Backend

### 🎯프로젝트 소개 
조깅을 하며 쓰레기를 줍는 '플로깅'에 재미요소를 가미하여 
일상에서 환경운동에 동참할 수 있도록 돕는 앱서비스입니다.

### 🎯진행내역
- DRF를 활용한 모델설계(4/7)
- 기본 CRUD기능


### 🎯에러로그
1. SystemCheckError: System check identified some issues:
    ERRORS:
    User.MgmtUser.groups: (fields.E304) Reverse accessor for 'MgmtUser.groups' clashes with reverse accessor for 'User.groups'.<br>

    **문제:**기본유저모델을 커스텀했는데 커스텀한 버전을 디폴트로 안해놔서 발생한 에러입니다. <br>
    **해결:**settings.py밑에 AUTH_USER 환경변수를 커스텀버전으로 설정합니다.

2. AttributeError:'str'object has no attribute 'values'<br>
    **문제:** Quest 모델에서 필드값을 불러올때 str객체로 인식하여 발생한 에러입니다.<br>
    **해결:** 시리얼라이저에 class Meta:를 추가해줍니다.