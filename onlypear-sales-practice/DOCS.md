# 오로지배 매출관리 (연습)

운영 add-on과 같은 프로그램을 연습용 DB로 한 번 더 띄웁니다. 여기서 입력한 내용은 운영 장부에 남지 않습니다. 자세한 내용은 저장소의 `docs/deployment.md` "연습 서버" 절을 참고하세요.

## 설정

| 옵션 | 설명 |
|---|---|
| `database_url` | 연습 DB. 예) `postgresql+asyncpg://sales_practice:비밀번호@77b2833f-timescaledb:5432/onlypear_sales_practice` |
| `source_database_url` | [연습 데이터 초기화]가 복사해 올 운영 DB. 읽기 권한만 있는 계정으로. 예) `postgresql+asyncpg://sales_practice:비밀번호@77b2833f-timescaledb:5432/onlypear_sales` |
| `login_password` | 연습 서버 로그인 비밀번호(필수). 운영과 다르게 정합니다. |
| `log_level` | 로그 레벨 |
| `bolta_api_key` | 볼타 **테스트** 키(`test_`, 선택). `live_` 키를 넣으면 시작하지 않습니다 |
| `bolta_webhook_token` | 볼타 웹훅 주소의 비밀 토큰(선택) |

## 운영과 다른 점

- DB 덤프(백업)를 만들지 않습니다.
- SFG 메일과 계산서 안내 메일은 설정과 상관없이 `onlypearson-dev@naver.com`으로만 갑니다. 거래처 알림톡은 보내지 않습니다.
- 모든 화면 위에 "연습 중" 띠가 보이고, 영수증·입금표 맨 위에 `[연습용]`이 찍힙니다.
- PC 화면 설정의 [연습 데이터 초기화]로 지금의 운영 데이터를 복사해 옵니다. 이메일은 연습용 주소로 바뀝니다.

## 처음 설치할 때

1. DB `onlypear_sales_practice`와 계정 `sales_practice`를 만듭니다(`docs/deployment.md`의 SQL).
2. 옵션을 넣고 시작합니다. 빈 연습 DB에 마이그레이션이 자동으로 실행됩니다.
3. 내부망에서는 `http://<HA IP>:8003`, 외부에서는 `https://onlypear-sales-practice.onlypearson.com`으로 접속합니다.
4. PC 화면 → 설정 → 메일 설정에 `onlypearson-dev@naver.com`의 애플리케이션 비밀번호를 넣고, [연습 데이터 초기화]를 누릅니다.
