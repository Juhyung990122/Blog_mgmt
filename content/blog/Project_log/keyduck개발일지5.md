---
title: Keyduck개발일지5
date: 2021-03-20 15:03:96
category: project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 5

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 유저 어드민 기능 만들기 - R 구축중

### 🎯에러로그
1. 406 Not Acceptable(Could not find acceptable representation)
**문제 :** DTO에서 매핑하고 컨트롤러단에서 리턴하려니 해당 에러가 발생했습니다. <br>
**해결 :** 컨트롤러의 리턴은 Getter를 사용하는데, 해당 DTO 클래스에 Getter가 없어 발생한 에러입니다. 따라서 lombok 에서 제공하는 @Getter를 붙여 해결하였습니다!

