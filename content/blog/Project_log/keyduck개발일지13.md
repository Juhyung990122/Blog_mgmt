---
title: keyduck개발일지13
date: 2021-05-06 05:05:40
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---
## 🌟키덕 개발일지 - 13

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- addKeyboard 수정
- getAllkeyboards, getKeyboardDetail, deleteKeyboard 구현
- 코드 형식 수정

### 🎯에러로그 및 메모
1. HttpMediaTypeNotAcceptableException 406 에러<br>
**문제 :** jackson이 데이터를 변환하려면 비어있는 생성자가 필요한데 dto 클래스에 비어있는 생성자가 없었습니다.<br>
**해결 :** KeyboardGetDto에 NoArg 어노테이션 넣어주어 해결했습니다.