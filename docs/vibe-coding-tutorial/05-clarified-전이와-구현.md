# 챕터 5: clarified 전이와 산출물 제작

> **소요**: 약 20분
> **리서치 투입**: 병렬 에이전트 3기 (포트폴리오 샘플 확장)
> **핵심 인사이트**: 의도가 명확(clarified)해지면 **조사를 멈추고 만들기 시작**한다. "순서대로 진행해" 한 마디로 산출물이 줄줄이 나온다.

## Context
3차례 탐구로 Why/What/Not이 모두 확신으로 채워지고 `(?)`가 사라졌다. 이제 의도를 `exploring → clarified`로 올리고, 실제 학생이 쓸 자료를 만든다.

## The Prompts
```
clarified로 전이
```
```
순서대로 진행해
```
```
진행시켜
```

## What Happened
**1) 상태 전이**: INTENT.md를 clarified로. "포트폴리오로 증명하면 기회가 열린다"가 조건부 참으로 검증됐으므로 구현 단계로.

**2) 1차 산출물 3종** ("순서대로 진행해"):
- `content/domain-knowledge.md` — 도메인 6모듈 실제 콘텐츠
- `content/portfolio-samples/skhynix-yield-data-analysis.md` — 직무 1개 포트폴리오 샘플
- `content/templates/jd-gap-analysis.md` — JD 갭분석 프롬프트 템플릿

**3) 2차 확장** ("진행시켜"):
- 포트폴리오 샘플 3종 추가(삼성 SW·AI인프라·NVIDIA) — **3개 에이전트 병렬 제작**
- `content/recruitment-roadmap.md` — 기업별·시기별 타임라인
- `content/domain-quiz.md` — 자가진단 퀴즈
- `README.md` — 학생용 시작 동선

## The Result
저장소가 "조사 문서(docs/)"에서 **"학생이 바로 쓰는 자료(content/)"**로 확장됐다. 모든 자료가 INTENT의 Not·hard-to-fake 원칙을 콘텐츠 안에 가드레일로 박았다.

## Lessons Learned
- **조사와 제작을 구분하라.** 의도가 흐릿할 땐 조사, 명확해지면 제작. 이 전환점이 clarified다.
- **포트폴리오 샘플은 "틀"로 만든다.** 한 직무를 제대로 설계해두면(역량 추출 → hard-to-fake 프로젝트 → 스토리), 나머지 직무는 같은 틀로 복제된다 — 그래서 병렬 제작이 가능했다.
- **짧은 신호("진행시켜")로도 큰 작업이 굴러간다** — 의도 문서가 공유 맥락 역할을 하기 때문.

## Try It Yourself
```
내 의도가 이제 명확해졌어. INTENT를 clarified로 올리고,
[도메인 학습자료 / 내 직무 포트폴리오 샘플 / 갭분석 템플릿]을
순서대로 만들어줘. 전부 "허위 금지·hard-to-fake" 원칙을 지켜서.
```

## Timeline
- 00:00 — clarified 전이
- 00:05 — 1차 산출물 3종
- 00:12 — 포트폴리오 샘플 3종 병렬 제작
- 00:18 — 로드맵 + 퀴즈 + README

## Running 리서치 투입
| 단계 | 활동 | 에이전트 | 누적 |
|------|------|---------|------|
| 챕터4 | AI워크플로+도메인 | 2 | 7 |
| 챕터5 | 포트폴리오 샘플 3종 병렬 | 3 | 10 |
