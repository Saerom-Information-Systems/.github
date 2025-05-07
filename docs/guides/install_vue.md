# Vue 프로젝트 설치 가이드

다음 프로젝트는 Vue 기반이며 동일한 설치 절차를 따릅니다.

## 설치 절차

1. 저장소 클론
    ```bash
    git clone <레포지토리 주소>
    ```

2. 디렉토리 이동
    ```bash
    cd <프로젝트명>
    ```

3. 패키지 설치
    ```bash
    npm install
    ```

4. 환경변수 파일 `.env` 생성


# Vue build 파일 배포 경로

- {Domino 설치경로}/notesdata/domino/html
   - ex) /local/notesdata/domino/html

# 대상 프로젝트

## 1. vue_portal
### 1) env 설정
```
# config_*.json 파일에서 사용되는 회사 식별 키
VITE_COMPANY=saerom

# portal에서 사용하는 cookie key
VITE_COOKIE=dswg.saerom.sid

# document.title에 표시할 제목
VITE_SSO_TITLE=홈앤+ (홈앤서비스의 모든 공간)

# ====== 여기까지가 SSO 없으면 평범하게 쓰는 값 ======

# SSO 사용 여부 (true | false)
VITE_SSO=true

# SSO에서 사용하는 cookie key
VITE_SSO_COOKIE=sMateJWT

# SSO 로그아웃 페이지 주소 (운영, 개발 따로)
# HNS를 예시로 들면
# 운영: https://sso.homenservice.com/logout.do
# 개발: https://ssodev.homenservice.com/logout.do
VITE_SSO_LOGOUT=https://sso.homenservice.com/logout.do

# ====== 여기까지가 SSO 있면 평범하게 쓰는 값 ======

# 챗봇 사용 여부
VITE_FLOATING_ICON=true

# 챗봇 타입 (예: chatbot_hns - 홈앤서비스용)
VITE_FLOATING_ICON_TYPE=chatbot_hns

# 챗봇 접속 URL
VITE_FLOATING_URL=https://chatbot.example.com

# 챗봇 시큐리티 키
VITE_FLOATING_SECURITYKEY=securekey-example

# 챗봇 환경 (예: live, dev 등)
VITE_FLOATING_ENVIRONMENT=live

# 외부 통합검색 솔루션 사용 여부
VITE_ALL_SEARCH=true

# 외부 통합검색 HOST
# 예: https://search.sebang.com
VITE_ALL_SEARCH_HOST=https://search.sebang.com

# 외부 통합검색 경로
# 예: /sebang/search.jsp
VITE_ALL_SEARCH_PATH=/sebang/search.jsp

# 검색어 파라미터 필드명
# 예: ?q=검색어
VITE_ALL_SEARCH_PRAMNAME=q
```
## 2. vue_approval
### 1) env 설정
```
# Portal 사용여부(true | false)
VUE_APP_PORTAL=true

# config_*.json 파일에서 사용되는 회사 식별 키
VUE_APP_PACKAGE=FOOSUNG
```

## 3. vue_search
### 1) env 설정
```
# config_*.json 파일에서 사용되는 회사 식별 키
VUE_APP_COMPANY=HNS
```
## 4. vue_bbs
### 1) env 설정
```
# Portal 사용여부(true | false)
VITE_APP_PORTAL=true
# config_*.json 파일에서 사용되는 회사 식별 키
VITE_PACKAGE=dev
# 회사별 고유 색깔 지정
VITE_PRIMARY_COLOR='#2b0ebc'
```
## 5. vue_teamspace
### 1) env 설정
```
# Portal 사용여부(true | false)
VITE_APP_PORTAL=true
# config_*.json 파일에서 사용되는 회사 식별 키
VITE_PACKAGE=dev
```
## 6. vue_mobile
### **<span style="color:red">상세 옵션은 해당 repository의 [README.md](https://github.com/Saerom-Information-Systems/vue_mobile/blob/master/README.md) 참조</span>**
### 1) env 설정
 - 운영용(.env)
```
# SSO 사용여부(true | false)
VUE_APP_SSO = false
```
 - 개발용(.env.develop)
 ```
 VUE_APP_SSO = true
VUE_APP_LOGIN = https://ssodev.homenservice.com/mlogin.do
VUE_APP_LOGOUT = https://ssodev.homenservice.com/logout.do
VUE_APP_DOWNLOAD = https://mgwdev.homenservice.com/download/download.html
# 옵션 추가 영역
VUE_APP_ADD_OPTION = true
VUE_APP_ADD_OPTION_FEILDS = VUE_APP_synapHost,VUE_APP_host
# 옵션
VUE_APP_host = https://mgwdev.homenservice.com
VUE_APP_synapHost = https://gwdev.homenservice.com
# 챗봇 추가 영역
VUE_APP_FLOATING_ICON=true
VUE_APP_FLOATING_ICON_TYPE=chatbot_hns
VUE_APP_CHATBOT_URL=https://chatbot.homenservice.com/chatbot/workgroup/hns-ai-faq
VUE_APP_CHATBOT_SECURITY_KEY=ww0ECQMC6Zw7fO0Yuq1s0kABkj8Pb6mv/FBKjla1gmRaV9Z+zw+SlC0G8SusgTy/7nwGIUpGL96VGw1KcbyrpylZ+I9KuJrWPwFPjBwj8qUI
VUE_APP_CHATBOT_ENVIRONMENT=live
NODE_ENV=production
 ```
### 2) config 설정
 1. /src/config/config_sample.json을 복사하여 /src/config/config.json을 생성
 2. config.env 값을 회사명칭으로 변경

## 7. vue_manual
 - 별도의 설정없음
## 8. vue_video
### 1) env 설정
```
VUE_APP_BASE_URL=
VUE_APP_BASE_PATH= /ematenapi/video/video/api/
VUE_APP_BASE_PATH_NOTICE= /ematenapi/video/notice/api/
VUE_APP_API_URL_UPLOAD = videoUpload
VUE_APP_API_URL_CATEGORY = category
VUE_APP_API_URL_SERIES = series
VUE_APP_API_URL_DETAIL = detail
VUE_APP_API_URL_USERINFO = /ematenapi/video/user/api/info
VUE_APP_API_URL_THUMBNAIL = /ematenapi/video/video/api/thumbnail/
VUE_APP_API_URL_PAGING = pagingList
VUE_APP_API_URL_SEARCH = search
VUE_APP_API_URL_RECORD = record
VUE_APP_API_URL_COMMENT = comment
VUE_APP_API_URL_VIEWCOUNT = viewcount
VUE_APP_API_URL_SIGN = sign
VUE_APP_API_URL_LIKE = like
VUE_APP_API_URL_BOOKMARK = bookmark
VUE_APP_BASE_PATH2=/
VUE_APP_API_URL_LOGOUT = /names.nsf?Logout
VUE_APP_API_URL_REPORT = report
VUE_APP_API_URL_LANGUAGE = /ematenapi/video/lang/api/lang
VUE_APP_API_URL_ORGCHART = /ematenapi/video/video/api/orgchart
VUE_APP_API_URL_ORG_SEARCH = /ematenapi/video/video/api/orgchart
VUE_APP_API_URL_ORG_GET_MEMBERS = /emate_org/org/api/member
# 여기까지는 기본설정(변경 필요 X)
# Portal 사용여부(true | false)
VUE_APP_PORTAL=false
```
## 9. vue_pms
### 1) env 설정
```
# 로그아웃시 호출 URL
VUE_APP_API_URL_LOGOUT = /names.nsf?Logout
# Portal 사용여부(true | false)
VUE_APP_PORTAL=false
```
## 10 .vue_calendar
### 1) env 설정
```
VUE_APP_BASE_URL=/
VUE_APP_API_URL =/ematenapi/mail/calendar/api/
VUE_APP_BASE_PATH=/vue_calendar/
# config.json 파일에서 사용되는 회사 식별 키
VUE_APP_COMPANY=SAEROM
# Portal 사용여부(true | false)
VUE_APP_PORTAL=false
```
### 2) config 설정
```json
{
    "default_color": "#574bad", //기본 지정색
    "other_default_color_4_detailcalerndar":"#f1f3f4", //타인 기본지정색
    "datetime_displaytype": 0, //시간 표기방식
    "useEntryCompany": true,
    "DESC_useEntryCompany": "전사일정 사용 유무",
    "useEntryGoogle": true,
    "DESC_useEntryGoogle" : "구글 캘린더 연동 사용 유무",
    "re_deleteOption": {
        "select": true,
        "default": "all",
        "desc": "반복일정 삭제 옵션  select : 선택할건지 , default : select가 false일 경우 defualt값"
    },
    "color": { //추가적인 색상 커스텀
        "borderColor": "#2b0ebc",
        "borderColor2": "#2c9ef1",
        "borderColor3": "#2b0ebc",
        "bgColor": "#cbedf9",
        "textpointColor": "#2c9ef1"
    }
}
```
