# 🧠 AI Prompts Playbook

**한국 1인 빌더·PM·CPO를 위한 업무형 AI 프롬프트 레지스트리 + 실행 워크플로우 + 평가 가능한 샘플셋**

<p align="center">
  <img src="assets/hero-question-prism.png" alt="AI Prompts Playbook — Question Prism Framework" width="960">
</p>

이 저장소는 범용 프롬프트 모음이 아닙니다. 혼자 제품을 만들거나 제품 의사결정을 맡는 사람이 매일 하는 일을 **입력 → 프롬프트 → 산출물 → 검증 → 다음 업무**로 연결하기 위한 실행형 플레이북입니다.

| 바로 하려는 일 | 시작점 | 결과물 |
|----------------|--------|--------|
| 처음 써보기 | [Starter Path](starter/) | 5개 핵심 업무 흐름 |
| 프롬프트 찾기 | [Prompt Registry](registry/prompts.yaml) | 검색/추천 가능한 메타데이터 |
| 업무 흐름으로 실행 | [워크플로우 체인](#-프롬프트는-혼자-쓰는-게-아니라-연결해서-쓴다) | 분석 → 결정 → 문서 → 측정 → 정렬 |
| 품질 검증하기 | [Evaluation Guide](evals/) | 샘플 입력, 기대 출력, 평가 루브릭 |

## 이 저장소가 해결하는 문제

| 문제 | 이 플레이북의 답 |
|------|------------------|
| 프롬프트가 너무 많아 뭘 써야 할지 모른다 | 35개 업무 프롬프트를 역할, 입력, 출력, 다음 단계로 정리 |
| AI 결과가 그럴듯하지만 의사결정에 쓰기 어렵다 | 판단 기준, 근거, 가정, 검증 질문을 출력에 포함 |
| 프롬프트가 한 번 쓰고 끝난다 | 앞 프롬프트의 출력이 다음 프롬프트의 입력이 되는 워크플로우 설계 |
| 한국 제품 업무 맥락이 빠진다 | PIPA, DART, 잡플래닛, 품의서, 합의제 의사결정 맥락 반영 |
| 좋은 프롬프트인지 평가하기 어렵다 | `evals/`에 샘플 입력과 평가 루브릭 제공 |

## 저장소 구조

| 경로 | 역할 |
|------|------|
| [`prompts/`](prompts/) | 35개 업무 프롬프트와 5개 메타 가이드 |
| [`registry/`](registry/) | 앱, RAG, 검색에 쓰기 위한 구조화 메타데이터 |
| [`starter/`](starter/) | 초급자를 위한 5단계 시작 경로 |
| [`evals/`](evals/) | 프롬프트 품질 평가 기준과 핵심 시나리오 |
| [`docs/`](docs/) | 시장 조사, 전략, 설계 배경 |

## AI_PM에서 검증된 프롬프트

일부 프롬프트는 [kimsanguine/AI_PM](https://github.com/kimsanguine/AI_PM)의 Claude Code for PMs 과정에서 실제 command/skill로 사용된 패턴을 범용 프롬프트 카드로 재구성했습니다.

| AI_PM 실행 자산 | 이 레포의 canonical prompt |
|----------------|----------------------------|
| `/discovery`, `discovery-synthesizer` | [Discovery 인사이트 합성](prompts/analyze/discovery-insight-synthesis.md) |
| `/competitor`, `competitor-battlecard` | [경쟁사 배틀카드](prompts/analyze/competitor-battlecard.md) |
| `/prd`, `prd-generator` | [소크라틱 PRD 생성기](prompts/create/socratic-prd-generator.md) |
| `experiment-analyzer` | [실험 결과 분석](prompts/measure/experiment-result-analysis.md) |
| `kpi-card-builder` | [KPI 정의 카드](prompts/measure/kpi-definition-card.md) |

## AI에게 "답"을 구하지 마세요. "질문하는 법"을 바꾸세요.

2024년 Harvard AI 튜터 실험에서 흥미로운 결과가 나왔습니다.
같은 AI를 쓴 두 그룹 — 한 그룹은 답을 달라고 했고, 다른 그룹은 **구조적 질문**을 받았습니다.
결과: 구조적 질문을 받은 학생의 학습 성과가 **2배** 높았고, 답만 받은 학생의 추론 능력은 오히려 **하락**했습니다.

같은 AI. 다른 질문. 완전히 다른 결과.

이 플레이북은 **"AI에게 어떻게 질문할 것인가"**에 대한 35개의 업무 프롬프트와 5개의 메타 가이드입니다.
1인 빌더와 PM/CPO가 매일 하는 일 — 경쟁사 분석, PRD 작성, 우선순위 결정, AI 기능 설계, 의사결정 보고 — 을
**구조화된 질문, 판단 기준, 검증 루프**로 풀어냅니다.

---

## 왜 "질문의 구조"가 중요한가?

```
❌ "경쟁사 분석해줘"
→ AI가 아는 것을 나열함 → 어디서든 볼 수 있는 결과

✅ "경쟁사 유저 5,000명의 리뷰를 5개 페르소나로 분류하고,
    각 페르소나의 JTBD와 감정 점수를 산출한 뒤,
    감정 점수가 가장 낮은 그룹에서 우리의 기회를 도출해줘"
→ AI가 단계별로 추론함 → 전략적 의사결정 근거가 나옴
```

차이는 "더 자세히 쓴 것"이 아닙니다.
**AI에게 어떤 기준으로 보고, 어떤 순서로 정리하고, 무엇을 검증해야 하는지 설계해준 것**입니다.

이 플레이북의 모든 프롬프트는 이 원리 위에 있습니다:
> **전문가의 프레이밍을 빌리고, 판단 근거와 가정을 드러내며, 마지막에는 실제 데이터로 검증한다.**

---

## 세 개의 질문 — 이 플레이북의 설계 철학

모든 프롬프트는 세 가지 질문을 따릅니다:

```mermaid
graph LR
    Q1["❓ 전문가는 이걸<br/>어떤 틀로 보나요?<br/><br/>⚡ Layer 1: 전문가의 눈"]
    Q2["❓ 전문가들도 답을<br/>못 내린 부분은?<br/><br/>🧠 Layer 2: 합의 너머"]
    Q3["❓ 내가 이해한 걸<br/>어떻게 검증하나요?<br/><br/>🔧 Layer 3: 자기 검증"]

    Q1 -->|"결과가 피상적이면"| Q2
    Q2 -->|"확신이 필요하면"| Q3

    style Q1 fill:#e8f5e9,stroke:#4caf50
    style Q2 fill:#e3f2fd,stroke:#2196f3
    style Q3 fill:#fce4ec,stroke:#f44336
```

| | Layer 1: 전문가의 눈 | Layer 2: 합의 너머 | Layer 3: 자기 검증 |
|--|--|--|--|
| **질문** | 전문가는 이 문제를 어떤 프레임으로 보나? | 전문가들 사이에서도 의견이 갈리는 지점은? | 내가 얻은 답을 어떻게 테스트하나? |
| **AI 활용** | 전문가의 프레이밍을 빌려서 질문 | 판단 기준, 근거, 가정을 분리 | Python/SQL로 결과를 코드 검증 |
| **소요** | 5-10분 | 20-30분 | 30-60분 |
| **결과** | 구조화된 초안 | 전문가급 분석 | 자동화된 파이프라인 |

이것은 "초보 → 고급" 난이도가 아닙니다.
**"빌려서 생각하기 → 의심하기 → 검증하기"라는 인지의 깊이**입니다.

> 📖 더 깊이 읽기: [세 개의 질문 — AI 시대의 사고법](prompts/meta/three-questions.md)

---

## ⚡ 지금 바로 시작하기

아래를 복사해서 ChatGPT/Claude/Gemini에 붙여넣으세요:

```
당신은 10년 경력의 프로덕트 전략 컨설턴트입니다.

# 목표
{경쟁사명}의 사용자 감정을 분석하여 우리 제품의 기회를 발견합니다.

# 추론 전략
1. 먼저 {경쟁사명} 사용자들의 주요 불만/칭찬을 5개 페르소나로 분류하세요.
2. 각 페르소나별로: 목표, JTBD, 감정 점수(-1~1), 핵심 불만을 정리하세요.
3. 마지막으로, 감정 점수가 가장 낮은 페르소나의 불만에서 우리의 기회를 3개 도출하세요.

# 출력 형식
페르소나별 표 + 기회 매트릭스 (영향력 × 실현 가능성)
```

`{경쟁사명}`을 실제 경쟁사로 바꾸면 끝입니다.

**왜 이게 일반 프롬프트와 다른가요?**
- `역할 설정` → AI가 전문가의 프레이밍을 빌림
- `추론 전략 1→2→3` → AI가 결과를 구조화하고 근거를 남김
- `출력 형식 지정` → 결과가 바로 의사결정에 쓸 수 있는 형태

→ [이 프롬프트의 Layer 2, 3 보기](prompts/analyze/competitor-sentiment.md)

---

## 🔗 프롬프트는 혼자 쓰는 게 아니라 연결해서 쓴다

하나의 프롬프트로 끝나지 않습니다. **앞 프롬프트의 출력이 다음 프롬프트의 입력**이 됩니다.

```mermaid
graph TD
    A["🔍 경쟁사 감정 분석<br/><i>5개 페르소나 + 기회</i>"]
    B["🔧 문제 정의<br/><i>구조화된 Problem Statement</i>"]
    C["⚖️ RICE 우선순위<br/><i>점수화된 기능 목록</i>"]
    D["🛠️ AI 기능 PRD<br/><i>기술 스펙 포함 PRD</i>"]
    E["📊 AI 도입 메트릭스<br/><i>성공 지표 정의</i>"]
    F["💬 이해관계자 얼라인먼트<br/><i>팀 승인 확보</i>"]

    A -->|"기회 매트릭스"| B
    B -->|"문제 정의서"| C
    C -->|"우선순위 목록"| D
    D -->|"PRD"| E
    E -->|"메트릭 대시보드"| F

    style A fill:#e8f5e9,stroke:#4caf50
    style B fill:#e8f5e9,stroke:#4caf50
    style C fill:#fff3e0,stroke:#ff9800
    style D fill:#e3f2fd,stroke:#2196f3
    style E fill:#f3e5f5,stroke:#9c27b0
    style F fill:#fce4ec,stroke:#f44336
```

각 프롬프트에 `📥 워크플로우 입력` 섹션이 있습니다.
"이전 프롬프트에서 뭘 가져와야 하는지"가 명시되어 있어서, 자연스럽게 체인이 만들어집니다.

---

## 🧭 초급자는 여기서 시작하세요

35개를 모두 읽지 마세요. 처음에는 [`starter/`](starter/)의 5개 경로만 따라가면 됩니다.

| 순서 | 프롬프트 | 결과물 |
|------|----------|--------|
| 1 | [경쟁사 감성 분석](prompts/analyze/competitor-sentiment.md) | 페르소나 + 기회 매트릭스 |
| 2 | [문제 정의](prompts/analyze/problem-framing.md) | 검증 가능한 Problem Statement |
| 3 | [기능 우선순위](prompts/decide/feature-prioritization.md) | RICE 기반 우선순위 |
| 4 | [AI 기능 PRD](prompts/create/prd-for-ai-feature.md) | 실패 시나리오 포함 PRD |
| 5 | [임원 브리핑](prompts/create/executive-briefing.md) | 의사결정용 브리핑 |

---

## 🗂️ 데이터로 활용하기

이 저장소는 Markdown 문서로 읽을 수도 있고, 구조화된 프롬프트 레지스트리로 활용할 수도 있습니다.

| 용도 | 파일 |
|------|------|
| 프롬프트 검색/추천 | [`registry/prompts.yaml`](registry/prompts.yaml) |
| 초급자 첫 실행 경로 | [`starter/README.md`](starter/README.md) |
| 프롬프트 평가 시나리오 | [`evals/scenarios/core.yaml`](evals/scenarios/core.yaml) |
| 평가 기준 | [`evals/README.md`](evals/README.md) |

앱이나 RAG에 연결할 때는 Markdown 전체를 바로 임베딩하기보다 `registry/prompts.yaml`의 `id`, `category`, `input_types`, `output_types`, `tags`, `next`를 먼저 인덱싱하세요.

---

## 🎯 나에게 맞는 프롬프트

### 지금 급한 일이 뭔가요?

**스프린트를 시작해야 한다**
→ [백로그 우선순위](prompts/decide/backlog-prioritization.md) → [스프린트 킥오프](prompts/decide/sprint-kickoff.md) → [유저 스토리](prompts/create/user-story.md)

**PRD를 써야 한다**
→ [JTBD 분석](prompts/analyze/jobs-to-be-done.md) → [페르소나 프로파일링](prompts/analyze/persona-profiling.md) → [요구사항 → PRD](prompts/create/requirements-to-prd.md)

**경쟁사가 움직였다**
→ [경쟁사 감정 분석](prompts/analyze/competitor-sentiment.md) → [포지셔닝 전략](prompts/decide/positioning-strategy.md) → [임원 브리핑](prompts/create/executive-briefing.md)

**임원에게 보고해야 한다**
→ [임원 브리핑](prompts/create/executive-briefing.md) → [이해관계자 얼라인먼트](prompts/communicate/stakeholder-alignment.md) → [스토리텔링](prompts/communicate/storytelling.md)

**AI 기능을 도입하려 한다**
→ [Build vs Buy](prompts/decide/build-vs-buy-ai.md) → [AI 기능 PRD](prompts/create/prd-for-ai-feature.md) → [AI 도입 메트릭스](prompts/measure/ai-adoption-metrics.md)

### 역할별 추천

| PM | CPO | 디자이너 | 엔지니어 |
|-----|------|---------|---------|
| [요구사항→PRD](prompts/create/requirements-to-prd.md) | [임원 브리핑](prompts/create/executive-briefing.md) | [페르소나](prompts/analyze/persona-profiling.md) | [AI 기능 PRD](prompts/create/prd-for-ai-feature.md) |
| [스프린트 킥오프](prompts/decide/sprint-kickoff.md) | [의사결정 캔버스](prompts/decide/decision-canvas.md) | [고객 여정](prompts/analyze/customer-journey-mapping.md) | [A/B 테스트](prompts/measure/ab-test-design.md) |
| [백로그 우선순위](prompts/decide/backlog-prioritization.md) | [포지셔닝 전략](prompts/decide/positioning-strategy.md) | [JTBD](prompts/analyze/jobs-to-be-done.md) | [리텐션 분석](prompts/measure/retention-analysis.md) |
| [유저 스토리](prompts/create/user-story.md) | [Build vs Buy](prompts/decide/build-vs-buy-ai.md) | [스토리 맵핑](prompts/create/user-story-mapping.md) | [AI 윤리 리뷰](prompts/communicate/ai-ethics-review.md) |

---

## 📦 전체 35개 업무 프롬프트

<details>
<summary><b>🔍 analyze/ — 데이터 구조화 & 패턴 발견 (9개)</b></summary>

| 프롬프트 | 핵심 |
|---------|------|
| [경쟁사 감정 분석](prompts/analyze/competitor-sentiment.md) | 리뷰 데이터 → 5개 페르소나 + 감정 점수 + 기회 매트릭스 |
| [Discovery 인사이트 합성](prompts/analyze/discovery-insight-synthesis.md) | 인터뷰·설문·로그 → 근거 있는 인사이트 |
| [문제 정의](prompts/analyze/problem-framing.md) | 모호한 문제 → 구조화된 Problem Statement |
| [Jobs to Be Done](prompts/analyze/jobs-to-be-done.md) | 기능 중심 → Job 중심 사고 전환 |
| [페르소나 프로파일링](prompts/analyze/persona-profiling.md) | 데이터 기반 페르소나 생성 |
| [고객 여정 맵](prompts/analyze/customer-journey-mapping.md) | 접점별 감정 곡선 + 기회 포인트 |
| [PESTEL 분석](prompts/analyze/pestel-analysis.md) | 거시환경 → 제품 전략 영향도 |
| [기업 프로파일링](prompts/analyze/company-profiling.md) | DART + 잡플래닛 한국 기업 분석 |
| [경쟁사 배틀카드](prompts/analyze/competitor-battlecard.md) | 동일 축 비교 + 세일즈 공격/응답 |

</details>

<details>
<summary><b>⚖️ decide/ — 우선순위 & 전략 (6개)</b></summary>

| 프롬프트 | 핵심 |
|---------|------|
| [RICE 우선순위](prompts/decide/feature-prioritization.md) | 프레임워크 기반 기능 우선순위 |
| [포지셔닝 전략](prompts/decide/positioning-strategy.md) | April Dunford 프레임워크 |
| [의사결정 캔버스](prompts/decide/decision-canvas.md) | 합의제 의사결정 구조화 |
| [백로그 우선순위](prompts/decide/backlog-prioritization.md) | 규제/보안 포함 P0-P3 |
| [스프린트 킥오프](prompts/decide/sprint-kickoff.md) | 목표 + 용량 + 리스크 |
| [AI Build vs Buy](prompts/decide/build-vs-buy-ai.md) | AI 특화 의사결정 프레임 |

</details>

<details>
<summary><b>🛠️ create/ — 문서 & 산출물 (10개)</b></summary>

| 프롬프트 | 핵심 |
|---------|------|
| [AI 기능 PRD](prompts/create/prd-for-ai-feature.md) | 모델 스펙 + 실패 시나리오 |
| [소크라틱 PRD 생성기](prompts/create/socratic-prd-generator.md) | 질문 → 옵션 비교 → PRD |
| [유저 스토리](prompts/create/user-story.md) | INVEST + Bad vs Good 비교 |
| [유저 스토리 맵핑](prompts/create/user-story-mapping.md) | Activity → Task → Story |
| [유저 스토리 분할](prompts/create/user-story-splitting.md) | 스프린트 단위 분할 |
| [AI 강화 유저 스토리](prompts/create/user-story-ai-enhanced.md) | AI 특화 AC |
| [스펙 → PRD](prompts/create/spec-to-prd.md) | 기술 스펙 → 비즈니스 PRD |
| [요구사항 → PRD](prompts/create/requirements-to-prd.md) | PIPA/AI기본법 규제 포함 |
| [임원 브리핑](prompts/create/executive-briefing.md) | 두괄식 + 품의서 문화 |
| [제품 EOL 메시지](prompts/create/product-eol-message.md) | 서비스 종료 커뮤니케이션 |

</details>

<details>
<summary><b>📊 measure/ — 지표 & 실험 (5개)</b></summary>

| 프롬프트 | 핵심 |
|---------|------|
| [AI 도입 메트릭스](prompts/measure/ai-adoption-metrics.md) | 신뢰도를 핵심 지표로 |
| [KPI 정의 카드](prompts/measure/kpi-definition-card.md) | 계산식 + source + owner |
| [A/B 테스트 설계](prompts/measure/ab-test-design.md) | AI 특화 샘플 크기 |
| [실험 결과 분석](prompts/measure/experiment-result-analysis.md) | ship / iterate / kill 권고 |
| [리텐션 분석](prompts/measure/retention-analysis.md) | 신뢰도-리텐션 인과관계 |

</details>

<details>
<summary><b>💬 communicate/ — 설득 & 정렬 (5개)</b></summary>

| 프롬프트 | 핵심 |
|---------|------|
| [이해관계자 얼라인먼트](prompts/communicate/stakeholder-alignment.md) | 이해관계자 맵 |
| [프레스 릴리즈](prompts/communicate/press-release.md) | Working Backwards |
| [스토리텔링](prompts/communicate/storytelling.md) | 데이터 + 내러티브 |
| [AI 윤리 리뷰](prompts/communicate/ai-ethics-review.md) | 편향성 통계 검증 |
| [크로스팀 핸드오프](prompts/communicate/cross-team-handoff.md) | 팀별 자동 인수인계 |

</details>

<details>
<summary><b>🧩 meta/ — 철학 & 도구</b></summary>

| 문서 | 역할 |
|------|------|
| [세 개의 질문](prompts/meta/three-questions.md) | 설계 철학 |
| [설계 원칙](prompts/meta/design-principles.md) | 7가지 원칙 |
| [사용법 가이드](prompts/meta/how-to-use.md) | 레이어별 실행법 |
| [프롬프트 빌더](prompts/meta/prompt-builder.md) | 나만의 프롬프트 |
| [프롬프트 해부학](prompts/meta/prompt-anatomy.md) | 역공학 가이드 |

</details>

---

## 🇰🇷 왜 한국 PM 전용인가

영어 프롬프트를 번역하면 한국에서 쓸 수 없습니다. 맥락이 다르기 때문입니다.

| 영역 | 글로벌 프롬프트 | 이 플레이북 |
|------|---------------|------------|
| 규제 | GDPR 중심 | PIPA, 전자문서법, AI 기본법, CSAP |
| 보고 | Executive summary | 두괄식 + 품의서 결재 라인 |
| 데이터 | SEC Filing | DART 전자공시 + 잡플래닛 |
| 지표 | Global SaaS 벤치마크 | 카카오톡 알림 영향도, 한국 구독 피로도 |
| 문화 | Top-down 의사결정 | 합의제 + 린품의 |
| 근무 | Flexible hours | 주 52시간제 + 공휴일 캘린더 |

---

## 🤝 기여하기

새 프롬프트 추가, 한국 데이터 보강, 실전 사례 공유 모두 환영합니다.
→ [CONTRIBUTING.md](prompts/CONTRIBUTING.md)

---

## 🌐 English

### AI Prompts Playbook — Don't Ask AI for Answers. Redesign Your Questions.

A Harvard AI tutor study (2024) found that students who received **structured questions** achieved 2x higher learning outcomes than those who simply received answers — using the exact same AI. The difference wasn't the AI. It was the structure of the question.

This playbook applies that principle to Product Management. It contains **35 workflow prompts** and **5 meta guides**. Each prompt defines a task frame, decision criteria, evidence requirements, and a verification step — not just a request for information.

```mermaid
graph LR
    Q1["❓ How would an expert<br/>frame this problem?<br/><br/>⚡ Layer 1: Expert's Lens"]
    Q2["❓ Where do experts<br/>still disagree?<br/><br/>🧠 Layer 2: Beyond Consensus"]
    Q3["❓ How can I verify<br/>what I've learned?<br/><br/>🔧 Layer 3: Self-Verification"]

    Q1 -->|"Too shallow?"| Q2
    Q2 -->|"Need proof?"| Q3

    style Q1 fill:#e8f5e9,stroke:#4caf50
    style Q2 fill:#e3f2fd,stroke:#2196f3
    style Q3 fill:#fce4ec,stroke:#f44336
```

These aren't difficulty levels. They're **depths of cognition** — borrow expert thinking → challenge consensus → verify with code.

**What makes this different:**
- Every prompt asks for **decision criteria, evidence, assumptions, and verification** instead of hidden reasoning traces
- Prompts **chain together** — output of one becomes input of the next, creating end-to-end PM workflows
- **Korean market data** built in — local regulations (PIPA, AI Act), business culture (consensus decision-making, 품의서), and data sources (DART, JobPlanet)
- **Educational annotations** (`[Expert's Lens]`, `[Debate Point]`, `[Self-Check]`) explain *why*, not just *what*

→ [How to Use](prompts/meta/how-to-use.md) · [Three Questions Philosophy](prompts/meta/three-questions.md) · [Contributing](prompts/CONTRIBUTING.md)

---

## Sources and Verification

- Harvard Gazette: [Professor tailored AI tutor to physics course. Engagement doubled.](https://news.harvard.edu/gazette/story/2024/09/professor-tailored-ai-tutor-to-physics-course-engagement-doubled/)
- OpenAI docs: [Prompting guide](https://platform.openai.com/docs/guides/prompting) and [Reasoning best practices](https://platform.openai.com/docs/guides/reasoning-best-practices)

Claims about regulations, model behavior, and market data should be checked against current primary sources before production use.

---

**License**: [MIT](LICENSE) · **Version**: 2.2 (2026-03-12) · **Author**: Ethan Kim
