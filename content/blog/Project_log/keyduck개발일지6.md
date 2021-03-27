---
title: Keyduck개발일지6
date: 2021-03-22 22:03:05
category: project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 6

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 유저 어드민 기능 만들기 - R(회원디테일)
- Entity를 DTO로 매칭하여 리턴하기

### 🎯에러로그 및 메모
1. ModelMapper vs Mapstruct<br>
    일전에 프로젝트를 마치고 적은 목표들 중 Entity가 아닌 DTO로 리턴하기가 있었는데<br>
    이를 일일이 하다보면 필드가 누락될 수도 있고, 사소한 실수가 있을 수 있습니다.<br>
    이런 상황을 방지하고 반복과 중복을 최소화 하기위하여 찾아본 것이 Mapper였고<br>
    가장 유명한 두가지를 비교하여 성능과 처리량이 좋은 Mapstruct를 사용하기로 했습니다.
    <br>
    성능관련 참고글 = https://www.baeldung.com/java-performance-mapping-frameworks 
    <br><br>
2. 'Service' required a bean of type 'Mapper' that could not be found.<br>
Consider defining a bean of type 'Mapper' in your configuration.<br>
    <br>
    **문제 :** 도입에 있어 크게 두가지 문제점이 있었는데 그중 하나는 lombok과 mapstruct 사이에 뭔일이 났는지 Service 단에서 @Autowired로 Mapper 주입하면 interface로 선언해둔 Mapper의 implement가 없다는 에러가 떴습니다.<br>
    <br>
    **해결 :** 찾아보니 이클립스 사용자한테서 발생하는 문제라고 합니다...휴ㅠ 
    https://sonbbang78.tistory.com/2 다음 링크에서 제시하는 방법대로 해보았으나 
    .apt_generated에 Impl파일이 안만들어져서 실패...ㅎ
    결국 2일정도 끙끙대다가 Intellij로 바꾸었습니다.
<br>
<br>
3. Intellij dependency 설정<br>
    플러그인으로 Mapstruct Support 다운로드 한 후 build.gradle에
    ```Java
    plugin{
        ...
        id 'net.ltgt.apt' version '0.15'
    }
    apply plugin: "net.ltgt.apt"
    dependencies{
        ...
        lombok
        compile('org.mapstruct:mapstruct:1.3.0.Beta2')
        compileOnly('org.mapstruct:mapstruct-processor:1.3.0.Beta2')
        annotationProcessor('org.mapstruct:mapstruct-processor:1.3.0.Beta2')
    }
    ```
    를 작성해줍니다.(작성을 다하면 꼭 gradle을 다시 빌드해주세요.) 이후 Mapper코드를 작성하고, Service에는 @autowired를 사용하여 Mapper를 주입시켜줍니다. 
