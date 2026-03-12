# 경쟁 분석: deanpeters/product-manager-prompts

> 조사일: 2026-03-11
> 대상: [deanpeters/product-manager-prompts](https://github.com/deanpeters/product-manager-prompts)
> 목적: ai-pm-prompts 차별화 전략 도출

---

## 1. 기본 정보

| 항목 | 값 |
|------|-----|
| Stars | 709 |
| Forks | 157 |
| Watching | 24 |
| Contributors | 2 (본인 + Claude) |
| Language | Python 100% |
| License | MIT |
| 시작일 | ~2024년 |
| 최근 업데이트 | 2026-03-02 (last week) |

---

## 2. 레포 구조

```
product-manager-prompts/
├── prompts/                    # 메인 컬렉션 (~25개 프롬프트)
│   ├── a-generative-AI-prompt-builder-for-product-...md
│   ├── backlog-epic-hypothesis.md
│   ├── company-profile-executive-insights-research...md
│   ├── customer-journey-mapping-prompt-template...md
│   ├── eol-for-a-product-message.md
│   ├── framing-the-problem-statement.md
│   ├── futuristic-product-faq.md
│   ├── howto.md
│   ├── jobs-to-be-done.md
│   ├── pestel-analysis-prompt-template.md
│   ├── positioning-statement.md
│   ├── proto-persona-profile.md
│   ├── recommendation-canvas-template.md
│   ├── reverse-engineer-IEEE830srs-to-PRD-promp...md
│   ├── reverse-engineer-ISO29148-to-PRD-prompt-...md
│   ├── storyboard-storytelling-prompt.md
│   ├── strategic-scrum-team-session-kickoff.md
│   ├── user-story-mapping.md
│   ├── user-story-prompt-template.md
│   ├── user-story-splitting-prompt-template.md
│   ├── user-story_ai-enhanced_prompt-template.md
│   └── visionary-press-release.md
├── prompt-generators/          # 메타 프롬프트 (프롬프트를 만드는 프롬프트)
├── storytelling/               # 스토리보드, 프레스릴리즈
├── resumes-resignations-reactions/  # 유머/치유 콘텐츠
├── vibes/                      # Vibe coding 가이드
├── skeletons/                  # 프롬프트 분석/역공학
├── flows/                      # LangFlow 연동
├── AGENTS.md
├── README.md
├── SESSION-SUMMARY-2026-...md
├── SUBMISSIONS-GUIDE.md
└── prompting-style-guide.md
```

---

## 3. 콘텐츠 특성

### 포지셔닝
> "Practical AI tools that actually help with both the strategic thinking and daily execution of product management"

### 접근 방식
- "복사해서 AI에 붙여넣기" 방식 — **AI를 도구로 사용하는 관점**
- Step 1: Find a prompt → Step 2: Paste it → Step 3: Answer and iterate
- 전통 PM 프레임워크 기반 (JTBD, Value Proposition Canvas, DACI)
- "대화형" 프롬프트 — AI가 질문을 하고 유저가 응답하는 구조

### 설계 철학
- You stay in control — AI asks questions, you make the strategic decisions
- Context builds gradually — AI learns about your situation step by step
- Framework thinking — Uses proven PM methodologies
- Quality control built in — The AI knows when to ask for missing information

### 강점
- 프롬프트 수가 25개+로 꽤 많음
- 꾸준히 업데이트 (최근 1주 전)
- Product-Manager-Skills 별도 레포로 확장 (Skills/Plugins 형태)
- SUBMISSIONS-GUIDE로 커뮤니티 기여 유도

### 약점
- 영어 only
- 단발성 프롬프트 (프롬프트 간 연결 없음)
- 실행 결과 예시 없음
- AI 제품 특화 콘텐츠 없음
- 범용 PM 대상 (시니어/CPO 관점 부재)

---

## 4. GAP 분석: deanpeters가 하는 것 vs 안 하는 것

| deanpeters가 하는 것 | deanpeters가 안 하는 것 |
|---|---|
| 전통 PM 프레임워크 (JTBD, PESTEL) | **Agentic PM 워크플로우** (Agent가 능동적으로 작업) |
| 단발성 프롬프트 (복사→붙여넣기) | **멀티턴 체인** (결과물이 다음 프롬프트의 입력) |
| 영어만 | **한국어 + 아시아 SaaS 컨텍스트** |
| 범용 PM | **AI 제품 PM 특화** (AI Dubbing, AI Avatar, Agentic AI) |
| 프롬프트만 | **프롬프트 + 실행 결과 예시** |
| AI를 "도구"로 사용 | **AI Native 사고** (Product Trio 멀티 관점) |
| 개인 기여 위주 | **실전 사례 기반** (20년 경력 CPO 관점) |

---

## 5. 시장 내 다른 PM 프롬프트/스킬 레포

| 레포 | Stars | 특징 | 차별점 |
|------|-------|------|--------|
| [deanpeters/product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) | 709 | PM 프롬프트 컬렉션 | 전통 PM 프레임워크 |
| [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills) | - | Claude Code Skills/Plugins | Skills 형태 |
| [jinjin1/Cursor-for-Product-Managers](https://github.com/jinjin1/Cursor-for-Product-Managers) | - | Cursor IDE 기반 PM 워크플로우 | AI-native IDE 연동 |
| [phuryn/pm-skills](https://github.com/phuryn/pm-skills) | - | 100+ agentic PM skills | Teresa Torres, Marty Cagan 프레임워크 |
| [sdi2200262/agentic-project-management](https://github.com/sdi2200262/agentic-project-management) | - | Multi-agent 프로젝트 관리 | AI 에이전트 협업 |

**핵심 발견:** 한국어 PM 프롬프트 레포는 검색 결과 **0개**. 완전한 블루오션.

---

## Sources

- [deanpeters/product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) — 709 Stars
- [deanpeters/Product-Manager-Skills](https://github.com/deanpeters/Product-Manager-Skills)
- [jinjin1/Cursor-for-Product-Managers](https://github.com/jinjin1/Cursor-for-Product-Managers)
- [phuryn/pm-skills](https://github.com/phuryn/pm-skills)
- [sdi2200262/agentic-project-management](https://github.com/sdi2200262/agentic-project-management)
