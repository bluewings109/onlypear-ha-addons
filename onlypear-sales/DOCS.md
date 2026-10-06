# 오로지배 매출관리

## 설정

| 옵션 | 설명 |
|---|---|
| `database_url` | PostgreSQL 접속 주소. 예) `postgresql+asyncpg://sales:비밀번호@<PostgreSQL add-on 호스트명>:5432/onlypear_sales` |
| `log_level` | 로그 레벨 |

## 처음 설치할 때

1. PostgreSQL add-on에서 DB `onlypear_sales`와 사용자 `sales`를 만듭니다.
2. 이 add-on의 설정에 `database_url`을 넣고 시작합니다. 시작할 때 DB 마이그레이션이 자동으로 실행됩니다.
3. cloudflared add-on에 `onlypear-sales.onlypearson.com` → 이 add-on의 8000 포트 규칙을 추가합니다.
