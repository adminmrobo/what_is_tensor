# 00번 「시리즈 목차」 이미지 제작 명세서

| 항목 | 내용 |
|---|---|
| 페이지 | index.html |
| 주 앵커 | D 복도 |
| 시즌 | 기본 |
| 대결 | — |
| 새로 그릴 그림 | P1 1장 (cover_index) · 나머지는 표지 자르기 |
| 재사용 | 캐릭터 팩 표정 0장 (페이지에 base64로 들어 있음) |
| 그림이 없을 때 | 페이지는 캐릭터 팩 표정 + CSS·SVG 대체 표지로 이미 완성 상태 |

## 1. 필요한 그림

| # | 키 | 판 | 크기 | 상태 | 우선 | 들어가는 곳 | 대신 쓰는 그림 |
|---|---|---|---|---|---|---|---|
| 0 | cover_index | L | 1920×1080 | 새로 (COVER_00_index.md) | P1 | 맨 위 글 표지 | 대체 표지 (CSS 벌집 + 캐릭터 넷 + SVG) |
| 1 | thumb_index | I | 600×400 | 새로 (cover_index 3:2 자르기) | P2 | 목차 카드 | 색 카드 |
| 2 | og_index | K | 1200×630 | 새로 (cover_index 자르기) | P3 | 공유 미리보기 | 없음 |
| — | 시뮬레이션 그림 전부 | — | — | 코드 (Canvas 2D) | — | 각 사다리 칸 | — |

## 2. 새로 그릴 그림
- `cover_index`: 지시문과 영어 프롬프트는 `COVER_00_index.md`에 있습니다(Genspark에 그대로 붙여 넣기).
- `thumb_index`, `og_index`: 표지를 받은 뒤 잘라 만듭니다. 따로 생성하지 않습니다.

## 3. 점검 (SKILL 18-13)
- [x] HTML의 `data-img` 키(`cover_index`)가 이 명세서에 있음
- [x] 결과 전 그림에 승패 암시 없음 (표지는 대결 전 장면)
- [x] 그림 안 글자 없음, 실존 브랜드·인물 없음
- [x] 생물 앵커가 아니므로 현미경·초파리 해부 소품 없음

## 4. 매니페스트
```json
{
 "page": "index",
 "anchor": "D 복도",
 "season": "default",
 "images": [
  {
   "key": "cover_index",
   "plate": "L",
   "size": [
    1920,
    1080
   ],
   "status": "new",
   "priority": "P1",
   "slot": "cover"
  },
  {
   "key": "thumb_index",
   "plate": "I",
   "status": "crop:cover_index",
   "priority": "P2"
  },
  {
   "key": "og_index",
   "plate": "K",
   "status": "crop:cover_index",
   "priority": "P3"
  }
 ],
 "reuse": []
}
```
