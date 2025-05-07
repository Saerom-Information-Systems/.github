# Node.js 프로젝트 설치 가이드

다음 프로젝트는 Node.js 기반이며 동일한 설치 절차를 따릅니다.

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
    ```
    PACKAGE={config폴더명} 
    MODE={config파일명}
    ```

# 대상 프로젝트

## 1. ematenapi
### config 설정
#### /config/{process.env.PACKAGE}/{process.env.MODE}
    - corsWhitelist : cors Url
    - pathList : api path 허용 경로 리스트
    - sso : sso 관련 설정
    - fileUpload : 파일 업로드 관련 설정
    - pdf : pdf 관련 설정
    - docviewer : 결재문서 등의 원문보기 시 웹페이지를 이미지로 변환하는데 필요한 설정
    - apps.video.domino : video에서 사용하는 domino 관련 설정
    - apps.video.uploadDirectory : video 파일 업로드 경로
    - apps.approval.elasticsearch.index : 완료함 연도별 설정 분리 (회사마다 다를듯)
    - apps.approval.elasticsearch.search.host : Elastic 경로 
    - apps.gw.approval.api.excel.writePath : 전자결재 엑셀 write 경로
    - apps.gw.pms.api.talk : pms 와 talk(메신저) 연동 관련 설정 
    - apps.gw.bbs.megaAttach : 게시판 대용량 관련 설정
    - apps.gw.readcheck.mail : 메일 읽음 관련 설정
    - apps.gw.collabo_messenger : talk(메신저) 관련 설정
    - systems: 전체적인 db, 연동 관련 설정들 -> protocol, server, url 변경
    - proxy.pathList : nginx와 같은 proxy 설정
    - proxy.helmetExceptionList : helmet 라이브러리 예외 url 리스트
    - proxy.session : 토큰 key 명
    - proxy.db : proxy에서 사용하는 db 관련 설정
    - proxy.sso : sso 관련 설정
    - proxy.deadlink : 특정 url 접근 불가 처리 리스트
#### task/portal/config/{process.env.PACKAGE}/{process.env.MODE}
    - sso : sso 관련 설정
    - session.config : session 관련 설정
    - db : db 관련 설정
    - systems : gw 정보 관련 설정
## 2. emate_org
## 3. ematenapi_lei
### config 설정
#### /config/{process.env.PACKAGE}/{process.env.MODE}
    - systems : db, 연동 관련 설정들 -> protocol, server, admin_id, url 변경 필요
## 4. emate_search
## 5. m60
### config 설정
    - host : 모바일 domain
    - host_webserver : nginx를 거치지않는 Domino appl 서버
    - elastic_address : 모바일 Elasticsearch 호출 URL
    - search_elastic_address : 통합검색 Elasticsearch 호출 URL(보통 PC와 같이있음)
    - autoLogin : 자동로그인 관련 설정
    - domino : Domino 로그인 관련 설정
    - ssouse : SSO 사용유무
    - sso : SSO 사용설정(회사별 커스텀 가능성 많음)
    - mongoDB : MongoDB 접속정보 설정
    - appServer : 모바일 domain => editor.js에서 사용 
    - synap : synap 관련 설정
    - epapyrus : epapyrus 관련 설정
## 6. m60_org
### config 설정
    - host : PC domain 
    - elastic_address : 모바일 Elasticsearch 호출 URL
    - domino : Domino 로그인 관련 설정
### app.org.schedule.js node로 실행
    - 처음 데이터만 밀어넣기 (1번만 실행)
    - 추후에는 was(app.js)로 열고 Domino Agent를 통해 호출 
    - m60.orginfo index에서 데이터 확인
        