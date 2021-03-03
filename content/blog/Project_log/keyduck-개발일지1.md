---
title: Keyduck 개발일지1
date: 2021-02-28 23:02:82
category: project_log
thumbnail: { thumbnailSrc }
draft: false
---

## 🌟키덕 개발일지 - 1 

### 🎯깃허브 링크 
https://github.com/Juhyung990122/Keyduck_back

### 🎯프로젝트 소개

### 🎯진행내역
- 기본환경 세팅
- 유저단 VO, DTO 설정
- 회원가입 기능 구현

### 🎯에러로그 및 메모

1. security할때는 webconfig에서 보안 일단 다 풀어두어야합니다<br>
```Java
@Override
	protected void configure(HttpSecurity http) throws Exception {
		http
		.csrf()
		.disable();
		
		http
		.headers()
		.frameOptions() 
		.disable();	
	}
```
2. DTO는 또하나의 객체, 모델 원본을 안건들기위한 또하나의 객체를 생성한다고 보면 편합니다.<br>
3. 리턴값에서 제외하고싶은 필드는 Jsonproperty에서 접근권한을 WO로 해두어야합니다.
JsonIgnore하면 deserializer했을때 데이터가 없습니다ㅎ
```Java
@JsonProperty(access = JsonProperty.Access.WRITE_ONLY)
	private 필드형식 필드이름;
```
<br>
5. 리턴은 일단 포맷 맞추기전까지 ResponseEntity<?>로 통일합니다.

6. VO에서는 Setter을 안줬습니다. 일전에 이야기했던 일관성문제나 코드의 가독성을 위해 
builder컨셉으로 바꾸었기 때문입니다. 다만 이번 DTO에서는 Setter을 사용했는데
Controller에서 @RequestBody로 외부에서 데이터를 받는 경우엔 기본생성자 + set메소드를 통해서만 값이 할당되기때문에 setter을 허용하고 있습니다.

참고자료 - https://github.com/alalstjr/Java-spring-boot-security-jwt

