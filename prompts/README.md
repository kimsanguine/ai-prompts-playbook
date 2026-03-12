# AI Prompts Playbook

**AI 시대의 사고법 — PM이 설계하고, 누구나 쓰고, 엔지니어가 자동화하는 프롬프트**

*Think like a PM. Prompt like an engineer. Ship with AI.*

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Prompts](https://img.shields.io/badge/Prompts-33-blue.svg)](#-프롬프트-목록)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

---

## 이런 경험, 있지 않나요?

> "AI한테 경쟁사 분석해달라고 했는데, 위키피디아 수준의 요약만 나와요."

> "PRD 써달라고 했는데, 빈 칸 채우기 같은 결과가 나왔어요."

> "프롬프트 잘 쓰는 법을 배우고 싶은데, 이론만 있고 실전 예시가 없어요."

이 Playbook은 **"AI에게 어떻게 생각해야 하는지"를 알려주는 프롬프트 모음**입니다.
단순한 질문 템플릿이 아니라, 20년간 AI 제품을 만들며 검증한 **구조화된 사고 프레임워크**가 각 프롬프트에 담겨 있습니다.

---

## 왜 세 개의 레이어인가?

AI에게 "경쟁사 분석해줘"라고 하면 위키피디아 수준의 요약이 나옵니다. 그런데 같은 AI에게 **세 가지 다른 질문**을 던지면, 한 분야의 뼈대가 세워집니다.

| 레이어 | 던지는 질문 | 하는 일 | 대상 |
|--------|-----------|---------|------|
| ⚡ **Layer 1: 전문가의 눈** | "전문가는 이걸 어떤 틀로 보나요?" | 전문가의 프레이밍을 5분 만에 빌림 | 누구나 |
| 🧠 **Layer 2: 합의 너머** | "전문가들도 답을 못 내린 부분은?" | 확실한 것과 불확실한 것을 구분 | PM, 기획자 |
| 🔧 **Layer 3: 자기 검증** | "내가 이해한 걸 어떻게 테스트하나?" | 코드로 가설을 실제 데이터에 부딪혀봄 | 엔지니어 |

**세 질문을 모두 던져야 뼈대가 완성됩니다.** 하나만 써도 결과는 나오지만, 셋이 모이면 새로운 정보가 들어올 때 어디에 꽂아야 하는지 보입니다.

→ 자세한 철학: [세 개의 질문 — AI 시대의 사고법](meta/three-questions.md)

---

## ⚡ 30초 Quick Start

**1단계:** 아래에서 프롬프트를 하나 고르세요

**2단계:** `⚡ Layer 1: Quick Start` 섹션을 복사하세요

**3단계:** ChatGPT, Claude, Gemini 아무 곳에나 붙여넣으세요

```
당신은 사용자 리서처입니다.
아래 리뷰 데이터에서 상위 5개 페르소나를 찾고,
각 페르소나의 감성 점수(-1~1)와 핵심 불만을 정리하세요.

# 데이터
{여기에 리뷰 데이터를 붙여넣으세요}
```
→ *이게 Layer 1입니다. 5분이면 결과가 나옵니다.*

더 깊은 분석이 필요하면? → Layer 2로.
자동화하고 싶으면? → Layer 3로.

---

## 📂 프롬프트 목록

<details>
<summary><b>🔍 분석하기 (analyze/) — 7개 프롬프트</b></summary>

> *"데이터는 있는데, 어디서부터 봐야 할지 모르겠어요"*
> *"경쟁사 분석을 했는데, '그래서 뭐?' 하는 반응이 돌아왔어요"*

데이터를 구조화하고, 패턴을 발견하고, 실행 가능한 인사이트로 바꿔주는 프롬프트입니다.

| 프롬프트 | 이럴 때 쓰세요 |
|---------|--------------|
| 🎯 [경쟁사 감성 분석](analyze/competitor-sentiment.md) | 앱스토어/Reddit 리뷰에서 경쟁사 약점을 찾아야 할 때 |
| 🔍 [문제 정의 프레이밍](analyze/problem-framing.md) | "무슨 문제를 풀어야 하지?"가 명확하지 않을 때 |
| 🎯 [Jobs to Be Done 분석](analyze/jobs-to-be-done.md) | 사용자가 진짜 원하는 게 뭔지 파악해야 할 때 |
| 👤 [페르소나 프로파일링](analyze/persona-profiling.md) | 감 대신 데이터로 타겟 사용자를 정의해야 할 때 |
| 🗺️ [고객 여정 맵핑](analyze/customer-journey-mapping.md) | 사용자 경험의 어느 단계에서 이탈하는지 알고 싶을 때 |
| 🌍 [PESTEL 거시환경 분석](analyze/pestel-analysis.md) | 시장 진출이나 신규 사업의 외부 리스크를 점검할 때 |
| 🏢 [기업/경쟁사 프로파일링](analyze/company-profiling.md) | 경쟁사나 파트너사의 전략, 조직, 재무를 빠르게 파악할 때 |

</details>

<details>
<summary><b>⚖️ 결정하기 (decide/) — 6개 프롬프트</b></summary>

> *"기능 10개 중 어떤 걸 먼저 만들어야 하죠?"*
> *"AI를 직접 만들어야 하나, 외부 API를 써야 하나?"*

우선순위를 정하고, 전략을 세우고, 트레이드오프를 명확히 판단할 수 있게 돕는 프롬프트입니다.

| 프롬프트 | 이럴 때 쓰세요 |
|---------|--------------|
| 📊 [기능 우선순위 결정 (RICE)](decide/feature-prioritization.md) | 백로그에 기능이 쌓여있고 어디부터 해야 할지 모를 때 |
| 🎯 [포지셔닝 전략 수립](decide/positioning-strategy.md) | 제품의 시장 포지션을 정의하거나 재정립할 때 |
| 🧭 [의사결정 캔버스](decide/decision-canvas.md) | 복잡한 결정을 앞두고 논리적으로 정리가 필요할 때 |
| 📋 [백로그 우선순위 정리](decide/backlog-prioritization.md) | 에픽과 가설이 뒤섞인 백로그를 정리해야 할 때 |
| 🏃 [스프린트 킥오프 설계](decide/sprint-kickoff.md) | 스프린트 시작 전 목표와 범위를 팀과 합의할 때 |
| 🤖 [AI Build vs Buy 판단](decide/build-vs-buy-ai.md) | AI 역량을 직접 개발할지, 외부 솔루션을 도입할지 고민될 때 |

</details>

<details>
<summary><b>🛠️ 만들기 (create/) — 9개 프롬프트</b></summary>

> *"PRD를 써야 하는데, AI 기능의 스펙을 어떻게 정의하지?"*
> *"유저 스토리를 썼는데, 개발팀이 '이걸로는 못 만들어요'라고 해요"*

문서를 작성하고, 스펙을 정의하고, 바로 실행 가능한 결과물을 만드는 프롬프트입니다.

| 프롬프트 | 이럴 때 쓰세요 |
|---------|--------------|
| 📝 [AI 기능 PRD 작성](create/prd-for-ai-feature.md) | AI/ML 기능의 요구사항 문서를 작성해야 할 때 |
| 📖 [유저 스토리 작성](create/user-story.md) | INVEST 원칙에 맞는 유저 스토리가 필요할 때 |
| 🗺️ [유저 스토리 맵핑](create/user-story-mapping.md) | 스토리를 전체 제품 맥락에서 배치하고 릴리즈를 계획할 때 |
| ✂️ [유저 스토리 분할](create/user-story-splitting.md) | 스토리가 너무 커서 한 스프린트에 안 들어갈 때 |
| 🤖 [AI 기준 유저 스토리](create/user-story-ai-enhanced.md) | AI Acceptance Criteria가 포함된 스토리가 필요할 때 |
| 🔄 [기술 스펙 → PRD 변환](create/spec-to-prd.md) | 개발팀의 기술 스펙을 비즈니스 관점 PRD로 바꿔야 할 때 |
| 📋 [요구사항 → PRD 변환](create/requirements-to-prd.md) | 흩어진 요구사항을 구조화된 PRD로 정리해야 할 때 |
| 🎤 [경영진 전략 브리핑](create/executive-briefing.md) | C-Level 대상 AI 전략 보고서를 작성해야 할 때 |
| 👋 [제품 종료 안내문](create/product-eol-message.md) | 제품/기능 종료를 고객에게 안내해야 할 때 |

</details>

<details>
<summary><b>📊 측정하기 (measure/) — 3개 프롬프트</b></summary>

> *"AI 기능을 출시했는데, 성공을 어떻게 정의하죠?"*
> *"A/B 테스트를 하고 싶은데, 실험 설계를 어떻게 해야 하나요?"*

메트릭을 설계하고, 실험을 구조화하고, 데이터에 기반한 의사결정을 돕는 프롬프트입니다.

| 프롬프트 | 이럴 때 쓰세요 |
|---------|--------------|
| 📈 [AI 기능 채택 메트릭](measure/ai-adoption-metrics.md) | AI 기능의 성공 지표(채택률, Trust Score, 리텐션)를 정의할 때 |
| 🧪 [A/B 테스트 설계](measure/ab-test-design.md) | AI 기능의 실험 설계와 가설 수립이 필요할 때 |
| 📉 [리텐션 분석](measure/retention-analysis.md) | 코호트별 리텐션을 분석하고 이탈 원인을 진단할 때 |

</details>

<details>
<summary><b>💬 소통하기 (communicate/) — 5개 프롬프트</b></summary>

> *"좋은 제품을 만들었는데, 이해관계자 설득이 안 돼요"*
> *"AI 윤리 검토를 해야 하는데, 어디서부터 시작하지?"*

이해관계자를 설득하고, 팀을 정렬하고, 신뢰를 만드는 프롬프트입니다.

| 프롬프트 | 이럴 때 쓰세요 |
|---------|--------------|
| 🤝 [이해관계자 정렬](communicate/stakeholder-alignment.md) | 각 이해관계자에게 맞춤형 메시지를 전달해야 할 때 |
| 📰 [프레스 릴리즈 (Working Backwards)](communicate/press-release.md) | Amazon 스타일로 제품 비전을 구체화하고 싶을 때 |
| 📖 [제품 스토리텔링](communicate/storytelling.md) | 제품의 가치를 데이터 대신 이야기로 전달해야 할 때 |
| ⚖️ [AI 윤리 검토](communicate/ai-ethics-review.md) | AI 제품의 편향, 공정성, 투명성을 검토해야 할 때 |
| 🔄 [팀 간 인수인계](communicate/cross-team-handoff.md) | PM↔엔지니어 간 맥락 손실 없이 인수인계할 때 |

</details>

<details>
<summary><b>🧩 메타 프롬프트 (meta/) — 3개 프롬프트</b></summary>

> *"프롬프트를 잘 쓰고 싶은데, 어디서부터 배우죠?"*

프롬프트 설계 원칙을 배우고, 나만의 프롬프트를 만들 수 있게 돕는 메타 프롬프트입니다.

| 프롬프트 | 이럴 때 쓰세요 |
|---------|--------------|
| 🧠 [세 개의 질문](meta/three-questions.md) | AI 시대에 어떻게 질문해야 하는지, 이 Playbook의 철학을 이해하고 싶을 때 |
| 📐 [설계 원칙 가이드](meta/design-principles.md) | 이 Playbook의 7가지 원칙이 왜 작동하는지 이해하고 싶을 때 |
| 🔧 [프롬프트 빌더](meta/prompt-builder.md) | 나만의 프롬프트를 처음부터 만들고 싶을 때 |
| 🔬 [프롬프트 해부학](meta/prompt-anatomy.md) | 좋은 프롬프트가 왜 좋은지 역공학으로 분석하고 싶을 때 |

</details>

---

## 🗺️ 워크플로우 체인

프롬프트는 단독으로도 쓸 수 있지만, **체인으로 연결하면 더 강력합니다.**

```
[분석] 경쟁사 감성 분석
  │ 페르소나 5개 + 기회 매트릭스
  ▼
[분석] 문제 정의 프레이밍
  │ 구조화된 문제 정의
  ▼
[결정] 기능 우선순위 결정 (RICE)
  │ RICE 스코어 기반 우선순위
  ▼
[만들기] AI 기능 PRD 작성
  │ AI 기능 PRD
  ▼
[측정] AI 기능 채택 메트릭
  │ 성공 메트릭 정의
  ▼
[소통] 이해관계자 정렬
    이해관계자 정렬 완료
```

각 프롬프트의 `🔗 다음 단계` 섹션에서 연결 가이드를 확인하세요.

---

## 🎓 처음이세요? 이 순서로 시작하세요

| 단계 | 뭘 하나요? | 소요 시간 |
|------|-----------|----------|
| 1️⃣ | [세 개의 질문](meta/three-questions.md)을 읽으세요 — 이 Playbook이 왜 존재하는지 | 10분 |
| 2️⃣ | [경쟁사 감성 분석](analyze/competitor-sentiment.md)의 **Layer 1**을 실행하세요 — 전문가의 눈 빌리기 | 10분 |
| 3️⃣ | 같은 프롬프트의 **Layer 2**를 실행하세요 — 합의 너머 보기 | 20분 |
| 4️⃣ | [기능 우선순위 결정](decide/feature-prioritization.md)을 체인으로 연결하세요 | 30분 |
| 5️⃣ | [프롬프트 빌더](meta/prompt-builder.md)로 나만의 프롬프트를 만드세요 | 30분 |

→ **2시간이면 "어떻게 질문하는가"의 구조를 체득할 수 있습니다.**

### 프롬프트 엔지니어링을 더 배우고 싶다면

이 Playbook은 "잘 설계된 프롬프트를 쓰면서 자연스럽게 배우는" 접근입니다.
이론과 기법(CoT, Few-shot, Self-consistency 등)을 체계적으로 공부하려면:

- [Prompt Engineering Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) — 300만+ 학습자, 가장 포괄적인 가이드
- [NirDiamant/Prompt_Engineering](https://github.com/NirDiamant/Prompt_Engineering) — 초보→고급 튜토리얼

---

## 🧠 세 질문이 레이어에 어떻게 녹아 있는가

하나의 프롬프트 파일에 **3개 레이어**가 있습니다. 각 레이어는 서로 다른 질문을 던집니다.

```
┌─────────────────────────────────────────────────────────┐
│  ⚡ Layer 1: 전문가의 눈 빌리기                           │
│                                                         │
│  "이 분야의 전문가는 어떤 틀로 보는가?"                     │
│  → 복사-붙여넣기만으로 전문가의 프레이밍을 빌릴 수 있습니다   │
├─────────────────────────────────────────────────────────┤
│  🧠 Layer 2: 합의된 영역 너머 보기                        │
│                                                         │
│  "어디서 전문가들조차 답을 못 내리는가?"                     │
│  → CoT로 단계별 추론 + [논쟁 지점] 교육 주석               │
├─────────────────────────────────────────────────────────┤
│  🔧 Layer 3: 자기 검증                                   │
│                                                         │
│  "내가 이해한 것을 어떻게 증명하는가?"                      │
│  → Python 코드로 가설을 실제 데이터에 부딪혀봅니다           │
└─────────────────────────────────────────────────────────┘
```

**교육 주석은 세 가지 유형입니다:**

```markdown
<!-- 💬 [전문가의 눈] 전략 분석가는 "사업 모델 → 경쟁우위 → 성장 벡터" 순서로 봅니다.
     왜? 사업 모델 없는 경쟁우위는 수익이 안 되고, 경쟁우위 없는 성장은 지속 안 되기 때문. -->

<!-- 💬 [논쟁 지점] 리텐션을 D1으로 볼지 W1으로 볼지는 앱 유형마다 전문가 의견이 다릅니다. -->

<!-- 💬 [자기 검증] 경쟁사 앱스토어 리뷰 10개를 직접 읽어 AI 분석과 비교하세요. -->
```

→ 프롬프트를 쓰면서 **"왜 이 질문인가"를 동시에 배웁니다.**
→ 자세한 철학: [세 개의 질문 — AI 시대의 사고법](meta/three-questions.md)

---

## 💡 설계 원칙

이 Playbook의 모든 프롬프트는 7가지 원칙으로 설계되었습니다.

| # | 원칙 | 핵심 |
|---|------|------|
| 1 | **질문과 답변 구조** | 결과물보다 사고 과정을 설계한다 |
| 2 | **데이터 기반 가설** | 감이 아니라 데이터에서 가설을 세운다 |
| 3 | **Reasoning Strategy** | AI의 추론 단계를 명시적으로 설계한다 |
| 4 | **워크플로우 체인** | 하나의 결과물이 다음 프롬프트의 입력이 된다 |
| 5 | **자기 검증** | 마지막 단계에서 모호한 부분을 스스로 찾아 고친다 |
| 6 | **레이어드 접근성** | 누구나 시작할 수 있고, 깊이는 선택이다 |
| 7 | **교육적 투명성** | "왜 이렇게 설계했는가"를 숨기지 않는다 |

→ 자세한 해설: [설계 원칙 가이드](meta/design-principles.md)

---

## 🤝 기여하기

프롬프트 추가, 번역, 오류 수정 모두 환영합니다.

- 📝 **새 프롬프트 제안** — [Issue](../../issues/new) 작성
- 🔧 **프롬프트 개선** — Pull Request
- 🌏 **영어 번역** — `prompts/en/` 폴더에 기여
- ⭐ **도움이 되었다면** — Star를 눌러주세요

기여 가이드: [CONTRIBUTING.md](CONTRIBUTING.md)

---

## 📎 관련 프로젝트

| 프로젝트 | 설명 |
|----------|------|
| [AI_PM_Skills](https://github.com/kimsanguine/AI_PM_Skills) | 이 Playbook의 프롬프트를 Claude Code Skills로 자동화 |
| [100 Agents](https://github.com/kimsanguine/AI_Engineer) | AI Agent 컬렉션 — Playbook의 워크플로우를 Agent가 실행 |

```
ai-prompts-playbook (사고법)
       ↕ Layer 3 → Skills
AI_PM_Skills (자동화)
       ↕ Skills → Agent 도구
100 Agents (실행)
```

---

## 📄 License

MIT License — 자유롭게 사용, 수정, 배포할 수 있습니다.

---

<p align="center">
  <b>AI 시대의 사고법</b><br>
  PM이 설계하고, 누구나 쓰고, 엔지니어가 자동화하는 프롬프트<br><br>
  <i>Think like a PM. Prompt like an engineer. Ship with AI.</i>
</p>
