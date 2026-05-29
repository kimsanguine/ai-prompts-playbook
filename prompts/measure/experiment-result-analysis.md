# 🧪 실험 결과 분석 (Experiment Result Analysis)

> 예상 소요: 10분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: ← `ab-test-design.md` → `executive-briefing.md` → `retention-analysis.md`
> Source: [`kimsanguine/AI_PM`](https://github.com/kimsanguine/AI_PM) `skills/experiment-analyzer/SKILL.md`

---

## 🧩 Prompt Card

| 항목 | 내용 |
|------|------|
| ID | `experiment-result-analysis` |
| Job | A/B 테스트 결과를 PM 보고 포맷과 ship/iterate/kill 권고로 변환 |
| Best for | PM, growth, data analyst |
| Required inputs | 실험 가설, control/treatment 결과, p-value, 표본 수 |
| Optional inputs | 가드레일 지표, 세그먼트, 기간, novelty 효과 가능성 |
| Output | 결론, 결과 표, 가드레일, 의심 신호, 권고 |
| Next prompts | `executive-briefing` → `retention-analysis` |
| Evaluation | [`evals/scenarios/core.yaml`](../../evals/scenarios/core.yaml)의 `ai-pm-experiment-result` |

## ✅ Output Contract

AI의 답변은 반드시 다음을 포함해야 합니다:

1. **결론 한 줄**: 주 메트릭 변화, p-value, 표본, 권고
2. **무엇을 했나**: 변경, 기간, 표본, 가설
3. **결과 표**: Control, Treatment, 변화량, p-value
4. **가드레일**: 악화된 지표와 ship 차단 여부
5. **의심 신호**: 표본 균형, novelty, segment 편향, Simpson's paradox
6. **권고**: ship / iterate / kill / extend 중 하나와 이유

## 🎯 이 프롬프트가 해결하는 문제

실험 결과는 숫자가 있어도 의사결정으로 이어지기 어렵습니다. p-value만 보고 출시하면 effect size, 가드레일, 표본 편향을 놓칠 수 있습니다.

이 프롬프트는 실험 결과를 PM 보고 포맷으로 정리하고, **통계적 유의성과 비즈니스 의미를 분리**해 출시 판단을 돕습니다.

---

## ⚡ Layer 1: Quick Start

```
당신은 Growth PM과 실험 분석가입니다.

아래 A/B 테스트 결과를 PM 보고 포맷으로 분석하고, ship / iterate / kill / extend 중 하나를 권고하세요.

# 입력
- 실험명: {실험명}
- 가설: {가설}
- 기간: {YYYY-MM-DD ~ YYYY-MM-DD}
- Control: {표본 수, 주 메트릭, 가드레일}
- Treatment: {표본 수, 주 메트릭, 가드레일}
- p-value: {주 메트릭 p-value}
- 알려진 제약: {세그먼트 편향, novelty 가능성 등}

# 출력
1. 결론 한 줄
2. 무엇을 했나
3. 결과 표
4. 가드레일
5. 의심 신호
6. 권고와 다음 step

규칙:
- p<0.05여도 effect size가 작으면 ship을 권고하지 마세요.
- 가드레일이 악화되면 주 메트릭이 좋아도 ship을 권고하지 마세요.
- 1주 미만 데이터는 novelty 가능성을 명시하세요.
```

## 🧠 Layer 2: Deep Dive

### 역할

당신은 PM에게 실험 결과를 설명하는 데이터 파트너입니다. 숫자를 요약하는 것보다, 어떤 의사결정을 해도 되는지와 아직 위험한 지점을 분리하는 것이 목적입니다.

### Reasoning Strategy

1. **실험 설계 회수**
   - 원래 가설, 주 메트릭, 가드레일, 기간, 표본을 재확인합니다.

2. **주 메트릭 해석**
   - 통계적 유의성과 effect size를 분리합니다.
   - p-value가 좋아도 비즈니스 의미가 작으면 iterate 또는 extend를 검토합니다.

3. **가드레일 확인**
   - 전환율이 좋아져도 환불, CS, 지연, 신뢰도 등 가드레일이 무너지면 ship을 막습니다.

4. **의심 신호 탐지**
   - 표본 불균형, novelty 효과, segment 편향, 다중 비교, Simpson's paradox를 점검합니다.

5. **권고 작성**
   - ship / iterate / kill / extend 중 하나만 선택하고, 다음 step을 한 줄로 제시합니다.

## 🔧 Layer 3: Build & Automate

실험 결과 CSV가 있다면 Claude Code에서 다음처럼 실행할 수 있습니다.

```bash
@samples/ab-test-results.csv 를 experiment-result-analysis 형식으로 분석해줘.
```

구조화 저장 예:

```yaml
experiment_result:
  decision: ship|iterate|kill|extend
  primary_metric_delta: ""
  p_value: ""
  guardrail_status: pass|fail|unknown
  suspicion_signals: []
  next_step: ""
```

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|---------------|------|
| ship 권고 | `executive-briefing.md` | 경영진 승인 브리핑으로 전환 |
| iterate 권고 | `ab-test-design.md` | 다음 실험 설계 |
| 장기 영향 확인 | `retention-analysis.md` | 코호트/리텐션 영향 추적 |

