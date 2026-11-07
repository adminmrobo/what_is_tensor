# W01번 「단어에 주소를 붙이는 법」 이미지 제작 명세서

| 항목 | 내용 |
|---|---|
| 페이지 | W01_word_embedding.html |
| 모드 / 주 앵커 | 교과서 / D 생활·현장: 도서관 서가 (초파리 생물 대응 없음 → 생물 앵커 안 씀) |
| 시즌 | 기본 |
| 대결 | 유추 8문제, 원-핫(초파리) vs 3축 임베딩(주판봇) → 결과 **R**, 차이 0.80 (0.20 vs 1.00) |
| 새로 그릴 그림 | P1 2장 · P2 1장 · P3 0장 (+ 직접 만든 것 2장) |
| 제작 경로 | 직접 2장 (thumb_w01, og_w01) · 외부 의뢰 3장 (bg_w01, sc_w01_hero, sc_w01_outro) |
| 의뢰 도구 | Genspark (기본) |
| 진행 | 받음 3 / 의뢰 3 · 반영 3 · 마지막 반영 2026-11-07 (사용자가 준 thumb·og도 반영) |
| 캐릭터 팩 표정 | 26장 (96px) + 대결 머리 9장 (192px) · 캐릭터 팩 1.3, 저장소 커밋 1fd4e40 |
| 주판봇 | 캐릭터 팩 1.3의 v2 그림 사용. 이 페이지 7장 중 E13·E16은 공식(gpt2) 기준 그림, E07·E12·E14·E18·E20은 Genspark 임시판 — gpt2판이 나오면 같은 키로 교체되므로 다시 빌드만 하면 됨 |
| 재사용 | 0장 (시리즈 기존 그림 목록 없음) |
| 그림이 없을 때 | 페이지는 캐릭터 팩 표정과 CSS·픽셀 서가 배경으로 이미 완성 상태 |

## 1. 그림체와 고정 외형
- 스타일: SKILL 18-3 (16비트 SNES 시대 픽셀 아트, 굵은 외곽선, 디더링 음영)
- 캐릭터 고정 외형: SKILL 18-4 표 그대로 (공식 저장소 `CHARACTER_CORE_EN`)
- 이 페이지 장소: 밤의 연구실 안 도서 서가. 책등이 여러 색으로 꽂힌 나무 서가 몇 단, 한쪽에서 보라 조명이 스며든다. 책등에는 글자가 없다.
- 장소 영어 묘사: *tall wooden library shelves with rows of colorful blank book spines rendered as part of the same night lab world, purple lab light spilling in from the left side*

## 2. 필요한 그림 전체

| # | 키 | 판 | 크기 | 상태 | 제작 | 우선 | 들어가는 곳 | 대신 쓰는 그림 |
|---|---|---|---|---|---|---|---|---|
| 1 | bg_w01 | F | 1920×720 | 반영 | 외부 | P1 | 히어로 배경 (`header .honey`) | CSS 그라데이션 + 벌집 무늬 |
| 2 | sc_w01_hero | E | 1200×800 | 반영 | 외부 | P1 | 히어로 무대 (`.stage`) | 픽셀 서가 캔버스 + 팩 캐릭터 합성 |
| 3 | sc_w01_outro | E | 1200×800 | 반영 | 외부 → 선택 | P2 | 아웃트로 (`.outro-stage`) | 픽셀 서가 캔버스 + 팩 캐릭터 합성 (로봇 앞·크게) |
| 4 | thumb_w01 | I | 600×400 | 반영 | 사용자 제공 | P2 | 목차 카드 | 합성 무대 3:2 자르기 |
| 5 | og_w01 | K | 1200×630 | 반영 | 사용자 제공 | P3 | 공유 미리보기 | 히어로 화면 캡처 |
| 6 | doc_think → doc_e09 | A | 팩 96 | 팩 | — | — | 히어로 무대·대화창 | — |
| 7 | doc_front → doc_e08 | A | 팩 96 | 팩 | — | — | 등장인물 카드, 아웃트로 | — |
| 8 | doc_board → doc_e07 | A | 팩 96 | 팩 | — | — | 큰 그림 “박사의 한 줄” | — |
| 9 | doc_magic → doc_e16 | A | 팩 96 | 팩 | — | — | ④ “박사의 한 줄” | — |
| 10 | doc_judge → doc_e10 | A | 팩 96 | 팩 | — | — | 대결 판정 | — |
| 11 | asst_smile → asst_e13 | B | 팩 96 | 팩 | — | — | 히어로, 등장인물 | — |
| 12 | asst_firm → asst_e12 | B | 팩 96 | 팩 | — | — | 대결 전, 아웃트로 | — |
| 13 | asst_spark → asst_e01 | B | 팩 96 | 팩 | — | — | 대결 후 (F·R·D) | — |
| 14 | asst_shock → asst_e24 | B | 팩 96 | 팩 | — | — | 대결 후 (X일 때만) | — |
| 15 | asst_e10 | B | 팩 96 | 팩 | — | — | ② 숫자 발표, 꾸러미 | — |
| 16 | asst_e07 | B | 팩 96 | 팩 | — | — | 정리 | — |
| 17 | fly_point → fly_e08 | C | 팩 96·192 | 팩 | — | — | 히어로, 대결 전 (`data-face="right"`) | — |
| 18 | fly_clip → fly_e10 | C | 팩 96 | 팩 | — | — | 등장인물 | — |
| 19 | fly_magnify → fly_e07 | C | 팩 96 | 팩 | — | — | ① 말풍선 | — |
| 20 | fly_e14 | C | 팩 96 | 팩 | — | — | 아웃트로 (머쓱한 인정) | — |
| 21 | fly_cry → fly_e21 | C | 팩 192 | 팩 | — | — | 대결 후 (R, 차이 ≥ 10%p) — **실제 결과** | — |
| 22 | fly_arms / fly_coffee → fly_e16 / fly_e13 | C | 팩 192 | 팩 | — | — | 대결 후 (F·X / R 작은 차이·D) | — |
| 23 | robo_coin → robo_e16 | D | 팩 96·192 | 팩 (v2 공식) | — | — | 히어로, 대결 전 | 반쯤 감은 눈 + 반짝이는 주판알 |
| 24 | robo_smile → robo_e13 | D | 팩 96 | 팩 (v2 공식) | — | — | 등장인물, 기본 | 네모 픽셀 눈 + 미소, 주판 |
| 25 | robo_chart → robo_e07 | D | 팩 96 | 팩 (v2 임시) | — | — | ③ 말풍선 | 설명 |
| 26 | robo_happy → robo_e12 | D | 팩 96·192 | 팩 (v2 임시) | — | — | 대결 후 (R) — **실제 결과**, 아웃트로 | 주판을 들고 응원 |
| 27 | robo_sigh / robo_meh / robo_blush → robo_e20 / e18 / e14 | D | 팩 192 | 팩 (v2 임시) | — | — | 대결 후 (F / D / X) | 땀방울 / 삐짐 / 머쓱 |
| — | 행동으로 보기 사서, 서가 | — | — | 코드 | 직접 | — | 픽셀 지도 A-2, 캔버스 | — |

상태 값: `팩` · `넣음`(직접 그림) · `의뢰`(외부, 받을 것) · `받음` · `반영` · `다시 의뢰`.
그림 없음 역할 키(`doc_scale`, `asst_ledger`, `asst_board`)는 이 페이지에서 쓰지 않는다. 옛 Money-Robo 그림(robo_e01~e24)은 회사 자산이라 이 페이지에서 모두 뺐다.

## 3. 새로 그릴 그림 상세

### 3-1. `bg_w01` — 밤의 연구실 서가 배경
| 항목 | 내용 |
|---|---|
| 판 · 크기 | F · 1920×720 (8:3, 정수배 가능) |
| 제작 경로 | 외부: Genspark |
| 배경 | 그림 전체 |
| 구도 | 왼쪽 45%는 어두운 벽과 보라 조명만 (제목 글자 자리), 오른쪽 55%에 서가 3~4단. 인물 없음 |
| 표정·몸짓 | 없음 |
| 소품 | 글자 없는 여러 색 책등, 서가 판자, 책 사이 작은 청록 모니터 불빛 하나, 바닥에 놓인 사다리 (글자 없음) |
| 빛·분위기 | 남보라 어둠, 왼쪽에서 들어오는 보라 조명, 책등에 분홍·초록 형광 반사 |
| 피할 것 | 책등 글자·숫자, 실존 출판사·도서관 로고, 초파리 해부·현미경 소품 |
| 대체 글 (alt) | 벌집 무늬가 비치는 밤의 연구실 도서 서가 배경 |
| 대신 쓰는 그림 | CSS 그라데이션 + 벌집 무늬 |

**프롬프트 (복사해서 사용)**
```
detailed 16-bit SNES-era pixel art, limited palette, crisp pixels, dithering shading, thick dark outlines, cheerful comedy mood, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, wide 8:3 background, left side simple and calm for title text, details on the right, tall wooden library shelves with rows of colorful blank book spines rendered as part of the same night lab world, purple lab light spilling in from the left side, a small cyan monitor glow between the books, a wooden ladder leaning on the shelf, no characters, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-2. `sc_w01_hero` — 서가 앞의 네 사람 (결과 전)
| 항목 | 내용 |
|---|---|
| 판 · 크기 | E · 1200×800 (3:2) |
| 제작 경로 | 외부: Genspark |
| 배경 | 그림 전체 |
| 구도 | 뒤 가운데 박사(턱에 손, 생각), 옆에 조수(하루)가 글자 없는 줄무늬 카드 묶음을 듦. 왼쪽 초파리가 오른쪽을 보며 서가를 가리키고, 오른쪽 주판봇이 왼쪽을 보며 작은 주판을 듦. 서가 한 칸에 책이 세 줄 좌표처럼 간격을 두고 꽂혀 빛남. 중요한 것은 위쪽 62% 안 |
| 표정·몸짓 | doc_think, fly_point, robo_coin, asst_smile (승패 암시 없음) |
| 소품 | 글자 없는 책등, 바닥에 그려진 옅은 세 방향 화살표(좌표축 느낌, 글자 없음) |
| 빛·분위기 | 보라 조명, 빛나는 책 세 권에 시선이 모임 |
| 피할 것 | 승패 암시 표정, 글자, 옛 Money-Robo(흰 둥근 로봇)의 모습, 금화 |
| 대체 글 (alt) | 밤의 연구실 서가 앞에 박사, 조수(하루), 초파리 연구원, 주판봇이 서 있는 장면 |
| 대신 쓰는 그림 | 픽셀 서가 캔버스 + 팩 캐릭터 합성 |

**프롬프트 (복사해서 사용)**
```
detailed 16-bit SNES-era pixel art, limited palette, crisp pixels, dithering shading, thick dark outlines, cheerful comedy mood, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 3:2 landscape scene, medium brightness, tall wooden library shelves with rows of colorful blank book spines rendered as part of the same night lab world, purple lab light spilling in from the left side; the Professor, a chibi male scientist with a big head, dark charcoal spiky hair with a white streak at the front, a small low ponytail at the back, very thick bold black eyebrows, teal-framed rectangular glasses, light peach skin, white lab coat over a black vest, black tie and black slacks, standing at the back center with a hand on his chin and a small question mark; Haru, a cute anime girl lab assistant, long straight pink hair with navy blue streaks including a thick navy streak down the center of the bangs, two round messy hair buns on top of the head, a small ahoge, big bright blue eyes, light peach skin, wearing a lavender hoodie with white drawstrings over a white t-shirt, under an open white knee-length lab coat, beside him holding a small stack of blank striped cards; the Fruit Fly, a tiny expressive cartoon fruit fly researcher with a dark charcoal-black segmented insect body, large glossy red compound eyes, a retro dark blue helmet with a yellow-white center stripe and small round side bolts, colorful dangling cables in magenta, purple and blue curving from the back of the helmet, a tiny white lab coat over a black vest, translucent veined wings, six thin black legs with the front pair used like hands, on the left facing right and pointing at the shelf with a doubtful look; JUPANBOT, a boxy beige retro CRT-monitor robot, dark green screen face with mint pixel eyes and mouth, short antenna topped with a red-brown abacus bead, gray segmented arms, two small tank treads, on the right facing left holding a small wooden abacus with colorful beads; three books on one shelf glow softly at spaced positions like points in a coordinate space, faint arrows on the floor pointing in three directions, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-3. `sc_w01_outro` — 결과 후 (주판봇 승, 초파리 인정)
| 항목 | 내용 |
|---|---|
| 판 · 크기 | E · 1200×800 (3:2) |
| 제작 경로 | 외부 (선택): Genspark. 지금은 합성본이 들어가 있음 |
| 배경 | 그림 전체 |
| 구도 | 주판봇이 앞 가운데에서 크게, 두 팔을 들고 옆에 주판이 떠 있음. 초파리는 같은 화면 오른쪽에서 머쓱하게 뒷머리를 긁으며 인정하는 몸짓. 박사는 왼쪽에서 손을 펴서 안내, 조수(하루)는 오른쪽 끝에서 주먹을 쥐고 응원 |
| 표정·몸짓 | robo_happy, fly_e14(머쓱함), doc_front, asst_firm |
| 소품 | 서가, 책 세 권이 좌표처럼 빛남 |
| 빛·분위기 | 로봇 쪽으로 따뜻한 빛, 패자도 밝게(조롱 금지) |
| 피할 것 | 조롱, 우는 얼굴, 글자, 금화, 옛 Money-Robo의 모습 |
| 대체 글 (alt) | 서가 앞에서 주판봇이 앞에 서서 기뻐하고, 초파리 연구원이 머쓱하게 인정하는 장면 |
| 대신 쓰는 그림 | 픽셀 서가 캔버스 + 팩 캐릭터 합성 |

**프롬프트 (복사해서 사용)**
```
detailed 16-bit SNES-era pixel art, limited palette, crisp pixels, dithering shading, thick dark outlines, cheerful comedy mood, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 3:2 landscape scene, medium brightness, tall wooden library shelves with rows of colorful blank book spines rendered as part of the same night lab world, purple lab light spilling in from the left side; JUPANBOT, a boxy beige retro CRT-monitor robot, dark green screen face with mint pixel eyes and mouth, short antenna topped with a red-brown abacus bead, gray segmented arms, two small tank treads, in the front center and larger, both arms raised happily, a small wooden abacus with colorful beads floating beside it; the Fruit Fly, a tiny expressive cartoon fruit fly researcher with a dark charcoal-black segmented insect body, large glossy red compound eyes, a retro dark blue helmet with a yellow-white center stripe and small round side bolts, colorful dangling cables in magenta, purple and blue curving from the back of the helmet, a tiny white lab coat over a black vest, translucent veined wings, six thin black legs with the front pair used like hands, on the right scratching the back of the helmet with a sheepish good-sport smile; the Professor, a chibi male scientist with a big head, dark charcoal spiky hair with a white streak at the front, a small low ponytail at the back, very thick bold black eyebrows, teal-framed rectangular glasses, light peach skin, white lab coat over a black vest, black tie and black slacks, on the left with eyes closed smiling and an open palm gesturing; Haru, a cute anime girl lab assistant, long straight pink hair with navy blue streaks including a thick navy streak down the center of the bangs, two round messy hair buns on top of the head, a small ahoge, big bright blue eyes, light peach skin, wearing a lavender hoodie with white drawstrings over a white t-shirt, under an open white knee-length lab coat, at the far right with a small cheering fist, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-4. `thumb_w01` — 목차 카드 썸네일 (직접, 완료)
| 항목 | 내용 |
|---|---|
| 판 · 크기 | I · 600×400 |
| 제작 경로 | 직접: 합성 무대(픽셀 서가 + 팩 캐릭터)를 3:2로 잘라 만듦. bg_w01을 받으면 다시 자른다 |
| 대체 글 (alt) | 서가 앞의 네 캐릭터 — 단어에 주소를 붙이는 법 |

### 3-5. `og_w01` — 공유 미리보기 (직접, 완료)
| 항목 | 내용 |
|---|---|
| 판 · 크기 | K · 1200×630 |
| 제작 경로 | 직접: 히어로 화면(제목 HTML + 합성 무대) 캡처 |
| 대체 글 (alt) | W01 「단어에 주소를 붙이는 법」 페이지 미리보기 |


## 4. 일관성 지침
- 참고 이미지: 공식 저장소 `images/_sheets/lab4_lineup_gpt2_labeled.png`(넷이 함께, 주판봇 기준). 옛 `keyart_rivals.png`는 Money-Robo가 있어 `archive/`로 옮겨졌으니 쓰지 않는다 + 장면에 나오는 표정의 원본 PNG (아래 의뢰 묶음에 경로)
- 같은 캐릭터는 같은 세션에서, 시드 고정 가능하면 고정: 박사 1101, 조수 1102, 초파리 1103, 주판봇 1104
- 표정만 바꿀 때 추가 문장: *same character, same size and position, only change the facial expression and pose to ...*
- 투명 배경이 안 되면: *solid flat #00ff00 background*

## 5. 넘겨받은 뒤 처리
SKILL 18-15 절차 그대로 (키 맞추기 → 눈으로 검수 → `--ingest` → 페이지에 넣기 → 상태 갱신 → 점검 → 전달).
```bash
python3 build_character_pack.py --ingest 받은폴더/ --plates bg_w01=F,sc_w01_hero=E,sc_w01_outro=E --out received_w01
```
받은 그림은 `SPRITE`에 넣고, 대신 쓰던 CSS·픽셀 배경은 지우지 않고 키가 없을 때만 보이게 둔다.

## 6. 체크리스트
- [x] HTML의 모든 `data-img` 키가 명세서에 있음 (bg_w01, sc_w01_hero, sc_w01_outro + 표정 26키)
- [x] 대결 결과 후 표정이 5-8절 표와 일치 (R, 차이 0.80 ≥ 10%p → fly_cry, robo_happy(robo_e12), asst_spark, doc_judge)
- [x] 결과 전 그림에 승패 암시 없음 (fly_point, robo_coin(robo_e16), asst_firm)
- [x] 모든 프롬프트에 18-4 고정 외형 영어 묘사와 금지 구절
- [x] 팩에 있는 표정을 “새로 그림”에 넣지 않음
- [x] 직접 그림(thumb_w01, og_w01)은 이미 만들어 둠
- [x] 장소가 주 앵커(D 도서관 서가)와 일치, 초파리 해부·현미경 소품 없음
- [x] P1 2장 (≤ 6), 페이지 그림 합계 약 295 KB (base64) ≤ 400 KB 빌드 기준
- 예외: thumb_w01·og_w01은 페이지 밖(목차·공유 메타)에서 쓰므로 HTML `data-img`에는 없다

## 8. 외부 의뢰 묶음 (Genspark 에 그대로 붙여 넣기)

같은 세션에서 이 순서대로 의뢰한다: 배경 → 히어로 장면 → 아웃트로 장면.

### 의뢰 1/3 · `bg_w01`
- **올릴 참고 이미지:** 없음 (배경만)
- **크기·비율:** 1920×720 (8:3) 이상
- **배경:** 그림 전체
- **받을 파일 이름:** `bg_w01.png`
- **프롬프트:** 3-1의 완성 프롬프트 그대로
- **네거티브:** `blurry, smooth vector art, 3D render, photorealistic, anti-aliased painting, inconsistent character, off-model, text, letters, watermark`
- **확인할 것:** 책등에 글자 같은 무늬가 생기면 다시. 왼쪽 45%가 복잡하면 다시

### 의뢰 2/3 · `sc_w01_hero`
- **올릴 참고 이미지:** `images/_sheets/lab4_lineup_gpt2_labeled.png`(네 식구 단체 사진), `images/jupanbot/E16_proud.png`, `images/doctor/E09_thinking.png`, `images/fruitfly/E08_guiding.png`, `images/haru/E13_neutral.png`
- **크기·비율:** 1200×800 (3:2) 이상
- **배경:** 그림 전체
- **받을 파일 이름:** `sc_w01_hero.png`
- **프롬프트:** 3-2의 완성 프롬프트 그대로
- **네거티브:** 위와 같음
- **확인할 것:** 박사 안경이 둥글게 나오면 다시. 로봇이 흰 둥근 로봇(옛 Money-Robo)으로 나오면 다시. 주판에 글자·숫자가 있으면 다시

### 의뢰 3/3 · `sc_w01_outro` (선택)
- **올릴 참고 이미지:** `images/_sheets/lab4_lineup_gpt2_labeled.png`(네 식구 단체 사진), `images/jupanbot/E16_proud.png`, `images/jupanbot/E12_cheering.png`, `images/fruitfly/E14_sheepish.png`, `images/doctor/E08_guiding.png`, `images/haru/E12_cheering.png`
- **크기·비율:** 1200×800 (3:2) 이상
- **배경:** 그림 전체
- **받을 파일 이름:** `sc_w01_outro.png`
- **프롬프트:** 3-3의 완성 프롬프트 그대로
- **네거티브:** 위와 같음
- **확인할 것:** 초파리가 우는 얼굴이면 다시(머쓱한 인정이어야 함). 로봇이 앞·크게


## 7. 매니페스트
```json
{
  "page": "W01_word_embedding",
  "anchor": "D:library-shelf",
  "season": "default",
  "duel": {"result": "R", "gap": 0.80},
  "images": [
    {"key":"bg_w01","plate":"F","size":[1920,720],"maker":"external","tool":"genspark","status":"applied","priority":"P1","slot":"hero-bg","fallback":"css","alt":"벌집 무늬가 비치는 밤의 연구실 도서 서가 배경"},
    {"key":"sc_w01_hero","plate":"E","size":[1200,800],"maker":"external","tool":"genspark","status":"applied","priority":"P1","slot":"hero-stage","fallback":"composite","alt":"밤의 연구실 서가 앞에 박사, 조수(하루), 초파리 연구원, 주판봇이 서 있는 장면"},
    {"key":"sc_w01_outro","plate":"E","size":[1200,800],"maker":"external","tool":"genspark","status":"applied","priority":"P2","slot":"outro","fallback":"composite","alt":"서가 앞에서 주판봇이 앞에 서서 기뻐하고, 초파리 연구원이 머쓱하게 인정하는 장면"},
    {"key":"thumb_w01","plate":"I","size":[600,400],"maker":"user","status":"applied","priority":"P2","slot":"index-card","alt":"서가 앞의 네 캐릭터 — 단어에 주소를 붙이는 법"},
    {"key":"og_w01","plate":"K","size":[1200,630],"maker":"user","status":"applied","priority":"P3","slot":"og","alt":"W01 「단어에 주소를 붙이는 법」 페이지 미리보기"},
    {"key":"doc_think","pack":"doc_e09","plate":"A","size":96,"status":"pack","slot":"hero","alt":""},
    {"key":"doc_front","pack":"doc_e08","plate":"A","size":96,"status":"pack","slot":"cast,outro","alt":""},
    {"key":"doc_board","pack":"doc_e07","plate":"A","size":96,"status":"pack","slot":"big","alt":""},
    {"key":"doc_magic","pack":"doc_e16","plate":"A","size":96,"status":"pack","slot":"lv4","alt":""},
    {"key":"doc_judge","pack":"doc_e10","plate":"A","size":96,"status":"pack","slot":"duel-verdict","alt":""},
    {"key":"asst_smile","pack":"asst_e13","plate":"B","size":96,"status":"pack","slot":"hero,cast","alt":""},
    {"key":"asst_firm","pack":"asst_e12","plate":"B","size":96,"status":"pack","slot":"duel-before,outro","alt":""},
    {"key":"asst_spark","pack":"asst_e01","plate":"B","size":96,"status":"pack","slot":"duel-after","alt":""},
    {"key":"asst_shock","pack":"asst_e24","plate":"B","size":96,"status":"pack","slot":"duel-after-X","alt":""},
    {"key":"asst_e10","pack":"asst_e10","plate":"B","size":96,"status":"pack","slot":"lv2,export","alt":""},
    {"key":"asst_e07","pack":"asst_e07","plate":"B","size":96,"status":"pack","slot":"sum","alt":""},
    {"key":"fly_point","pack":"fly_e08","plate":"C","size":192,"status":"pack","slot":"hero,duel-before","alt":""},
    {"key":"fly_clip","pack":"fly_e10","plate":"C","size":96,"status":"pack","slot":"cast","alt":""},
    {"key":"fly_magnify","pack":"fly_e07","plate":"C","size":96,"status":"pack","slot":"lv1","alt":""},
    {"key":"fly_e14","pack":"fly_e14","plate":"C","size":96,"status":"pack","slot":"outro","alt":""},
    {"key":"fly_cry","pack":"fly_e21","plate":"C","size":192,"status":"pack","slot":"duel-after-R","alt":""},
    {"key":"fly_arms","pack":"fly_e16","plate":"C","size":192,"status":"pack","slot":"duel-after-F/X","alt":""},
    {"key":"fly_coffee","pack":"fly_e13","plate":"C","size":192,"status":"pack","slot":"duel-after-D","alt":""},
    {"key":"robo_coin","pack":"robo_e16","plate":"D","size":192,"status":"pack","slot":"hero,duel-before","alt":""},
    {"key":"robo_smile","pack":"robo_e13","plate":"D","size":96,"status":"pack","slot":"cast","alt":""},
    {"key":"robo_chart","pack":"robo_e07","plate":"D","size":96,"status":"pack","slot":"lv3","alt":""},
    {"key":"robo_happy","pack":"robo_e12","plate":"D","size":192,"status":"pack","slot":"duel-after-R,outro","alt":""},
    {"key":"robo_sigh","pack":"robo_e20","plate":"D","size":192,"status":"pack","slot":"duel-after-F","alt":""},
    {"key":"robo_meh","pack":"robo_e18","plate":"D","size":192,"status":"pack","slot":"duel-after-D","alt":""},
    {"key":"robo_blush","pack":"robo_e14","plate":"D","size":192,"status":"pack","slot":"duel-after-X","alt":""}
  ],
  "character_pack": {"repo":"adminmrobo/fruitfly-lab-expressions","commit":"1fd4e40","pack_version":"1.3","note":"주판봇 v2"},
  "status_values": "pack | placed(직접, 넣음) | requested(의뢰) | received(받음) | applied(반영) | rejected(다시 의뢰)"
}
```

## 9. 반영 기록
- 2026-11-07: bg_w01·sc_w01_hero·sc_w01_outro 받음 → 검수 통과(승패 암시 없음, 책등 글자 없음, 주판봇 v2 외형) → WebP 변환(배경 1600×600, 장면 960×640, 품질 75, 합계 약 183 KB) → `assets/img/`에 두고 페이지에서 상대 경로로 부름. 원본은 `assets/img/src/`
- 그림 파일이 없을 때는 합성 무대(픽셀 서가 + 팩 캐릭터)가 자동으로 대신 보인다
- thumb_w01·og_w01은 사용자가 준 파일로 교체
