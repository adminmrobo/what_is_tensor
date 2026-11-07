# 표지 지시문 — 3장 텐서 연산 — 곱하고, 돌리고, 접기

| 항목 | 내용 |
|---|---|
| 키 · 판 | cover_03 · L (16:9, 가로 1920 이상) |
| 장소 (앵커) | D 생활·현장 — 작업대 위 공작 테이블 |
| 주제 은유 | 작업대 위에서 분홍 판과 파랑 판이 맞물려 초록 판이 되는 장면(행렬곱), 옆에 반쯤 접힌 큐브(reshape) |
| 네 캐릭터 포즈 | 박사: 가운데 뒤, 두 판을 맞물리는 손짓 / 조수: 오른쪽 앞, 큐브를 접는 중 / 초파리: 왼쪽, 오른쪽을 보며 돋보기로 맞물린 곳 확인 / 주판봇: 오른쪽, 왼쪽을 보며 여러 판을 한꺼번에 든 채 자신만만 |
| 대체 글 (alt) | 작업대 위에서 두 판이 맞물려 새 판이 되는 장면을 네 캐릭터가 둘러싼 표지 |
| 앞 표지와 다른 점 | 2장(벽 격자판) → 3장(작업대 맞물림) |

**참고 이미지 (함께 올리기):** 네 캐릭터 기본 그림 4장 (기준: GitHub `adminmrobo/fruitfly-lab-expressions`, 주판봇은 v2 기준 그림). 같은 대화에서 시리즈 표지를 이어서 만들면 그림체가 맞습니다.

**Genspark에 붙여 넣기 ↓**
```
웹페이지 맨 위에 거는 표지 그림 1장을 만들어 줘.
- 비율 16:9, 가로 1920px 이상
- 첨부한 참고 이미지의 네 캐릭터(박사, 조수, 초파리 연구원, 주판봇)를 같은 그림체·같은 외형으로, 넷 모두 등장
- 그림 안에 글자·숫자·로고를 넣지 말 것
- 얼굴과 손은 가장자리에서 떨어진 가운데 영역에, 왼쪽 아래 구석은 어둡고 단순하게
아래 영어 프롬프트를 그대로 써 줘.

Website top cover illustration, wide 16:9.
Match the art style, proportions and colors of the attached reference images exactly
(if there are no reference images: 16-bit RPG style pixel art, bold dark outline, 2–3 tone shading, small highlights).
Cozy night laboratory mood, purple light, soft magenta and green fluorescent accents.
Scene: a workbench where a magenta tile panel and a blue tile panel slide together and merge into a green tile panel, next to a translucent tile cube that is half folded like paper.
All four characters together: the doctor at the back center gesturing the two panels together; the girl at the front right folding the cube; the fruit fly on the left facing right inspecting the joint through a magnifying glass; the robot on the right facing left proudly holding several panels at once.
Character details: doctor = chibi scientist with thin teal rectangular glasses, black hair with one white streak and a short tied-back ponytail, white lab coat over black vest and tie; girl = girl researcher with long pink hair in two round buns and a navy streak, blue eyes, white lab coat over a lavender hoodie and jeans; fruit fly = anthropomorphic fruit fly researcher with big red compound eyes, black body, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings; robot = boxy beige retro CRT-monitor robot with a dark green screen face and mint pixel eyes, short antenna topped with an abacus bead, grey segmented arms and two tank treads.
Composition: keep every face and hand inside the central safe area (12% margin left and right, 10% top, 18% bottom); keep the bottom-left corner dark and simple; the light falls on the merging panels.
Mood: curious, friendly rivalry, the moment before the result.
No text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands.
```

**고칠 때 (같은 대화에서):** `Same four characters, same art style and composition. Change only: {고칠 점}. Still no text.`

**받은 뒤:** SKILL 18-15 절차 — 16:9·글자·네 캐릭터 확인 → WebP 1600×900(220 KB 이하)·960×540 → `03_tensor_ops.html`의 `<!-- lab-cover -->` 블록 안 `data-img="cover_03"` 자리에 반영.
