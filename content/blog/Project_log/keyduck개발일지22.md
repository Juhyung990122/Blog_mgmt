---
title: keyduck개발일지22
date: 2021-09-05 20:41:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 22

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개
기계식 키보드 안내 및 구매 정보제공 웹서비스 

### 🎯진행내역
- 서비스 레이어 테스트코드 작성
- 키보드 get 형식 전환하기

### 🎯에러로그 및 메모
1. Mapstruct 전환안됨.<br>
    **원인 :** mapstruct는 map할때 entity의 setter로 동작하는데 @Setter가 누락되어있었습니다.
    <br>
    **결과 :** @Setter을 추가하여 해결하였습니다.