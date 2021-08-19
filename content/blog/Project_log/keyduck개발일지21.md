---
title: keyduck개발일지21
date: 2021-08-19 20:41:48
category: Project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 20

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개
기계식 키보드 안내 및 구매 정보제공 웹서비스 

### 🎯진행내역
- 설정파일 환경 분리 및 배포
- 스웨거 재설정

### 🎯에러로그 및 메모
1. swagger에 example body 안나옴<br>
**원인 :** ResponseEntity<?> 처럼 불분명하고 유연한 형식은 swagger가 인식하지 못합니다.<br>
**해결 :** ResponsesEntity<정확한 응답형식> 형태로 수정하면 해결 됩니다.<br>
<br>

2. 헤로쿠 배포시 git push heroku main이 안될때<br>
**원인 :** 브랜치가 메인이 아니거나 어플리케이션 연결이 안되어있기 때문입니다.<br>
**해결 :** 프로젝트 폴더에서 
    ```
    "heroku git:remote -a <애플리케이션 이름>
    ``` 
    과 현재 브랜치가 메인인지 확인해보셔야 합니다.<br>
<br>

3. 헤로쿠에 WAR로 배포하고 싶을때, 일부 명령어가 듣지 않을때<br>
**원인 :** cli 버전이 맞지 않아서 입니다.<br>
**해결 :** heroku plugins:install heroku-cli-deploy로 cli를 다시 설치해줍니다.<br>
배포명령어는 다음과 같습니다.<br>
    ```
    heroku war:deploy build/libs/프로젝트 war파일 이름 --app 헤로쿠 등록한어플리케이션 이름
    ```