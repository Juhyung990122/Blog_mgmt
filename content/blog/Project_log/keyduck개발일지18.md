---
title: keyduck개발일지18
date: 2021-06-27 23:45:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---


## 🌟키덕 개발일지 - 18

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 리뷰 디테일 R기능 수정
- 모벨별 리뷰 R 기능 추가
- 멤버별 리뷰 R 기능 추가


### 🎯에러로그 및 메모
1. Type definition error: [simple type, class org.hibernate.proxy.pojo.bytebuddy.ByteBuddyInterceptor]; nested exception is com.fasterxml.jackson.databind.exc.InvalidDefinitionException: No serializer found for class org.hibernate.proxy.pojo.bytebuddy.ByteBuddyInterceptor and no properties discovered to create BeanSerializer (to avoid exception, disable SerializationFeature.FAIL_ON_EMPTY_BEANS)

    <br>

    **원인 :** 
    다대일 설정이 되어있는 도메인에서 Lazy로딩설정을 걸어놨기 때문입니다. jackson은 도메인에 연결되어있는 타 도메인을 serialize하려 했으나 lazy로딩으로 인해 정상적인 object상태가 아니게되어 발생하는 에러입니다.
    
    <br>
    
    **해결 :** 
    lazy 로딩 설정을 지우고 spring.jackson.serialization.fail-on-empty-beans=false 를 설정파일에 추가했습니다.
<br>
<br>

2. reviewGetDto 수정 예정<br>
    현재 사용하고있는 ReviewGetDto는 member와 Keyboard 모두 도메인 그대로 가져오는데
    이를 개인적으로 지양하고 있기에 DTO로 바꾸려합니다.

<br>

https://jhkang-tech.tistory.com/92