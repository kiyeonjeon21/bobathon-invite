# Bobathon — 소개 페이지

IBM Bob 고객 초청 해커톤 **Bobathon**의 **고객 배포용 소개(랜딩) 페이지**입니다.
아젠다 · 일정 · 등록 버튼만 담은 단일 페이지입니다.

- 상세 **진행 페이지**(참가자 안내)는 별도입니다: <https://kiyeonjeon21.github.io/bobathon-2607/>

---

## 행사 정보 (전부 확정 · 반영 완료)

| 항목 | 값 |
|---|---|
| 상위 행사 | AI Summit Korea |
| 날짜 | 9월 1일 |
| 시간 | 14:00 – 16:00 |
| 장소 | 웨스틴 서울 파르나스 LL층 앰버룸(Amber) |
| 등록 링크 | <https://forms.cloud.microsoft/r/kUjgHAJUQz> (`#registerTop`, `#registerBottom` 2곳) |

남은 placeholder 없음.

---

## 로컬에서 보기

```bash
python3 -m http.server 8000
# → http://localhost:8000
```

빌드 없음, 의존성 없음. `index.html` 단일 파일 + `assets/`.

## 디자인

IBM **Carbon Design System** — 액센트는 IBM Blue(`#0f62fe`) 하나뿐, 모서리 0px, 그림자 없음,
디스플레이(42px+)는 weight 300, 본문에 `letter-spacing: 0.16px`. 다크 테마는 Carbon Gray-100.
전체 토큰은 `DESIGN.md`(레포에는 커밋하지 않음, `.gitignore`) — 진행 페이지와 동일한 시스템입니다.
