---
title: '[Uniplogger]유니플로거 개발일지4'
date: 2020-09-22 01:52:05
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
- drf-yasg를 사용한 문서화
- 데이터베이스 설정 변경(sqlite3 -> MYSQL)

### 🎯에러로그

1. ERROR: Command errored out with exit status 1: python
setup.py egg_info Check the logs for full command output.<br>
**문제:** pip 로 mysqlclient를 설치할때 발생하는 에러입니다. <br>
**해결:** homebrew 설치 후 mysql, mysqlclient를 깔아준 뒤 pip 로 mysql을 깔아 해결하였습니다.

2. ERROR 1046 (3D000): No database selected<br>
**문제:** mysql에서 데이터베이스 조회를 할때 어떤 데이터베이스를 조회할건지 설정하지 않아서 생긴 에러입니다.<br>
**해결:** use tablename 으로 설정하여 해결하였습니다.