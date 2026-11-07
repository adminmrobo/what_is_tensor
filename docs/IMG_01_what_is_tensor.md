# 01번 「텐서란 무엇인가」 이미지 제작 명세서

| 항목 | 내용 |
|---|---|
| 페이지 | 01_what_is_tensor.html (텐서 연구실 1장) |
| 모드 / 주 앵커 | 교과서 / D 생활·현장 (아파트 주소, 엑셀 표, 셀로판 겹치기) |
| 시즌 | 기본 |
| 대결 | "원소 개수가 같으면 같은 텐서일까?" → 결과 F (초파리 승), 픽셀 일치율 100.0% vs 0.0%, 차이 100%p |
| 새로 그릴 그림 | P1 1장 (cover_01) · P2 3장 · P3 2장 |
| 재사용 | 표정 15장 (캐릭터 팩 96px, 페이지에 base64로 넣음) |
| 그림이 없을 때 | 페이지는 캐릭터 팩 표정 + CSS·SVG 대체 표지로 이미 완성 상태 |

## 1. 그림체와 고정 외형
- 스타일: SKILL 18-3 (16비트 RPG 픽셀아트, 굵은 외곽선, 2~3단계 명암)
- 캐릭터 고정 외형: 캐릭터 팩 18-4 그대로 (주판봇 v2)
- 장소: 밤의 연구실 작업대 + 주제 소품(구슬·격자판·숫자 큐브), 현미경·초파리 해부 소품 없음
- 장소 영어 묘사: *a night laboratory workbench with glowing beads, a tile grid panel and a translucent tile cube, purple lab light spilling in from the left*

## 2. 필요한 그림 전체

| # | 키 | 판 | 크기 | 상태 | 우선 | 들어가는 곳 | 대신 쓰는 그림 |
|---|---|---|---|---|---|---|---|
| 0 | cover_01 | L | 1920×1080 | 새로 (COVER_01_what_is_tensor.md) | P1 | 맨 위 글 표지 | 대체 표지 (CSS 벌집 + 캐릭터 넷 + SVG 큐브) |
| 1 | bg_01 | F | 1920×720 | 새로 | P3 (표지 있음) | 히어로 배경 | 표지 자르기 |
| 2 | cut_01_lv4 | G | 960×540 | 새로 | P2 | ④칸 컷: 셀로판 세 장 겹치기 | 없음(컷 생략) |
| 3 | sc_01_outro | E | 1200×800 | 새로 | P2 | 아웃트로 | cover_01 |
| 4 | thumb_01 | I | 600×400 | 새로 (cover_01 3:2 자르기) | P2 | 목차 카드 | 색 카드 |
| 5 | og_01 | K | 1200×630 | 새로 (cover_01 자르기) | P3 | 공유 미리보기 | 없음 |
| — | doc_front, doc_think, doc_judge | A | 96 | 재사용 | — | 히어로·큰 그림·판정·아웃트로 | — |
| — | asst_smile, asst_report, asst_spark | B | 96 | 재사용 | — | 히어로·발표·아웃트로·꾸러미 | — |
| — | fly_clip, fly_point, fly_arms, fly_coffee | C | 96 | 재사용 (좌우 뒤집어 오른쪽을 봄) | — | 대결 전·후, 본문 | — |
| — | robo_smile, robo_coin, robo_sigh, robo_happy | D | 96 | 재사용 | — | 대결 전·후, ④칸 주소 찾기 | — |
| — | 차수 계단·큐브·하트 그림·묶음 | — | — | 코드 | — | Canvas 2D | — |

## 3. 새로 그릴 그림 상세

### 3-1. `cut_01_lv4` — 셀로판 세 장으로 컬러 그림 만들기
| 항목 | 내용 |
|---|---|
| 판 · 크기 | G · 960×540 |
| 배경 | 그림 전체 |
| 구도 | 조수가 가운데에서 빨강·초록·파랑 투명판 세 장을 조금씩 어긋나게 들고, 겹친 부분에 하트 모양 픽셀 그림이 완성됨. 초파리가 왼쪽 아래에서 판 사이 틈을 들여다봄 |
| 표정·몸짓 | 조수 집중, 초파리 호기심 |
| 소품 | 투명 컬러판 3장, 작은 픽셀 하트 (글자 없음) |
| 피할 것 | 글자·숫자, 승패 암시 |
| 대체 글 (alt) | 조수가 빨강·초록·파랑 투명판 세 장을 겹쳐 하트 그림을 만드는 장면 |
| 대신 쓰는 그림 | 없음 |

```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 16:9 illustration panel, girl researcher with long pink hair in two round buns and a navy streak, blue eyes, white lab coat over a lavender hoodie and jeans, standing at center holding three slightly offset transparent sheets in red, green and blue, where they overlap a small pixel heart picture appears, anthropomorphic fruit fly researcher with big red compound eyes and a blue helmet with a gold stripe at the lower left facing right peeking curiously between the sheets, night lab workbench in the background, no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-2. `sc_01_outro` — 대결 뒤 (초파리 승)
| 항목 | 내용 |
|---|---|
| 판 · 크기 | E · 1200×800 |
| 구도 | 앞쪽 왼쪽에 초파리가 팔짱 끼고 만족한 얼굴로 축 이름표(색 띠 세 개, 글자 없음)를 큐브에 붙이는 중. 오른쪽에 주판봇이 흐트러진 색 타일 더미를 보며 머리를 긁지만 인정하는 몸짓. 박사가 뒤 가운데에서 엄지, 조수가 오른쪽 끝에서 체크 표시판 |
| 표정·몸짓 | 승자 앞·크게, 패자도 같은 화면에서 인정하는 몸짓 (조롱 금지) |
| 대체 글 (alt) | 초파리 연구원이 큐브에 축 이름표를 붙이고, 주판봇이 흐트러진 타일을 보며 웃으며 인정하는 연구실 장면 |
| 대신 쓰는 그림 | cover_01 |

```
16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights, consistent with the reference images, cozy night laboratory mood, purple light, soft magenta and green fluorescent accents, 3:2 landscape scene, medium brightness, anthropomorphic fruit fly researcher with big red compound eyes, blue helmet with a gold stripe, white lab coat over a black vest, front left facing right, arms crossed and satisfied, sticking three colored ribbon tags onto a glowing tile cube; boxy beige retro CRT-monitor robot with a dark green screen face and mint pixel eyes, abacus bead antenna and tank treads, on the right facing left, scratching its screen with a sheepish smile beside a scrambled pile of colored tiles; chibi scientist with thin teal rectangular glasses and a white hair streak at the back center giving a thumbs up; girl researcher with long pink hair in two buns at the far right holding a board with a big check mark; no text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands
```

### 3-3. `bg_01`, `thumb_01`, `og_01`
cover_01을 받은 뒤 잘라 쓴다 (bg_01 8:3, thumb_01 3:2, og_01 1200×630). 따로 생성하지 않는다.

## 4. 일관성 지침
- 참고 이미지: 캐릭터 팩 기본 그림 4장 + 주판봇 v2 단체 사진
- 같은 대화에서 cover_01 → cut_01_lv4 → sc_01_outro 순서로 연달아 생성
- 표정만 바꿀 때: *same character, same size and position, only change the facial expression and pose to ...*

## 5. 넘겨받은 뒤 처리
SKILL 18-15 절차 (비율·글자·네 캐릭터 확인 → WebP 1600/960 → 390·768·1280 폭 점검). 표지 블록은 `<!-- lab-cover -->` 표시 사이만 바꾼다.

## 6. 매니페스트
```json
{
  "page": "01_what_is_tensor",
  "series": "텐서 연구실",
  "anchor": "D:night-lab-workbench",
  "season": "default",
  "duel": {"result": "F", "gap": 1.0},
  "images": [
    {"key":"cover_01","plate":"L","size":[1920,1080],"status":"new","priority":"P1","slot":"cover","fallback":"css-svg-four","alt":"밤의 연구실에서 네 캐릭터가 구슬·줄·판·큐브로 이어지는 빛나는 계단을 둘러싼 표지"},
    {"key":"cut_01_lv4","plate":"G","size":[960,540],"status":"new","priority":"P2","slot":"lv4","fallback":null,"alt":"조수가 빨강·초록·파랑 투명판 세 장을 겹쳐 하트 그림을 만드는 장면"},
    {"key":"sc_01_outro","plate":"E","size":[1200,800],"status":"new","priority":"P2","slot":"outro","fallback":"cover_01","alt":"초파리 연구원이 큐브에 축 이름표를 붙이고, 주판봇이 흐트러진 타일을 보며 웃으며 인정하는 연구실 장면"},
    {"key":"bg_01","plate":"F","size":[1920,720],"status":"crop:cover_01","priority":"P3","slot":"hero-bg"},
    {"key":"thumb_01","plate":"I","size":[600,400],"status":"crop:cover_01","priority":"P2","slot":"index-card"},
    {"key":"og_01","plate":"K","size":[1200,630],"status":"crop:cover_01","priority":"P3","slot":"og"}
  ]
}
```
