---
title: '[Uniplogger]유니플로거 개발일지10'
date: 2020-10-31 15:39:24
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
- 중복 닉네임 방지기능 
- crontab을 활용한 유저상태 스케줄링 작업

### 🎯에러로그
1. 크론탭 실행X<br>
    **문제:** 로그 찍어가며 잘 돌아가던 크론탭이 갑자기 실행이 안됐습니다.<br>
    **해결:** cron 파일내에 코드를 수정하는 과정내에서 실수가 있었습니다.
    에러가 따로 찍히지 않으므로 view에서 완벽하게 돌아가게끔 만든 후에 
    크론탭에는 복사만 하는것을 추천합니다.

2. MYSQL 마이그레이션 dependency에러<br>
    **문제:** 유저가 다른앱들과 dependency가 있어서 migrate 명령어로는 순차적 처리가 안됐습니다.<br>
    **해결:** makemigrations 폴더내의 0001_initial.py 파일 확인후 dependency를 확인한 후 
    dependency에 맞춰서 앱별로 따로 makemigraitons, migrate 해줍니다.
    ```bash
    python3 manage.py makemigrations appname
    python3 manage.py migrate appname
    ```

3. 다음 파일의 로컬 변경 사항을 병합 때문에 덮어 쓰게 됩니다:<br>
     **문제:** git pull 시 pull 받는 파일 내에 변경사항이 있어서 충돌 났습니다. <br>
     **해결:** 저같은 경우는 pull 할 develop 브랜치와 pull을 받을 feature/users 브랜치가
     그닥 차이가 안나서 그냥 맘편하게 받을쪽을 push한뒤 충돌을 해결하는 방식을 택했습니다.
     공백이나 엔터도 변경사항으로 처리되니 비슷한 경우라면 맘편하게 받을쪽을 push 추천합니다. 
     그 다음 pull받아서 둘이 머지한 뒤 충돌나는거 해결했습니다.
     애시당초 브랜치 체크아웃을 잘했으면 안해도 되는 테스크였으니
     git branch로 체크아웃된 브랜치 확인하는 습관을 들입시다..


