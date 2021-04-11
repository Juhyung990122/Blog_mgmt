---
title: Keyduck개발일지9
date: 2021-03-30 20:03:10
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---
## 🌟키덕 개발일지 - 9

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- API 인터페이스 및 결과 표준화
- 일부 예외처리 변경

### 🎯에러로그 및 메모
1. 결과 데이터의 구조를 표준화했지만..
    오늘 에러는 딱히 없었으나 표준화된 구조가 좀 마음에 안드는게 있습니다.
    - error 메세지가 부실하다는 점
    - Exception을 활용하지 않고 야매롭게? 예외처리가 되어있어서 정해진 에러 외에는 예외처리가 안된다는 점
    - status는 200인데 메세지로 보면 에러인 경우가 있다는 점(REST에 위배된다ㅠ)
    아마 내일쯤 https://sanghaklee.tistory.com/57 를 참고하여 Service와 Controller의 전반적인 구조를 변경해보려합니다. 추가로 error에 대한 상태값과 에러메세지도 포함할 예정입니다. 