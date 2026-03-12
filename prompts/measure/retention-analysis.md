# 📈 리텐션 분석 (Retention Analysis for AI Features)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 35분+ (Build)
> 워크플로우: ← `ab-test-design.md`, `ai-adoption-metrics.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 기능을 출시한 후 "사용자들이 정말 계속 쓸까?"라는 질문에 답하기 어렵다. 일반적인 리텐션 메트릭 (DAU, MAU)은 AI 기능의 실제 "의존도"를 보여주지 않는다. **코호트별 리텐션, 신뢰도 기반 리텐션, AI 기능의 생명주기 분석**이 필요하다.

---

## 📥 이전 프롬프트에서 받는 입력

> `ai-adoption-metrics.md`에서 채택률 분석 후, 리텐션 심화 분석이 필요할 때 연결됩니다.

이전 프롬프트 결과에서 **코호트 기준, 분석 기간, 핵심 이벤트 정의**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 제품의 핵심 리텐션 메트릭을 분석할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI PM 데이터 분석가다.

{AI 기능명}의 리텐션을 분석하세요:

1. 코호트별 리텐션 (신규 사용자 기준)
   - 첫 사용 후 7일 / 30일 / 90일 재사용률
   - 코호트 트렌드 (시간 경과에 따라 좋아지나, 나빠지나?)

2. 신뢰도 기반 리텐션
   - "신뢰도 높은 사용자" vs "낮은 사용자" 리텐션 비교
   - 신뢰도가 리텐션을 얼마나 예측하는가?

3. 리텐션 세그먼트
   - 플랜별 (Free / Pro / Enterprise)
   - 사용 행동별 ("파워 사용자" vs "라이트 사용자")
   - 지역별

4. 위험 신호
   - "리텐션 급락"하는 사용자 그룹은?
   - "반복 사용을 중단한" 사용자들의 공통점은?

각 항목별로 해석과 액션을 제시하세요.
```

💡 **Quick Tips:**
- 코호트는 "첫 사용 날짜"를 기준으로 분류 (가입 날짜 아님)
- AI 신뢰도 떨어지면 리텐션도 급락 → 신뢰도는 조기 경고 신호
- 세그먼트별 "리텐션 곡선"이 다름 → "일괄 롤아웃"보다 "세그먼트별 전략" 필요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 데이터가 부족 (초기 제품) | "Day 1 리텐션"부터 시작하세요. 장기 리텐션은 데이터가 쌓인 후 |
| B2B라서 리텐션 정의 어려움 | "월간 활성 계정" 또는 "기능 사용률"로 정의 |
| 여러 기능의 리텐션 비교 | 기능별 사용 패턴과 전체 리텐션의 상관관계를 분석하세요 |
| 리텐션이 좋은데 성장이 안 됨 | Acquisition(획득) 문제일 수 있습니다. 리텐션과 분리해서 분석 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 리텐션을 코호트별, 기능별로 깊이 분석하고 싶은 분입니다.
"왜 고객이 떠나는가?"를 데이터로 파악하고 싶다면 이걸 써보세요.

### 📌 진행 방식

이 프롬프트는 **6단계 CoT(Chain of Thought)** 구조입니다. 두 가지 방식으로 쓸 수 있습니다:

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

당신은 **AI 제품 리텐션 분석 전문가**이다. 당신의 역할:

1. **코호트 분석**: 사용자 그룹을 세분화하고 리텐션 추이를 추적
2. **신뢰도-리텐션 연계**: AI 신뢰도가 얼마나 리텐션을 예측하는가 정량화
3. **생명주기 이해**: AI 기능의 "성장 → 성숙 → 감소" 단계 파악
4. **액션 도출**: 리텐션 저하 원인 진단 및 개선 방향 제시

<!-- 💬 일반 SaaS와 AI 제품의 리텐션 분석 차이
일반 SaaS (예: CRM):
- 리텐션이 떨어지면 → "기능 불만족" 또는 "더 좋은 대체 상품"
- 개선: 기능 추가, UX 개선

AI 제품 (예: AI 요약):
- 리텐션이 떨어지면 → "신뢰도 저하" (정확도 안 맞음, 불안감)
- 개선: 모델 정확도, 불확실성 표시, 신뢰도 강화

따라서 AI 제품의 리텐션 분석은 반드시 "신뢰도"를 함께 봐야 함.
-->

### 목표

최종 아웃풋:
- **코호트 리텐션 분석** (신규 사용자별 7/30/90일 리텐션)
- **신뢰도-리텐션 상관 분석** (신뢰도가 높을수록 리텐션도 높은가?)
- **위험 세그먼트 식별** (가장 리텐션이 낮은 그룹은?)
- **개선 액션 플랜** (리텐션 저하 원인과 처방)

### Reasoning Strategy

<!-- 💬 AI 기능의 리텐션 곡선은 일반 기능과 왜 다른가?
일반 기능 (예: 필터링):
┌─
│      ───────  ← 비교적 평탄 (한번 배우면 계속 씀)
│  ／
└──────────────

AI 기능 (예: 요약):
┌─
│   ╱╲
│  ╱  ╲
│ ╱    ╲──
└────────────

→ 초반에 높다 (신기함, 호기심)
→ 중반에 떨어진다 (정확도 부족, 신뢰 상실)
→ 마지막에 안정화 (신뢰할 수 있는 사용자만 남음)

따라서 "Day 7 → Day 30" 리텐션 저하가 AI 제품의 핵심 지표다.
-->

**Step 1: 리텐션 메트릭 정의**

```
1️⃣  Day-N Retention
정의: (첫 사용 후 N일에 다시 사용한 사용자) ÷ (첫 사용 사용자)
예: Day 7 Retention = 35% (사용자 100명 중 35명이 7일 내 재사용)

2️⃣  Cohort Retention Curve
정의: 같은 주/월에 처음 사용한 사용자들의 장기 리텐션 추적
예: "2월 첫 주 신규" 그룹이 1주/2주/4주/8주/12주에 몇 %가 활성인가?

3️⃣  Retention Decay Rate
정의: 주간/월간 리텐션 감소율
예: Day 7 Retention 35% → Day 30 Retention 25% = Decay 10pp

4️⃣  AI Trust-Based Retention
정의: 신뢰도 점수별 리텐션 분할
예: "신뢰도 8/10 이상" 사용자의 리텐션 vs "신뢰도 5/10 이하" 사용자 리텐션
```

**Step 2: 코호트 분석 설계**

```
🎯 코호트 분석 구조

┌─────────────────────────────────────────────────────────┐
│ Cohort: Users with First AI Usage in Week of 2/10/2026 │
├─────────────────────────────────────────────────────────┤
│ Cohort Size: 420 users                                  │
├─────────────────────────────────────────────────────────┤
│ Day    │ Active Users │ Retention % │ Trend            │
├────────┼──────────────┼─────────────┼──────────────────┤
│ D0     │ 420          │ 100% (Base) │ ─ (Definition)   │
│ D1     │ 315          │ 75%         │ 낮음 (초기 이탈) │
│ D7     │ 147          │ 35% ⚠️      │ 급락 (신뢰 상실) │
│ D14    │ 105          │ 25%         │ 안정화           │
│ D30    │ 84           │ 20%         │ 안정화           │
│ D90    │ 63           │ 15% (LTV)   │ 안정화           │
└─────────────────────────────────────────────────────────┘

Insight:
- D1 → D7: -40pp = 신뢰도/성능 이슈 (초기 경험 실패)
- D7 → D30: -15pp = 선택적 포기 (신뢰하는 사용자만 남음)
- D30 → D90: -5pp = 안정적 리텐션 (우수 사용자의 LTV)
```

**Step 3: 신뢰도-리텐션 상관 분석**

<!-- 💬 [전문가의 눈] 신뢰도와 리텐션의 상관관계를 먼저 정량화해야 하는 이유:
만약 상관계수가 0.6 이상이면: "신뢰도 개선이 리텐션 개선의 지름길"
만약 상관계수가 0.2 미만이면: "다른 요인들(가격, 경쟁사, UI)이 더 중요"
이를 알아야 로드맵 우선순위를 정할 수 있다. 한국 시장은 신뢰도 의존도가 높은 편(0.6+).
-->

```python
# 신뢰도 점수와 리텐션의 상관관계

# 데이터 구조
user_data = {
    "user_id": [u1, u2, u3, ...],
    "trust_score": [7.2, 6.1, 8.5, ...],  # D7 기준 신뢰도
    "d30_retained": [1, 0, 1, ...],       # D30 리텐션 여부
}

# 분석
Correlation(Trust Score, D30 Retention) = 0.62 (강한 양의 상관)
→ 해석: 신뢰도가 1점 높으면, D30 리텐션 확률이 15% 증가

# 신뢰도 구간별 리텐션
┌──────────────────────────────────────────┐
│ Trust Score 구간 │ D7 Ret │ D30 Ret │ LTV │
├──────────────────────────────────────────┤
│ 8.0-10  (높음)  │ 60%    │ 48%     │ ⭐⭐⭐ │
│ 6.0-7.9 (중간)  │ 35%    │ 22%     │ ⭐⭐  │
│ 4.0-5.9 (낮음)  │ 8%     │ 2%      │ ⭐   │
└──────────────────────────────────────────┘

Interpretation:
신뢰도 높은 사용자(8.0+)는 D30 리텐션이 48%
신뢰도 낮은 사용자(4.0-5.9)는 D30 리텐션이 2%

→ 리텐션 개선 = 신뢰도 개선에 직결
```

**Step 4: 세그먼트별 리텐션 비교**

<!-- 💬 [논쟁 지점] 어느 세그먼트를 우선으로 개선할 것인가?
관점 1: "Enterprise 리텐션 이미 높으니, Starter/Free 개선에 집중" (형평성)
관점 2: "Enterprise가 수익의 70%이므로, Enterprise 리텐션부터" (수익성)
정답은 비즈니스 전략에 따라 다름. 한국 기업은 보통 관점 2를 선호.
-->

```
┌──────────────────────────────────────────────────────────┐
│ Retention by Customer Segment                           │
├──────────────────────────────────────────────────────────┤
│ Segment    │ D7    │ D30   │ D90   │ Trend      │ Status │
├────────────┼───────┼───────┼───────┼────────────┼────────┤
│ Enterprise │ 55%   │ 45%   │ 38%   │ ↗️ 좋음   │ 🟢    │
│ Pro        │ 38%   │ 28%   │ 22%   │ → 중간    │ 🟡    │
│ Starter    │ 20%   │ 12%   │ 8%    │ ↘️ 나쁨   │ 🔴    │
│ Free       │ 8%    │ 3%    │ 1%    │ ↘️ 악함   │ ⛔    │
├────────────┼───────┼───────┼───────┼────────────┼────────┤
│ Power User │ 70%   │ 58%   │ 48%   │ ↗️ 우수   │ 🟢    │
│ Regular    │ 35%   │ 24%   │ 18%   │ → 중간    │ 🟡    │
│ Light      │ 12%   │ 6%    │ 3%    │ ↘️ 약함   │ 🔴    │
└──────────────────────────────────────────────────────────┘

Key Finding:
Enterprise & Power User 리텐션 5배 이상 높음
→ 전략: Free/Starter는 신뢰도 개선 우선 (또는 Freemium 재검토)
```

**Step 5: 위험 신호 및 원인 분석**

<!-- 💬 [자기 검증] 원인 분석을 하기 전에 다음을 확인하세요:
1. "통계적 유의성이 있는가?" → 샘플 크기가 충분한가?
2. "다른 요인이 섞여있지 않은가?" → 같은 기간에 다른 변화가 있었는가? (마케팅 캠페인, 가격 인상 등)
3. "가설과 데이터가 일치하는가?" → "모델 정확도 저하"를 주장하는데, 실제로 정확도 로그가 있는가?
증거 없는 가설은 의사결정을 오도할 수 있습니다.
-->

```
🚨 리텐션 저하의 근본 원인

문제: D7 리텐션 35% (목표 45%)

가설 1: 정확도 문제
┌─────────────────────────────────┐
│ Low Accuracy Users (0-70%)      │
│ - D7 Retention: 8%              │
│ - D7 Trust Score: 4.2/10        │
│ - Feedback: "부정확함"           │
│ → 작업: 모델 정확도 개선         │
└─────────────────────────────────┘

가설 2: 발견 문제
┌─────────────────────────────────┐
│ Never Tried Feature              │
│ - Onboarding 완료율: 45%        │
│ - D7 Retention (완료자): 55%    │
│ - D7 Retention (미완료자): 5%   │
│ → 작업: Onboarding 개선         │
└─────────────────────────────────┘

가술 3: 신뢰도 표시 부족
┌─────────────────────────────────┐
│ Users Who Edited Results         │
│ - Editing Rate: 32%             │
│ - D7 Retention (High Editor): 18%│
│ - "신뢰 안 해서 수정함"         │
│ → 작업: 신뢰도 점수 표시         │
└─────────────────────────────────┘
```

### 코호트 리텐션 분석 템플릿

```markdown
# 코호트 리텐션 분석 보고서

## 1. 종합 리텐션 현황

| 코호트 | 초기 | D7 | D30 | D90 | 추세 |
|------|------|------|------|------|------|
| 2/1-7주 | 450 | 157 (35%) | 102 (23%) | 68 (15%) | ↓ (신뢰도 회복 중) |
| 2/8-14주 | 520 | 156 (30%) | 89 (17%) | 52 (10%) | ↓↓ (모델 성능 저하?) |
| 2/15-21주 | 480 | 115 (24%) | 58 (12%) | 35 (7%) | ↓↓↓ (심각) |
| 2/22-28주 | 610 | 183 (30%) | 98 (16%) | - | 개선 중 |

## 2. 신뢰도 기반 리텐션

### Trust Score와 D30 리텐션 상관
- Pearson Correlation: 0.68 (강한 양의 상관)
- 해석: 신뢰도 1점 증가 시 D30 리텐션 8-10% 증가

### 신뢰도 구간별 리텐션
| Trust Score | D7 Ret | D30 Ret | Sample | LTV |
|-----------|--------|---------|--------|-----|
| 8.0-10.0 | 62% | 50% | 120 | 높음 |
| 6.0-7.9 | 38% | 25% | 280 | 중간 |
| 4.0-5.9 | 12% | 4% | 150 | 낮음 |

## 3. 세그먼트별 분석

### 플랜별 리텐션
- Enterprise: D30 45% (우수)
- Pro: D30 28% (중간)
- Starter: D30 12% (저조)
- Free: D30 3% (매우 저조)

### 행동별 리텐션
- "정확도 높게 평가" (90%+): D30 52%
- "정확도 보통" (70-89%): D30 22%
- "정확도 낮게 평가" (<70%): D30 3%

## 4. 위험 신호

### 🚨 Critical Issues
1. 2/15-21 코호트: D30 리텐션 12% (매우 저조)
   - 원인 추정: 2월 25일 모델 업데이트 후 정확도 저하?
   - 액션: 긴급 모델 성능 검사

2. Starter 플랜: D30 리텐션 12% (사업적으로 위험)
   - 원인 추정: 신뢰도 부족 + 제한된 피쳐
   - 액션: Starter 사용자 대상 Onboarding 강화

### 🟡 Warning Signs
- Editing rate 높은 사용자 (32%): D30 리텐션만 18%
  - 신뢰 안 해서 결과를 수정함
  - 액션: 신뢰도 점수 표시, 모델 정확도 개선

## 5. 추천 액션

### 즉시 (1주)
- [ ] 2/15-21 코호트 급락 원인 분석
- [ ] 모델 성능 비교 (2/25 업데이트 전후)

### 단기 (2-4주)
- [ ] Starter 사용자 대상 신뢰도 강화 (예: 신뢰도 점수 표시)
- [ ] 높은 편집율 사용자 피드백 수집

### 중기 (1-2개월)
- [ ] 모델 정확도 개선 (목표: 신뢰도 7.0+)
- [ ] Onboarding 개선 (목표: D7 리텐션 50% 이상)
```

💡 **Deep Tips:**
- **코호트 정의**: "가입 날짜" 아니라 "첫 AI 사용 날짜"로 분류 (더 정확)
- **신뢰도 핵심**: 리텐션 저하 → 신뢰도 먼저 확인 (정확도 이슈일 가능성 높음)
- **세그먼트 차이**: Free vs Enterprise 5배 이상 차이 → 가격 전략 재검토 필요

### 🇰🇷 한국 시장 리텐션 특수 고려사항

<!-- 💬 [전문가의 눈] 한국 시장의 리텐션 분석이 글로벌과 다른 이유:
한국 사용자의 서비스 전환율이 높다 (선택지가 많고, 비용 민감도 높음)
따라서 Day 1 리텐션은 낮지만, 일단 신뢰도를 형성한 사용자는 매우 충성도가 높다
리텐션 곡선의 "초반 급락 → 안정화" 패턴을 한국에서 더 자주 본다.
-->

```
한국 시장 리텐션 분석 추가 고려사항:

1. **주간 리텐션(W7)이 더 의미있음**:
   - 글로벌: D7 리텐션 기준 (일일 활성)
   - 한국: W7 리텐션 기준 (주간 활성) → 업무용 AI는 사용 빈도가 낮음
   - 권장: D1, D7, W1, W4 모두 추적

2. **요일 효과 고려**:
   - 월요일 리텐션 vs 금요일 리텐션 큰 차이 (한국은 주중 업무 중심)
   - 점심시간(12-1시), 퇴근시간(6-7시) 피크 후 사용 패턴 급락
   - 세그먼트: 직장인 vs 자영업자 리텐션 패턴 다름

3. **해석 시 주의**:
   - "리텐션 저하" = 사용 기회 자체 감소일 수도 있음 (계절성, 업무 시즌)
   - 3주 이상 연속 데이터로 추이를 봐야 월간 변동과 구분 가능

4. **한국 규제 리텐션 메트릭**:
   - 사용자 동의 거부 후 추적 데이터 제외 필요
   - 개인정보보호법 준수: 이탈 사용자 피드백 수집 시 동의 재확인
```



### # 🇰🇷 한국 시장 리텐션 분석 포인트

```
한국 시장 특수성:

1. **메신저 의존도**: 카카오톡 알림이 리텐션에 직접적 영향
   - 카톡 알림 On vs Off → D7 리텐션 차이 평균 15-20%
   - 앱 푸시보다 카톡 알림의 재방문 유도 효과가 2-3배 높음

2. **구독 피로도**: 한국 사용자는 구독 서비스에 민감
   - 무료 체험 → 유료 전환율이 글로벌 평균(3-5%)보다 낮음(1-3%)
   - "첫 달 할인" 보다 "3개월 번들" 전략이 한국에서 더 효과적

3. **데이터 소스**:
   - 앱스토어: Google Play (한국은 iOS < Android)
   - 결제: 토스페이먼츠, 카카오페이 결제 데이터
   - 분석: Amplitude Korea, 채널톡, Braze Korea

4. **리텐션 기준 차이**:
   - 글로벌 SaaS: D1 리텐션 기준
   - 한국 SaaS: W1 리텐션이 더 의미있음 (사용 빈도가 낮은 편)
   - AI 제품: "AI 기능 재사용률"을 별도 추적
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 리텐션 정의가 모호 | "활성 사용자"의 정의를 먼저 명확히 하세요. 로그인? 핵심 기능 사용? |
| 2단계 | 코호트 분류가 어려움 | 가입 시점(주/월) 기준이 가장 기본. 그 후 세그먼트별 추가 |
| 3단계 | 이탈 원인 파악 어려움 | 이탈 직전 행동 패턴을 분석하세요. "마지막으로 뭘 했나?" |
| 5단계 | 개선 시뮬레이션 어려움 | "이탈률을 X% 줄이면 연간 매출 Y 증가"로 임팩트 계산 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 리텐션 분석 대시보드와 이탈 예측 모델을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
리텐션은 매주 모니터링해야 합니다. 자동 코호트 분석과 이탈 예측 알림이 있으면 조기 대응이 가능합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 코호트 리텐션 분석

```python
# cohort_retention_analyzer.py
import pandas as pd
import numpy as np
from datetime import datetime, timedelta
from scipy.stats import pearsonr, spearmanr
import matplotlib.pyplot as plt
import seaborn as sns

class CohortRetentionAnalyzer:
    """코호트 기반 리텐션 분석"""

    def __init__(self, events_df: pd.DataFrame):
        """
        events_df columns:
        - user_id
        - event_date
        - event_name (ai_feature_execution, ai_result_feedback 등)
        - trust_score (optional)
        - plan (Free/Starter/Pro/Enterprise)
        """
        self.events = events_df
        self.cohorts = None
        self.retention_matrix = None

    def create_cohorts(self, cohort_period: str = "weekly"):
        """
        코호트 생성 (첫 사용 기준)
        cohort_period: "daily", "weekly", "monthly"
        """
        # 사용자별 첫 사용 날짜
        first_use = self.events.groupby('user_id').agg({
            'event_date': 'min',
            'plan': 'first',
            'trust_score': lambda x: x.iloc[0] if len(x) > 0 else None
        }).reset_index()

        first_use.columns = ['user_id', 'first_use_date', 'plan', 'initial_trust_score']

        # 코호트 정의
        if cohort_period == "weekly":
            first_use['cohort'] = first_use['first_use_date'].dt.to_period('W')
        elif cohort_period == "monthly":
            first_use['cohort'] = first_use['first_use_date'].dt.to_period('M')
        else:
            first_use['cohort'] = first_use['first_use_date']

        self.cohorts = first_use
        return self.cohorts

    def calculate_retention_matrix(self):
        """
        리텐션 행렬 계산
        행: 코호트, 열: 경과 일 (D0, D7, D14, D30, D90)
        """
        cohort_data = self.cohorts.copy()

        # 각 사용자의 활동 날짜 추출
        user_activity = self.events.groupby('user_id')['event_date'].apply(set).reset_index()
        cohort_data = cohort_data.merge(user_activity, on='user_id', how='left')
        cohort_data.columns = list(cohort_data.columns[:-1]) + ['activity_dates']

        # 경과 일 계산
        cohort_data['cohort_date'] = cohort_data['first_use_date'].dt.date

        retention_days = [0, 7, 14, 30, 90]
        for days in retention_days:
            if days == 0:
                cohort_data[f'D{days}'] = 1
            else:
                cohort_data[f'D{days}'] = cohort_data.apply(
                    lambda row: 1 if any(
                        d >= row['cohort_date'] + timedelta(days=days) and
                        d < row['cohort_date'] + timedelta(days=days+1)
                        for d in row['activity_dates']
                    ) else 0,
                    axis=1
                )

        # 코호트별 리텐션 계산
        retention_matrix = cohort_data.groupby('cohort')[
            ['D0', 'D7', 'D14', 'D30', 'D90']
        ].agg('sum')

        # 백분율로 변환
        retention_matrix = retention_matrix.div(retention_matrix['D0'], axis=0) * 100

        self.retention_matrix = retention_matrix
        return retention_matrix

    def retention_by_trust_score(self) -> pd.DataFrame:
        """신뢰도 점수별 리텐션 분석"""
        if 'trust_score' not in self.cohorts.columns:
            return None

        # 신뢰도 구간 정의
        def trust_category(score):
            if score >= 8.0:
                return "High (8.0-10)"
            elif score >= 6.0:
                return "Medium (6.0-7.9)"
            elif score >= 4.0:
                return "Low (4.0-5.9)"
            else:
                return "Very Low (<4.0)"

        cohort_trust = self.cohorts.copy()
        cohort_trust['trust_category'] = cohort_trust['initial_trust_score'].apply(trust_category)

        # 각 신뢰도 구간별 D7, D30 리텐션
        retention_by_trust = []
        for category in ["High (8.0-10)", "Medium (6.0-7.9)", "Low (4.0-5.9)", "Very Low (<4.0)"]:
            subset = cohort_trust[cohort_trust['trust_category'] == category]

            if len(subset) > 0:
                # D7 리텐션 계산
                d7_users = subset.merge(
                    self.events[(self.events['event_date'] <= datetime.now()) &
                               (self.events['event_date'] >= datetime.now() - timedelta(days=7))],
                    on='user_id',
                    how='inner'
                )
                d7_retention = len(d7_users.drop_duplicates('user_id')) / len(subset) * 100

                retention_by_trust.append({
                    "trust_category": category,
                    "sample_size": len(subset),
                    "d7_retention": d7_retention,
                    "avg_trust_score": subset['initial_trust_score'].mean(),
                })

        return pd.DataFrame(retention_by_trust)

    def retention_by_segment(self, segment_col: str = "plan") -> pd.DataFrame:
        """세그먼트별 리텐션 분석"""
        segment_retention = []

        for segment in self.cohorts[segment_col].unique():
            segment_users = self.cohorts[self.cohorts[segment_col] == segment]['user_id'].values

            # D7 리텐션
            d7_active = self.events[
                (self.events['user_id'].isin(segment_users)) &
                (self.events['event_date'] >= datetime.now() - timedelta(days=7))
            ]['user_id'].nunique()

            d7_retention = (d7_active / len(segment_users) * 100) if len(segment_users) > 0 else 0

            # D30 리텐션
            d30_active = self.events[
                (self.events['user_id'].isin(segment_users)) &
                (self.events['event_date'] >= datetime.now() - timedelta(days=30))
            ]['user_id'].nunique()

            d30_retention = (d30_active / len(segment_users) * 100) if len(segment_users) > 0 else 0

            segment_retention.append({
                "segment": segment,
                "cohort_size": len(segment_users),
                "d7_retention": d7_retention,
                "d30_retention": d30_retention,
                "d7_d30_decay": d7_retention - d30_retention,
            })

        return pd.DataFrame(segment_retention)

    def trust_retention_correlation(self) -> dict:
        """신뢰도와 리텐션의 상관계수 계산"""
        if 'trust_score' not in self.cohorts.columns or self.cohorts['initial_trust_score'].isna().all():
            return None

        # 각 사용자의 D30 리텐션 여부
        cohort_data = self.cohorts.copy()
        d30_threshold = datetime.now() - timedelta(days=30)

        cohort_data['d30_retained'] = cohort_data['user_id'].apply(
            lambda uid: 1 if any(
                d >= d30_threshold
                for d in self.events[self.events['user_id'] == uid]['event_date'].values
            ) else 0
        )

        # 상관계수 계산
        valid_data = cohort_data.dropna(subset=['initial_trust_score', 'd30_retained'])

        if len(valid_data) > 10:
            pearson_corr, pearson_p = pearsonr(valid_data['initial_trust_score'], valid_data['d30_retained'])
            spearman_corr, spearman_p = spearmanr(valid_data['initial_trust_score'], valid_data['d30_retained'])

            return {
                "pearson_correlation": pearson_corr,
                "pearson_p_value": pearson_p,
                "spearman_correlation": spearman_corr,
                "spearman_p_value": spearman_p,
                "interpretation": "Strong positive correlation (신뢰도 높을수록 리텐션 높음)" if pearson_corr > 0.5 else "Moderate correlation"
            }
        return None

    def generate_report(self) -> str:
        """코호트 리텐션 리포트 생성"""
        self.create_cohorts()
        self.calculate_retention_matrix()

        report = f"""
# 코호트 리텐션 분석 리포트
생성일: {datetime.now().strftime('%Y-%m-%d %H:%M UTC')}

## 1. 전체 리텐션 행렬

{self.retention_matrix.to_markdown()}

## 2. 신뢰도별 리텐션
{self.retention_by_trust_score().to_markdown() if self.retention_by_trust_score() is not None else "신뢰도 데이터 없음"}

## 3. 세그먼트별 리텐션
{self.retention_by_segment().to_markdown()}

## 4. 신뢰도-리텐션 상관관계
{self._format_correlation(self.trust_retention_correlation())}

## 5. 인사이트 및 액션
- 리텐션 추이: {self._interpret_retention_trend()}
- 주요 위험 신호: {self._identify_risks()}
- 추천 액션: {self._recommend_actions()}
"""
        return report

    def _format_correlation(self, corr_dict) -> str:
        if corr_dict is None:
            return "신뢰도-리텐션 상관 데이터 부족"

        return f"""
Pearson Correlation: {corr_dict['pearson_correlation']:.3f} (p={corr_dict['pearson_p_value']:.4f})
Spearman Correlation: {corr_dict['spearman_correlation']:.3f} (p={corr_dict['spearman_p_value']:.4f})

해석: {corr_dict['interpretation']}
"""

    def _interpret_retention_trend(self) -> str:
        if self.retention_matrix is None:
            return "데이터 부족"

        latest_cohort = self.retention_matrix.iloc[-1]
        d7_to_d30_change = latest_cohort['D30'] - latest_cohort['D7']

        if d7_to_d30_change > -10:
            return "안정적 (양호)"
        elif d7_to_d30_change > -20:
            return "중간 (주의 필요)"
        else:
            return "악화 (긴급 개선 필요)"

    def _identify_risks(self) -> str:
        segment_ret = self.retention_by_segment()
        worst_segment = segment_ret.loc[segment_ret['d30_retention'].idxmin()]

        return f"{worst_segment['segment']} 플랜: D30 {worst_segment['d30_retention']:.1f}% (매우 저조)"

    def _recommend_actions(self) -> str:
        trust_ret = self.retention_by_trust_score()
        if trust_ret is None:
            return "신뢰도 데이터 부족"

        low_trust_ret = trust_ret[trust_ret['trust_category'] == "Low (4.0-5.9)"]

        if len(low_trust_ret) > 0 and low_trust_ret.iloc[0]['d7_retention'] < 15:
            return "신뢰도 낮은 사용자 대상 모델 정확도 개선 우선"
        else:
            return "세그먼트별 맞춤형 온보딩 강화"


# 사용 예시
if __name__ == "__main__":
    # 데이터 로드
    # events_df = pd.read_csv("events.csv")
    # analyzer = CohortRetentionAnalyzer(events_df)
    # report = analyzer.generate_report()
    # print(report)
    pass
```

### SQL 쿼리 (자동화)

```sql
-- 1. 코호트 리텐션 행렬
CREATE OR REPLACE VIEW v_cohort_retention_matrix AS
WITH cohorts AS (
  SELECT
    user_id,
    DATE_TRUNC('week', MIN(event_date)) as cohort_week,
    MIN(event_date)::date as first_use_date
  FROM events
  WHERE event_name = 'ai_feature_execution'
  GROUP BY user_id
),
retention_data AS (
  SELECT
    c.cohort_week,
    c.user_id,
    MAX(CASE WHEN EXTRACT(DAY FROM e.event_date - c.first_use_date) < 7 THEN 1 ELSE 0 END) as d7,
    MAX(CASE WHEN EXTRACT(DAY FROM e.event_date - c.first_use_date) < 30 THEN 1 ELSE 0 END) as d30,
    MAX(CASE WHEN EXTRACT(DAY FROM e.event_date - c.first_use_date) < 90 THEN 1 ELSE 0 END) as d90
  FROM cohorts c
  LEFT JOIN events e ON c.user_id = e.user_id
    AND e.event_name = 'ai_feature_execution'
    AND e.event_date >= c.first_use_date
  GROUP BY c.cohort_week, c.user_id
)
SELECT
  rd.cohort_week,
  COUNT(DISTINCT rd.user_id) as cohort_size,
  ROUND(100.0 * COUNT(CASE WHEN rd.d7 = 1 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d7_retention,
  ROUND(100.0 * COUNT(CASE WHEN rd.d30 = 1 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d30_retention,
  ROUND(100.0 * COUNT(CASE WHEN rd.d90 = 1 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d90_retention
FROM retention_data rd
GROUP BY rd.cohort_week
ORDER BY rd.cohort_week DESC;

-- 2. 신뢰도별 리텐션
CREATE OR REPLACE VIEW v_trust_retention AS
WITH first_use_trust AS (
  SELECT
    user_id,
    trust_score,
    CASE
      WHEN trust_score >= 8.0 THEN 'High (8.0-10)'
      WHEN trust_score >= 6.0 THEN 'Medium (6.0-7.9)'
      WHEN trust_score >= 4.0 THEN 'Low (4.0-5.9)'
      ELSE 'Very Low (<4.0)'
    END as trust_category
  FROM (
    SELECT
      user_id,
      trust_score,
      ROW_NUMBER() OVER (PARTITION BY user_id ORDER BY event_date) as rn
    FROM events
    WHERE event_name = 'ai_feature_execution' AND trust_score IS NOT NULL
  )
  WHERE rn = 1
),
retention_flags AS (
  SELECT
    fut.user_id,
    fut.trust_category,
    COUNT(*) > 0 as retained_d7,
    COUNT(*) FILTER (WHERE event_date >= NOW() - INTERVAL 30 DAY) > 0 as retained_d30
  FROM first_use_trust fut
  JOIN events e ON fut.user_id = e.user_id
    AND e.event_name = 'ai_feature_execution'
  GROUP BY fut.user_id, fut.trust_category
)
SELECT
  trust_category,
  COUNT(*) as sample_size,
  ROUND(100.0 * COUNT(CASE WHEN retained_d7 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d7_retention,
  ROUND(100.0 * COUNT(CASE WHEN retained_d30 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d30_retention
FROM retention_flags
GROUP BY trust_category
ORDER BY trust_category;

-- 3. 세그먼트별 리텐션
CREATE OR REPLACE VIEW v_segment_retention AS
WITH user_cohorts AS (
  SELECT
    user_id,
    u.plan,
    MIN(e.event_date) as first_use_date
  FROM events e
  JOIN users u ON e.user_id = u.id
  WHERE e.event_name = 'ai_feature_execution'
  GROUP BY e.user_id, u.plan
),
segment_retention AS (
  SELECT
    uc.plan,
    uc.user_id,
    COUNT(DISTINCT CASE WHEN e.event_date >= uc.first_use_date AND e.event_date < uc.first_use_date + INTERVAL 7 DAY THEN 1 END) as active_d7,
    COUNT(DISTINCT CASE WHEN e.event_date >= uc.first_use_date AND e.event_date < uc.first_use_date + INTERVAL 30 DAY THEN 1 END) as active_d30
  FROM user_cohorts uc
  LEFT JOIN events e ON uc.user_id = e.user_id
    AND e.event_name = 'ai_feature_execution'
  GROUP BY uc.plan, uc.user_id
)
SELECT
  plan,
  COUNT(*) as cohort_size,
  ROUND(100.0 * COUNT(CASE WHEN active_d7 > 0 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d7_retention,
  ROUND(100.0 * COUNT(CASE WHEN active_d30 > 0 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as d30_retention
FROM segment_retention
GROUP BY plan
ORDER BY d30_retention DESC;
```

### Claude Code CLI 활용

```bash
# 1. 코호트 리텐션 분석 실행
claude code run analyze-cohort-retention \
  --db-url postgresql://metrics:***@db.prod/analytics \
  --cohort-period weekly \
  --lookback-days 90 \
  --output cohort-retention-report.md

# 2. 신뢰도-리텐션 상관 분석
claude code run analyze-trust-retention-correlation \
  --db-url postgresql://metrics:***@db.prod/analytics \
  --segment-by plan,region \
  --output trust-retention-analysis.json

# 3. 주간 리텐션 대시보드 갱신
claude code run update-retention-dashboard \
  --dashboard-url https://metabase.company.com/dashboards/retention \
  --schedule "every Monday 9am"

# 4. 리텐션 저하 경고 설정
claude code run setup-retention-alerts \
  --threshold-d7 35 \
  --threshold-d30 20 \
  --alert-channel slack \
  --recipients #product-alerts
```

---

## 📊 실행 결과 예시

### 코호트 리텐션 행렬

```
Cohort Week    | Size | D7 Ret | D30 Ret | D90 Ret | Status
──────────────────────────────────────────────────────────
2026-02-01~07  | 450  | 35%   | 23%    | 15%    | 🟡 중간
2026-02-08~14  | 520  | 30%   | 17%    | 10%    | 🔴 저조
2026-02-15~21  | 480  | 24%   | 12%    | 7%     | 🔴 매우 저조 ⚠️
2026-02-22~28  | 610  | 30%   | 16%    | -      | 🔴 저조
2026-03-01~07  | 580  | 32%   | -      | -      | 🟡 개선 중

Trend Analysis:
- 2/15-21 코호트 급락: D30 리텐션 12% (목표 20% 이상)
- 원인: 2/25 모델 업데이트 후 성능 저하 추정
- 최근 개선: 3/1+ 코호트 D7 32% (회복 추세)
```

### 신뢰도별 리텐션

```
Trust Category    | Sample | D7 Ret | D30 Ret | Correlation
──────────────────────────────────────────────────────────
High (8.0-10)    | 120    | 62%    | 50%     | 강한 양의
Medium (6.0-7.9) | 280    | 38%    | 25%     | 상관계수
Low (4.0-5.9)    | 150    | 12%    | 4%      | r = 0.68
Very Low (<4.0)  | 50     | 4%     | 1%      | p < 0.001

Key Finding:
신뢰도 높은 사용자(8+) D30 리텐션 50%
신뢰도 낮은 사용자(4-5) D30 리텐션 4%
= 12배 이상 차이

→ 리텐션 개선 = 신뢰도 개선이 최우선
```

### 세그먼트별 리텐션

```
Plan Type  | Cohort Size | D7 Ret | D30 Ret | Decay | Trend
──────────────────────────────────────────────────────────
Enterprise | 180         | 55%    | 45%     | -10pp | ↗️ 우수
Pro        | 520         | 38%    | 28%     | -10pp | → 중간
Starter    | 780         | 20%    | 12%     | -8pp  | ↘️ 위험
Free       | 1200        | 8%     | 3%      | -5pp  | ⛔ 심각

Action Plan:
1. Enterprise: 유지/심화 (추가 기능)
2. Pro: 신뢰도 강화 (모델 개선)
3. Starter: 온보딩 재설계 + Freemium 모델 검토
4. Free: Free→Pro 전환 유도 또는 폐지 검토
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 리텐션 커브에서 '안정화 구간(flattening point)'이 보이는지 확인하세요 — 안정화 없이 계속 떨어지면 Product-Market Fit이 없는 것입니다
2. **[논쟁 지점]** 리텐션 기준을 D1(일간)으로 볼지 W1(주간)으로 볼지는 제품 사용 주기에 따라 다릅니다
3. **[자기 검증]** 리텐션 분석에서 가장 높은 이탈 구간(예: D3-D7)의 사용자 10명의 행동 로그를 직접 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|------|-----------|------|
| ✅ 코호트 리텐션 데이터 | `ai-adoption-metrics.md` | "리텐션 저하의 원인이 신뢰도인지 확인" |
| ✅ 세그먼트별 성과 | `ab-test-design.md` | "리텐션 낮은 세그먼트를 위한 A/B 테스트" |
| ✅ 리텐션 개선 계획 | `communicate/stakeholder-alignment.md` | "리텐션 개선 방안을 팀에 설명" |
| 🔜 자동화 대시보드 | Claude Code `--weekly-retention-sync` | SQL + Python 자동화 |
