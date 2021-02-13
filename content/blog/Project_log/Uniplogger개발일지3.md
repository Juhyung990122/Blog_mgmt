---
title: '[Uniplogger]유니플로거 개발일지3'
date: 2020-09-22 01:52:05
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟유니플로거 개발일지 - 3

### 🎯깃허브 링크 
개인연습 : https://github.com/Juhyung990122/Yapp_temp
팀 : https://github.com/Yapp-17th/iOS_2_Backend

### 🎯프로젝트 소개 
조깅을 하며 쓰레기를 줍는 '플로깅'에 재미요소를 가미하여 
일상에서 환경운동에 동참할 수 있도록 돕는 앱서비스입니다.

### 🎯진행내역
- serializer.py과 views.py를 수정하여 랭크 업데이트 시도

### 🎯에러로그
1. "Invalid data. Expected a dictionary, but got MgmtUser."<br>
**문제:** HTTPRESPONSE는 사전형(JSON)으로 넘겨줘야하는데 넘어간 데이터는 ORM타입이라 생기는 문제입니다.<br>
**해결:** serializer = MgmtUserSerializer(data = ...)는 data에 입력된 Json을 ORM형태로 바꿔주는 인자입니다. 
따라서 'data = Json파일' 로 와야하는데, 여기 처음 넣어줬던건 ORM object였고 따라서 serializer.is_vaild()에서 걸렸던 것 입니다. 
(serializer.is_vaild()는 ORM에 데이터를 집어넣기전에 Json파일이 ORM과 같은 형식인지 검사하는 함수)

그런데 애초에 하고싶던건 ORM의 object를 가져와서 rank 값만 갱신하는 것이므로 
ORM object를 JSON으로 바꾸고 다시 그걸 ORM으로 바꾸어 유효성을 검사하는 과정은 불필요합니다.
따라서 해당 코드를 삭제하고 ORM object를 불러온 뒤 serailizer을 통해 직렬화 시킨 후 
정의해둔 rank_save로 rank값을 갱신했습니다. 

**문제:** body에 데이터를 넣어서 넘겨줄 필요가 없어져서 POST가 의미없어짐. <br>
**해결:** 지원하는 method를 GET으로 교체하고, serailizer에서 정의한 
rank_save(request, user_info, data)에서 data는 넘겨받지 않으니까 삭제했습니다. 


