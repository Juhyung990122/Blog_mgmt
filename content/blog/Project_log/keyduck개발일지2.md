---
title: Keyduck 개발일지2
date: 2021-03-03 20:03:61
category: project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 2

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 토큰 발급 및 유효성 확인 로직구현
- 로그인 기능 완성
- 권한별 설정 완료

### 🎯에러로그 및 메모

1.  No default constructor for entity<br>
**문제 :** Entity 객체내에 생성자가 없어서 나는 에러입니다. <br>
**해결 :** 생성자 어노테이션을 붙여 해결했습니다. <br>
```java
@NoArgsConstructor
@AllArgsConstructor
```
둘중 하나만 쓰면 빌더쪽에서 에러가 나던데 그건 왜그런지 모르겠....
<br><br>

2. DI 생성자 주입방식
```
public class BoardService {

    private BoardDao boardDao;

    // @Autowired Spring 4.3 버젼 부터 @Autowired 생략가능
    public BoardService(BoardDao boardDao) {
        this.boardDao = boardDao;
    }
}
```
더 간단하게 하려면 롬복의 어노테이션을 추가합니다.
```
@Service
@AllArgsConstructor
public class BoardService {

    private BoardDao boardDao;

}
```
Immutability  문제까지 해결
```
@Service
@RequiredArgsConstructor
public class BoardService {

    private final BoardDao boardDao;

}

```

https://leejisoo860911.tistory.com/2