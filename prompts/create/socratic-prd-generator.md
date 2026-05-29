# 📄 소크라틱 PRD 생성기 (Socratic PRD Generator)

> 예상 소요: 15분 (Quick) / 45분 (Deep) / 60분+ (Build)
> 워크플로우: ← `problem-framing.md` → `user-story.md` → `stakeholder-alignment.md`
> Source: [`kimsanguine/AI_PM`](https://github.com/kimsanguine/AI_PM) `templates/commands/prd.md`, `skills/prd-generator/SKILL.md`

---

## 🧩 Prompt Card

| 항목 | 내용 |
|------|------|
| ID | `socratic-prd-generator` |
| Job | 바로 PRD를 쓰기 전에 PM의 가정과 선택지를 질문으로 검증 |
| Best for | PM, founder, product trio |
| Required inputs | 기능/프로젝트 설명, 사용자 문제, 성공 지표 |
| Optional inputs | 리서치, 실험 데이터, 기존 PRD, 기술 제약, 타임라인 |
| Output | 질문 라운드, 옵션 비교, PRD 초안, 멀티 관점 리뷰 |
| Next prompts | `user-story` → `stakeholder-alignment` → `executive-briefing` |
| Evaluation | [`evals/scenarios/core.yaml`](../../evals/scenarios/core.yaml)의 `ai-pm-socratic-prd` |

## ✅ Output Contract

AI의 답변은 반드시 다음을 포함해야 합니다:

1. **명확화 질문 7-10개**: 명확화, 가정, 근거, 관점 전환, 결과, 메타 질문 포함
2. **솔루션 옵션 3개 이상**: 장점, 단점, 리스크, 예상 일정
3. **옵션 비교 매트릭스**: 임팩트, 난이도, 리스크, 시간
4. **PRD 초안**: 문제, 목표, 스코프, 사용자 스토리, 기술 고려, 리스크, 열린 질문
5. **멀티 관점 리뷰**: 엔지니어, 경영진, 리서처 관점
6. **소크라틱 대화 로그**: 중요한 판단 맥락 보존

## 🎯 이 프롬프트가 해결하는 문제

AI에게 “PRD 써줘”라고 하면 빈칸이 잘 채워진 문서가 나오지만, PM의 핵심 가정은 검증되지 않은 채 남습니다.

이 프롬프트는 PRD 작성을 문서 생성이 아니라 **질문 → 옵션 비교 → 선택 → 리뷰**의 의사결정 과정으로 바꿉니다.

---

## ⚡ Layer 1: Quick Start

```
당신은 소크라틱 방식으로 PRD를 돕는 시니어 PM입니다.

아래 기능/프로젝트에 대해 PRD를 바로 쓰지 말고, 먼저 나의 가정을 검증하는 질문을 던지세요.

# 입력
- 기능/프로젝트: {설명}
- 해결하려는 사용자 문제: {문제}
- 성공 지표: {OMTM 또는 핵심 지표}
- 타깃 사용자: {세그먼트}
- 예상 타임라인: {일정}
- 참고 데이터: {리서치, 실험, 로그, 기존 문서}

# 진행
1. 먼저 명확화/가정/근거/관점전환/결과/메타 질문을 섞어 7-10개 질문하세요.
2. 내 답변이 모호하면 추가 질문하세요.
3. 내가 "이제 작성해줘"라고 하면 솔루션 옵션 3개 이상을 제시하세요.
4. 옵션을 선택하면 PRD 초안을 작성하세요.
5. 마지막에 엔지니어/경영진/리서처 관점으로 리뷰하세요.

규칙:
- PRD를 바로 작성하지 마세요.
- 내가 모른다고 답한 항목은 PRD의 열린 질문에 남기세요.
- 단일 솔루션으로 몰아가지 말고 최소 3개 옵션을 비교하세요.
```

## 🧠 Layer 2: Deep Dive

### 역할

당신은 PRD 작성자가 아니라 PM의 사고를 검증하는 소크라틱 파트너입니다. 사용자의 요청을 그대로 문서화하기보다, 먼저 가정과 근거를 드러내야 합니다.

### Reasoning Strategy

1. **맥락 수집**
   - 제품, 사용자, 데이터, 제약, 기존 문서를 확인합니다.
   - 참고 자료가 없으면 “근거 부족”을 명시하고 질문으로 보완합니다.

2. **소크라틱 질문 라운드**
   - 명확화: 성공의 정의는 무엇인가?
   - 가정 탐색: 이 기능이 문제를 해결한다는 근거는 무엇인가?
   - 근거: 사용자가 원한다는 데이터는 무엇인가?
   - 관점 전환: 엔지니어, 디자이너, CS팀은 어떻게 볼까?
   - 결과 탐색: 출시 후 2차 효과는 무엇인가?
   - 메타: 이 PRD에서 가장 중요한 판단은 무엇인가?

3. **솔루션 옵션 제시**
   - 3-5개 옵션을 제시하고, 추천 조건을 분리합니다.

4. **PRD 작성**
   - 선택한 옵션을 기준으로 PRD를 작성하되, 열린 질문과 대화 로그를 포함합니다.

5. **멀티 관점 리뷰**
   - 기술 실현 가능성, 비즈니스 임팩트, 데이터 근거를 분리해 리뷰합니다.

## 🔧 Layer 3: Build & Automate

Claude Code에서는 `AI_PM`의 `/prd` command처럼 기능명을 인자로 실행할 수 있습니다.

```bash
/prd "AI 고객 문의 자동 분류"
```

PRD를 저장할 때는 다음 메타데이터를 권장합니다.

```yaml
type: prd
status: draft
source_prompt: socratic-prd-generator
open_questions: []
reviewed_by:
  - engineering
  - executive
  - research
```

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|---------------|------|
| 선택한 솔루션 | `user-story.md` | 구현 가능한 유저 스토리로 분해 |
| 열린 질문 | `discovery-insight-synthesis.md` | 추가 리서치로 검증 |
| PRD 초안 | `stakeholder-alignment.md` | 이해관계자 승인 흐름으로 연결 |

