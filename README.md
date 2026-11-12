# 텐서 연구실 — 축을 세면 보이는 것

텐서를 "축이 여러 개인 숫자 상자"로 시작해, 분야별 쓰임·연산·분해·학습을 거쳐 격투 게임 특별편까지 **직접 돌려 보며** 배우는 초보자용 해설 시리즈입니다. 박사 · 조수(하루) · 초파리 연구원 · 주판봇이 진행합니다.

- **바로 보기 (GitHub Pages):** https://adminmrobo.github.io/what_is_tensor/
- 글 · 안상선 ((주)M-Robo 대표) · 2026-11-07 · v1.0 · [저자 소개](https://adminmrobo.github.io/who_am_i/who_am_i.html)

## 차례

| 장 | 페이지 | 핵심 질문 | 다루는 것 | 대결 |
|---|---|---|---|---|
| 목차 | [index.html](index.html) | — | 시리즈 안내, 배우는 길, 대결 성적표, W01 바로가기 | — |
| 1장 | [텐서란 무엇인가](01_what_is_tensor.html) | 숫자에 축을 하나씩 더하면 무엇을 담을까? | 스칼라·벡터·행렬·3차·4차(큐브의 줄), shape, 슬라이스, 배치 | 펴고 다시 접기 → 초파리 승 |
| 2장 | [좌표판](02_tensor_map.html) | 같은 축 세기가 분야마다 무엇을 담을까? | 차수 × 분야 20칸 좌표판, 피벗, 임베딩·패딩, 공분산, 좌표 변환 | 흑백 vs 컬러 → 주판봇 승 |
| 3장 | [텐서 연산](03_tensor_ops.html) | 어떤 축이 짝지어지고 어떤 축이 사라질까? | 브로드캐스트, y = Ax, 행렬곱과 곱하는 순서, permute·reshape, einsum | 반복문 vs 벡터화 → 주판봇 승 |
| 4장 | [분해와 변화](04_decompose_change.html) | 큰 텐서를 쪼개고 조금씩 바꿀 수 있을까? | 고유벡터, SVD, CP 분해(ALS), 경사하강, 기울기 텐서, 계량 텐서(심화) | 학습률 → 조건부 |
| 특별편 | [박사 vs 조수 텐서 대전](sp_tensor_fight.html) | 한 판의 격투 게임에서 어떤 텐서를 다룰까? | 커맨드 원-핫(특성공학), 다음 기술 예측(딥러닝), 콤보·밸런스(최적화), 빈칸 장면 추천(텐서 완성) | 최종 대전 → 박사 2승 1패 |

## 다음 시리즈
- [뉴런 반응 연구실](https://github.com/adminmrobo/neuron_reaction) — 4장 경사하강에서 이어지는 활성화 함수(01편), 연구실 반응속도 대회(특별편), 역전파(02편, 준비 중). [바로 보기](https://adminmrobo.github.io/neuron_reaction/)

## 페이지에 들어 있는 것
- **시뮬레이션:** 모든 그림과 계산(SVD, CP-ALS, 경사하강, 소프트맥스 회귀, 완전 탐색)을 페이지 안에서 직접 합니다. 데이터는 시드를 고정한 설명용 모형입니다.
- **대결:** 장마다 초파리 연구원(의심하는 쪽)과 주판봇(확신하는 쪽)이 맞붙고, 승패는 페이지가 계산한 숫자로 정합니다. 특별편은 박사와 조수가 선수이고, 초파리 연구원이 심판, 주판봇이 점수판을 맡습니다.
- **학습 도우미:** 용어 말풍선, 확인 퀴즈 46문항, 진행 막대.
- **지식 색인·꾸러미:** 장마다 개념 그래프 검색과, 온톨로지(JSON-LD·Turtle·CSV)와 참고문헌(CSL-JSON·BibTeX·RIS)을 ZIP으로 내려받는 섹션이 있습니다.
- 파일 하나로 동작하며, 외부 요청은 웹 글꼴(Google Fonts)뿐입니다. 브라우저 저장소를 쓰지 않습니다.

## 저장소 구조
```
index.html                    시리즈 목차
01_what_is_tensor.html        1장
02_tensor_map.html            2장
03_tensor_ops.html            3장
04_decompose_change.html      4장
sp_tensor_fight.html          특별편
docs/COVER_*.md               장별 글 표지 지시문 (Genspark 등에 붙여 넣는 한국어 지시 + 영어 프롬프트)
docs/IMG_*.md                 장별 이미지 제작 명세서와 매니페스트
docs/REVIEW.md                페르소나 감사 결과 (6 페르소나, 기계 점검, 보완 과제)
docs/review_log.json          검수 기록
data/kg_*.json                장별 지식 그래프·참고문헌·페이지 서지 (꾸러미 원본)
data/KG_00_registry_additions_tensor.json   시리즈 등록부 추가분
W01_word_embedding.html, assets/, docs/IMG_W01_*, docs/kg_W01.json, docs/KG_00_registry.json   W01 (아래 절)
```

## 표지 그림 현황
| 키 | 상태 | 지시문 |
|---|---|---|
| cover_index | 대체 표지 사용 중 | docs/COVER_00_index.md |
| cover_01 ~ cover_04 | 대체 표지 사용 중 | docs/COVER_01~04_*.md |
| cover_SP | 대체 표지 사용 중 | docs/COVER_sp_tensor_fight.md |

그림을 받으면 각 HTML의 `<!-- lab-cover -->` 블록 안 `data-img` 자리에 WebP(1600×900)로 넣습니다.

## 출처와 참고
- Goodfellow, I., Bengio, Y., Courville, A. (2016). *Deep Learning*. MIT Press.
- Kolda, T. G., Bader, B. W. (2009). Tensor Decompositions and Applications. *SIAM Review*, 51(3).
- 개념 구성에 참고한 공개 인포그래픽(Sciences KL, Mathematics Learning Page, @eeanimation, matharium 등)은 각 장 바닥글에 적었습니다. 그림은 옮기지 않고 새로 그렸습니다.
- 캐릭터 그림: [fruitfly-lab-expressions](https://github.com/adminmrobo/fruitfly-lab-expressions)
- 확인이 필요한 서지 항목(쪽수·DOI 등)은 각 장 꾸러미 섹션의 "확인 필요 목록"에 있습니다.

## 인용
안상선 (2026). 텐서 연구실 (1~4장, 특별편), v1.0. https://adminmrobo.github.io/what_is_tensor/

## 라이선스
저자가 정할 예정입니다. 정하기 전에는 개인 학습 목적의 열람만 허용합니다.

---

## 같은 저장소 · 단어 주소 연구실 (W01)

글 · 안상선 ((주)M-Robo 대표)

박사 · 조수(하루) · 초파리 연구원 · 주판봇이 진행하는 연구실 해설 대시보드입니다.

![서가 앞의 네 캐릭터](assets/img/sc_w01_hero.webp)

### 페이지

| 번호 | 제목 | 파일 |
|---|---|---|
| W01 | 단어에 주소를 붙이는 법 — 원-핫 인코딩에서 워드 임베딩까지 | [W01_word_embedding.html](W01_word_embedding.html) |

W01은 단어를 숫자로 바꾸는 네 가지 방법을 사다리처럼 올라갑니다.

1. **정수 번호** — 도서관 등록번호. 번호에 뜻 없는 순서가 생긴다.
2. **원-핫 인코딩** — 책마다 체크칸 하나. 모든 단어 쌍의 유사도가 0이고, 단어가 늘면 행렬이 V²으로 커진다.
3. **손으로 정한 좌표** — 성별·지위·나이 세 축. 비슷한 단어가 가깝고 벡터 연산으로 유추가 된다. 새 단어는 좌표 3개만 늘어난다.
4. **문맥에서 배운 좌표** — 동시출현 횟수 → PPMI → SVD. 축을 데이터가 정한다.

대결: 유추 8문제에서 원-핫(초파리) 0.20, 3축 임베딩(주판봇) 1.00.

### 폴더

| 경로 | 내용 |
|---|---|
| `W01_word_embedding.html` | 해설 페이지 (캐릭터 표정은 파일 안에, 장면 그림은 `assets/img/`) |
| `index.html` | 목차 |
| `assets/img/` | 배경·장면 WebP, 썸네일, 공유 미리보기 |
| `assets/img/src/` | 받은 그림 원본 |
| `docs/IMG_W01_word_embedding.md` | 이미지 제작 명세서 |
| `docs/kg_W01.json`, `docs/KG_00_registry.json` | 지식 그래프, 시리즈 등록부 |

온톨로지·서지 꾸러미(JSON-LD·Turtle·CSV·BibTeX·RIS)는 페이지 맨 아래 「꾸러미」에서 ZIP으로 받을 수 있습니다.

### 출처

1. Harris, Z. S. (1954). Distributional Structure. *Word*, 10(2–3), 146–162. doi:10.1080/00437956.1954.11659520
2. Mikolov, T., Yih, W., & Zweig, G. (2013). Linguistic Regularities in Continuous Space Word Representations. *NAACL-HLT 2013*, 746–751.
3. Mikolov, T., et al. (2013). Efficient Estimation of Word Representations in Vector Space. arXiv:1301.3781.
4. Levy, O., & Goldberg, Y. (2014). Neural Word Embedding as Implicit Matrix Factorization. *NeurIPS 2014*, 2177–2185.
5. Bolukbasi, T., et al. (2016). Man is to Computer Programmer as Woman is to Homemaker? Debiasing Word Embeddings. *NeurIPS 2016*.
6. Nissim, M., van Noord, R., & van der Goot, R. (2020). Fair Is Better than Sensational. *Computational Linguistics*, 46(2), 487–497. doi:10.1162/coli_a_00379

페이지의 좌표·문장·정확도는 설명용 예시값입니다.

### 캐릭터

캐릭터 그림: [adminmrobo/fruitfly-lab-expressions](https://github.com/adminmrobo/fruitfly-lab-expressions) (캐릭터 팩 1.3, 주판봇 v2)

### 채워 넣을 것

- 라이선스
- 공개 주소 (GitHub Pages를 켜면 `https://adminmrobo.github.io/what_is_tensor/`)
