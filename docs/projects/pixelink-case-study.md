# PIXELINK 케이스 스터디 원고 (4장)

포트폴리오 저장소 `case/pixelink.html`에 넣기 위한 원고와 이미지. 디자인 언어는 **장난감·스티커·폴라로이드** (시스템·HUD 문법 사용 금지). 글은 배경 위에 그냥 두지 않고 패널이나 이미지 캡션 안에 넣는다. 확인이 필요한 곳은 `(추후)`로 표시했다.
이미지는 `img/`(webp)에 있다. BUILD TRACK 이미지는 `../build-track/`, 기획서 PDF는 `../../docs/PIXELINK_기획서.pdf`.

---

## 01 · CHALLENGE
**커버 이미지**: `img/result1_hero.webp`

**과제 패널**
- 과제: 픽셀 레트로와 사이버팝을 섞은 오리지널 캐릭터 브랜드 사이트. 인트로부터 메인까지 한 번에 이어지고, 굿즈 소개가 우선이면서 캐릭터를 직접 만져 보는 경험을 갖는 사이트.
- 목표: 캐릭터(CHI:EE · LEENKI · GLEEN)를 소개하고, 입어 보기 → 알게 되기 → 모으기 → 갖기(실물 굿즈)로 이어지는 흐름의 첫 단계를 만든다.

**개요 패널**
| 항목 | 내용 |
|---|---|
| 유형 | 오리지널 캐릭터 IP 브랜드 사이트 (인트로 + 메인 + 서브페이지) |
| 역할 | 기획·브랜드 방향·화면 결정: miint.s0da / 구현은 AI 도구와 협업 (표기 문구 확인 필요) |
| 기술 | HTML / CSS / JavaScript 단일 파일, WebAudio, PWA, Vercel |
| 상태 | 재작업 중, 1차 오픈 전 |

---

## 02 · UX
**사용자 흐름 한 줄**: 인트로(카세트 삽입) → 메인 히어로 PRESS START → 캐릭터·아트워크·월드·굿즈 탐색 → 드레스룸에서 CHI:EE 입혀 보기

**근거 카드 3개**

| # | 이미지 | 문제 | 해결 |
|---|---|---|---|
| 1 | `img/ux1_intro.webp` | 방문할 때마다 인트로가 나오면 메인을 확인하는 데 방해가 된다 | 처음 방문에만 30일간 1회, SKIP 버튼·Esc, 메인의 INTRO 버튼으로 다시 보기 |
| 2 | `img/ux2_sound.webp` | PC 브라우저는 첫 클릭 전에 소리를 막고, 섹션마다 소리 크기가 달라 어떤 곳은 거의 안 들린다 | 첫 클릭에서 소리를 열고 잠금 상태를 표시, 소리마다 크기를 측정해 맞추고 5단계 볼륨 + 음소거 추가 |
| 3 | `img/ux3_hover.webp` | 모든 카드가 같은 호버라 단조롭고, 떠오르며 빛나는 호버는 다른 사이트와 겹친다 | 섹션·캐릭터마다 다른 통통 반응 + 다른 효과음, 빛 효과 제거 |

---

## 03 · PROCESS & DECISION
**전/후 변화**
1. 장난감·스티커 언어로 정리
   - 전: 카드 위 타이틀바(● ● ●)와 로딩바 구분선 (`img/before_characters.webp`, git 첫 커밋 화면)
   - 후: 타이틀바·구분선 제거, 섹션 라벨과 CH.0x 번호를 스티커 배지로 (`img/result2_characters.webp`)
2. 커서
   - 전: 28px 시안 링 + 핑크 점
   - 후: 린키 전신 픽셀 스프라이트가 마우스를 따라다님 (인트로 포함) (`img/ux3_hover.webp`에서 확인 가능)

**A 대신 B를 고른 이유**
- **드레스룸을 메인 대신 서브페이지로.** 먼저 메인 CHARACTERS 안에 넣었지만, 기획에서 서브페이지로 정한 것이라 `dress.html`로 옮겼다. 메인은 소개·진입 역할을 유지하고, 놀이 공간은 따로 둔다. (이유 문구는 본인 확인 필요) (`img/extra_dress.webp`)

---

## 04 · RESULT
**핵심 화면 3장 + 모바일**
- `img/result1_hero.webp` 히어로 (쇼룸 + 카피 순서)
- `img/result2_characters.webp` CHARACTERS 카드 (CHI:EE · LEENKI · GLEEN)
- `img/result3_goods.webp` GOODS
- `img/result4_mobile.webp` 모바일 (반응형, 홈 화면 추가 지원)

**툴 한 줄**: Notion(기획) · Gemini / ChatGPT(초안·히어로 시안) · Claude Code(구현·테스트·배포) · Playwright(렌더링 확인) · GitHub · Vercel

**다음 계획 한 줄**: 드레스룸을 아이템별 레이어 종이인형으로 확장하고 도감·코디 카드를 더한다. 실물 굿즈 연결은 (추후).

**버튼 2개**
- 사이트 보기 → https://pixel-neon-linked.vercel.app
- 기획서 PDF → `../../docs/PIXELINK_기획서.pdf`

---

## 팝업 디자인 메모 (PIXELINK)
스티커 카드(흰 외곽선 + 딱딱한 그림자, 살짝 기울인 라벨), 폴라로이드 프레임(캡션이 아래), 둥근 픽셀 한글(NeoDunggeunmo). 스캔·HUD 표현은 쓰지 않는다.
