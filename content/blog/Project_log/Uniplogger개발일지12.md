---
title: '[Uniplogger]유니플로거 개발일지12'
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
- 레벨 관리 로직 만들기
- 피드 압축 저장하는 법 알아보기

### 🎯에러로그
1. Image object has no attribute 'write'
이미지 리사이징을 통해 압축저장(PIL -> image활용)
image.save()의 첫번째 인자 입력시 에러발생<br>
2. django에서 PIL 로 압축한 이미지를 인식하지 못함(upload a valid image.)<br>
**문제:** 장고가 인식하는 이미지포멧과 압축된 이미지 포멧이 달라서 생기는 문제입니다.<br>
**해결:** 따로 설정을 해도 인식하지 못하기에 모델 내 필드를 django-resized 의 Resizedfield로 대체하여 해결했습니다.
