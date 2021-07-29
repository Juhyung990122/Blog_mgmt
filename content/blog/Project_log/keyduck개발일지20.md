---
title: keyduck개발일지18
date: 2021-07-03 23:45:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---


## 🌟키덕 개발일지 - 19

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 다중요소 검색기능 추가
- 결과 나올때까지 조건빼면서 재검색 기능 세팅


### 🎯에러로그 및 메모
1. "Content type 'application/octet-stream' not supported"

**원인 :** 해당 입력형식을 지원하지 않아서 디폴트 content-type으로 인식하여 나는 에러입니다.

**해결 :** 입력형식을 다시 맞춰주면 됩니다,
저같은 경우 text(multiline) 으로 바꾼뒤 JSON으로 전송하자 해결되었습니다.