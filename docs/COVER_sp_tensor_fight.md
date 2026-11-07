# 표지 지시문 — 특별편 — 박사 vs 조수 텐서 대전

| 항목 | 내용 |
|---|---|
| 키 · 판 | cover_SP · L (16:9, 가로 1920 이상) |
| 장소 (앵커) | D 생활·현장 — 연구실을 개조한 원형 링(조명, 바닥 격자) |
| 주제 은유 | 링 위 두 선수 사이에 빛나는 버튼 격자(원-핫) 기둥, 위에 떠 있는 예측 확률 막대들 |
| 네 캐릭터 포즈 | 박사: 왼쪽, 오른쪽을 보며 양손에 보랏빛 불꽃(필살기 자세) / 조수: 오른쪽, 왼쪽을 보며 주먹 쥐고 결의 / 초파리: 가운데 뒤, 심판 자세로 한 손을 들어 시작 신호 / 주판봇: 링 밖 오른쪽 아래, 빈 점수판(글자 없음)을 들고 있음 |
| 대체 글 (alt) | 원형 링에서 박사와 조수가 마주 서고 초파리가 심판, 주판봇이 점수판을 든 특별편 표지 |
| 앞 표지와 다른 점 | 4장(풀리는 큐브) → 특별편(링 위 대결 직전) |

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
Scene: a round arena made from the night laboratory with spotlights and a glowing grid floor; between the fighters a pillar of glowing button cells, and above them a few floating probability bars without numbers.
All four characters together: the doctor on the left facing right with purple flames in both hands in a special-move stance; the girl on the right facing left with a clenched fist and determined eyes; the fruit fly at the back center as a referee raising one hand to signal the start; the robot outside the ring at the lower right holding a blank scoreboard.
Character details: doctor = chibi scientist with thin teal rectangular glasses, black hair with one white streak and a short tied-back ponytail, white lab coat over black vest and tie; girl = girl researcher with long pink hair in two round buns and a navy streak, blue eyes, white lab coat over a lavender hoodie and jeans; fruit fly = anthropomorphic fruit fly researcher with big red compound eyes, black body, blue helmet with a gold stripe and pink and blue cables, white lab coat over a black vest, black gloves, transparent wings; robot = boxy beige retro CRT-monitor robot with a dark green screen face and mint pixel eyes, short antenna topped with an abacus bead, grey segmented arms and two tank treads.
Composition: keep every face and hand inside the central safe area (12% margin left and right, 10% top, 18% bottom); keep the bottom-left corner dark and simple; the light falls on the space between the two fighters.
Mood: curious, friendly rivalry, the moment before the result.
No text, no letters, no numbers, no logos, no weapons, no cigarettes, no alcohol, no blood, no real brands.
```

**고칠 때 (같은 대화에서):** `Same four characters, same art style and composition. Change only: {고칠 점}. Still no text.`

**받은 뒤:** SKILL 18-15 절차 — 16:9·글자·네 캐릭터 확인 → WebP 1600×900(220 KB 이하)·960×540 → `sp_tensor_fight.html`의 `<!-- lab-cover -->` 블록 안 `data-img="cover_SP"` 자리에 반영.
