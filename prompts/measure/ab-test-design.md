# 🧪 A/B 테스트 설계 (A/B Test Design for AI)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 40분+ (Build)
> 워크플로우: ← `ai-adoption-metrics.md` → `retention-analysis.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 기능의 성능을 개선하기 위해 테스트를 하려는데, 일반적인 A/B 테스트 가이드는 AI 특화 문제들을 다루지 않는다. **"모델 A vs 모델 B"**, **"프롬프트 변형"**, **"응답 형식 변경"** 등 AI 고유의 실험 설계, 통계적 유의성 판단, 신뢰도 영향도 측정이 필요하다.

---

## 📥 이전 프롬프트에서 받는 입력

> `feature-prioritization.md`에서 선정된 기능의 효과를 실험으로 검증할 때 연결됩니다.

이전 프롬프트 결과에서 **실험 대상 기능, 가설, 성공 메트릭**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 AI 기능의 A/B 테스트를 설계할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI PM 실험 설계자다.

{AI 기능명}에서:
- 현재 상태: {메트릭} (예: Trust Score 6.8/10)
- 개선 가설: {가설} (예: "프롬프트를 한국어 최적화하면 정확도 ↑")

다음을 설계하세요:
1. 실험 목표 (성공의 정의)
2. 대조군 vs 실험군 정의
3. 샘플 크기 계산
4. 통계적 유의성 판단 방법
5. 윤리/안전 체크리스트
6. 롤아웃 계획 (Ramp-up)

각 항목별로 구체적이고 실행 가능하게.
```

💡 **Quick Tips:**
- AI 실험은 "사용자 경험"과 "모델 성능"을 동시에 측정
- 샘플 크기: 일반 SaaS보다 크게 (모델 분포도가 넓음)
- 신뢰도 평가 추가: "결과를 믿겠나?" 설문 필수


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 트래픽이 적어서 샘플 부족 | 실험 기간을 늘리거나, MDE(최소 감지 효과)를 높이세요 |
| AI 결과가 매번 달라짐 | 고정 시드(seed) 또는 캐싱을 사용해서 재현성을 확보하세요 |
| 윤리적 우려 | ai-ethics-review.md를 먼저 수행하세요 |
| 여러 변수를 동시에 테스트 | 한 번에 1개 변수만 테스트하세요. 다변량은 결과 해석이 어렵습니다 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — AI 기능의 A/B 테스트를 통계적으로 엄밀하게 설계하고 싶은 분입니다.
모델 불확실성, 신뢰도 영향, 안전성까지 고려한 실험을 하고 싶다면 이걸 써보세요.

### 📌 진행 방식

이 프롬프트는 **8단계 CoT(Chain of Thought)** 구조입니다. 두 가지 방식으로 쓸 수 있습니다:

**방식 A: 한 번에 넣기 (추천)**
- 아래 전체를 통째로 복사해서 AI에 붙여넣으세요
- AI가 모든 단계를 순서대로 실행합니다
- 결과가 한 번에 나옵니다 (길지만 완결적)

**방식 B: 단계별로 넣기 (더 깊은 분석)**
- 1-2단계를 먼저 넣고 결과를 확인하세요
- 결과가 만족스러우면 다음 단계를 이어서 넣으세요
- 중간에 수정이 필요하면 해당 단계를 수정 요청할 수 있습니다
- 시간이 더 걸리지만, 각 단계를 직접 검증할 수 있습니다

**`<!-- 💬 -->` 교육 주석이란?**
- 프롬프트 안에 `<!-- 💬 ... -->` 형태의 주석이 있습니다
- 이건 **여러분을 위한 설명**이지, AI에게 보내는 지시가 아닙니다
- AI에 붙여넣을 때 포함해도 되고 빼도 됩니다 (결과에 영향 없음)
- "왜 이렇게 설계했는가?"를 이해하면 더 좋은 프롬프트를 만들 수 있습니다

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### 역할 설정

당신은 **AI 제품 실험 설계 전문가**이다. 당신의 역할:

1. **AI 고유 실험 설계**: 모델 자체의 테스트 (A/B 프롬프트, 모델 버전, 하이퍼파라미터)
2. **통계 엄밀성**: 샘플 크기, 신뢰 구간, 다중 비교 보정 (Multiple Testing Correction)
3. **신뢰도 영향도**: 새 모델/프롬프트가 사용자 신뢰도에 미치는 영향 추정
4. **안전성 검증**: AI 기능의 개선이 부정적 부작용을 만들지 않는지 확인

<!-- 💬 왜 AI 실험은 일반 SaaS와 다른가?
일반 SaaS 테스트 (예: 버튼 색깔 A/B 테스트):
- 효과가 확정적 (파란 버튼은 항상 파란색)
- 샘플 크기: 수백~수천 명 = 몇 시간 만에 결론

AI 테스트 (예: 프롬프트 A vs B):
- 효과가 확률적 (같은 프롬프트도 모델이 다른 결과 생성)
- 샘플 크기: 수천~수만 개 요청 필요 (일주일+ 필요)
- 신뢰도 평가: "결과 정확도"만이 아니라 "사용자가 결과를 믿는가?"도 중요
-->

### 목표

최종 아웃풋:
- **실험 계획서** (목표, 가설, 메트릭 정의, 샘플 크기)
- **통계 분석 계획** (유의성 판단 기준, 신뢰 구간)
- **안전성 체크리스트** (롤아웃 전 검증 항목)
- **롤아웃 전략** (Ramp-up 일정, Rollback 조건)

### Reasoning Strategy

<!-- 💬 AI 실험 설계의 핵심 이슈는 무엇인가?
1. 모델 불확실성: 같은 입력도 다른 출력 → 더 큰 샘플 필요
2. 분포 시프트: 사용자 질문이 날마다 달라짐 → 단기 테스트는 신뢰할 수 없음
3. 신뢰도 변화: 정확도 1% 개선이라도, 신뢰도 1점 하락하면 전체적으로 손해
4. 부작용: 새 모델이 특정 카테고리에서 성능 저하 (숨은 버그) → 세그먼트별 분석 필수
-->

**Step 1: 실험의 종류 결정**

<!-- 💬 [전문가의 눈] 왜 AI 실험 설계를 먼저 해야 하는가?
일반 제품의 A/B 테스트는 "빠르게" 결론을 낼 수 있지만(수 시간~하루), AI 실험은 모델의 확률적 특성 때문에 더 큰 샘플과 더 긴 기간이 필요하다. 따라서 "어떤 종류의 실험인가"를 먼저 결정하면 샘플 크기, 기간, 비용을 정확히 추정할 수 있다.
-->

AI 실험은 크게 3가지:

```
1️⃣  Model Selection Test (모델 A vs B)
    예: GPT-4 vs Claude 3 vs Llama 2
    특징: 높은 비용, 명확한 성능 차이
    샘플: 1,000-5,000 요청

2️⃣  Prompt Variation Test (프롬프트 A vs B)
    예: 한국어 최적화 프롬프트 vs 영어 번역 프롬프트
    특징: 낮은 비용, 미세한 개선
    샘플: 500-2,000 요청

3️⃣  UX/Presentation Test (UI A vs B)
    예: "신뢰도 표시" vs "신뢰도 숨김"
    특징: 사용자 신뢰도와 채택에 영향
    샘플: 100-500 사용자
```

**Step 2: 가설 정의 (SMART 형식)**

<!-- 💬 [논쟁 지점] 가설의 "구체성" 수준은 팀 성숙도에 따라 다르다.
초보 팀: "프롬프트 B가 더 좋을 것이다" 수준에서 시작 (정성적)
성숙한 팀: "기존 대비 정확도 5% 이상, 신뢰도 저하 없음"까지 구체화 (정량적)
한국 팀의 특성: 상세한 검증을 좋아하므로, SMART 형식을 처음부터 권장
-->

```
📋 SMART 가설 예시:

❌ 나쁜 가설: "이 프롬프트가 더 나을 것이다"
✅ 좋은 가설: "한국어 최적화 프롬프트(B)는
   기존 프롬프트(A) 대비
   정확도 5% 이상 개선(90% → 95%)
   신뢰도 저하 없음
   7일 내 정의하는 테스트 요청 100개 이상에서"

Components:
- Treatment 명확히 (B의 구체적 정의)
- Baseline 명확히 (A의 현 상태)
- Primary Metric (정확도 +5%)
- Secondary Metric (신뢰도 유지)
- Sample Size & Duration (100 요청, 7일)
```

**Step 3: 메트릭 선정 및 정의**

<!-- 💬 [자기 검증] 메트릭을 선정한 후 반드시 확인할 사항:
1. 각 메트릭을 실제로 수집할 수 있는가? (데이터 파이프라인 확인)
2. Primary/Secondary/Guardrail의 역할이 명확한가? (혼동하면 결론 왜곡 위험)
3. 메트릭 간에 트레이드오프가 있지 않은가? (정확도↑ but 응답시간↑)
-->

AI 실험에서 추적할 메트릭:

```
1. Primary Metric (반드시 측정)
   - Accuracy / Correctness: 모델 출력이 정확한가?
   - Latency: 응답 시간
   - Cost: 인프라 비용 (새 모델은 더 비쌀 수 있음)

2. Secondary Metric (영향 이해)
   - User Trust: 사용자가 결과를 믿는가?
   - User Action: 사용자가 결과를 수정했는가? (편집율)
   - User Satisfaction: NPS / CSAT
   - Adoption: 피처 사용률 변화

3. Guardrail Metric (부작용 감지)
   - Error Rate: 에러 증가 없는가?
   - Latency P95/P99: 응답 시간 악화 없는가?
   - Safety Incidents: 부정확한 결과로 인한 사고?
```

**Step 4: 샘플 크기 계산**

<!-- 💬 AI 실험의 샘플 크기는 왜 크게 필요한가?
일반 SaaS A/B 테스트:
- 분산 낮음 (버튼 클릭은 1 또는 0)
- 필요 샘플: ~500-1,000명

AI 실험:
- 분산 높음 (모델 출력의 품질은 0-100 스펙트럼)
- 필요 샘플: ~1,000-5,000개 요청

공식: n = (Z_α + Z_β)² × (σ₁² + σ₂²) / (μ₁ - μ₂)²
-->

```python
# 샘플 크기 계산 예시
from scipy import stats

def calculate_sample_size(
    baseline_metric: float,      # e.g., 0.90 (90% accuracy)
    expected_improvement: float,  # e.g., 0.05 (5% improvement)
    alpha: float = 0.05,         # 유의 수준 (5%)
    power: float = 0.80,         # 통계 검정력 (80%)
    metric_type: str = "accuracy" # accuracy, binary, continuous
):
    """
    AI 실험의 샘플 크기 계산

    # 예시
    calculate_sample_size(
        baseline_metric=0.90,       # 현재 정확도 90%
        expected_improvement=0.05,  # 5% 개선 기대
        alpha=0.05,
        power=0.80
    )
    # Output: 1,200 samples per group
    """

    # 효과 크기 (Effect Size) 계산
    if metric_type == "accuracy":
        # Accuracy는 비율 (proportion)
        effect_size = stats.norm.ppf(baseline_metric + expected_improvement) - stats.norm.ppf(baseline_metric)
    else:
        effect_size = expected_improvement

    # Z-값 계산
    z_alpha = stats.norm.ppf(1 - alpha/2)  # 양측 검정
    z_beta = stats.norm.ppf(power)

    # 샘플 크기 공식
    n = 2 * ((z_alpha + z_beta) ** 2) * (baseline_metric * (1 - baseline_metric) + (baseline_metric + expected_improvement) * (1 - baseline_metric - expected_improvement)) / (expected_improvement ** 2)

    return {
        "sample_size_per_group": int(n),
        "total_samples": int(n * 2),
        "duration_estimate_days": int(n / 10) if metric_type == "accuracy" else int(n / 100),
        "effect_size": effect_size,
    }

# 실행 예시
result = calculate_sample_size(baseline_metric=0.90, expected_improvement=0.05)
print(f"필요 샘플 크기: {result['total_samples']}개 (그룹당 {result['sample_size_per_group']}개)")
print(f"예상 테스트 기간: {result['duration_estimate_days']}일")
```

**Step 5: 통계 분석 계획**

<!-- 💬 [전문가의 눈] 다중 비교 보정(Multiple Testing Correction)이 왜 중요한가?
팀: "10개 세그먼트에서 각각 유의성 검정을 하겠습니다"
문제: 0.05 × 10 = 0.5 (50% 확률로 거짓 양성 발생 가능)
해결: Bonferroni (보수적) 또는 FDR (유연함)로 보정
한국 규제: 한국 개인정보보호법상 A/B 테스트 데이터 사용 동의 필요 여부 확인 권장
-->

```
📊 A/B 테스트 통계 분석 체크리스트

□ Primary Metric 분석
  - 평균값 비교 (t-test or Mann-Whitney U test)
  - 신뢰 구간 (95% CI) 계산
  - Effect Size (코헨의 d) 계산

□ Secondary Metric 분석
  - 각 메트릭별 통계 유의성 검정
  - 신뢰도 & 편집율 상관관계 분석

□ Guardrail Metric 검토
  - 안전성 메트릭이 "정상 범위"인지 확인
  - 부작용 감지 (특정 세그먼트에서 성능 저하)

□ 세그먼트 분석
  - 플랜별 (Free / Pro / Enterprise)
  - 지역별 (KR / APAC / Global)
  - 사용자 레벨별 (초보자 / 고급 사용자)
  - ⚠️ 주의: 다중 비교 보정 필요 (Bonferroni or FDR)

□ 다중 비교 보정 (Multiple Testing Correction)
  문제: 10개 세그먼트를 검정하면, 0.05 × 10 = 0.5 (50% 확률로 거짓 양성)
  해결책:
  - Bonferroni: p-value < 0.05 / 세그먼트 수
  - FDR (False Discovery Rate): 더 유연한 방법, 권장
```

**Step 6: 롤아웃 전략**

```
🚀 Staged Rollout Plan

Phase 1: Canary (1-2%)
├─ 규모: 사용자의 1-2% 또는 요청의 1-2%
├─ 기간: 3-7일
├─ 목표: 명백한 에러 감지, Guardrail 메트릭 확인
└─ 판단: "정상인가?" → 전진 또는 Rollback

Phase 2: Early Adopter (10-25%)
├─ 규모: 기대치 높은 고객 또는 무작위 샘플 10-25%
├─ 기간: 7-14일
├─ 목표: Primary Metric 유의성 검정 (90% 신뢰도 달성)
└─ 판단: "통계적으로 유의한가?" → 전진 또는 Rollback

Phase 3: Full Rollout (100%)
├─ 규모: 모든 사용자
├─ 기간: 즉시 또는 점진적 (1주)
├─ 목표: 모든 세그먼트에서 개선 확인
└─ 판단: 완료, 또는 특정 세그먼트만 Rollback

Rollback 조건 (자동 Trigger):
- Error Rate > 1% (평상시 0.5%)
- Latency P99 > 5초 (평상시 2초)
- Safety Incidents 발생
- Trust Score 급락 (1점 이상)
```

### 실험 계획서 템플릿

<!-- 💬 [자기 검증] 실험 계획서를 완성한 후 스스로 물어보세요:
1. "샘플 크기가 부족하면 어쩔 것인가?" → Contingency plan이 있는가?
2. "롤백 조건이 명확한가?" → 누가 언제 의사결정을 할 것인가?
3. "모든 이해관계자가 동의했는가?" → 엔지니어, PM, 데이터팀 모두?
한국 기업 특성상 "기획 → 검토 → 결재" 프로세스가 있으므로 계획서는 상세할수록 좋습니다.
-->

```markdown
# [기능명] A/B 테스트 계획서

## 1. 실험 개요
- 실험명: "한국어 프롬프트 최적화"
- 목표: Trust Score 6.8 → 7.5/10 (10% 개선)
- 예상 기간: 2주
- Owner: [PM 이름]
- Stakeholder: Product, Engineering, Data

## 2. 가설
**If** 우리가 프롬프트를 한국어 특화 (문맥 추가, 존댓말 톤 조정)로 변경하면
**Then** 정확도 3-5% 개선 + 신뢰도 0.5점 상승
**Because** 한국 사용자는 맥락 기반 커뮤니케이션을 선호함

## 3. 메트릭 정의

### Primary Metric
- **정확도 (Accuracy)**: 현재 90% → 목표 93%+
  - 정의: 자동 평가 (기준: 기존 모델과 사람의 일치율)
  - 측정: 각 결과를 자동으로 채점, 샘플: 1,000 요청

### Secondary Metrics
- **신뢰도 (Trust Score)**: 현재 6.8/10 → 목표 7.3/10+
  - 측정: 주간 설문 (최소 200명)
- **편집율 (Editing Rate)**: 32% 유지 또는 감소
  - 정의: 결과를 수정한 사용자 비율
- **채택율 (Adoption)**: 현재 24% 이상 유지

### Guardrail Metrics
- **에러율**: 1% 이상 증가 금지
- **응답시간**: P95 > 3초 금지
- **특정 세그먼트 성능**: 초보자 그룹 성능 10% 이상 저하 금지

## 4. 샘플 크기 및 기간
- 필요 샘플: 2,400개 요청 (그룹당 1,200)
- 예상 기간: 10-14일 (일일 150-200개 요청)
- 신뢰도: 95%, 검정력: 80%

## 5. 실험 설계
- **대조군 (Control)**: 기존 프롬프트
- **실험군 (Treatment)**: 한국어 최적화 프롬프트
- **할당 비율**: 50% / 50% (균등)
- **대상 사용자**: 무작위 샘플 (세그먼트별 균형 확인)

## 6. 롤아웃 계획
- Phase 1 (Canary): 2% (3-5일)
- Phase 2 (Early Adopter): 25% (7-10일)
- Phase 3 (Full): 100% (즉시 또는 1주)

## 7. 성공 조건
✅ Primary Metric: 정확도 93% 이상 + 통계적 유의성 (p < 0.05)
✅ Secondary Metrics: 신뢰도 0.3점 이상 상승
✅ Guardrail: 모든 안전 지표 정상 범위
✅ 세그먼트: 모든 주요 세그먼트에서 긍정적 또는 중립

## 8. 실패 조건 (Rollback Trigger)
❌ 정확도 90% 미만으로 하락
❌ 신뢰도 6.5 이하로 저하
❌ 특정 세그먼트 (예: 초보자) 성능 10%+ 저하
❌ 에러율 1% 초과

### 🇰🇷 한국 시장 맥락

```
한국 시장 A/B 테스트 고려사항:

1. **한국 사용자 행동 특성**:
   - 모바일 중심 (PC 대비 모바일 80% 이상)
   - 카카오톡/네이버 로그인 의존도 높음 (사용자 추적 용이)
   - 점심시간(12-1시), 퇴근시간(6-7시) 피크 → 샘플 분포 불균형 가능

2. **한국 개인정보보호법 (PIPA) 준수**:
   - A/B 테스트 실시 전 사용자 동의 필요 여부 법무팀 검토 권장
   - 개인정보 수집/이용 동의에 "테스트"가 명시되어 있는가?
   - 특히 금융, 의료, 통신 업계: 규제 더 엄격

3. **한국 시장 샘플 크기 고려**:
   - 전체 인구 5,100만 명 (한정된 시장)
   - 국내 서비스의 경우 사용자 100만 명 기준으로 샘플 계산
   - 글로벌 대비 작은 샘플로 통계 유의성 확보 어려울 수 있음
   - 해결: 장기 테스트(2-4주) 또는 MDE(최소 감지 효과) 상향 조정

4. **한국 기업의 A/B 테스트 문화**:
   - "기획 → 검토 → 결재" 단계별 승인 필수 (Western 기업보다 더 엄격)
   - 실험 계획서는 상세할수록 승인이 빠름
   - 진행 중 발견 사항도 주간 보고 필요 (결재권자 신뢰 유지)
```
```

💡 **Deep Tips:**
- **샘플 크기**: 너무 작으면 유의성 감지 못함, 너무 크면 시간 낭비
- **다중 비교**: 10개 세그먼트를 검정하면 Bonferroni 보정 필수
- **신뢰도 추적**: AI 기능은 "객관적 정확도" + "사용자 신뢰도"를 함께 봐야 함


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 가설이 모호 | "X를 변경하면 Y가 Z%만큼 개선된다"형식으로 명확히 |
| 3단계 | 샘플 크기 계산 어려움 | 통계 계산기를 사용하세요. AI에게 "이 조건에서 필요한 샘플 크기"를 물어보세요 |
| 5단계 | 통계적 유의성 판단 어려움 | p-value < 0.05를 기본으로 하되, 효과 크기(Effect Size)도 함께 확인 |
| 7단계 | 롤아웃 판단이 어려움 | 1% → 5% → 25% → 100% 단계적 롤아웃. 각 단계에서 메트릭 확인 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — A/B 테스트 설계, 실행, 분석을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
AI 실험은 일반 SaaS보다 복잡합니다 (모델 불확실성, 분포 시프트 등). 자동화하면 통계적 엄밀성을 유지하면서 빠르게 실험할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 실험 설계 및 분석 프레임워크

```python
# ai_experiment_framework.py
import numpy as np
import pandas as pd
from scipy import stats
from dataclasses import dataclass
from typing import Dict, List, Tuple
from datetime import datetime, timedelta

@dataclass
class ExperimentConfig:
    """A/B 테스트 설정"""
    experiment_id: str
    experiment_name: str
    control_group: str
    treatment_group: str
    baseline_metric: float
    expected_improvement: float
    alpha: float = 0.05
    power: float = 0.80
    duration_days: int = 14
    start_date: str = None

class AIExperimentDesigner:
    """AI 실험 설계 및 분석"""

    def __init__(self, config: ExperimentConfig):
        self.config = config
        self.results_df = None

    def calculate_sample_size(self) -> Dict:
        """필요한 샘플 크기 계산"""
        z_alpha = stats.norm.ppf(1 - self.config.alpha / 2)
        z_beta = stats.norm.ppf(self.config.power)

        # 비율 데이터 (accuracy) 기준
        p1 = self.config.baseline_metric
        p2 = p1 + self.config.expected_improvement

        numerator = (z_alpha + z_beta) ** 2 * (p1 * (1 - p1) + p2 * (1 - p2))
        denominator = (p2 - p1) ** 2

        n_per_group = numerator / denominator

        return {
            "sample_size_per_group": int(np.ceil(n_per_group)),
            "total_samples": int(np.ceil(n_per_group * 2)),
            "alpha": self.config.alpha,
            "power": self.config.power,
            "baseline": self.config.baseline_metric,
            "expected_improvement": self.config.expected_improvement,
        }

    def analyze_results(self,
                       control_data: np.ndarray,
                       treatment_data: np.ndarray) -> Dict:
        """A/B 테스트 결과 분석"""

        # 기본 통계
        control_mean = np.mean(control_data)
        treatment_mean = np.mean(treatment_data)
        control_std = np.std(control_data)
        treatment_std = np.std(treatment_data)

        # t-검정 (독립표본 t-test)
        t_stat, p_value = stats.ttest_ind(treatment_data, control_data)

        # 신뢰 구간 (95%)
        se = np.sqrt((control_std**2 / len(control_data)) +
                     (treatment_std**2 / len(treatment_data)))
        ci_lower = (treatment_mean - control_mean) - 1.96 * se
        ci_upper = (treatment_mean - control_mean) + 1.96 * se

        # 효과 크기 (코헨의 d)
        pooled_std = np.sqrt(((len(control_data)-1) * control_std**2 +
                              (len(treatment_data)-1) * treatment_std**2) /
                             (len(control_data) + len(treatment_data) - 2))
        cohens_d = (treatment_mean - control_mean) / pooled_std if pooled_std > 0 else 0

        # 실질적 유의성 (Practical Significance)
        improvement_pct = ((treatment_mean - control_mean) / control_mean * 100) if control_mean > 0 else 0

        return {
            "control_mean": control_mean,
            "treatment_mean": treatment_mean,
            "difference": treatment_mean - control_mean,
            "improvement_pct": improvement_pct,
            "t_statistic": t_stat,
            "p_value": p_value,
            "statistically_significant": p_value < self.config.alpha,
            "confidence_interval": (ci_lower, ci_upper),
            "cohens_d": cohens_d,
            "effect_size_interpretation": self._interpret_cohens_d(cohens_d),
            "samples": {
                "control": len(control_data),
                "treatment": len(treatment_data),
            }
        }

    def _interpret_cohens_d(self, d: float) -> str:
        """코헨의 d 해석"""
        if abs(d) < 0.2:
            return "Negligible (무시할 수 있음)"
        elif abs(d) < 0.5:
            return "Small (작음)"
        elif abs(d) < 0.8:
            return "Medium (중간)"
        else:
            return "Large (큼)"

    def segment_analysis(self,
                        df: pd.DataFrame,
                        segment_col: str,
                        metric_col: str) -> pd.DataFrame:
        """
        세그먼트별 분석 with Bonferroni 보정
        """
        segments = df[segment_col].unique()
        n_segments = len(segments)

        # Bonferroni 보정
        bonferroni_alpha = self.config.alpha / n_segments

        results = []
        for segment in segments:
            segment_data = df[df[segment_col] == segment]
            control = segment_data[segment_data['group'] == self.config.control_group][metric_col].values
            treatment = segment_data[segment_data['group'] == self.config.treatment_group][metric_col].values

            if len(control) > 0 and len(treatment) > 0:
                t_stat, p_value = stats.ttest_ind(treatment, control)
                results.append({
                    "segment": segment,
                    "control_mean": np.mean(control),
                    "treatment_mean": np.mean(treatment),
                    "improvement_pct": ((np.mean(treatment) - np.mean(control)) / np.mean(control) * 100),
                    "t_statistic": t_stat,
                    "p_value": p_value,
                    "bonferroni_adjusted_p_value": p_value * n_segments,
                    "significant_bonferroni": p_value < bonferroni_alpha,
                    "n_control": len(control),
                    "n_treatment": len(treatment),
                })

        return pd.DataFrame(results)

    def generate_report(self,
                       analysis_results: Dict,
                       segment_results: pd.DataFrame = None) -> str:
        """실험 결과 리포트 생성"""

        report = f"""
# A/B Test Report: {self.config.experiment_name}
Generated: {datetime.now().strftime('%Y-%m-%d %H:%M UTC')}

## Experiment Overview
- ID: {self.config.experiment_id}
- Control Group: {self.config.control_group}
- Treatment Group: {self.config.treatment_group}
- Duration: {self.config.duration_days} days
- Start Date: {self.config.start_date}

## Sample Size
- Samples (Control): {analysis_results['samples']['control']:,}
- Samples (Treatment): {analysis_results['samples']['treatment']:,}
- Total: {analysis_results['samples']['control'] + analysis_results['samples']['treatment']:,}

## Results
### Primary Metric
- Control Mean: {analysis_results['control_mean']:.4f}
- Treatment Mean: {analysis_results['treatment_mean']:.4f}
- Difference: {analysis_results['difference']:.4f}
- Improvement: {analysis_results['improvement_pct']:.2f}%
- Confidence Interval (95%): [{analysis_results['confidence_interval'][0]:.4f}, {analysis_results['confidence_interval'][1]:.4f}]

### Statistical Significance
- t-statistic: {analysis_results['t_statistic']:.4f}
- p-value: {analysis_results['p_value']:.6f}
- Statistically Significant (α=0.05): {"✅ YES" if analysis_results['statistically_significant'] else "❌ NO"}

### Effect Size
- Cohen's d: {analysis_results['cohens_d']:.4f}
- Interpretation: {analysis_results['effect_size_interpretation']}

## Recommendation
"""

        if analysis_results['statistically_significant'] and analysis_results['improvement_pct'] > 0:
            report += "✅ **ROLL OUT**: Treatment shows significant improvement\n"
        elif analysis_results['improvement_pct'] > 0 and not analysis_results['statistically_significant']:
            report += "⚠️ **MONITOR**: Positive trend but not statistically significant (need more samples)\n"
        else:
            report += "❌ **ROLLBACK**: No improvement or statistically worse\n"

        if segment_results is not None:
            report += f"\n## Segment Analysis (Bonferroni Corrected)\n"
            report += segment_results.to_markdown()

        return report


# 사용 예시
if __name__ == "__main__":
    # 1. 실험 설정
    config = ExperimentConfig(
        experiment_id="exp_001_ko_prompt",
        experiment_name="한국어 프롬프트 최적화",
        control_group="baseline_prompt",
        treatment_group="ko_optimized_prompt",
        baseline_metric=0.90,  # 90% accuracy
        expected_improvement=0.05,  # 5% improvement
        alpha=0.05,
        power=0.80,
        duration_days=14,
        start_date="2026-03-10"
    )

    designer = AIExperimentDesigner(config)

    # 2. 샘플 크기 계산
    sample_size = designer.calculate_sample_size()
    print(f"필요 샘플 크기: {sample_size['total_samples']:,} (그룹당 {sample_size['sample_size_per_group']:,})")

    # 3. 결과 분석 (시뮬레이션)
    np.random.seed(42)
    control_accuracy = np.random.beta(11, 1.1, 1200)  # 평균 ~90%
    treatment_accuracy = np.random.beta(11.5, 1.1, 1200)  # 평균 ~91.2%

    analysis = designer.analyze_results(control_accuracy, treatment_accuracy)
    print(f"\n결과: {analysis['improvement_pct']:.2f}% 개선 (p={analysis['p_value']:.4f})")

    # 4. 리포트 생성
    report = designer.generate_report(analysis)
    print(report)
```

### Claude Code CLI 실험 관리

```bash
# 1. 실험 계획서 생성
claude code run design-experiment \
  --experiment-name "한국어 프롬프트 최적화" \
  --baseline-metric 0.90 \
  --expected-improvement 0.05 \
  --duration-days 14 \
  --output design-doc.md

# 2. 실험 설정 적용 (코드 배포)
claude code run deploy-experiment \
  --experiment-id exp_001_ko_prompt \
  --control-code "prompt_v1.json" \
  --treatment-code "prompt_v2_ko.json" \
  --rollout-percentage 2

# 3. 실시간 모니터링 (Guardrail 메트릭)
claude code run monitor-experiment \
  --experiment-id exp_001_ko_prompt \
  --metric accuracy,error_rate,latency \
  --alert-threshold 0.01

# 4. 결과 분석 및 리포팅
claude code run analyze-experiment \
  --experiment-id exp_001_ko_prompt \
  --input results.csv \
  --generate-report

# 5. 롤아웃 결정
claude code run rollout-decision \
  --experiment-id exp_001_ko_prompt \
  --phase 2 \
  --target-percentage 25
```

---

## 📊 실행 결과 예시

### 실험 계획서 (수립 단계)

```
# 한국어 프롬프트 최적화 A/B 테스트

## 가설
"한국어 문맥 최적화 프롬프트는 기본 영어 프롬프트 대비
정확도 5% 개선 + 신뢰도 0.5점 상승"

## 샘플 크기 계산
필요 샘플: 2,400개 (그룹당 1,200)
예상 기간: 10-14일
신뢰도: 95%, 검정력: 80%

## 메트릭
| Metric | Control | Target |
|--------|---------|--------|
| Accuracy | 90% | 95%+ |
| Trust Score | 6.8/10 | 7.3/10+ |
| Error Rate | <0.5% | <0.5% (유지) |
```

### 실험 결과 분석 (2주 후)

```
# 한국어 프롬프트 최적화 - 최종 결과

## Primary Metric: Accuracy
- Control (기본 프롬프트): 90.2%
- Treatment (한국어 최적화): 93.8%
- 개선: +3.6 pp (목표 +5pp는 미달하지만 유의미)
- p-value: 0.0023 ✅ 통계적 유의성 확보

## Secondary Metrics
- Trust Score: 6.8 → 7.2/10 (+0.4점) ✅
- Editing Rate: 32% → 29% (-3pp) ✅ 신뢰도 향상 신호
- Adoption: 24% 유지 ✅

## Guardrail Metrics
- Error Rate: 0.48% (정상) ✅
- Latency P95: 2.1초 (정상) ✅
- No Safety Incidents ✅

## Segment Analysis (Bonferroni 보정)
| Segment | Improvement | p-value | Significant |
|---------|-------------|---------|-------------|
| Enterprise | +4.2% | 0.0001 | ✅ Yes |
| Pro | +3.5% | 0.0042 | ✅ Yes |
| Starter | +3.1% | 0.0156 | ✅ Yes |
| Free | +1.9% | 0.1234 | ❌ No* |
| KR Region | +5.1% | <0.0001 | ✅ Yes |
| Global | +3.2% | 0.0015 | ✅ Yes |

*Free 플랜은 샘플 부족, 더 모니터링 필요

## 결론
✅ **RECOMMEND ROLLOUT**
- 통계적으로 유의한 개선 (p < 0.05)
- 모든 주요 세그먼트 (Enterprise, Pro, KR)에서 개선
- Guardrail 메트릭 정상
- 신뢰도 향상 신호 확인 (편집율 감소)

## 롤아웃 계획
Phase 1: 100% 즉시 배포 (금토일 모니터링)
Phase 2: 이전 프롬프트는 1주일 후 폐지
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 실험 설계에서 '표본 크기(sample size)'가 통계적으로 충분한지 확인하세요
2. **[논쟁 지점]** A/B 테스트에서 '통계적 유의성(p<0.05)' vs '실질적 유의성(practical significance)'을 어디에 무게를 둘지는 비즈니스 맥락에 따라 다릅니다
3. **[자기 검증]** 실험 결과 해석 시 Simpson's Paradox가 없는지 — 세그먼트별로 나눠서도 같은 결과인지 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|------|-----------|------|
| ✅ 실험 설계 & 샘플 크기 | `ai-adoption-metrics.md` | "메트릭 정의를 바탕으로 실험 설계" |
| ✅ 롤아웃 데이터 | `retention-analysis.md` | "롤아웃 후 코호트별 리텐션 추적" |
| ✅ 결과 의사소통 | `communicate/stakeholder-alignment.md` | "A/B 테스트 결과를 경영진에게 설명" |
| 🔜 자동화 | Claude Code `--continuous-monitoring` | 매주 실험 결과 자동 분석 |
