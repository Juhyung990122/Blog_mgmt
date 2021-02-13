---
title: '[Uniplogger]유니플로거 개발일지6'
date: 2020-10-09 11:43:20
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
- 순위 정렬 알고리즘 추가
- API 기능 리스트업

### 🎯에러로그
1. AssertionError: Expected a 'Response', 'HttpResponse' or 'HttpStreamingResponse'
    to be returned from the view, but received a '<class 'NoneType'>'<br>
    **문제:** Response나 HttpResponse가 형식상 들어가야하는데 넣지않아서 생긴 에러입니다. 

2. AttributeError: 'ListSerializer' object has no attribute 'rank_save'<br>
    **문제:** serializer의 매개변수중 many = True 를 설정할 시 ListSerializer형태로 바뀌게 되는데, rank_save는 일반 ModelSerailizer 내에 선언되어 있어서 발생하는 에러입니다.


