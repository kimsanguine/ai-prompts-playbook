# 🔎 Discovery 인사이트 합성 (Discovery Insight Synthesis)

> 예상 소요: 10분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: → `problem-framing.md` → `requirements-to-prd.md`
> Source: [`kimsanguine/AI_PM`](https://github.com/kimsanguine/AI_PM) `templates/commands/discovery.md`, `skills/discovery-synthesizer/SKILL.md`

---

## 🧩 Prompt Card

| 항목 | 내용 |
|------|------|
| ID | `discovery-insight-synthesis` |
| Job | 인터뷰, 설문, 사용 로그를 PRD/실험으로 전환 가능한 인사이트로 합성 |
| Best for | PM, UX researcher, founder |
| Required inputs | 인터뷰 트랜스크립트, 설문 결과, 사용 로그, 표본 수 |
| Optional inputs | 세그먼트, 제품 단계, 현재 가설, 의사결정 deadline |
| Output | 인사이트 3-7개, 근거 quote, 합성 표, 약한 신호, 한계 |
| Next prompts | `problem-framing` → `feature-prioritization` → `requirements-to-prd` |
| Evaluation | [`evals/scenarios/core.yaml`](../../evals/scenarios/core.yaml)의 `ai-pm-discovery-synthesis` |

## ✅ Output Contract

AI의 답변은 반드시 다음을 포함해야 합니다:

1. **인사이트 3-7개**: 한 인사이트는 한 문장으로 압축
2. **빈도와 표본**: `N/M 응답자`, 가능하면 `%`
3. **근거 quote 3개**: 원문 의미를 바꾸지 않고 인용
4. **So what**: PM이 취해야 할 행동 한 줄
5. **가능한 가설/실험**: 다음 단계로 넘길 수 있는 검증 후보
6. **약한 신호**: N=1-2 패턴은 인사이트로 승격하지 않음
7. **한계**: 표본 편향, 신뢰 한계, 추가 조사 필요

## 🎯 이 프롬프트가 해결하는 문제

리서치 원문은 많지만, PM 의사결정으로 바로 이어지지 않는 경우가 많습니다. 이 프롬프트는 사용자의 말, 설문 응답, 로그 패턴을 **근거 있는 인사이트**와 **다음 실험 후보**로 바꿉니다.

핵심은 “그럴듯한 테마”를 만드는 것이 아니라, 표본 크기와 근거를 분리해 **강한 신호와 약한 신호를 구분**하는 것입니다.

---

## ⚡ Layer 1: Quick Start

```
당신은 제품 Discovery 리서처입니다.

아래 인터뷰/설문/로그 데이터를 합성해 PM이 바로 의사결정에 쓸 수 있는 인사이트 표로 정리하세요.

# 입력
- 제품/상황: {제품 또는 문제 상황}
- 데이터: {인터뷰 트랜스크립트, 설문 CSV, 사용 로그 요약}
- 표본 수: {응답자 수 또는 로그 기간}
- 현재 가설: {있다면 작성}

# 출력
1. 인사이트 3-7개
2. 각 인사이트별 빈도, 근거 quote 3개, So what, 가능한 가설/실험
3. 합성 표: 인사이트 / 빈도 / 임팩트 / 난이도 / 권장 행동
4. 약한 신호: N=1-2 패턴
5. 한계: 표본 편향, 신뢰 한계, 추가 조사 필요

규칙:
- 표본이 1-2명인 패턴은 "약한 신호"로만 표기하세요.
- "다양한", "여러", "효과적" 같은 추상 표현 대신 숫자와 근거를 쓰세요.
- 데이터가 현재 가설과 다르면 가설이 약하다고 말하세요.
```

## 🧠 Layer 2: Deep Dive

### 역할

당신은 PM과 UX researcher를 돕는 Discovery synthesis partner입니다. 당신의 목적은 사용자의 원자료를 PM 판단에 필요한 구조로 압축하되, 데이터가 말하지 않는 것을 말하지 않는 것입니다.

### Reasoning Strategy

1. **입력 품질 점검**
   - 표본 수, 세그먼트 편향, 데이터 출처, 기간을 확인합니다.
   - 데이터가 너무 적으면 먼저 “약한 신호 중심 분석”이라고 선언합니다.

2. **반복 패턴 찾기**
   - 동일한 문제를 다른 표현으로 말한 응답을 묶습니다.
   - 직무명이나 인구통계가 아니라 사용자의 목표, 장애물, 감정으로 클러스터링합니다.

3. **인사이트 승격 기준 적용**
   - 최소 3개 이상의 독립 근거가 있는 패턴만 인사이트로 승격합니다.
   - N=1-2 패턴은 약한 신호로 분리합니다.

4. **PM 행동으로 변환**
   - 각 인사이트를 PRD, 실험, 추가 리서치 중 하나의 다음 행동으로 연결합니다.

5. **자기 검증**
   - 근거 없는 추론, 과도한 일반화, confirmation bias를 찾아 수정합니다.

## 🔧 Layer 3: Build & Automate

Claude Code에서 사용할 때는 `AI_PM`의 `/discovery` command처럼 입력 파일을 명시해 실행하세요.

```bash
/discovery @samples/user-survey-results.csv
```

자동화 파이프라인에서는 다음 필드를 구조화해 저장하면 좋습니다.

```yaml
insight:
  statement: ""
  evidence_count: 0
  respondent_ratio: ""
  quotes: []
  so_what: ""
  experiment_candidate: ""
  confidence: high|medium|low
```

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|---------------|------|
| 강한 인사이트 | `problem-framing.md` | 검증 가능한 문제 정의로 전환 |
| 실험 후보 | `feature-prioritization.md` | RICE 또는 ICE로 우선순위화 |
| 요구사항 후보 | `requirements-to-prd.md` | PRD 초안으로 변환 |

