---
title: keyduck개발일지16
date: 2021-05-10 22:45:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---


## 🌟키덕 개발일지 - 16

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- likes 기능 추가 및 수정

### 🎯에러로그 및 메모
처음에는 백엔드쪽에서 member와 keyboard 사이에 <br>
scrap이라는 모델을 두고 CRUD를 하려했습니다 <br>
하지만 프론트와 회의한 결과 로컬에서 데이터를 갖고있다가<br>
로그아웃하는 시점의 로컬데이터만 백에 저장하는 것이 <br>
서버쪽에서도 요청처리가 덜할 것 같다는 결론이 났습니다.<br>
혹시몰라 미리 구현하던 과정에서 복합키에 대한 것들을 학습하였고,<br>
이에 대한 것은 추후 TIL로 작성할 예정입니다.<br>
<br>
아니 근데 likes가 member쪽 필드고.. 이걸 갱신하는 기능이긴 한데.. <br>
좀 애매한게 memberController는 그냥 진짜 회원에 관련된 기능들(가입이나 탈퇴, 프로필설정..등등)이라서<br>
좋아요 해둔 키보드들 갱신하는건 memberController쪽에 들어가기엔 은근 이질적인 느낌... <br>
그래서 likes 관련된 컨트롤러랑 서비스랑 다 따로 파고<br>
<br>

```
    member 
        ㄴ controller
            ㄴ memberController
            ㄴ likesController

        ㄴ service
            ㄴ memberService 
            ㄴ likesService 
```

<br>
요렇게 해뒀는데 이게 맞는지.. <br>
아니면 아예 likes를 member 외부로 빼야하는건지..<br>
아니면 member안에 likes 디렉토리 만들고 따로 넣어야하는건지...<br>
모르겠어요..8ㅅ8..<br>

