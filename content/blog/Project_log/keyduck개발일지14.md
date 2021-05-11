---
title: keyduck개발일지13
date: 2021-05-06 05:05:40
category: project_log
thumbnail: { thumbnailSrc }
draft: false
---
## 🌟키덕 개발일지 - 13

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- url 포맷 변경
- 설정파일 복구
### 🎯에러로그 및 메모
1. url에 한글 넣지 않기<br>
    keyboard 디테일페이지와 삭제페이지 url을 keyboards/상품명/ 으로 설정했었는데 <br>
    이렇게 하면 웹사이트 상에서 볼때 링크창에 갑자기 한글이 나와서 통일성이 좀 떨어지기도 하고 <br>
    복붙할때 url encoding때문에 링크가 어마무시하게 길어질 수 있어 상품 아이디값으로 수정했습니다.<br>

2. 설정파일 복구
    바로 어제.. 제 맥북(뿌기..)가 갑자기 눈을 뜨지 못하게 됐습니다...<br>
    중요한 프로젝트들은 다 깃헙에 올라가있어서 괜찮았는데 <br>
    문제는 gitignore시켜둔 설정파일들(secret.json, application.xml 등...) 뿌기와 함께 눈을 감았습니다<br> 
    다행스럽게도 설정파일들이 많지 않았고 기억이 나서 복구에 성공했지만 <br>
    클라우드나 외장하드에 틈틈이 백업시켜놓는 습관을 들여야 겠다고 생각했습니다.<br>
