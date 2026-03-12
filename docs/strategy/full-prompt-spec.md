# 전체 프롬프트 스펙 (Full Prompt Specification)

> 작성일: 2026-03-11
> 버전: v2 (레이어드 프롬프트 구조)
> 전략: deanpeters 25개 재해석 + 오리지널 프롬프트 추가

---

## 1. 전체 구조 요약

| 구분 | 프롬프트 수 | 설명 |
|------|-----------|------|
| 🔄 deanpeters 재해석 | 22개 | 검증된 PM 프롬프트를 v2 레이어드 구조로 재설계 + 한국어 |
| 🆕 오리지널 (MVP) | 5개 | AI Native PM 관점의 차별화 프롬프트 |
| 🆕 오리지널 (Phase 2) | 8개 | 확장 프롬프트 |
| **총계** | **35개** | Phase 1 출시: 27개 / Phase 2: +8개 |

> **참고:** deanpeters 25개 중 `howto.md`(사용법 문서), `a-generative-AI-prompt-builder`(메타 프롬프트), `futuristic-product-faq`(니치)는 별도 처리

---

## 2. deanpeters 25개 → v2 카테고리 매핑

### analyze/ (분석하기) — 7개

| # | 원본 (deanpeters) | v2 파일명 | 한국어 제목 | 재해석 포인트 |
|---|-------------------|-----------|------------|-------------|
| A1 | `company-profile-executive-insights-research` | `company-profiling.md` | 기업 프로파일링 | Layer 3에 크롤링 자동화 코드 추가 |
| A2 | `customer-journey-mapping-prompt-template` | `customer-journey-mapping.md` | 고객 여정 맵핑 | Layer 1을 5줄 Quick Start로 단순화 |
| A3 | `jobs-to-be-done.md` | `jobs-to-be-done.md` | JTBD 분석 | 교육 주석으로 JTBD 프레임워크 설명 |
| A4 | `pestel-analysis-prompt-template` | `pestel-analysis.md` | PESTEL 분석 | AI 산업 특화 컨텍스트 추가 |
| A5 | `proto-persona-profile` | `persona-profiling.md` | 페르소나 프로파일링 | 한국 SaaS 페르소나 예시 추가 |
| A6 | `framing-the-problem-statement` | `problem-framing.md` | 문제 정의 프레이밍 | Reasoning Strategy 내장 |
| A7 | 🆕 오리지널 | `competitor-sentiment.md` | ⭐ 경쟁사 감성 분석 | **MVP** — 감성 점수 + 기회 매트릭스 |

### decide/ (결정하기) — 6개

| # | 원본 (deanpeters) | v2 파일명 | 한국어 제목 | 재해석 포인트 |
|---|-------------------|-----------|------------|-------------|
| D1 | `positioning-statement` | `positioning-strategy.md` | 포지셔닝 전략 | AI 제품 포지셔닝 컨텍스트 추가 |
| D2 | `recommendation-canvas-template` | `decision-canvas.md` | 의사결정 캔버스 | Layer 2에 Product Trio 관점 추가 |
| D3 | `backlog-epic-hypothesis` | `backlog-prioritization.md` | 백로그 우선순위 | RICE + ICE 프레임워크 비교 |
| D4 | `strategic-scrum-team-session-kickoff` | `sprint-kickoff.md` | 스프린트 킥오프 | Agile + AI 팀 운영 컨텍스트 |
| D5 | 🆕 오리지널 | `feature-prioritization.md` | ⭐ 기능 우선순위 (RICE) | **MVP** — 데이터 기반 우선순위 |
| D6 | 🆕 오리지널 | `build-vs-buy-ai.md` | AI Build vs Buy | Phase 2 — AI 역량 내재화 판단 |

### create/ (만들기) — 9개

| # | 원본 (deanpeters) | v2 파일명 | 한국어 제목 | 재해석 포인트 |
|---|-------------------|-----------|------------|-------------|
| C1 | `user-story-prompt-template` | `user-story.md` | 유저 스토리 작성 | 3C's + INVEST 교육 주석 |
| C2 | `user-story-mapping` | `user-story-mapping.md` | 유저 스토리 맵핑 | Layer 3에 자동 매핑 코드 |
| C3 | `user-story-splitting-prompt-template` | `user-story-splitting.md` | 유저 스토리 분할 | SPIDR 기법 교육 주석 |
| C4 | `user-story_ai-enhanced_prompt-template` | `user-story-ai-enhanced.md` | AI 강화 유저 스토리 | AI Acceptance Criteria 패턴 |
| C5 | `reverse-engineer-IEEE830srs-to-PRD` | `spec-to-prd.md` | 스펙→PRD 역공학 | Layer 1으로 즉시 쓸 수 있게 단순화 |
| C6 | `reverse-engineer-ISO29148-to-PRD` | `requirements-to-prd.md` | 요구사항→PRD 변환 | C5와 워크플로우 체인 연결 |
| C7 | `eol-for-a-product-message` | `product-eol-message.md` | 제품 종료 메시지 | 한국 시장 EOL 커뮤니케이션 패턴 |
| C8 | 🆕 오리지널 | `prd-for-ai-feature.md` | ⭐ AI 기능 PRD | **MVP** — AI 제품 특화 PRD |
| C9 | 🆕 오리지널 | `executive-briefing.md` | 경영진 브리핑 | Phase 2 — AI 전략 보고서 |

### measure/ (측정하기) — 4개

| # | 원본 (deanpeters) | v2 파일명 | 한국어 제목 | 재해석 포인트 |
|---|-------------------|-----------|------------|-------------|
| M1 | (deanpeters에 없는 영역) | — | — | deanpeters는 측정 프롬프트 없음 |
| M2 | 🆕 오리지널 | `ai-adoption-metrics.md` | ⭐ AI 기능 채택 메트릭 | **MVP** — AI 제품 특화 메트릭 |
| M3 | 🆕 오리지널 | `ab-test-design.md` | A/B 테스트 설계 | Phase 2 — AI 기능 실험 설계 |
| M4 | 🆕 오리지널 | `retention-analysis.md` | 리텐션 분석 | Phase 2 — 코호트 분석 프롬프트 |

### communicate/ (소통하기) — 5개

| # | 원본 (deanpeters) | v2 파일명 | 한국어 제목 | 재해석 포인트 |
|---|-------------------|-----------|------------|-------------|
| CM1 | `visionary-press-release` | `press-release.md` | 비전 프레스 릴리즈 | Amazon Working Backwards 교육 주석 |
| CM2 | `storyboard-storytelling-prompt` | `storytelling.md` | 스토리텔링 | 한국 시장 스토리텔링 패턴 추가 |
| CM3 | 🆕 오리지널 | `stakeholder-alignment.md` | ⭐ 이해관계자 정렬 | **MVP** — 크로스팀 커뮤니케이션 |
| CM4 | 🆕 오리지널 | `ai-ethics-review.md` | AI 윤리 리뷰 | Phase 2 — AI 제품 윤리 체크리스트 |
| CM5 | 🆕 오리지널 | `cross-team-handoff.md` | 크로스팀 핸드오프 | Phase 2 — PM↔엔지니어 인수인계 |

### meta/ (메타 프롬프트) — 별도 폴더

| # | 원본 (deanpeters) | v2 파일명 | 한국어 제목 | 재해석 포인트 |
|---|-------------------|-----------|------------|-------------|
| MT1 | `a-generative-AI-prompt-builder` | `prompt-builder.md` | 프롬프트 빌더 | Layer 구조로 재설계, 학생용 교육 콘텐츠 |
| MT2 | (deanpeters skeletons/) | `prompt-anatomy.md` | 프롬프트 해부학 | 프롬프트 역공학 + 설계 원칙 교육 |
| MT3 | (deanpeters prompting-style-guide) | `design-principles.md` | 설계 원칙 가이드 | AI Native PM 7원칙 해설 |

---

## 3. 최종 디렉토리 구조

```
prompts/
├── analyze/                          # 분석하기 (7개)
│   ├── company-profiling.md          🔄 deanpeters
│   ├── customer-journey-mapping.md   🔄 deanpeters
│   ├── jobs-to-be-done.md            🔄 deanpeters
│   ├── pestel-analysis.md            🔄 deanpeters
│   ├── persona-profiling.md          🔄 deanpeters
│   ├── problem-framing.md            🔄 deanpeters
│   └── competitor-sentiment.md       🆕 오리지널 MVP
│
├── decide/                           # 결정하기 (6개)
│   ├── positioning-strategy.md       🔄 deanpeters
│   ├── decision-canvas.md            🔄 deanpeters
│   ├── backlog-prioritization.md     🔄 deanpeters
│   ├── sprint-kickoff.md             🔄 deanpeters
│   ├── feature-prioritization.md     🆕 오리지널 MVP
│   └── build-vs-buy-ai.md            🆕 오리지널 Phase 2
│
├── create/                           # 만들기 (9개)
│   ├── user-story.md                 🔄 deanpeters
│   ├── user-story-mapping.md         🔄 deanpeters
│   ├── user-story-splitting.md       🔄 deanpeters
│   ├── user-story-ai-enhanced.md     🔄 deanpeters
│   ├── spec-to-prd.md                🔄 deanpeters
│   ├── requirements-to-prd.md        🔄 deanpeters
│   ├── product-eol-message.md        🔄 deanpeters
│   ├── prd-for-ai-feature.md         🆕 오리지널 MVP
│   └── executive-briefing.md         🆕 오리지널 Phase 2
│
├── measure/                          # 측정하기 (3개) ← deanpeters 빈 영역
│   ├── ai-adoption-metrics.md        🆕 오리지널 MVP
│   ├── ab-test-design.md             🆕 오리지널 Phase 2
│   └── retention-analysis.md         🆕 오리지널 Phase 2
│
├── communicate/                      # 소통하기 (5개)
│   ├── press-release.md              🔄 deanpeters
│   ├── storytelling.md               🔄 deanpeters
│   ├── stakeholder-alignment.md      🆕 오리지널 MVP
│   ├── ai-ethics-review.md           🆕 오리지널 Phase 2
│   └── cross-team-handoff.md         🆕 오리지널 Phase 2
│
├── meta/                             # 메타 프롬프트 (3개)
│   ├── prompt-builder.md             🔄 deanpeters
│   ├── prompt-anatomy.md             🔄 deanpeters (skeletons 재해석)
│   └── design-principles.md          🆕 AI Native PM 7원칙
│
└── templates/
    └── layered-prompt-template.md    # v2 레이어드 템플릿
```

---

## 4. 수량 비교 최종

| 레포 | 총 프롬프트 | 구조 | 실질 콘텐츠 양 |
|------|-----------|------|-------------|
| awesome-chatgpt-prompts | 170개 | 단일 레이어 (1-2줄) | 170개 |
| deanpeters | 25개 | 단일 레이어 (구조화) | 25개 |
| phuryn/pm-skills | 65 skills | Skills 형태 | 65개 |
| **ai-pm-prompts (ours)** | **33개** + 3 meta | **3 레이어** | **~99개 분량** (33×3) |

> deanpeters 대비 프롬프트 수는 +30% 많고, 레이어드 구조 덕분에 실질 콘텐츠는 **4배**.
> measure/ 카테고리는 deanpeters에 완전히 없는 영역 → 차별화 포인트.

---

## 5. 출시 로드맵

### Phase 1: 출시 (Week 1-2)

**작업 순서:**
1. 레포 생성 + README + templates
2. 🆕 오리지널 MVP 5개 작성 (카테고리당 1개)
3. 🔄 deanpeters 재해석 22개 작성
4. meta/ 3개 작성
5. 총 30개로 출시

**우선순위 근거:**
- 오리지널 MVP 5개를 먼저 → "이 레포만의 차별점" 확보
- deanpeters 재해석은 "검증된 프레임워크의 한국어 + 레이어드 버전"
- meta/는 "이 레포를 어떻게 활용하는지" 온보딩 역할

### Phase 2: 확장 (Week 3-6)

- 🆕 오리지널 Phase 2: 8개 추가
- 워크플로우 체인 연결 검증 (analyze → decide → create 흐름)
- 커뮤니티 기여 가이드 (CONTRIBUTING.md) 공개
- 총 38개 + meta 3개 = **41개**

### Phase 3: 생태계 연결 (Month 2-3)

- AI_PM_Skills와 크로스 링크
- 100 Agents와 연동
- 커뮤니티 기여 프롬프트 수용
- 영어 번역 버전 추가 (글로벌 유입)

---

## 6. 재해석 원칙 (deanpeters → v2)

deanpeters 프롬프트를 단순 번역이 아닌 **재해석**하는 원칙:

| 원칙 | 설명 | 예시 |
|------|------|------|
| **레이어 분리** | 원본 1개 → Layer 1/2/3으로 분리 | JTBD 원본 → Quick(5줄) + Deep(Reasoning Strategy) + Build(API) |
| **교육 주석** | 설계 의도를 `<!-- 주석 -->`으로 추가 | `<!-- 왜 4단계로 나누는가? AI는 단일 지시보다 단계별 지시에서 30-50% 더 구체적 -->` |
| **AI 제품 컨텍스트** | Layer 2 Tips에 AI 제품 특화 조언 | "AI 기능이라면: hallucination rate, latency, 모델 비용을 추가 고려" |
| **한국 SaaS 컨텍스트** | Layer 2 Tips에 한국 시장 특수성 | "네이버 카페, 블라인드 리뷰, 국내 SaaS 경쟁 환경" |
| **코드 연동** | Layer 3에 Python/CLI 코드 추가 | OpenAI/Anthropic API 호출, Claude Code 연동 |
| **워크플로우 체인** | 🔗 다음 단계로 연결 | "이 분석 결과 → feature-prioritization.md의 input으로" |
| **자기 검증** | 마지막 단계에 검증 지시 추가 | "모호한 부분을 찾아 구체적으로 다시 쓰세요" |

---

## 7. 작업량 추정

| 작업 | 예상 소요 | 비고 |
|------|----------|------|
| 레포 생성 + 구조 셋업 | 30분 | README, templates, 폴더 생성 |
| 오리지널 MVP 5개 | 2-3시간 | 가장 깊이 있는 프롬프트, 실행 예시 포함 |
| deanpeters 재해석 22개 | 4-6시간 | 원본 분석 → 레이어드 재구성 → 한국어 → 코드 |
| meta/ 3개 | 1시간 | 설계 원칙 + 프롬프트 빌더 + 해부학 |
| README + CONTRIBUTING | 1시간 | 바이럴 진입점인 README 품질이 핵심 |
| **Phase 1 총계** | **~10시간** | 일주일 내 출시 가능 |
