---
title: keyduck개발일지10
date: 2021-04-07 19:04:00
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 10

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 예외처리 REST식으로 변경
- Controller 테스트코드 작성
- Swagger 사용하여 문서화

### 🎯에러로그 및 메모
1. RestControllerAdvice로 예외들 처리하기
    일단 예외상황에 날아가는 리턴포맷을 통일해줄 수 있게끔 getFaultResult 클래스를 정의해주었습니다. 이렇게 포맷을 통일해두면 클라이언트쪽에서 좀더 이해하기 쉬운 형태로 응답이 갑니다. 포맷은 code와 msg를 선언해서 http상태코드와 예외상황이 발생한 이유를 담아 리턴하게끔 했습니다.
2. CustomException 만들기 + 메세지 따로 설정하는법
    기본적으로 spring에서 제공하는 표준예외 이외에 사용할 예외가 필요했습니다.(비밀번호 불일치상황이나...) 그래서 RuntimeException을 상속받아 CustomException을 만들고
    메세지를 직접 입력할 수 있게끔 오버로딩하여 사용했습니다.
    ```java
    public class CustomException extends RuntimeException {
    public CustomException(String msg){
        super(msg);
        }
    }
    ```
    하지만 이럴거면 그냥 RuntimeException에 메세지만 주면 되지않나..라는 생각이 좌우뇌를 스치고...ㅎ 커스텀예외를 사용할만한 상황을 생각해보니 메세지에 범위값이나 필드처럼 이것저것 정보가 많이 들어갈때 사용하면 좋을 것 같더라구요!.. 그래서 일단 지금 커스텀예외는 삭제하고 필요할때 사용할까 합니다...ㅎㅎ


https://cheese10yun.github.io/spring-guide-exception/