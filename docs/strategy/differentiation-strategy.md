# ai-pm-prompts 차별화 전략

> 작성일: 2026-03-11
> 목적: ai-pm-prompts 레포의 포지셔닝과 설계 원칙 정의

---

## 1. 포지셔닝: "AI 제품을 만드는 PM이 AI를 쓰는 법"

| | deanpeters | ai-pm-prompts (Ethan) |
|---|---|---|
| 타겟 | 일반 PM | **AI 제품 PM / CPO** |
| 언어 | English | **한국어 (Korean-first)** |
| 관점 | AI를 도구로 사용 | **AI Native 사고로 제품 만들기** |
| 형식 | 단발성 프롬프트 | **워크플로우 체인 (Input→Output→Next)** |
| 실전성 | 프레임워크 중심 | **실제 제품 사례 기반 (AI Dubbing, Avatar 등)** |
| 경력 관점 | 범용 | **20년 CPO 관점의 시니어 사고** |

**핵심 차별화:** deanpeters는 "AI를 도구로 쓰는 PM"이고, 이 레포는 "AI 제품을 만드는 PM이 AI를 쓰는 법"

---

## 2. 프롬프트 설계 원칙

### 기존 프레임워크 vs AI Native PM 접근

| 기존 (WISER/SMART) | AI Native PM 접근 (이 레포) |
|---|---|
| 역할 1개 지정 | **Product Trio로 3관점 동시 사고** (PM + Designer + Engineer) |
| 단일 출력 | **Reasoning Strategy로 단계별 사고 과정 설계** |
| 결과물 중심 | **과정과 탐구 과정 중시** |
| 범용 | **경쟁사 데이터 기반 가설 수립** |
| 정적 프롬프트 | **멀티턴 + 자기 검증 내장** |

### AI Native PM 프롬프트 5원칙

1. **질문과 답변 구조** — 결과물보다 사고 과정을 설계
2. **경쟁사 기반 가설** — 시장 데이터에서 가설을 세우고 검증
3. **Reasoning Strategy** — 단계별 추론 전략을 프롬프트에 명시
4. **워크플로우 체인** — 결과물이 다음 프롬프트의 입력 (🔗 다음 단계)
5. **자기 검증** — 마지막 단계에서 "모호한 부분을 찾아 구체화" 지시

---

## 3. 각 프롬프트 파일의 표준 구조

```markdown
# [이모지] [프롬프트 제목] (English Name)

> 카테고리: XX-category
> 난이도: ★☆☆ / ★★☆ / ★★★
> 예상 소요: XX분 (멀티턴)
> 연결 프롬프트: → `다음-프롬프트.md` → `그다음-프롬프트.md`

## 🎯 이 프롬프트가 해결하는 문제
[어떤 상황에서, 어떤 고통이 있고, 이 프롬프트를 쓰면 어떻게 해결되는지]

## 📋 프롬프트
[실제 프롬프트 텍스트 — 역할, 목표, Reasoning Strategy, 출력 형식, 컨텍스트]

## 💡 사용 팁
### 데이터 수집 방법
### AI 제품 PM이라면 추가할 컨텍스트
### 한국 SaaS 컨텍스트

## 📊 실행 결과 예시
### Input 예시
### Output 요약 (Claude/ChatGPT 실행 결과)

## 🔗 다음 단계
[이 분석 결과를 가지고 연결할 수 있는 프롬프트들]
```

### deanpeters와의 구조 차이

| 구조 요소 | deanpeters | ai-pm-prompts |
|-----------|-----------|---------------|
| 프롬프트 텍스트 | ✅ | ✅ |
| 문제 정의 | ❌ | ✅ **🎯 이 프롬프트가 해결하는 문제** |
| 사용 팁 | ❌ | ✅ **💡 데이터 수집법 + AI 제품 팁 + 한국 컨텍스트** |
| 실행 결과 예시 | ❌ | ✅ **📊 Before→After 포함** |
| 워크플로우 연결 | ❌ | ✅ **🔗 다음 단계** |
| Reasoning Strategy | ❌ | ✅ **단계별 추론 전략 내장** |

---

## 4. 카테고리 구조

PM의 **의사결정 여정** 기준 분류 (deanpeters는 PM 업무 유형 분류):

```
ai-pm-prompts/
├── 01-discovery/          # 문제 발견 & 기회 탐색
│   ├── competitor-sentiment-analysis.md
│   ├── user-problem-hypothesis.md
│   └── market-sizing-with-ai.md
├── 02-strategy/           # 전략 수립 & 우선순위
│   ├── feature-prioritization-rice.md
│   ├── ai-product-positioning.md
│   └── build-vs-buy-ai-capability.md
├── 03-execution/          # 스펙 & 실행
│   ├── prd-for-ai-feature.md
│   ├── ai-model-evaluation-criteria.md
│   └── prompt-engineering-for-pm.md
├── 04-growth/             # 그로스 & 메트릭
│   ├── ai-feature-adoption-metrics.md
│   ├── ab-test-design-ai-product.md
│   └── retention-analysis-prompt.md
├── 05-leadership/         # 리더십 & 커뮤니케이션
│   ├── executive-briefing-ai-strategy.md
│   ├── cross-functional-alignment.md
│   └── ai-ethics-review-checklist.md
└── templates/             # 공통 템플릿
    └── prompt-template.md
```

---

## 5. 3각 구도 전략

```
ai-pm-prompts (한국어 AI PM 프롬프트)
       ↕ 시너지
AI_PM_Skills (Claude Code Skills/Plugins)
       ↕ 시너지
AI_Engineer / 100 Agents (실행 가능한 Agent 컬렉션)
```

- **ai-pm-prompts** → "이런 프롬프트로 이렇게 생각하세요"
- **AI_PM_Skills** → "이 프롬프트가 자동화된 Skills로 실행됩니다"
- **100 Agents** → "Agent가 이 워크플로우를 능동적으로 수행합니다"

세 레포가 서로 링크하면서 시너지 + 크로스 Star 유입.

---

## 6. 초기 프롬프트 우선순위

| 순위 | 프롬프트 | 카테고리 | 수요 | 차별화 | 근거 |
|------|---------|---------|------|--------|------|
| 1 | competitor-sentiment-analysis | 01-discovery | 🥇 | 🔴 높음 | 수요 1위 + 감성 점수 + 기회 매트릭스 |
| 2 | user-problem-hypothesis | 01-discovery | 🥈 | 🟠 높음 | 수요 2위 + 1번 결과 연결 |
| 3 | prd-for-ai-feature | 03-execution | 🥉 | 🔴 높음 | AI 제품 특화 PRD |
| 4 | feature-prioritization-rice | 02-strategy | 4위 | 🟡 중간 | 데이터 기반 우선순위 |
| 5 | ai-product-positioning | 02-strategy | - | 🔴 높음 | 빈 영역, AI 제품 특화 |
