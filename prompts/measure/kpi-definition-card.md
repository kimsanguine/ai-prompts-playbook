# 📏 KPI 정의 카드 (KPI Definition Card)

> 예상 소요: 8분 (Quick) / 25분 (Deep) / 40분+ (Build)
> 워크플로우: ← `ai-adoption-metrics.md` → `executive-briefing.md`
> Source: [`kimsanguine/AI_PM`](https://github.com/kimsanguine/AI_PM) `skills/kpi-card-builder/SKILL.md`

---

## 🧩 Prompt Card

| 항목 | 내용 |
|------|------|
| ID | `kpi-definition-card` |
| Job | KPI 하나를 계산식, source, 임계치, owner가 있는 정의 카드로 변환 |
| Best for | PM, CPO, data analyst, ops |
| Required inputs | KPI 이름, 비즈니스 맥락, 측정 목적 |
| Optional inputs | 이벤트/테이블, 목표치, owner, review cadence |
| Output | KPI 정의 카드, 계산식, source, 임계치, 반사례, 의존 KPI |
| Next prompts | `executive-briefing` → `stakeholder-alignment` |
| Evaluation | [`evals/scenarios/core.yaml`](../../evals/scenarios/core.yaml)의 `ai-pm-kpi-card` |

## ✅ Output Contract

AI의 답변은 반드시 다음을 포함해야 합니다:

1. **정의 한 문장**: 무엇을 측정하는지
2. **계산식**: 수식 또는 SQL pseudo-code
3. **Source**: 데이터 출처, source owner, refresh cadence
4. **임계치**: Green / Amber / Red와 각 행동
5. **소유자**: KPI owner, backup, review cadence
6. **반사례**: 이 KPI가 잡지 못하는 것
7. **의존 KPI**: 함께 봐야 하는 가드레일

## 🎯 이 프롬프트가 해결하는 문제

팀에서 “사용자 만족도”, “품질”, “활성화” 같은 말을 쓰지만, 실제 계산식과 owner가 없으면 지표가 아니라 슬로건입니다.

이 프롬프트는 KPI 하나를 운영 가능한 정의 카드로 바꿉니다. 측정 불가능한 KPI는 억지로 작성하지 않고, 측정 가능한 후보로 재정의합니다.

---

## ⚡ Layer 1: Quick Start

```
당신은 제품 지표 설계자입니다.

아래 KPI 하나를 정의 카드로 작성하세요. 측정 불가능하면 카드를 억지로 만들지 말고, 측정 가능한 후보 3개로 재정의하세요.

# 입력
- KPI 이름: {KPI 이름}
- 비즈니스 맥락: {제품/팀/의사결정}
- 이 KPI를 쓰려는 이유: {목적}
- 데이터 출처: {이벤트, 테이블, 설문, 로그}
- 목표치 또는 현재 수치: {있다면 작성}

# 출력
## KPI Card — <이름>
### 정의
### 계산식
### Source
### 임계치
### 소유자
### 반사례
### 의존 KPI

규칙:
- 한 카드에는 KPI 하나만 다루세요.
- 계산식이 모호하면 "명확화 필요"를 표시하세요.
- 반사례 없는 KPI 카드는 미완성입니다.
```

## 🧠 Layer 2: Deep Dive

### 역할

당신은 PM과 데이터팀 사이의 지표 계약을 만드는 metric architect입니다. KPI를 예쁜 이름이 아니라, 운영 중 의사결정에 쓰이는 계약으로 정의해야 합니다.

### Reasoning Strategy

1. **측정 가능성 점검**
   - KPI가 실제 데이터로 계산 가능한지 확인합니다.
   - “사용자 만족”, “혁신”, “품질”처럼 추상적이면 재정의 후보를 냅니다.

2. **계산식 고정**
   - 분자, 분모, 기간, 제외 조건을 명시합니다.
   - SQL pseudo-code가 가능하면 함께 씁니다.

3. **Source와 owner 정의**
   - 이벤트/테이블/설문 출처와 source owner를 분리합니다.

4. **반응 임계치 설계**
   - Green / Amber / Red에 따라 어떤 행동을 할지 정합니다.

5. **반사례와 가드레일**
   - 이 KPI가 좋아져도 놓칠 수 있는 부작용을 적고, 함께 볼 의존 KPI를 연결합니다.

## 🔧 Layer 3: Build & Automate

KPI 카드는 대시보드나 metric catalog에 다음 구조로 저장할 수 있습니다.

```yaml
kpi:
  id: ""
  name: ""
  definition: ""
  formula: ""
  source:
    system: ""
    table_or_event: ""
    owner: ""
    refresh_cadence: ""
  thresholds:
    green: ""
    amber: ""
    red: ""
  owner: ""
  counterexamples: []
  guardrails: []
```

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|---------------|------|
| KPI 카드 | `executive-briefing.md` | 경영진 보고용 metric narrative 생성 |
| AI 기능 지표 | `ai-adoption-metrics.md` | AI feature metric tree로 확장 |
| 이해관계자 합의 | `stakeholder-alignment.md` | 지표 owner와 review cadence 합의 |

