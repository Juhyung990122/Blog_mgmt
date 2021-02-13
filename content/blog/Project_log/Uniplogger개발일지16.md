---
title: '[Uniplogger]유니플로거 개발일지16'
date: 2020-11-03 23:43:10
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---
### 🎯깃허브 링크 
개인연습 : https://github.com/Juhyung990122/Yapp_temp
팀 : https://github.com/Yapp-17th/iOS_2_Backend

### 🎯프로젝트 소개 
조깅을 하며 쓰레기를 줍는 '플로깅'에 재미요소를 가미하여 
일상에서 환경운동에 동참할 수 있도록 돕는 앱서비스입니다.

### 🎯진행내역
- weekly_stats 에러 수정 및 로직 변경
- error msg 포맷 변경

### 🎯에러로그
1. Queryset에서 가장 많이 나온 값의 key값 리턴하기<br>
주간기록 판단기준이 일주일중에 가장 많이 피드를 갱신한 요일을 띄우는 것이었습니다.
이에 datetime으로 일주일을 계산하고 이 기간을 넣어 피드를 필터링 한 뒤
결과값에 `values_list('date')`를 사용하여 date만 뽑았습니다. 
뽑은 date값은 queryset상태이며, 이를 Counter().most_common(1)을 사용하여
최빈값(날짜데이터 : 횟수)을 구했고, 여기서 [0][0][0] 을 붙여 날짜값만 뺴냈습니다. 

2. cron 실행에러<br>
cron 설정 건드렸으면 꼭!! cron 재시작해줘야합니다.
재시작하지 않을 시 서버에서 sync가 맞지 않는다는 에러가 나는데
그떈 침착하게 python manage.py crontab add 를 반복해줍시다.

3. error msg 포맷설정 관련 메모<br>
이건 에러는 아니고 클라쪽에서 처리하기에는 response format을 정해주는게 좋은 듯 합니다.
미들웨어를 커스텀하면 서버 내 대부분의 API에 형식이 적용되며
대부분 위와같은 형식으로 내보냅니다.
```python
{
  "success": true,
  "result": {
    "some": "data"
  },
  "message": null
}
```
msg에서는 detail의 내용을 넣어줘야하니
`response.data['detail']`로 설정해주는게 처리가 편하다고 합니다.
간혹가다가 detail 이 필드명 : [이 필드명이 필요합니다] 형태의 에러메세지가 나오는 경우도 있는데
그땐 필드별로 필터링해주는게 좋습니다. 

참고자료 : https://gyukebox.github.io/blog/django-%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%AF%B8%EB%93%A4%EC%9B%A8%EC%96%B4-%EB%A7%8C%EB%93%A4%EA%B8%B0---rest-framework-%EB%A5%BC-%EC%9C%84%ED%95%9C-http-response-formatting/