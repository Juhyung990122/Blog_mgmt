---
title: Keyduck개발일지3
date: 2021-03-05 12:03:86
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 3

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- VO에 프로필 추가
- 이미지 업로드 구현

### 🎯에러로그 및 메모

1. multipartfile는 Getter,Setter을 직접 작성해주어야합니다. (롬복은 안먹혔음)
<br><br>
2. MultipartFile cannot be cast to class java.sql.Blob<br>
**문제 :** JPA에서는 MultipartFile을 지원하지 않아서 생기는 에러입니다. <br>
**해결 :** 필드값 위에 @Lob 어노테이션을 붙여줍니다.  <br>@LOB는 대용량데이터를 처리하기위한 타입입니다.<br> 본 프로젝트에서는 이미지를 저장하기 위해 다음의 과정을 거쳤습니다. <br>

    * @PathVariable로 이미지 받기
    * 이미지를 받아서 경로값으로 파싱
    * 파싱한 이미지 경로값을 DB에 저장
    * 해당 경로값 GET 요청시 이미지 로드
<br><br>
3. File처리에는 예외처리가 필수입니다.


