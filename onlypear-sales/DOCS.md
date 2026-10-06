# 오로지배 매출관리

## 설정

| 옵션 | 설명 |
|---|---|
| `database_url` | PostgreSQL 접속 주소. 예) `postgresql+asyncpg://sales:비밀번호@<PostgreSQL add-on 호스트명>:5432/onlypear_sales` |
| `login_password` | 로그인 비밀번호(필수). 화면에서 가려집니다. 바꾸면 add-on을 다시 시작해야 적용됩니다. |
| `log_level` | 로그 레벨 |

> `database_url`은 반드시 **`postgresql+asyncpg://`**로 시작해야 합니다. `postgresql://`로 넣으면 이미지에 없는 다른 드라이버(psycopg)를 찾다가 시작에 실패합니다.

## 처음 설치할 때

1. PostgreSQL add-on에서 DB `onlypear_sales`와 사용자 `sales`를 만듭니다.
2. 이 add-on의 설정에 `database_url`을 넣고 시작합니다. 시작할 때 DB 마이그레이션이 자동으로 실행됩니다.
3. 내부망에서는 `http://<HA IP>:8002`로 접속합니다. 외부 주소는 cloudflared add-on에 `onlypear-sales.onlypearson.com` → `http://<이 add-on 호스트명>:8000` 규칙을 추가해서 연결합니다(인증 구현 후).
