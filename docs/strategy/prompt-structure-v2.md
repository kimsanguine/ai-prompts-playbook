# 프롬프트 구조 재설계 v2: 레이어드 프롬프트

> 작성일: 2026-03-11
> 목적: "AI PM 프롬프트이지만 AI 학생, AI 엔지니어도 쓸 수 있는" 구조 설계

---

## 1. 핵심 컨셉: "Layered Prompts"

하나의 프롬프트가 3개 레이어를 가집니다.
같은 파일인데, 사용자가 자기 수준과 역할에 맞게 골라 씁니다.

```
┌─────────────────────────────────────────┐
│  Layer 1: Quick Start (누구나 즉시 사용)    │  ← AI 학생, 비개발자, 초보
│  "이 프롬프트를 복사해서 AI에 붙여넣으세요"    │     5분이면 결과
├─────────────────────────────────────────┤
│  Layer 2: Deep Dive (사고 과정 설계)       │  ← PM, 기획자, 시니어
│  Reasoning Strategy + Multi-perspective   │     20분, 깊은 분석
│  교육적 주석 포함 (<!-- 왜 이렇게? -->)       │
├─────────────────────────────────────────┤
│  Layer 3: Build & Automate (코드 연동)     │  ← AI 엔지니어, 개발자
│  API 호출, Agent 연동, 자동화 스크립트       │     30분+, 파이프라인
└─────────────────────────────────────────┘
```

### 설계 근거

| 벤치마크 | 채용한 것 | 이유 |
|----------|-----------|------|
| awesome-chatgpt-prompts (151K) | **낮은 진입장벽** → Layer 1 | "Act as..." 한 줄로 즉시 시작 → 바이럴 |
| deanpeters (709) | **교육적 주석** → Layer 2 | 프롬프트 안에서 배움 → 충성도 |
| NirDiamant/Prompt_Engineering | **초보→고급 스펙트럼** | 다양한 수준의 사용자 커버 |
| agency-agents (27K) | **실행 가능성** → Layer 3 | 코드 연동이 있으면 개발자 유입 |

---

## 2. 새로운 포지셔닝

### v1 → v2 전환

| | v1 (기존) | v2 (재설계) |
|---|---|---|
| 타겟 | AI PM/CPO 전용 | **AI로 일하는 모든 사람** |
| 포지셔닝 | "AI 제품을 만드는 PM이 AI를 쓰는 법" | **"AI 시대의 사고법"** |
| 진입장벽 | 긴 구조화된 프롬프트 하나 | **Layer 1: 5분에 결과** |
| 교육성 | 사용 팁 섹션 | **주석으로 "왜"를 설명** |
| 엔지니어 유입 | 없음 | **Layer 3: 코드 + API + Agent** |
| 언어 | 한국어 only | **한국어 우선 + 영어 프롬프트 병기** |
| 바이럴 잠재력 | PM 커뮤니티 한정 | **개발자 + 학생 + PM 교차 유입** |

### 태그라인

- 한국어: **"AI 시대의 사고법 — PM이 설계하고, 누구나 쓰고, 엔지니어가 자동화하는 프롬프트"**
- 영어: **"Think like a PM. Prompt like an engineer. Ship with AI."**

---

## 3. 프롬프트 파일 표준 구조 (v2)

```markdown
# [이모지] [프롬프트 제목 한국어] ([English Name])

> 난이도: ★☆☆ → ★★★ (레이어별 난이도 상승)
> 예상 소요: 5분 (Quick) / 20분 (Deep) / 30분+ (Build)
> 워크플로우: → `다음-프롬프트.md` → `그다음-프롬프트.md`

---

## 🎯 이 프롬프트가 해결하는 문제
[역할 무관하게 공감할 수 있는 문제 정의]
[어떤 상황에서, 어떤 고통이 있고, 이 프롬프트로 어떻게 해결되는지]

---

## ⚡ Layer 1: Quick Start
<!-- 복사해서 바로 쓰세요. AI 초보자도 5분이면 결과를 얻습니다. -->

[짧고 직관적인 프롬프트 — 최대 10줄]

**💡 Quick Tips:**
- [데이터를 어디서 구하는지]
- [흔한 실수와 해결법]

---

## 🧠 Layer 2: Deep Dive
<!-- PM, 기획자를 위한 구조화된 사고 설계.
     "왜 이렇게 설계했는가"를 주석으로 설명합니다. -->

[구조화된 프롬프트 — 역할, 목표, Reasoning Strategy]
[HTML 주석으로 설계 의도 설명]

**💡 Deep Tips:**
- **데이터 수집 방법**
- **AI 제품이라면 추가할 컨텍스트**
- **한국 SaaS 컨텍스트**
- **Product Trio 확장 (PM + 디자이너 + 엔지니어 관점)**

---

## 🔧 Layer 3: Build & Automate
<!-- AI 엔지니어를 위한 코드 연동.
     이 프롬프트를 자동화 파이프라인에 넣으세요. -->

### Python + API 자동화
[코드 스니펫]

### Claude Code / MCP 연동
[CLI 명령어]

### Agent 워크플로우 연결
[다른 프롬프트와의 자동 파이프라인]

---

## 📊 실행 결과 예시
### Layer 1 실행 결과
[Quick Start 프롬프트의 실제 출력]

### Layer 2 실행 결과
[Deep Dive 프롬프트의 실제 출력 — 더 깊고 구조화됨]

---

## 🔗 다음 단계
| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| [결과 A] | → `next-prompt.md` | [왜 이 순서인지] |
| [결과 B] | → `another-prompt.md` | [어떻게 연결되는지] |
```

---

## 4. 카테고리 재설계: "사고 유형" 기준

### v1 (PM 업무 여정) → v2 (사고 유형)

| v1 카테고리 | 문제점 | v2 카테고리 | 왜 더 나은가 |
|------------|--------|------------|-------------|
| 01-discovery | PM 전문용어 | **analyze/** | "분석하기"는 누구나 이해 |
| 02-strategy | PM 전문용어 | **decide/** | "결정하기"는 보편적 |
| 03-execution | PM 전문용어 | **create/** | "만들기"는 직관적 |
| 04-growth | PM 전문용어 | **measure/** | "측정하기"는 데이터팀도 관심 |
| 05-leadership | PM 전문용어 | **communicate/** | "소통하기"는 모든 역할 |

### v2 디렉토리 구조

```
ai-pm-prompts/
├── README.md                            # 3초 안에 이해 가능한 소개
├── CONTRIBUTING.md                      # 커뮤니티 기여 가이드
├── prompts/
│   ├── analyze/                         # 분석하기 (경쟁사, 시장, 데이터)
│   │   ├── competitor-sentiment-analysis.md
│   │   ├── market-sizing.md
│   │   └── user-review-clustering.md
│   ├── decide/                          # 결정하기 (우선순위, 전략, 트레이드오프)
│   │   ├── feature-prioritization-rice.md
│   │   ├── build-vs-buy-ai.md
│   │   └── positioning-strategy.md
│   ├── create/                          # 만들기 (PRD, 스펙, 제안서)
│   │   ├── prd-for-ai-feature.md
│   │   ├── user-story-with-ai-criteria.md
│   │   └── executive-briefing.md
│   ├── measure/                         # 측정하기 (메트릭, 실험, 성과)
│   │   ├── ai-feature-adoption-metrics.md
│   │   ├── ab-test-design.md
│   │   └── retention-analysis.md
│   └── communicate/                     # 소통하기 (설득, 정렬, 리포트)
│       ├── stakeholder-alignment.md
│       ├── ai-ethics-review.md
│       └── cross-team-handoff.md
├── templates/
│   └── layered-prompt-template.md       # v2 레이어드 프롬프트 템플릿
└── docs/
    ├── prompt-design-principles.md      # AI Native PM 프롬프트 설계 원칙
    └── how-to-contribute.md             # 기여 방법 상세 가이드
```

---

## 5. AI Native PM 프롬프트 설계 원칙 (v2 업데이트)

### v1 5원칙 → v2 7원칙

| # | v1 원칙 | v2 원칙 (업데이트) |
|---|---------|-------------------|
| 1 | 질문과 답변 구조 | **질문과 답변 구조** (유지) |
| 2 | 경쟁사 기반 가설 | **데이터 기반 가설** (범용화: 경쟁사뿐 아니라 모든 데이터) |
| 3 | Reasoning Strategy | **Reasoning Strategy** (유지) |
| 4 | 워크플로우 체인 | **워크플로우 체인** (유지) |
| 5 | 자기 검증 | **자기 검증** (유지) |
| 6 | (신규) | **레이어드 접근성** — 누구나 시작, 깊이는 선택 |
| 7 | (신규) | **교육적 투명성** — "왜 이렇게 설계했는가"를 주석으로 공개 |

### 원칙 6: 레이어드 접근성 (Layered Accessibility)
- Layer 1은 5줄 이내, 전문용어 최소화
- Layer 2는 "왜"를 설명하며 깊이 추가
- Layer 3는 코드로 실행 가능하게
- **같은 문제를 다른 깊이로 해결**

### 원칙 7: 교육적 투명성 (Educational Transparency)
- deanpeters의 "Teaching through doing" 채용
- HTML 주석(`<!-- 왜 이렇게? -->`)으로 설계 의도 공개
- 프롬프트를 쓰면서 동시에 **프롬프트 엔지니어링을 학습**
- AI 학생이 가장 많이 얻어가는 부분

---

## 6. 각 페르소나별 가치 제안

### 🎓 AI 학생 / 초보자
- **진입점:** Layer 1 — 복사해서 붙여넣기, 5분에 결과
- **학습:** Layer 2의 주석 — "왜 이 구조가 작동하는지" 학습
- **가치:** "프롬프트 엔지니어링을 실전으로 배우는 교과서"

### 📋 PM / 기획자
- **진입점:** Layer 2 — 구조화된 사고 프레임워크
- **활용:** Reasoning Strategy, Product Trio 멀티 관점, 워크플로우 체인
- **가치:** "AI Native 시대의 PM 사고법"

### 🔧 AI 엔지니어
- **진입점:** Layer 3 — API 코드, Agent 연동, 자동화 스크립트
- **활용:** 프롬프트를 파이프라인에 통합, MCP/Claude Code 연동
- **가치:** "PM의 사고가 녹아든 프로덕션 프롬프트"

---

## 7. 3각 구도 전략 업데이트

```
ai-pm-prompts (사고법 프롬프트 — 누구나)
       ↕ Layer 3가 Skills와 직접 연결
AI_PM_Skills (자동화 Skills — Claude Code 사용자)
       ↕ Skills가 Agent의 도구로 작동
100 Agents (AI Agent 컬렉션 — Agent 빌더)
```

**크로스 링크 전략:**
- ai-pm-prompts Layer 3 → "이 프롬프트를 자동화하려면 → AI_PM_Skills의 XX Skill"
- AI_PM_Skills → "이 Skill의 사고 기반 → ai-pm-prompts의 XX 프롬프트"
- 100 Agents → "이 Agent가 사용하는 프롬프트 → ai-pm-prompts의 XX"

---

## Sources

- [deanpeters/product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) — 709 Stars, "Teaching through doing" 접근
- [f/awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) — 151K Stars, 낮은 진입장벽의 힘
- [agency-agents](https://github.com/msitarzewski/agency-agents) — 27K Stars, MD-only 컬렉션
- [NirDiamant/Prompt_Engineering](https://github.com/NirDiamant/Prompt_Engineering) — 초보→고급 스펙트럼
- [DAIR-AI/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) — 3M+ learners
- [GitHub Stars Guide 2026](https://blog.tooljet.com/github-stars-guide/)
- [10 Proven Ways to Boost GitHub Stars](https://scrapegraphai.com/blog/gh-stars)
