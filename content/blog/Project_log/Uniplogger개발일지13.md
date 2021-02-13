---
title: '[Uniplogger]유니플로거 개발일지13'
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
- REST API 테스트 및 수정

### 🎯에러로그
1. {"detail": "Authentication credentials were not provided."}<br>
**문제 :** JWT 활성화 후 API 테스트를 진행하자 뜬 에러입니다.<br>
**해결 :** Authorization: jwt <사용자토큰>을 헤더에 넣고 전송하니 정상적으로 작동되었습니다.
테스트에는 Insomnia라는 REST API 테스트 툴을 사용했지만 
이외에도 프로젝트내에 테스트파일을 생성하여 테스트하는 방법도 있습니다. 코드는 다음과 같습니다.
```python
import requests
import json

def client():    
    token_h = "발급받은 토큰"
    headers = {"Authorization": 'jwt'+token_h}

    response = requests.get("요청보낼 url", headers=headers)

    print("Status Code:", response.status_code)
    response_data = response.json()
    print(response_data)

if __name__ == "__main__":
    client()
```
