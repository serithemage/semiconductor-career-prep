# 반도체 도메인 지식 자가진단 퀴즈

> [domain-knowledge.md](domain-knowledge.md) 6모듈을 제대로 이해했는지 점검하는 퀴즈. 면접 구술 대비도 겸한다.
> 사용법: 정답을 가리고 풀고, 객관식은 "왜 답인지"까지 말로 설명할 수 있어야 통과.

---

## 모듈 1 — 반도체 제조 기본 흐름

**Q1. (객관식)** 웨이퍼에서 잘라낸 개별 칩 한 개를 부르는 단위는?
① Lot ② Die ③ Package ④ Node

**Q2. (객관식)** EDS(전기적 검사) 공정에서 나오는, 웨이퍼 위 양·불량 위치를 표시한 데이터는?
① CD 계측값 ② Wafer Bin Map ③ OEE ④ Recipe

**Q3. (단답)** IDM, 팹리스, 파운드리의 차이를 한 줄씩 쓰고, 삼성DS·NVIDIA·TSMC를 각각 분류하라.

<details><summary>정답</summary>

- Q1: **② Die**
- Q2: **② Wafer Bin Map** (불량 패턴이 원인 공정을 가리킴)
- Q3: IDM=설계+제조(삼성DS, SK하이닉스) / 팹리스=설계만(NVIDIA) / 파운드리=위탁제조(TSMC)
</details>

---

## 모듈 2 — 수율과 불량

**Q4. (객관식)** 반도체 회사에서 "수율(Yield) 1%"가 중요한 가장 직접적 이유는?
① 환경 규제 ② 웨이퍼 1장당 팔 수 있는 칩 수가 달라져 원가/이익에 직결 ③ 직원 복지 ④ 마케팅

**Q5. (객관식)** 불량 3분류가 아닌 것은?
① Random(이물/particle) ② Parametric(설비 파라미터 이탈) ③ Systematic(설계-공정 불일치) ④ Seasonal(계절성)

**Q6. (단답)** Wafer Bin Map의 불량 "패턴"이 데이터 직무에서 왜 중요한가? ML 문제로 어떻게 연결되는지 설명하라.

<details><summary>정답</summary>

- Q4: **②**
- Q5: **④ Seasonal** (반도체 불량 3분류는 Random/Parametric/Systematic)
- Q6: 패턴(예: Edge-Ring, Center, Scratch)이 **원인 공정을 가리킨다** → 패턴을 자동 분류하면 원인 추적 가속. CNN 기반 **이미지 분류 문제(defect classification)**로 연결.
</details>

---

## 모듈 3 — 스마트팩토리 IT 스택

**Q7. (객관식)** ERP–MES–제어 3계층에서 MES의 위치와 역할은?
① 최상위 경영 계획 ② ERP와 설비 사이 "실행" 계층, 실시간 추적·제어 ③ 설비 밸브 직접 제어 ④ 회계 처리

**Q8. (객관식)** HOST(MES)와 설비 간 통신 표준으로, IT/SW 직무 지원자가 이름·역할을 알면 차별점이 되는 것은?
① HTTP ② SECS/GEM ③ FTP ④ MQTT만

**Q9. (매칭)** 약어와 역할을 연결하라: FDC / SPC / APC(R2R) / VM
- (a) 통계적 공정관리(관리도)
- (b) 설비 실시간 이상탐지·분류
- (c) 가상계측(센서로 품질 예측)
- (d) 자동 공정제어(되먹임)

<details><summary>정답</summary>

- Q7: **②**
- Q8: **② SECS/GEM** (SEMI 표준, 다수 MES 공고 우대사항)
- Q9: FDC=(b), SPC=(a), APC/R2R=(d), VM=(c)
</details>

---

## 모듈 4 — 반도체 데이터의 특수성

**Q10. (객관식)** 가상계측(Virtual Metrology, VM)이 필요한 이유는?
① 데이터가 부족해서 ② 비용·시간 때문에 일부(약 1%)만 실측하고 나머지는 센서로 품질을 예측해야 해서 ③ 법규 때문 ④ 고객 요청

**Q11. (객관식)** 반도체 공정 데이터가 일반 비즈니스 데이터와 다른 "Large P / Small N" 구조란?
① 관측치 많고 변수 적음 ② 변수(센서 수천 개) 많고 실측 관측치 극소수 ③ 결측치 없음 ④ 전부 범주형

**Q12. (단답)** 데이터 직무 면접에서 "반도체 도메인을 이해했다"는 인상을 주려면 반드시 언급할 2종 핵심 과제는?

<details><summary>정답</summary>

- Q10: **②**
- Q11: **②** (일반 ML은 보통 N≫P, 반도체 VM은 정반대)
- Q12: **VM(가상계측)** 과 **FDC(불량 탐지·분류)**. (보너스: process drift, alignment 문제 언급 시 가점)
</details>

---

## 모듈 5 — 회사별 맞춤

**Q13. (객관식)** 도메인 지식 요구가 상대적으로 낮고 "CS/AI 실력이 본체, 반도체 도메인은 공급망/제조데이터 직무에서만 가산점"인 회사는?
① 삼성DS ② SK하이닉스 ③ NVIDIA ④ 셋 다 동일

**Q14. (단답)** 삼성·SK 지원 시 자소서·면접에 녹이면 좋은 시의성 키워드 3개와, NVIDIA용 키워드 3개를 각각 써라.

**Q15. (구술)** 본인의 프로젝트 경험 1개를 `Issue → Root Cause → Hypothesis → Test → Result` 5단계로 1분 안에 말해보라.

<details><summary>정답</summary>

- Q13: **③ NVIDIA**(팹리스). 삼성·SK(IDM)는 제조 도메인+데이터를 강하게 요구.
- Q14: 삼성·SK = HBM, CXL, PIM, EUV, DRAM/NAND 중 3개 / NVIDIA = CUDA, Triton, LLM/GenAI, GPU 아키텍처 중 3개
- Q15: (정답 없음 — 5단계 구조로 막힘없이 말하면 통과. 면접 핵심 평가요소)
</details>

---

## 부록 — "과한 영역" 경계 점검

**Q16. (O/X)** 비전공 IT/데이터 직무 지원자는 MOSFET/FinFET 트랜지스터의 양자역학적 동작과 Verilog 회로 설계를 깊이 공부해야 한다.

<details><summary>정답</summary>

**X**. 이름 수준만 알면 충분. 깊이 가야 할 곳은 수율·불량 데이터 구조, MES/SECS-GEM, VM/FDC, SQL/ML. 소자물리·회로설계·TCAD는 비전공 IT 직무 범위 밖.
</details>

---

## 채점 가이드
- **13~16개 + 구술 통과**: 도메인 기반 충분. 포트폴리오·전형 준비로 이동.
- **9~12개**: 약한 모듈 재학습([domain-knowledge.md](domain-knowledge.md) 해당 모듈).
- **8개 이하**: 모듈 0~2부터 다시. "왜 IT가 반도체를 아는가"의 관통 메시지부터 체화.

> 면접 대비 팁: 객관식 정답을 맞히는 것보다 **"왜 그런지 30초 구술"**이 진짜 실력. 모든 문항을 말로 설명하는 연습을 하라.
