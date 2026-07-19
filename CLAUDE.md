# CLAUDE.md

## What this is

**Bobathon 소개(랜딩) 페이지** — IBM Bob 고객 초청 해커톤 **Bobathon**의 고객 배포용 단일 페이지. 아젠다·일정·등록 버튼만 담는다. 한국어(`lang="ko"`) 대상.

상세 **진행 페이지**(참가자 안내)는 별도 레포다: <https://kiyeonjeon21.github.io/bobathon-2607/> — 같은 디자인 시스템을 쓴다.

## Structure

빌드 없음, 의존성 없음. 전부 정적 파일이다.

- `index.html` — 페이지 전체. CSS(`<style>`)와 JS(테마 토글 `<script>`)를 인라인으로 담은 단일 파일이다. 별도 CSS/JS 파일 없음.
- `assets/ibmbob.png` — Bob 마스코트 이미지 (히어로 + 파비콘)
- `assets/ibmlogo.svg` — IBM 로고 (실제 페이지의 IBM 8-bar 마크는 `index.html` 안에 인라인 SVG `<symbol id="ibm-8bar">`로 정의되어 있음)
- `DESIGN.md` — 전체 디자인 토큰/시스템 명세. **`.gitignore`에 있어 커밋되지 않음** (로컬에만 존재). 색·타이포·간격을 바꾸기 전에 참고할 것.
- `README.md` — 프로젝트 개요 + placeholder 목록

## Working on it

로컬 미리보기:

```bash
python3 -m http.server 8000   # → http://localhost:8000
```

모든 스타일과 스크립트가 `index.html` 한 파일 안에 있으므로 편집도 그 파일에서 한다.

## Design system — IBM Carbon

- **액센트는 IBM Blue(`#0f62fe`) 하나뿐.** 다른 강조색 추가 금지.
- **모서리 0px** (border-radius 없음), **그림자 없음.** 깊이는 hairline(1px 보더)과 surface 톤 차이로만 표현.
- 색은 전부 `:root`의 CSS 변수 토큰(`--primary`, `--ink`, `--canvas`, `--surface-1`, `--hairline` 등)으로 관리. 하드코딩된 색값 대신 토큰을 쓴다.
- 폰트: IBM Plex Sans / Plex Sans KR / Plex Mono (Google Fonts). 디스플레이(42px+)는 **weight 300**, 본문은 400에 `letter-spacing: 0.16px`.
- **다크 테마**는 Carbon Gray-100 팔레트 — 단순 반전이 아니라 별도로 정의된 값이다. `prefers-color-scheme`를 따르되 `.theme-toggle` 버튼으로 `data-theme` 속성을 덮어쓰고 `localStorage('bobathon-theme')`에 저장한다. 세 곳(미디어쿼리, `[data-theme="dark"]`, `[data-theme="light"]`)의 토큰을 함께 맞춰야 한다.

세부 토큰과 do/don't는 `DESIGN.md` 참조.

## 행사 정보 (전부 확정 · 반영 완료)

- 상위 행사: **AI Summit Korea** / 날짜: **9월 1일** / 시간: **14:00 – 16:00**
- 장소: **웨스틴 서울 파르나스 LL층 앰버룸(Amber)**
- 등록 링크: `https://forms.cloud.microsoft/r/kUjgHAJUQz` — **2곳**(`#registerTop`, `#registerBottom`)에 들어간다. 바꿀 때 한쪽만 고치지 않도록 주의.

시간을 바꾸면 아젠다 표의 `clock` 값(현재 14:00 오프닝 ~ 15:50 플레이백)과 푸터 `.meta` 줄도 함께 맞춰야 한다. 남은 `<!-- TODO -->` placeholder는 없다.

## Conventions

- 커밋 메시지는 **영어**로 작성.
- 사용자 대면 텍스트(페이지 카피)는 한국어.
