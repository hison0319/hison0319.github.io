---
title: "단어장 프로젝트 포트폴리오 입니다."
date: 2020-09-17 16:02:00 -0400
categories: 프로젝트
---
# Git repository : https://github.com/hison0319/202006tjProject
# 제목 : 단어장(개인 단어장을 만들고 서로 공유하는 웹 서비스)
## 기간 : `20. 6. 22 ~ `20. 7. 16
## 기관 : 더조은 아카데미 컴퓨터학원
## 팀원 : 손한이, 심윤선, 조은지
### 개요 : 개인 단어장을 번역API를 활용하여 문단 삽입 시 자동으로 생성하고, 생성된 단어장을 타 사용자에게 공유하는 기능을 갖는 스프링 프레임워크 기반의 웹 서버 개발

### 1. 화면구성
#### 홈 화면 구성
<img src="/img/wordbook/1.home.jpg"  width="700" height="370">


#### 로그인 화면 구성
<img src="/img/wordbook/2.login.jpg"  width="700" height="370">


#### 화면가입 화면 구성
<img src="/img/wordbook/3.signup.jpg"  width="700" height="370">


#### 카카오톡 로그인 화면 구성
<img src="/img/wordbook/4.kakao_login.jpg"  width="700" height="370">


#### 친구에게 홈페이지 공유하기 화면 구성
<img src="/img/wordbook/5.sns_share.jpg"  width="700" height="370">


#### 공지사항 페이지 화면 구성
<img src="/img/wordbook/6.notice_board.jpg"  width="700" height="370">


#### 공지사항 등록 페이지 화면 구성
<img src="/img/wordbook/7.notice_insert.jpg"  width="700" height="370">


#### 개별 공지사항 페이지 화면 구성
<img src="/img/wordbook/8.notice.jpg"  width="700" height="370">


#### 단어장 등록 페이지 화면 구성
<img src="/img/wordbook/10.wordbook_insert.jpg"  width="700" height="370">


#### 단어장 리스트 페이지 화면 구성
<img src="/img/wordbook/10.wordbook_list.jpg"  width="700" height="370">


#### 단어 리스트 페이지 화면 구성
<img src="/img/wordbook/11.word_list.jpg"  width="700" height="370">


#### 개별 단어 삽입하기 기능
<img src="/img/wordbook/12.word_insert.jpg"  width="700" height="370">


#### 개별 단어 수정하기 기능
<img src="/img/wordbook/13.word_update.jpg"  width="700" height="370">


#### 단어 리스트 정렬 방식 기능(중요단어-입력순서/ 오름차순, 전체단어- 입력순서/ 오름차순)
<img src="/img/wordbook/14.word_array.jpg"  width="700" height="370">


#### 단어장 공유키 발급 및 복사 기능
<img src="/img/wordbook/14.wordbook_sharing_key.jpg"  width="700" height="370">


#### 단어장 공유키 카카오톡으로 바로 전송하기 기능
<img src="/img/wordbook/15.wordbook_sharing_key_kakao.jpg"  width="700" height="370">


#### 단어장 리스트 정렬 방식 기능(중요, 소유, 공유 단어장)
<img src="/img/wordbook/16.wordbook_array.jpg"  width="700" height="370">


#### 마이페이지 화면 구성 및 메일 인증하기 기능
<img src="/img/wordbook/17.mypage.jpg"  width="700" height="370">


#### 마이페이지 수정 시 비밀번호 재확인 기능
<img src="/img/wordbook/18.mypage_password.jpg"  width="700" height="370">


#### 회원 정보 수정 기능 구성 화면
<img src="/img/wordbook/19.mypage_update.jpg"  width="700" height="370">


#### 공유 단어장 및 공유 멤버 리스트 확인 기능
<img src="/img/wordbook/20.sharing_list.jpg"  width="700" height="370">


#### 공유 취소 기능
<img src="/img/wordbook/21.sharing_member_list_and_delete.jpg"  width="700" height="370">


### 2. 요구사항 정의서(기능 정리)
>> * 회원가입 서비스
>>> - 기본 회원 가입
>>>> + 프론트 엔드 유효성 검사(javascript, jquery)
>>>> + 벡엔드 유효성 검사(dependency hibernate-validator, validation-api)
>>>> + 이용약관 동의
>>>> + 데이터 베이스 무결성 검증(DB 외래키, 유니크키)
>>>> + 주소 API (DAUM API)
>>> - 카카오톡 회원 가입
>>>> + 카카오톡 회원정보 가져오기 (REST 방식 카카오 디벨로퍼 활용)
>>>> + 추가 정보 삽입 후 회원가입
>> * 로그인 서비스
>>> - 기본 로그인 
>>>> + 아이디/ 비밀번호 유효성 검사
>>> - 카카오톡 로그인
>>>> + 카카오톡 로그인 (REST 방식 카카오 디벨로퍼 활용)
>>>> + 제공되는 정보 변형 및 DB저장
>>> - 아이디/ 비밀번호 찾기
>>>> + 아이디 분실 시 메일 정보 제공
>>>> + 해당 메일로 임시 비밀번호를 생성해 메일 보냄 (dependency javax.mail)
>> * 로그아웃 서비스
>>> - 로그아웃
>>>> + 세션에 저장된 회원 정보 삭제
>>>> + 세션에 저장된 카카오톡 토큰 정보 삭제
>> * 마이페이지
>>> - 내정보 보기
>>>> + DB에 저장된 내 정보를 확인할 수 있는 페이지
>>>> + 내 정보 수정 가능, 수정 시 유효성 검사. 메일 수정 시 기존 메일 인증 취소
>>> - 메일 인증
>>>> + 메일 인증을 해야 단어장 생성 가능.
>>>> + 임시 키 생성, 메일 전송 해당 브라우저에서 키 확인. 인증된 사용자로 전환
>>> - 공유단어장 목록 확인
>>>> + 공유된 단어장 조회 기능 (ajax비동기식)
>>>> + 공유된 단어장 공유 취소 기능 (ajax비동기식)
>>> - 공유 친구 목록 확인
>>>> + 공유된 친구 조회 기능 (ajax비동기식)
>>>> + 공유된 친구 공유 취소 기능 (ajax비동기식)
>> * 공지사항
>>> - 공지사항 조회
>>>> + 로그인 상태가 아니어도 공지사항 조회 가능
>>>> + 한 페이지 당 5개의 공지사항 표시. 페이지 네이션 5개씩 하단 표시
>>> - 공지사항 삽입, 수정, 삭제
>>>> + 운영자 아이디 확인. 운영자가 아닐 시 행위 불가 (기본키 값 20이하의 아이디를 운영자 아이디로 설정)
>>>> + 공지사항 삽입, 수정 (summernote-0.8.18, bootstrap-3.4.1, jquery-3.5.1)
>>>> + 공지사항 삽입, 수정 시 유효성 검사
>> * 단어장
>>> - 단어장 생성
>>>> + 회원 인증이 안된 회원은 단어장 만들기 페이지 진입 시 이메일 인증 창으로 이동
>>>> + 단어장 제목 공백, 특수문자 불가. 유효성 검사
>>>> + 문장단위의 문단을 넣을 시 단어 – 의미(번역)로 변경 되어 자동 저장 (파파고API)
>>>> + 문단에서 많이 사용된 단어 순서로 정리
>>>> + 텍스트 파일 삽입 시 동일한 결과 제공
>>>> + 단어장 생성 버튼 중복 클릭 방지
>>>> + 단어장은 텍스트 파일로 생성되고 DB에는 파일 주소가 저장됨
>>> - 단어장 공유키 생성
>>>> + 단어장 생성 창에서 공유키 란에 타 사용자에게 받은 공유키를 입력, 생성버튼 클릭 시 공유된 단어장 생성 가능
>>> - 단어장 조회, 수정, 삭제
>>>> + 조회된 단어 리스트에서 수정, 삭제 기능 (ajax비동기식)
>>>> + 중요한 단어 지정 기능 (ajax비동기식) 
>>>> + 중요단어, 입력순서, 오름차순 정렬방식 기능 제공
>>>> + 수정 시 개별 단어 추가뿐 아니라 장문으로 추가하여 자동으로 단어로 정리되는 기능 구현
>> * 단어장 리스트
>>> - 단어장 조회
>>>> + 단어장 목록 조회 기능
>>>> + 최근 수정, 중요 단어장, 소유 단어장, 공유 단어장 정렬 기능
>>>> + 단어장 키워드 검색 기능
>>>> + 중요 단어장 체크 (ajax비동기식)
>>>> + 소유 단어장 공유키 자동 복사 기능
>>>> + 소유 단어장 공유키 카카오톡으로 바로 전송하기 (카카오톡 전송 javascript, 카카오 디벨로퍼 활용)
>>>> + 페이지 당 6개 단어장 출력 하단 페이지 리스트 제공
>>>> + 단어장 삭제하기 기능. 삭제하기 시 확인 텍스트 입력 기능
>> * 기타
>>> - SNS공유
>>>> + 카카오톡으로 홈페이지 공유하기
>>>> + 트위터로 홈페이지 공유하기
>>>> + 페이스북으로 홈페이지 공유하기
>>>> + 네이버 블로그로 홈페이지 공유하기 (각 API, javascript)
>>> - 에러처리
>>>> + 에러 발생 시 개발자 메일로 에러사항 전송기능
>>> - 프론트 엔드
>>>> + 반응형 웹 페이지. (템플릿 사용, 프로젝트 적용)


### 3. ERD
<img src="/img/wordbook/ERD.jpg"  width="700" height="370">


### 4. Class Diagram
<img src="/img/wordbook/classDiagram1.jpg"  width="700" height="370">
<img src="/img/wordbook/classDiagram2.jpg"  width="700" height="370">
<img src="/img/wordbook/classDiagram3.jpg"  width="700" height="370">
<img src="/img/wordbook/classDiagram4.jpg"  width="700" height="370">


### 5. 개발 환경
> 1. 개발 환경
>> *	Java 11.0.6
>> *	Apache Tomcat 9.0.35
>> *	MySQL 8.0.20
>> *	Spring 3.9.13
>> *	Servlet 4.0
>> *	Jquery 1.12.4
>> *	Window10, eclipse 4.15.0, HTML5, CSS3, Bootstrap 3.4.1, JSP 2.3
