# 단어 주소 연구실

글 · 안상선 ((주)M-Robo 대표)

박사 · 조수(하루) · 초파리 연구원 · 주판봇이 진행하는 연구실 해설 대시보드입니다.

![서가 앞의 네 캐릭터](assets/img/sc_w01_hero.webp)

## 페이지

| 번호 | 제목 | 파일 |
|---|---|---|
| W01 | 단어에 주소를 붙이는 법 — 원-핫 인코딩에서 워드 임베딩까지 | [W01_word_embedding.html](W01_word_embedding.html) |

W01은 단어를 숫자로 바꾸는 네 가지 방법을 사다리처럼 올라갑니다.

1. **정수 번호** — 도서관 등록번호. 번호에 뜻 없는 순서가 생긴다.
2. **원-핫 인코딩** — 책마다 체크칸 하나. 모든 단어 쌍의 유사도가 0이고, 단어가 늘면 행렬이 V²으로 커진다.
3. **손으로 정한 좌표** — 성별·지위·나이 세 축. 비슷한 단어가 가깝고 벡터 연산으로 유추가 된다. 새 단어는 좌표 3개만 늘어난다.
4. **문맥에서 배운 좌표** — 동시출현 횟수 → PPMI → SVD. 축을 데이터가 정한다.

대결: 유추 8문제에서 원-핫(초파리) 0.20, 3축 임베딩(주판봇) 1.00.

## 폴더

| 경로 | 내용 |
|---|---|
| `W01_word_embedding.html` | 해설 페이지 (캐릭터 표정은 파일 안에, 장면 그림은 `assets/img/`) |
| `index.html` | 목차 |
| `assets/img/` | 배경·장면 WebP, 썸네일, 공유 미리보기 |
| `assets/img/src/` | 받은 그림 원본 |
| `docs/IMG_W01_word_embedding.md` | 이미지 제작 명세서 |
| `docs/kg_W01.json`, `docs/KG_00_registry.json` | 지식 그래프, 시리즈 등록부 |

온톨로지·서지 꾸러미(JSON-LD·Turtle·CSV·BibTeX·RIS)는 페이지 맨 아래 「꾸러미」에서 ZIP으로 받을 수 있습니다.

## 출처

1. Harris, Z. S. (1954). Distributional Structure. *Word*, 10(2–3), 146–162. doi:10.1080/00437956.1954.11659520
2. Mikolov, T., Yih, W., & Zweig, G. (2013). Linguistic Regularities in Continuous Space Word Representations. *NAACL-HLT 2013*, 746–751.
3. Mikolov, T., et al. (2013). Efficient Estimation of Word Representations in Vector Space. arXiv:1301.3781.
4. Levy, O., & Goldberg, Y. (2014). Neural Word Embedding as Implicit Matrix Factorization. *NeurIPS 2014*, 2177–2185.
5. Bolukbasi, T., et al. (2016). Man is to Computer Programmer as Woman is to Homemaker? Debiasing Word Embeddings. *NeurIPS 2016*.
6. Nissim, M., van Noord, R., & van der Goot, R. (2020). Fair Is Better than Sensational. *Computational Linguistics*, 46(2), 487–497. doi:10.1162/coli_a_00379

페이지의 좌표·문장·정확도는 설명용 예시값입니다.

## 캐릭터

캐릭터 그림: [adminmrobo/fruitfly-lab-expressions](https://github.com/adminmrobo/fruitfly-lab-expressions) (캐릭터 팩 1.3, 주판봇 v2)

## 채워 넣을 것

- 라이선스
- 공개 주소 (GitHub Pages를 켜면 `https://adminmrobo.github.io/what_is_tensor/`)
