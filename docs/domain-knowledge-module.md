# 반도체 도메인 지식 모듈 — 비전공 IT 취준생용 (탐구 3b)

> 필요 수준: "공정을 개발하는 수준"❌ → **"공정·수율·설비 데이터가 무엇이고 왜 돈(원가·품질)과 직결되는지 IT 언어로 번역할 수 있는 수준"**. 원칙: 얕고 넓게 + 데이터 접점은 깊게.

## 제안 모듈 목차

```
모듈 0. 왜 비전공 IT가 반도체를 알아야 하는가 ("수율=이익", IT/데이터 기여 지점 지도)

모듈 1. 반도체 제조 1분 브리핑  [얕고 넓게]
        1.1 웨이퍼→다이→칩→패키지 (단위 감각)
        1.2 8대 공정 한 장 요약 (각 공정=무슨 데이터를 만드나)
        1.3 전공정(FAB) vs 후공정(OSAT), IDM vs 팹리스 vs 파운드리

모듈 2. 수율과 불량  [데이터 접점 — 깊게]
        2.1 Yield 계산, Die/Defect/D₀
        2.2 불량 3분류(Random/Parametric/Systematic)
        2.3 Wafer Bin Map과 불량 패턴
        2.4 OEE 등 제조 KPI
        2.5 수율분석 SW: JMP/Spotfire/Minitab/SPC, Commonality

모듈 3. 스마트팩토리 IT 스택  [IT 직무 핵심 — 깊게]
        3.1 ERP–MES–제어 3계층, MESA-11 기능
        3.2 CIM/EES, 추적성(genealogy)
        3.3 설비통신 SECS/GEM(SEMI 표준) — 이름·역할 (비전공 차별점)
        3.4 FDC/SPC/APC/R2R/VM/YMS 한 줄 사전

모듈 4. 반도체 데이터 사이언스의 특수성  [DS 직무 — 깊게]
        4.1 가상계측(VM)과 Large P/Small N
        4.2 공정 시계열(alignment·drift·교호작용)
        4.3 FDC: 불량 탐지·분류(CNN/이미지)
        4.4 멀티소스 데이터 통합과 근본원인 추적

모듈 5. 회사별 맞춤  [지원 직전]
        5.1 삼성DS/SK하이닉스/NVIDIA 강조점 비교
        5.2 시의성 키워드(HBM·CXL·PIM·EUV / CUDA·LLM)
        5.3 자소서·면접 프레임: Issue→Root Cause→Hypothesis→Test→Result

부록. "여기까지는 과함" 체크리스트
```

## 회사별 강조점

| | 삼성 DS / SK하이닉스 (IDM·메모리) | NVIDIA (팹리스·GPU SW) |
|---|---|---|
| 도메인 요구 | **제조 도메인 + 데이터** 강하게 (비전공자 필수 보완재). SK는 "공정 이해 있는 SW엔지니어, T형 인재" | CS·AI가 본체, 반도체 도메인은 **공급망/제조데이터 직무에서만 가산점** |
| 키워드 | HBM·CXL·PIM·EUV, DRAM/NAND, MES/수율 | CUDA·Triton·LLM·GPU 아키텍처 |

## "여기까지는 과함" (비전공 IT는 깊이 안 가도 됨)

❌ 소자물리·고체물리·양자역학 / 회로설계·Verilog·EDA(Cadence) / TCAD·SPICE·공정 레시피 튜닝 / 공정별 화학 메커니즘 디테일 / EUV 광학·OPC 내부.
→ 트랜지스터(FinFET/GAA)·EUV는 **이름 수준만**. 대신 수율·불량 데이터 구조, MES/CIM/SECS-GEM, VM/FDC, SQL/ML에 깊이 투자.

## 설계 원칙

1. 지식 나열 금지, **데이터 접점 중심** — 모든 개념을 "내 IT 역량과 어떻게 연결되나"로 닫음.
2. **5단계 문제해결 프레임**(Issue→Root Cause→Hypothesis→Test→Result)을 관통축으로.
3. 회사별 분기는 마지막에.

출처: 삼성 반도체 백과사전(8대 공정), SK하이닉스 합격전략(careerdawn.tistory.com/46), SK실트론 MES 공고(SECS/GEM), NVIDIA Data System Analyst(팹리스 flow), bluediary8(VM/Large P Small N), SAP MES(MESA-11), 현직자 자소서 프레임(linkareer).
