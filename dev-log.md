# 2020.06.07

# 회의 내용

API 관련

- 어떤 공공데이터 API 사용할지 결정
  => 질병 발생 데이터 사용
- 앱에 어떻게 적용할지 논의
  => 가져온 API 데이터 -> csv 포맷의 정적 데이터
  => 해당 데이터를 firebase 데이터베이스에 sync

개발 계획 수립

- 로그인 기능
  => UI design
  => sign-up and authentication method 결정
  => 이메일 인증 및 전화번호

- 프로필 페이지
  => name@Farm, location, owner, introduce message

# Todo!

Github

- organization 생성 ✔️
  =>https://github.com/Sunny-Fresh-Farm/
- 안드로이드 클라이언트 리포지토리 생성 ✔️

# 2020.06.08

# 회의 내용

개발 계획 수립

- 메인 페이지
  => 맵 액티비티 구현
  => 가져온 질병 데이터의 발생 주소 정보를 지도에 표현
  => 어떤 지도 API 사용할지 결정 : naver map api 사용 예정

- 정보 페이지
  => 뉴스 정보 표시
  => 광고 정보 표시를 통한 수익 창출
  => 내 프로필 정보 받아오기 및 수정

# Todo!

Naver Map API

- 회원 가입 및 사용 신청 ✔️
- 앱에 지도 페이지 연동 ✔️

# 2020.06.09

# Todo!

프로필 페이지

- UI 구현 ✔️
- 수정 페이지 ✔️
- 다른 유저의 프로필 조회 😅
  => 데이터베이스 아직 미연동 상태로 구현 실패

공공데이터 API 접목

- 데이터 저장 및 서버 업로드 ✔️
- 데이터 사용성 및 앱 방향성 검토 😅

<!--  사용한 API 정보 -->

1. 가축 질병 정보
   http://data.mafra.go.kr/opendata/data/indexOpenDataDetail.do?data_id=20151204000000000564&service_ty=&filter_ty=G&sort_id=rdcnt&s_data_nm=&cl_code=&instt_id=&shareYn=

2. 발생했던 질병 정보
   http://data.mafra.go.kr/opendata/data/indexOpenDataDetail.do?data_id=20151204000000000563&service_ty=&filter_ty=G&sort_id=rdcnt&s_data_nm=%EC%A7%88%EB%B3%91&cl_code=&instt_id=&shareYn=

# 2020.06.11

# 회의 내용

- 앱 콘셉트 점검
  => 유사 어플리케이션 발견
  => 동일 공모전 이전 수상작 : 건강한 우리 가축

- 유사점

1-1. API : 활용 데이터의 중복성

1-2. 목적 : 위치기반 가축질병 발생현황정보
1-3. 기능 : 가축질병정보 제공
1-4. 기능 : 방역 단체 신고 기능

- 차별점

1-4'. 기능상의 차별점 : (기존) 전화를 통한 App 외부의 연락 수단 사용 vs (우농푸) App 내에서의 연락 수단 사용
1-5. 기능 : 데이터를 분석하여 질병 발생 예측
=> EX. 최근 1주일 내의 전염병 목록 분석 => 암소 대상 결핵 10번 발생 시 특별 경고 알림 발생(PUSH, 공지사항, 특정 지역 대상 가능)
=> 관련 링크 : 농림축산식품 공공데이터 포털, 가축 질병 전염 정보 : http://data.mafra.go.kr/opendata/data/indexOpenDataDetail.do?data_id=20151204000000000563&service_ty=&filter_ty=G&sort_id=rdcnt&s_data_nm=&cl_code=&instt_id=&shareYn=
=> 자세한 사항 추가 논의 필요(Pending Issue 참고)

# Todo!

기능 추가

- firebase function을 이용한 데이터 분석 및 푸쉬 알림 기능
  => 동일 지역 다수 질병 발생 시 푸쉬 알림 보내기

# 2020.06.12

# Todo!

- 로그인 페이지 버그 디버깅
  => 로그인 대기 시간 중, 버튼 다중 입력 시 여러번 앱이 시작되는 버그 발견
  => 로딩 중 다른 function 실행 차단 ✔️

- 가축 선택 페이지 구현 ✔️

# 2020.06.13

# Todo!

푸쉬 알림 보내기

- database base triggered function 구현
  => using typescript and async task
  => getting token from user device
  => firebase FCM 기능 사용
  => 개인 모바일 기기에 대한 실험용 알림 구현 ✔️

- 질병 발생 정보 리스트 UI 생성 ✔️
  => client 내부에서 firebase sdk 를 받아와 db 접근
  => 받아온 데이터를 recycler view를 통해 실시간 업데이트
  => kotlin callback function 사용

# 2020.06.14

프로토타입 어플리케이션 작업 완료

# Todo for later

- 디자인 수정 => 좀 더 직관적으로
- 질병 신고 및 신고 처리 기능 구현
