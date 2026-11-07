# 표지 지시문 — 2장 좌표판 — 텐서는 어디에 쓰이나

| 항목 | 내용 |
|---|---|
| 키 · 판 | cover_02 · L (16:9, 가로 1920 이상) |
| 장소 (앵커) | D 생활·현장 — 연구실 벽의 큰 격자 지도 앞 |
| 주제 은유 | 벽에 걸린 5×4 격자판, 칸마다 다른 작은 아이콘(막대·점구름·화살표·사진 조각)이 빛남. 글자 없음 |
| 네 캐릭터 포즈 | 박사: 가운데 뒤, 지휘봉 없이 검지로 격자판 한 칸을 가리킴 / 조수: 오른쪽 앞, 칸 카드를 한 장 들고 확인 / 초파리: 왼쪽, 오른쪽을 보며 팔짱 끼고 의심스러운 눈 / 주판봇: 오른쪽, 왼쪽을 보며 주판으로 칸을 세는 중 |
| 대체 글 (alt) | 벽의 차수×분야 격자판 앞에서 네 캐릭터가 칸 하나를 살피는 표지 |
| 앞 표지와 다른 점 | 1장(계단과 큐브) → 2장(벽 격자판) |

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
Scene: a big wall board divided into a 5 by 4 grid of glowing cells, each cell showing a different tiny icon without text: bar chart, scatter cloud, arrow field, small photo tile, cube.
All four characters together: the doctor at the back center pointing at one glowing cell with his index finger; the girl at the front right holding one cell card and checking it; the fruit fly on the left facing right with arms crossed and a skeptical look; the robot on the right facing left counting cells on its abacus.
Character details: doctor = chibi scientist with thin teal rectangular glasses, black hair with one white streak and a short tied-back ponytail, white lab coat over black vest and tie; girl = girl researcher with long pink hair in two round buns and a navy streak, blue eyes, white lab coat over a lavender hoodie and jeans; fruit fly = anthropomorphic fruit fly researcher with big red compound eyes, black body, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings; robot = boxy beige retro CRT-monitor robot with a dark green screen face and mint pixel eyes, short antenna topped with an abacus bead, grey segmented arms and two tank treads.
Composition: keep every face and hand inside the central safe area (12% margin left and right, 10% top, 18% bottom); keep the bottom-left corner dark and simple; the light falls on the grid board.
Mood: curious, friendly rivalry, the moment before the result.
No text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands.
```

**고칠 때 (같은 대화에서):** `Same four characters, same art style and composition. Change only: {고칠 점}. Still no text.`

**받은 뒤:** SKILL 18-15 절차 — 16:9·글자·네 캐릭터 확인 → WebP 1600×900(220 KB 이하)·960×540 → `02_tensor_map.html`의 `<!-- lab-cover -->` 블록 안 `data-img="cover_02"` 자리에 반영.
