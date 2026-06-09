# 포트폴리오 샘플 — NVIDIA 데이터 직무 (Data Scientist/Engineer/Analyst)

> 이 문서는 **하나의 직무를 골라 "증명해야 할 역량 → hard-to-fake 포트폴리오"로 변환한 샘플**이다.
> 레퍼런스(SK하이닉스 수율 샘플)와 **같은 틀**(① JD에서 역량 추출 → ② 검증 가능한 프로젝트 설계 → ③ 스토리)을 따른다.
> 근거: [jd-reverse-mapping.md](../../docs/jd-reverse-mapping.md) (NVIDIA 항목), [portfolio-hire-cases.md](../../docs/portfolio-hire-cases.md) (Kaggle/KGMON 경로), [domain-knowledge-module.md](../../docs/domain-knowledge-module.md)

## 0. 왜 이 직무인가 (CS·MIS 적합도 ★★★★)

- NVIDIA 데이터 직무(DS/DE/Analyst)는 **CS·MIS 양쪽 모두에게 열린 현실적 글로벌 진입로** — 칩설계(RTL/Verilog)와 달리 전공·학위 장벽이 상대적으로 낮음(탐구2 "조건부 참": SW/데이터/ML 직무에서만 가설 성립).
- 다만 **냉정한 현실 3가지**를 전제로 설계한다:
  1. **다수가 경력 요구**(7년+ 흔함). 신입은 **글로벌 NCG/인턴 + 인프라·데이터 직무로 우회**가 현실적([jd-reverse-mapping.md](../../docs/jd-reverse-mapping.md) §3).
  2. **referral이 사실상 필수** — 대량지원 거절률 ~80%. "지원 버튼"이 아니라 "사람"으로 들어간다.
  3. **영문 이력서 + 영어 면접 필수** — 단 영어 실력보다 기술·문제해결이 우선.
- 그래서 이 포트폴리오는 단순 GitHub이 아니라 **"객관적으로 순위화·검증 가능한(hard-to-fake)" 성과물 + referral을 끌어오는 공개 활동**으로 설계한다. NVIDIA가 Kaggle 성과를 **KGMON(Kaggle Grandmasters of NVIDIA)** 팀으로 제도화했다는 사실 자체가 "검증가능 포트폴리오 = 채용신호"임을 회사가 인정한 증거다(Titericz·Deotte·Tunguz, [portfolio-hire-cases.md](../../docs/portfolio-hire-cases.md)).

---

## 1. JD에서 추출한 "증명해야 할 역량"

| # | 역량 | 출처(JD) | 증명 난이도 |
|---|------|---------|-----------|
| C1 | **Python(pandas/numpy) + SQL** 데이터 핸들링 | 필수 | 낮음 |
| C2 | **통계 + ML**(scikit-learn/PyTorch/TensorFlow) 모델링 | 필수 | 중 |
| C3 | **결과 커뮤니케이션** (영어, 비기술 청중 설득) | 필수 | 높음 |
| C4 | **대규모 데이터 + GPU 가속**(PySpark, RAPIDS/CUDA) | 우대 | 높음 |
| C5 | 클라우드(AWS/Azure/GCP) 데이터 파이프라인 | 우대 | 중 |
| C6 | **referral을 만드는 공개 평판** (OSS·커뮤니티) | 채용문화 | 매우 높음(혼자선 불가) |

> 핵심 통찰: C1·C5는 누구나 증명할 수 있어 **변별력이 낮다**(GitHub 토이프로젝트 수천 개). NVIDIA 합격을 가르는 건 **C2·C4·C6** — 그래서 포트폴리오는 "순위가 매겨지는 곳에서의 성과 + GPU 가속 + referral을 부르는 공개성"에 집중해야 한다. **막연한 GitHub은 신호가 아니다.**

---

## 2. 포트폴리오 설계 — "Kaggle 입상 + GPU 가속(RAPIDS) 파이프라인 + GPU MODE 리더보드 도전"

### 2.1 프로젝트 한 줄 정의

> 공개 테이블·시계열 Kaggle/DACON 대회에서 **메달권 입상을 목표로 한 검증가능 솔루션**을 만들고, 그 파이프라인을 **RAPIDS(cuDF/cuML)로 GPU 가속**해 CPU 대비 속도·규모 우위를 수치로 증명하며, 동시에 **GPU MODE KernelBot 공개 리더보드**에 CUDA 커널을 제출해 "GPU를 다룰 줄 안다"는 NVIDIA 특이적 신호를 심는다.

- **왜 hard-to-fake한가**: Kaggle 순위(public+private LB), RAPIDS 벤치마크 수치, GPU MODE 리더보드 등수는 **모두 제3자가 검증하고 위조 불가능**하다. Tunguz의 표현 — "Grandmaster는 위조하기 매우 어렵다, top 대학 박사보다 도달이 어렵다"([portfolio-hire-cases.md](../../docs/portfolio-hire-cases.md)). 막연한 토이프로젝트와 명확히 갈린다.
- **데이터셋/플랫폼**: Kaggle(테이블/시계열 대회) 또는 DACON(국내, 영어 자신 없으면 워밍업), RAPIDS(GPU DataFrame/ML), GPU MODE Discord + KernelBot 리더보드.

### 2.2 역량 커버리지 매핑

| 역량 | 이 프로젝트에서 어떻게 증명되나 |
|------|------------------------------|
| C1 Python+SQL | pandas/numpy 피처엔지니어링, BigQuery/DuckDB SQL 집계 |
| C2 통계+ML | GBDT(XGBoost/LightGBM/CatBoost) + 딥러닝, 교차검증·앙상블, 통계적 검정 |
| C3 커뮤니케이션 | **영문 Kaggle write-up/솔루션 공개 + 30초 데모 + 영문 README** (영어 결과 전달 그 자체) |
| C4 대규모+GPU | **RAPIDS cuDF/cuML로 GPU 가속**, CPU 대비 N배 벤치마크, PySpark로 대용량 전처리 |
| C5 클라우드 | 학습/추론을 클라우드 GPU 인스턴스(또는 Kaggle/Colab GPU)에서 재현 가능하게 |
| C6 referral 평판 | **GPU MODE 커뮤니티 활동 + RAPIDS/OSS PR 1건** → 타인 이름이 git·LB에 남고 referral 연결 |

### 2.3 hard-to-fake 4신호 심기 (2026 시장 핵심)

2026년엔 "deploy된 앱"만으론 부족하다. NVIDIA 데이터 직무에선 다음을 의도적으로 심는다:

1. **순위화된 성과** — Kaggle/DACON **메달권 입상(또는 상위 %)** + 공개 솔루션 write-up. GPU MODE **KernelBot 리더보드 제출 기록**(= "Kaggle의 GPU판", [portfolio-hire-cases.md](../../docs/portfolio-hire-cases.md)). 등수는 위조 불가.
2. **GPU 가속 벤치마크** — RAPIDS(cuDF/cuML)로 동일 파이프라인을 GPU에서 돌려 **CPU 대비 처리시간/규모 수치**를 README에 기록. NVIDIA가 보고 싶은 정확히 그 신호.
3. **개발자다운 git 히스토리 + OSS 기여** — atomic 커밋, RAPIDS/관련 OSS에 **PR 1건** → 타인 리뷰가 git에 남게. "initial commit에 5천 줄" 금지.
4. **referral 경로 + 영어 공개성** — GPU MODE/Kaggle 디스커션에서 활동 → **현직자·커뮤니티 멤버와의 접점**을 referral로 전환. 모든 산출물은 **영문**으로 공개(영어 면접의 사전 증명).

> 4신호의 NVIDIA 특수성: SK하이닉스 샘플이 "협업 커밋 + 살아있는 배포"였다면, 여기선 **"공개 리더보드 등수 + GPU 가속 수치 + referral을 부르는 영어 공개활동"**이 핵심이다.

### 2.4 4주 빌드 플랜

| 주차 | 산출물 |
|------|--------|
| 1주 | Kaggle/DACON 대회 1개 선정, EDA, GBDT 베이스라인 + SQL 집계, public LB 첫 제출 |
| 2주 | 피처엔지니어링·교차검증·앙상블로 LB 끌어올리기, 오류분석, **영문 솔루션 노트 초안** |
| 3주 | **RAPIDS(cuDF/cuML) 이식** — 동일 파이프라인 GPU 가속, CPU 대비 벤치마크 표 작성 |
| 4주 | GPU MODE **KernelBot 리더보드 1회 제출** + RAPIDS/OSS PR 1건 + 영문 README/write-up + 30초 데모 |

### 2.5 절대 하지 말 것 (Not 일관 — 윤리 가드레일)

- ❌ **LB 점수·등수 조작/대리참여** — Kaggle 순위는 검증 인프라 자체. 조작은 영구 신호 파괴이자 "hiring managers can smell fake numbers".
- ❌ **공개 솔루션을 그대로 복붙해 자기 것으로** — 면접 후속질문(왜 이 피처? 왜 이 CV?)에서 즉시 붕괴. 출처 인용하고 "재현+개선"으로 정직하게 프레이밍.
- ❌ **AI가 통째로 짠 코드를 이해 없이 제출** — NVIDIA는 "코드가 하드웨어/메모리와 어떻게 상호작용하는지 설명하는 능력"을 본다([jd-reverse-mapping.md](../../docs/jd-reverse-mapping.md) §3). 이해 못 하면 시스템 디자인 라운드에서 무너진다.
- ❌ **referral을 스팸으로 구걸** — 평판은 기여로 쌓는 것. 가치 없는 대량 DM은 역효과.

---

## 3. 스토리 — 영문이력서·면접 직무직결 (STAR + 5단계 프레임)

### 3.1 영문 이력서 불릿 (Action+scope+tool+metric+outcome+proof)

> "Placed **top X% (medal)** in a Kaggle tabular/time-series competition; **accelerated the pipeline with RAPIDS cuDF/cuML, cutting feature-engineering time ~Nx vs. CPU**, and submitted a CUDA kernel to the **GPU MODE KernelBot leaderboard**. [Kaggle profile / GitHub / leaderboard links]"

- 한국어 버전(국내 워밍업·자소서용): "Kaggle 시계열 대회에서 상위 X%(메달) 입상한 솔루션을 **RAPIDS로 GPU 가속(CPU 대비 N배)**하고, GPU MODE 공개 리더보드에 커널을 제출했습니다."

### 3.2 면접 예상 질문 → 답 뼈대 (Issue→Root Cause→Hypothesis→Test→Result)

- **"Walk me through your solution."**(영어) → 문제정의 → CV 전략 → 핵심 피처 가설 → 검증(LB/local 상관) → 결과. **영어로 막힘없이 설명**하는 것 자체가 C3 증명.
- **"Why RAPIDS / how does it speed things up?"** → cuDF가 GPU 메모리에서 컬럼연산을 병렬화 → CPU 대비 어디서 N배 → 어떤 워크로드에서 이득/한계(데이터 전송 오버헤드 등). **하드웨어-코드 상호작용 설명** = NVIDIA 핵심 시그널.
- **"How would this scale to billions of rows?"** → PySpark/멀티GPU(dask-cuDF) → 파티셔닝·셔플 비용 → 클라우드 GPU 인스턴스 선택 트레이드오프.
- **"This number looks high — is it real?"** → CV-LB gap, leak 점검 방법 제시. **모르면 솔직히 + 논리적 접근** 제시(조작 절대 금지).

### 3.3 C6(referral·평판) 보강 멘트

> "이 솔루션을 GPU MODE 디스커션에 공유하며 피드백을 받았고, RAPIDS에 [구체 버그/문서] PR을 1건 머지했습니다. 그 과정에서 만난 [현직자/메인테이너]를 통해 팀과 연결됐습니다." → NVIDIA 채용에서 **사실상 필수인 referral**을 "기여로 얻은 평판"으로 정직하게 서사화. (referral 스팸 ❌, 기여 기반 ⭕)

### 3.4 영어 게이트 현실 멘트

> 영어는 **완벽함이 아니라 "기술을 영어로 전달 가능한가"**가 기준. 따라서 모든 산출물(README·write-up·데모)을 **처음부터 영문**으로 만들어 두면, 그 자체가 영어 면접의 사전 증명이자 reviewer가 referral하기 쉬운 형태가 된다.

---

## 4. 이 샘플을 다른 직무로 복제하는 법

1. **JD 1~3개** 수집 → 1번 표처럼 역량 추출, **변별력 낮은 역량 vs 가르는 역량** 구분.
2. 가르는 역량에 **hard-to-fake 프로젝트** 1개 집중 설계. NVIDIA의 경우 핵심 축은 **순위화된 성과(Kaggle/리더보드) + GPU 가속 수치 + referral을 부르는 공개성**.
3. 2.3의 **4신호**를 의도적으로 심기 — 회사 문화에 맞춰 변주(NVIDIA = 공개 리더보드·GPU·referral·영어).
4. 3번처럼 STAR + 5단계 프레임으로 스토리화하되, **영문 버전을 1급 산출물로** 둔다.

> 같은 틀의 다른 샘플: [skhynix-yield-data-analysis.md](skhynix-yield-data-analysis.md)(제조 도메인 + 협업·배포 신호). NVIDIA는 도메인 대신 **검증가능 순위 + GPU + referral + 영어**로 무게중심이 이동한다는 점이 차이.
