# 바이브 코딩 기반 반도체 포트폴리오 — 조사 종합 (탐구 4)

> 명제: **전산/경영정보 전공자가 바이브 코딩 기반 데이터 사이언스로, 오픈소스+오픈 데이터셋을 활용해 공정개선·불량탐지 포트폴리오를 만들어 반도체 기업에 취업한다.**
> 세 갈래 조사(데이터셋 / 오픈소스 / 기업 관심 프로젝트·실현성) 종합.

---

## 핵심 결론 (먼저)

1. **데이터는 충분하다** — 실제 fab 데이터는 기밀이지만, WM-811K·SECOM 등 **반도체 직결 공개 데이터 + 인접 도메인 대체 데이터**로 포트폴리오 제작 가능.
2. **2026 함정**: "캐글 따라하기 + 배포된 앱 + 정확도 99%"는 **신호가 죽었다**. 바이브 코딩으로 누구나 만들 수 있어 table stakes로 전락.
3. **살아남는 신호 5가지**: ① 실데이터의 지저분함 처리 ② **도메인 해석**(패턴↔공정 원인 번역) ③ 정량 성과(구체적 작은 숫자) ④ 의사결정 기록(ADR) ⑤ 협업·공개 리더보드·유지보수 흔적.
4. **바이브 코딩을 숨기지 말고 신호로 전환**: "무엇을 AI에 지시했고 무엇을 내가 검증했는가"를 문서화 + 손수 만든 eval set(20~30개)이 곧 현대 엔지니어링 역량 신호.

---

## A. 공개 데이터셋 (검증됨, 2026-06)

### 반도체 직결 (최우선)
| 데이터셋 | 접근 | 내용 | 라이선스 | 과제 |
|---|---|---|---|---|
| **WM-811K** ★ | Kaggle `qingyi/wm811k-wafer-map` | 81만 웨이퍼맵, 9결함패턴(라벨 21%) | **CC0** | 패턴 다중분류·불균형·self-supervised |
| **SECOM** ★ | UCI `secom` / `ucimlrepo` | 591센서×1567행, pass/fail | **CC BY 4.0** | 불량 이진분류·고차원 피처선택 |
| **MixedWM38** | github `Junliangwangdhu/WaferMap` | 혼합결함 38종, 전량 라벨 | 연구용 | 멀티라벨 분류 |
| **PHM 2016 CMP** | `data.phmsociety.org` | 실제 CMP 공정 시계열 | 학술 | 제거율 회귀(드문 진짜 공정데이터) |
| **KAMP**(한국) | `kamp-ai.kr` | 반도체 부품 정밀가공 등 50종 | 무료(국내) | 한국 기업 지원 시 차별화 |

### 인접 대체 (결함 이미지·설비 PHM)
- 이미지: **MVTec AD**(CC BY-NC), Severstal/NEU 강판, DeepPCB(MIT), INU 반도체 스크래치(한국)
- 설비 PHM/RUL: **NASA C-MAPSS**(RUL 표준), CWRU/IMS 베어링, Bosch Production Line(Kaggle)
- ⚠️ 실제 SEM 결함 원본은 매우 희소 → 합성 생성 또는 wafer map/인접 표면결함으로 대체.

## B. 오픈소스 생태계 (PR로 hard-to-fake 협업 신호 만들기)

### PR 머지로 "타인 이름 박힌 커밋" 만들기 좋은 활발 repo
1. **Anomalib** (Intel, 5.8K★, 매일 푸시, good-first-issue) — **반도체 결함탐지 직결, 최우선**
2. **RAPIDS cuDF/cuML** (Apache-2.0, 매일) — NVIDIA 지원 시 시너지
3. **sktime/tsfresh** (각 9K+★) — 공정 시계열
4. **Gradio/MLflow/ZenML/BentoML** — 배포·MLOps, 문서 PR로 빠른 머지
5. **secsgem / opcua-asyncio** — 작지만 **반도체 장비통신 특화 = MIS 전공자 독보적 차별점**

### 활용 라이브러리
- Wafer 분류 베이스라인: `Junliangwangdhu/WaferMap`(133★), ViT판(48★, MIT) → 포크·확장
- 이상탐지: Anomalib, PyOD(9.8K★)
- 시계열/SPC: sktime, tsfresh, pyspc(SPC 관리도)
- 도메인 통신: **secsgem**(SECS/GEM Python), opcua-asyncio, node-red
- GPU: RAPIDS(cuDF=GPU pandas, cuML=GPU sklearn), Triton 서빙
- 배포: Streamlit/Gradio + **HF Spaces 무료 호스팅**, MLflow 추적
- ⚠️ 라이선스: Apache/MIT/BSD 안전 / GPL·AGPL(pyspc·pm4py·Odoo)은 파생물 공개의무 주의

## C. 기업이 관심 갖는 문제 + 실현 가능성

### 반도체 데이터 문제 Top 7 (가치 순)
① 불량/결함 탐지(이미지+WBM) ② 수율 예측 ③ 가상계측(VM) ④ 설비 PHM/예지보전 ⑤ 공정 최적화 ⑥ 근본원인분석(RCA) ⑦ 로그/LLM 분석.
- 가치 근거: 수율 1%p = 수억 달러/년, 다운타임 1시간 = $100K~250K, 계측 병목 → 사이클타임.
- **한국 JD 연결**: SK 양산기술/FA/빅데이터분석, 삼성 평가·분석/Fab Automation이 **산업공학·통계·컴퓨터·경영정보 전공을 명시**하고 "프로젝트/경진대회 경력"을 우대 → 비전공자 진입로.

### 바이브 코딩 실현성: ①②⑥ 조합 최적 (⑤ 비추-데이터장벽, ④ 반도체 공개데이터 약함)

### 핵심 차별화: WBM 패턴 ↔ 공정 원인 매핑 (이게 무기)
| WBM 패턴 | 추정 원인 | 구분 단서 |
|---|---|---|
| Center | CMP 균일도/플라즈마 중심 과식각 | 식각 직후=플라즈마, 이전=핸들링 |
| Edge-Ring | 식각/증착 seal ring/CMP edge | seal breach=날카로운 완전원, CMP=완만 gradient |
| Scratch | 핸들링(cassette/로봇) | 같은 slot 여러 웨이퍼 일관된 호=cassette |
| Donut | 툴링/식각 marginality | center 깨끗+링 |
| Random | 입자 오염(본질적 변동) | assignable 원인 없음 |
> 신호: "정확도 99%"가 아니라 *"Edge-Ring 분류 웨이퍼들이 특정 식각 챔버 출신이고 seal breach 특유 경계를 보였다"*는 **해석 리포트**.

### 추천 포트폴리오 (3개 깊게 > 5개 얕게)
| # | 프로젝트 | 데이터 | 기술 | 난이도 | hard-to-fake |
|---|---|---|---|---|---|
| **A**(플래그십) | WBM 분류 + **공정원인 해석 리포트** | WM-811K | CNN/ViT+공간특징+해석 | 하~중 | 패턴→원인 물리 해석, 오분류 분석 |
| **B** | 수율예측 **Large-P-Small-N 정공법** | SECOM | XGBoost+SMOTE+SHAP+누수방지 | 중 | 결측·익명피처·불균형 처리 과정 |
| **C** | WBM 유사사례 검색 **RCA** | WM-811K | 임베딩+FAISS+LLM설명 | 중 | 도메인룰 결합, 2025 RCA 트렌드 |
| D | **Self-supervised** WBM(라벨부족 극복) | WM-811K 미라벨 | VAE/대조학습 | 중~상 | 라벨링 비용 도메인 논거 |
| E | **생성형 결함증강** | WM-811K 소수클래스 | GAN/VAE+before/after | 중 | 증강 전후 정량 측정 |

### 2024~26 트렌드 무기
생성형 결함증강(GAN/diffusion), 반도체 LLM(**SemiKong**), LLM 기반 RCA, GPU 가속(RAPIDS), self-supervised WBM.

---

## 종합 권고
**시작 조합**: WM-811K + SECOM (둘 다 반도체 직결, CC0/CC BY). 플래그십 A + 데이터현실 B + 트렌드 C/E 중 하나, 총 **3개를 깊게**. 각 프로젝트에 5가지 신호(지저분함·도메인해석·정량성과·ADR·협업)를 의도적으로 심고, **Anomalib/RAPIDS/secsgem에 PR 1~3건**으로 협업 신호 확보.

출처: 각 조사 에이전트 보고서(Kaggle/UCI/HF, GitHub API 검증 2026-06-09, arXiv, 반도체 기업 JD, 2026 포트폴리오 신호 분석글). 상세 URL은 원 보고서 참조.
