# 📊 AI 기능 채택 메트릭 (AI Adoption Metrics)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 45분+ (Build)
> 워크플로우: → `ab-test-design.md` → `retention-analysis.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 기능을 출시했지만 실제로 사용자들이 얼마나 채택하고 신뢰하는지 측정할 수 없다. 일반적인 SaaS 메트릭 (DAU, Signup)은 AI 특화 메트릭을 놓친다. **AI 기능의 활성화율, 신뢰도, 의존도를 정량적으로 측정하는 방법이 필요하다.**

---

## 📥 이전 프롬프트에서 받는 입력

> `prd-for-ai-feature.md`에서 출시된 AI 기능의 성과를 측정할 때 연결됩니다.

이전 프롬프트 결과에서 **기능명, 출시일, 성공 기준, 타겟 사용자**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 AI 기능의 핵심 도입 메트릭을 정의할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI PM 메트릭 전문가다.

{제품명} 의 AI 기능({기능명})에 대해:
1. 활성화율(Activation Rate): 가입한 사용자 중 AI 기능을 처음 사용한 비율
2. 피처 채택율(Feature Adoption): 월 활성 사용자 중 이 기능을 사용하는 %
3. AI 신뢰도(AI Trust Score): 사용자의 AI 결과에 대한 신뢰도 (1-10)
4. 의존도(Dependency Rate): "이 AI 기능 없이는 못 쓸 것 같다" 응답 비율
5. 재사용률(Repeat Usage): 처음 사용 후 7일/30일 재사용률

각 메트릭의:
- 정의 (명확한 한국어)
- 측정 방법 (어떤 이벤트/쿼리?)
- 목표치 (좋음/보통/나쁨)
- 해석 (수치가 올라가면 뭘 의미하는가?)

을 제시하세요.
```

💡 **Quick Tips:**
- AI 기능은 "신뢰도"라는 일반 기능과 다른 메트릭이 필요
- 첫 3개 메트릭으로 시작해서 점진적으로 추가
- 데이터 엔지니어와 함께 이벤트 정의 (Activation은 "첫 실행" vs "결과 확인"?)


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| AI 기능이 아직 출시 전 | 출시 전에 베이스라인 메트릭을 먼저 설정하세요. 출시 후 비교 기준이 됩니다 |
| 메트릭이 너무 많음 | North Star 메트릭 1개 + 보조 메트릭 3개로 집중하세요 |
| 데이터 수집이 안 됨 | 이벤트 트래킹부터 설정하세요. 메트릭은 데이터 없으면 무의미 |
| AI 성능과 사용자 만족 차이 | 모델 정확도 ≠ 사용자 만족. 둘 다 측정해야 합니다 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — AI 기능의 도입률, 사용률, 영향도를 체계적으로 측정하고 싶은 분입니다.
"AI 기능이 정말 효과가 있나?"를 증명하고 싶다면 이걸 써보세요.

### 📌 진행 방식

이 프롬프트는 **5단계 CoT(Chain of Thought)** 구조입니다. 두 가지 방식으로 쓸 수 있습니다:

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

당신은 **AI 제품 메트릭 아키텍트**이다. 당신의 역할:

1. **AI 특화 메트릭 설계**: 일반 SaaS 메트릭과 AI 제품만의 차이를 이해
   - 일반 메트릭: 누가 썼는가? (DAU, MAU)
   - AI 메트릭: AI를 얼마나 잘 썼는가? (정확도, 신뢰도, 의존도)

2. **인과관계 파악**: 메트릭 간의 인과 체인 이해
   - 활성화 → 채택 → 신뢰도 → 의존도 → 리텐션

3. **프로덕트 팀 가이드**: 데이터 수집 방법과 해석 방법을 팀에 설명 가능해야 함

<!-- 💬 왜 AI 제품은 신뢰도가 중요할까?
일반 기능(예: 필터링)은 "작동한다/안 한다" 이분법이지만, AI 기능은 "정확성이 떨어질 수 있다"는 불확실성이 있다. 따라서 사용자의 AI에 대한 신뢰도(신뢰하는가? 결과를 믿고 액션하는가?)가 채택과 리텐션의 가장 중요한 지표다. -->

### 목표

최종 아웃풋:
- **AI 채택 메트릭 프레임워크** (5개 메트릭, 정의 + 측정 방법 + 해석)
- **대시보드 설계** (주 1회 리포팅할 메트릭 선택)
- **데이터 이벤트 스키마** (개발팀이 구현할 이벤트 명세)

### Reasoning Strategy

<!-- 💬 AI 기능의 생명주기를 먼저 설계해야 왜 필요한가?
사용자가 AI 기능을 경험하는 순간들:
1. 발견 (Discover) → 활성화
2. 첫 사용 (Try) → 피처 채택
3. 결과 평가 (Evaluate) → 신뢰도 형성
4. 반복 (Repeat) → 의존도 증가
5. 추천 (Advocate) → NPS

각 단계마다 어떤 메트릭을 추적할지 명확히 하면, 메트릭 간의 인과관계가 보인다.
-->

**Step 1: AI 기능의 생명주기 정의**

<!-- 💬 [전문가의 눈] AI 기능의 생명주기가 일반 기능과 다른 이유:
일반 기능: 발견 → 사용 → 정착 (한 방향)
AI 기능: 발견 → 사용 → 신뢰도 평가 → 재사용 또는 포기 (순환)
신뢰도가 떨어지면 사용자는 즉시 떠난다. 따라서 "신뢰도 형성 시점"을 정확히 파악해야 한다.
-->

- 사용자가 이 AI 기능을 경험하는 순간들을 시간순으로 나열
- 각 순간마다 "성공"의 정의가 뭔지 기술
- 예) Copilot의 생명주기:
  1. 발견 (검색 UI에서 Copilot 버튼 보임)
  2. 활성화 (첫 쿼리 입력 → AI 결과 수신)
  3. 평가 (사용자가 결과를 "좋음"/"나쁨" 피드백 또는 편집)
  4. 반복 (일주일 내 다시 사용)

**Step 2: 메트릭 역공학**
- 각 단계의 성공 조건을 "측정 가능한" 형태로 변환
- 활성화 = {사용자 수} ÷ {가입자 수} × 100%
- 신뢰도 = NPS + 사용자 피드백 + "결과를 액션한 비율"

**Step 3: 데이터 수집 전략**
- 프로덕트 이벤트 (클라이언트 측: 버튼 클릭, 텍스트 입력 등)
- 서버 이벤트 (서버 측: API 호출, 모델 응답 시간, 에러율 등)
- 설문 (주간/월간 신뢰도, 만족도 설문)
- 행동 데이터 (편집 비율, 공유 비율, "다시 사용" 비율)

**Step 4: 목표치 설정**
- 벤치마크: 업계 표준 또는 경쟁사 (Copilot, ChatGPT 통합 제품 등)
- 내부 목표: 제품 로드맵 (3개월 후 달성할 목표)

<!-- 💬 목표치는 어디서 나오는가?
1. 벤치마킹: Intercom, Slack, Notion 같은 AI 도입 기업의 공개 사례 연구
2. 코호트 분석: 초기 사용자 그룹의 메트릭을 보고, "초기 20%는 50% 채택율"이면, "3개월 후 전체 30% 채택"이 현실적 목표
3. AI 산업 표준: 생성형 AI 기능의 평균 활성화율은 15-25% (대부분 시도하지만 대부분 포기함)
-->

### 핵심 메트릭 상세 설계

#### 메트릭 #1: Activation Rate (활성화율)

**정의:**
```
(처음 AI 기능을 실행한 사용자 수) ÷ (AI 기능이 출시된 후 가입한 사용자) × 100%
```

**측정 방법:**
- 이벤트: `ai_feature_first_run` (사용자가 첫 번째로 버튼 클릭하고 결과를 받은 순간)
- SQL:
  ```sql
  SELECT
    COUNT(DISTINCT user_id) as activated_users,
    COUNT(DISTINCT registration_date) as total_users,
    ROUND(100.0 * COUNT(DISTINCT user_id) / COUNT(DISTINCT registration_date), 2) as activation_rate
  FROM events
  WHERE event_name = 'ai_feature_first_run'
    AND event_date > '2026-03-01'
  ```

**목표치:**
- 🟢 좋음: 25% 이상 (사용자 4명 중 1명 이상 시도)
- 🟡 보통: 10-25%
- 🔴 나쁨: 10% 미만 (발견 문제 또는 UX 마찰)

**해석:**
- 활성화율이 낮으면 → 발견 문제 (사용자가 기능을 못 찾음) 또는 오너보딩 실패
- 활성화율이 높지만 채택율이 낮으면 → 신뢰도/성능 문제

#### 메트릭 #2: Feature Adoption Rate (피처 채택율)

**정의:**
```
(한 달에 AI 기능을 1회 이상 사용한 월 활성 사용자) ÷ (전체 월 활성 사용자) × 100%
```

**측정 방법:**
- 이벤트: `ai_feature_execution` (결과를 성공적으로 생성한 순간)
- SQL:
  ```sql
  WITH monthly_active = (
    SELECT COUNT(DISTINCT user_id) as mau_total
    FROM events
    WHERE event_date >= DATE_TRUNC('month', CURRENT_DATE)
  ),
  ai_adopters = (
    SELECT COUNT(DISTINCT user_id) as ai_mau
    FROM events
    WHERE event_name = 'ai_feature_execution'
      AND event_date >= DATE_TRUNC('month', CURRENT_DATE)
  )
  SELECT
    ROUND(100.0 * ai_adopters.ai_mau / monthly_active.mau_total, 2) as adoption_rate
  FROM monthly_active, ai_adopters
  ```

**목표치:**
- 🟢 좋음: 30% 이상 (활성 사용자의 1/3이 이 기능을 정기 사용)
- 🟡 보통: 15-30%
- 🔴 나쁨: 15% 미만 (니치 기능 또는 구현 문제)

**해석:**
- 채택율이 활성화율보다 훨씬 낮으면 → 첫 경험 후 신뢰도 상실
- 채택율이 안정적으로 유지되면 → AI 기능이 워크플로우에 통합됨

#### 메트릭 #3: AI Trust Score (신뢰도 점수)

<!-- 💬 [논쟁 지점] Trust Score를 정의하는 방식은 팀마다 다르다.
학파 1: "설문 점수만 사용" → 명확하지만 응답율 낮음
학파 2: "행동 데이터만 사용" → 세밀하지만 편향 가능성
최적 방식: 둘 다 수집하고, 격차가 크면 그 이유를 조사 (신뢰도와 실제 행동의 괴리)
한국 사용자: 명시적 신뢰도(설문)를 매우 중시 → 월간 NPS 조사 병행 권장
-->

**정의:**
```
AI 기능의 결과에 대한 사용자 신뢰도 (1-10 스케일)
= (명시적 신뢰도 점수 + 암묵적 신뢰도) / 2
```

**측정 방법:**

**명시적 신뢰도** (설문):
- 월간 인앱 설문: "이 AI의 결과를 얼마나 신뢰하시나요?" (1-10)
- 응답 샘플링: 전체 사용자의 5-10%에게 설문 제시
- 목표: 500+ 응답 / 월

**암묵적 신뢰도** (행동):
```sql
SELECT
  user_id,
  ROUND(100.0 * edits_after_ai_result / total_ai_results, 2) as editing_rate,
  ROUND(100.0 * shares_after_ai_result / total_ai_results, 2) as sharing_rate,
  ROUND(100.0 * accepts_without_edit / total_ai_results, 2) as accept_rate
FROM user_ai_behavior
```

- 편집율: AI 결과를 받은 후 사용자가 편집한 비율 (낮을수록 신뢰 높음)
- 공유율: AI 결과를 팀에 공유한 비율 (높을수록 신뢰 높음)
- 수락율: AI 결과를 그대로 수락한 비율 (높을수록 신뢰 높음, 단 산업별로 다름)

**목표치:**
- 🟢 좋음: 7.5/10 이상 (신뢰도 75%)
- 🟡 보통: 6.0-7.5
- 🔴 나쁨: 6.0 미만 (기능이 신뢰받지 못함)

**해석:**
- 신뢰도가 낮으면 → AI 모델 정확도 개선 또는 불확실성 표시 필요
- 신뢰도는 높지만 채택율이 낮으면 → 발견/접근성 문제

#### 메트릭 #4: Dependency Rate (의존도율)

**정의:**
```
"이 AI 기능이 없으면 업무 효율이 크게 떨어질 것 같다"고 응답한 사용자 비율
```

**측정 방법:**

**설문 기반** (월간):
```
Q. 이 AI 기능에 얼마나 의존하고 있나요?
1. 없어도 상관없음 (의존 안함)
2. 편하지만 있어도 되고 없어도 됨
3. 자주 쓰긴 하는데 필수는 아님
4. 이 기능이 없으면 업무 효율이 크게 떨어짐 (의존함)

의존도율 = (응답 3 + 응답 4) / 전체 응답 × 100%
```

**행동 기반**:
```sql
-- 1주일 사용 중단 후 "다시 활용" 여부
SELECT
  ROUND(100.0 * COUNT(DISTINCT CASE WHEN days_since_last_use > 7 AND active_again = 1 THEN user_id END)
    / COUNT(DISTINCT user_id), 2) as dependency_churn_rate
FROM user_ai_sessions
WHERE ai_sessions > 5
```

**목표치:**
- 🟢 좋음: 40% 이상 (정기 사용자의 40% 이상이 의존함 = 필수 기능화)
- 🟡 보통: 20-40%
- 🔴 나쁨: 20% 미만 (선택 기능 = 리텐션 낮음)

**해석:**
- 의존도가 높으면 → AI 기능이 코어 워크플로우에 통합됨 (큰 성공 신호)
- 의존도가 낮으면 → 니치 기능 또는 니즈 재검토 필요

#### 메트릭 #5: 7-Day Repeat Usage Rate (7일 재사용률)

<!-- 💬 [자기 검증] 재사용율을 측정한 후 꼭 확인할 사항:
1. "재사용"의 정의가 명확한가? (버튼 클릭? 결과 확인? 결과 사용?)
2. 코호트별 재사용율이 서로 다른가? (신규 vs 기존, Free vs Pro)
3. 재사용율과 신뢰도의 상관관계는? (신뢰도 높을수록 재사용 많은가?)
한국 시장: 초보자와 파워유저의 재사용율 격차가 큰 경향 → 세그먼트 분석 필수
-->

**정의:**
```
(첫 사용 후 7일 이내에 다시 사용한 사용자) ÷ (처음 사용한 사용자) × 100%
```

**측정 방법:**
```sql
WITH first_usage AS (
  SELECT
    user_id,
    MIN(event_date) as first_use_date
  FROM events
  WHERE event_name = 'ai_feature_execution'
  GROUP BY user_id
),
repeat_usage AS (
  SELECT
    user_id,
    MIN(event_date) as second_use_date
  FROM events
  WHERE event_name = 'ai_feature_execution'
  GROUP BY user_id
  HAVING MIN(event_date) > first_usage.first_use_date
    AND MIN(event_date) <= first_usage.first_use_date + INTERVAL 7 DAY
)
SELECT
  ROUND(100.0 * COUNT(DISTINCT repeat_usage.user_id) / COUNT(DISTINCT first_usage.user_id), 2) as repeat_rate
FROM first_usage
LEFT JOIN repeat_usage ON first_usage.user_id = repeat_usage.user_id
```

**목표치:**
- 🟢 좋음: 35% 이상 (사용자 1/3이 7일 내 재사용 = 습관화 시작)
- 🟡 보통: 20-35%
- 🔴 나쁨: 20% 미만 (일회성 시도 = 가치 미달 또는 모델 성능 문제)

**해석:**
- 7일 재사용율이 높으면 → 사용자가 기능의 가치를 빨리 인식
- 30일 재사용율도 함께 추적 (28-30% 유지 = 건강한 코호트)

### 대시보드 설계

<!-- 💬 [전문가의 눈] 대시보드 설계 시 "메트릭의 인과관계"를 먼저 그려야 한다.
활성화↓ → 채택↓ → 신뢰도↓ → 재사용↓ → 의존도↓
역방향도 있다: 신뢰도↓ → 채택↓ (활성화 높아도 의미 없음)
따라서 "신뢰도"는 가장 중요한 선행지표 → 대시보드 상단에 배치
-->

**주간 리포팅** (매주 월요일):
```
┌─────────────────────────────────────────────┐
│ AI Feature Adoption Report - Week of 3/10   │
├─────────────────────────────────────────────┤
│ Activation Rate       │ 22% │ ↑3% from last week │
│ Adoption Rate (MAU)   │ 28% │ ↓1% from last week │
│ Trust Score           │ 7.2 │ ↑0.3 from last month │
│ Dependency Rate       │ 35% │ ↑5% from last month │
│ 7-Day Repeat Rate     │ 31% │ ↑2% (good trend)   │
├─────────────────────────────────────────────┤
│ 🔴 Alert: Trust score dropped for Enterprise │
│           segment after model update         │
│ 🟢 Win: Repeat rate in SMB cohort now 40%+  │
└─────────────────────────────────────────────┘
```

**월간 분석** (각 메트릭별 코호트 분석):
- 신규 vs 기존 사용자
- 플랜별 (Free / Starter / Pro)
- 업계별 (Finance / Tech / Healthcare)
- 지역별 (KR / APAC / Global)

💡 **Deep Tips:**
- **데이터 수집**: 이벤트 정의를 먼저 (Analytics / 데이터팀과 함께). "활성화"는 "버튼 클릭"인가 "결과 수신"인가?
- **AI 제품 특화**: AI 기능은 정확도/응답시간도 메트릭으로 추적 (별도 문서: `ai-model-metrics.md`)
- **한국 SaaS 특화**: 한국 사용자는 신뢰도를 매우 중시 (수정/검증율이 높음). "편집율"도 신뢰도 신호로 해석

### 🇰🇷 한국 시장 맥락

```
한국 시장 AI 도입 메트릭 고려사항:

1. **한국어 응답 품질이 핵심 메트릭**:
   - 한국 사용자는 AI가 "한국어를 제대로 이해하는가"를 매우 중시
   - 영어 번역 기반 AI는 거부감 높음
   - Trust Score 측정 시 "한국어 자연스러움" 항목 추가 권장
   - 메트릭: 한국어 응답 품질 (0-10)별 사용률 비교

2. **한국 기업의 AI 도입 허들**:
   - 데이터 주권 우려: "우리 고객 데이터가 해외로 나가는 건 아닌가?" → on-premise/프라이빗 클라우드 선호
   - 사내 보안 정책: 금융/보험/의료 기업은 내부 승인 프로세스 복잡함
   - 결과: Adoption Rate 초반 낮을 수 있음 → 1-2개월 더 긴 추적 필요

3. **한국 시장 벤치마크 데이터 소스**:
   - KISA (한국인터넷진흥원) AI 관련 보고서
   - NIA (정보통신산업진흥원) AI 도입 현황 조사
   - KISDI (정보통신정책연구원) AI 서비스 영향 분석
   - → 경쟁사 메트릭과 직접 비교보다 "한국 산업 평균"과 비교 권장

4. **AI기본법 규제 영향**:
   - 2024년부터 한국의 AI기본법 준수 의무화
   - Trust Score 외에 "규제 준수율" 메트릭 추가 필요 (투명성, 편향 모니터링)
   - 고위험 AI 시스템은 정부 신고 필요 → 메트릭 리포팅 시 정부 보고 양식 고려
```
```


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | North Star 메트릭 선정 어려움 | "이 AI 기능의 성공을 한 문장으로 말하면?"에서 출발 |
| 2단계 | AI 특화 메트릭 모름 | 정확도, 응답 시간, 사용률, 신뢰도 점수가 기본 4대 메트릭 |
| 3단계 | 벤치마크가 없음 | 경쟁사 공개 데이터 또는 산업 평균을 참고하세요 |
| 4단계 | 메트릭이 움직이지 않음 | 세그먼트별로 나눠서 분석하세요. 전체 평균은 숨겨진 패턴을 가립니다 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — AI 도입 메트릭 대시보드를 자동 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
AI 메트릭은 매일/매주 추적해야 합니다. 자동 대시보드가 있으면 트렌드를 놓치지 않습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### 데이터 이벤트 스키마 (개발팀 구현용)

```python
# events.py - Analytics event tracking

class AIFeatureEvents:
    """AI 기능 메트릭 수집용 이벤트"""

    @staticmethod
    def ai_feature_first_run(user_id: str, feature_name: str):
        """
        사용자가 처음으로 AI 기능을 실행하고 결과를 받은 순간
        Event: ai_feature_first_run
        """
        analytics.track(
            event="ai_feature_first_run",
            user_id=user_id,
            properties={
                "feature_name": feature_name,  # e.g., "ai_copilot", "ai_summary"
                "timestamp": datetime.now().isoformat(),
                "plan": user.plan,  # Free / Starter / Pro
                "region": user.region,
            }
        )

    @staticmethod
    def ai_feature_execution(user_id: str, feature_name: str,
                             execution_time_ms: float, error: bool = False):
        """
        AI 기능이 성공적으로 결과를 생성한 순간
        Event: ai_feature_execution
        """
        analytics.track(
            event="ai_feature_execution",
            user_id=user_id,
            properties={
                "feature_name": feature_name,
                "execution_time_ms": execution_time_ms,
                "error": error,
                "model_version": "v2.1",
                "prompt_template": "korean_optimized_v3",
            }
        )

    @staticmethod
    def ai_result_feedback(user_id: str, feature_name: str,
                           feedback_type: str, rating: int = None):
        """
        사용자가 AI 결과에 피드백을 준 순간
        feedback_type: "helpful" / "not_helpful" / "edited" / "shared"
        Event: ai_result_feedback
        """
        analytics.track(
            event="ai_result_feedback",
            user_id=user_id,
            properties={
                "feature_name": feature_name,
                "feedback_type": feedback_type,
                "rating": rating,  # 1-10 if explicit rating
                "edit_distance": None,  # 편집된 텍스트의 레벤슈타인 거리 (optional)
                "shared_with": "team" if feedback_type == "shared" else None,
            }
        )

    @staticmethod
    def ai_result_action(user_id: str, feature_name: str, action: str):
        """
        사용자가 AI 결과에 대해 취한 액션
        action: "accepted" / "edited" / "discarded" / "shared" / "approved"
        Event: ai_result_action
        """
        analytics.track(
            event="ai_result_action",
            user_id=user_id,
            properties={
                "feature_name": feature_name,
                "action": action,
                "time_to_action_seconds": None,  # 결과 수신부터 액션까지 소요 시간
            }
        )
```

### SQL 쿼리 (메트릭 자동화)

```sql
-- 1. Activation Rate Dashboard
CREATE OR REPLACE VIEW v_ai_activation_metrics AS
SELECT
  DATE_TRUNC('week', first_seen) as week,
  COUNT(DISTINCT user_id) as activated_users,
  COUNT(DISTINCT CASE WHEN first_seen >= DATE_TRUNC('week', CURRENT_DATE) - INTERVAL 7 DAY THEN user_id END) as new_activations,
  ROUND(100.0 * COUNT(DISTINCT CASE WHEN first_seen >= DATE_TRUNC('week', CURRENT_DATE) - INTERVAL 7 DAY THEN user_id END)
    / NULLIF(COUNT(DISTINCT user_id), 0), 2) as weekly_growth_rate
FROM (
  SELECT
    user_id,
    MIN(event_date) as first_seen
  FROM events
  WHERE event_name = 'ai_feature_first_run'
  GROUP BY user_id
)
GROUP BY DATE_TRUNC('week', first_seen)
ORDER BY week DESC;

-- 2. Adoption Rate (MAU)
CREATE OR REPLACE VIEW v_ai_adoption_monthly AS
SELECT
  DATE_TRUNC('month', event_date) as month,
  COUNT(DISTINCT user_id) as mau_total,
  COUNT(DISTINCT CASE WHEN event_name = 'ai_feature_execution' THEN user_id END) as ai_mau,
  ROUND(100.0 * COUNT(DISTINCT CASE WHEN event_name = 'ai_feature_execution' THEN user_id END)
    / NULLIF(COUNT(DISTINCT user_id), 0), 2) as adoption_rate
FROM events
WHERE event_date >= DATE_TRUNC('month', CURRENT_DATE) - INTERVAL 12 MONTH
GROUP BY DATE_TRUNC('month', event_date)
ORDER BY month DESC;

-- 3. Trust Score (Implicit)
CREATE OR REPLACE VIEW v_ai_trust_implicit AS
SELECT
  user_id,
  COUNT(*) as total_executions,
  ROUND(100.0 * COUNT(CASE WHEN feedback_type = 'edited' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as editing_rate,
  ROUND(100.0 * COUNT(CASE WHEN feedback_type = 'shared' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as sharing_rate,
  ROUND(100.0 * COUNT(CASE WHEN feedback_type = 'helpful' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as helpful_rate,
  ROUND(100.0 - 100.0 * COUNT(CASE WHEN feedback_type = 'edited' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as trust_score_editing_basis
FROM events
WHERE event_name IN ('ai_feature_execution', 'ai_result_feedback')
GROUP BY user_id;

-- 4. 7-Day Repeat Rate
CREATE OR REPLACE VIEW v_ai_repeat_cohorts AS
WITH first_use AS (
  SELECT
    user_id,
    MIN(event_date) as first_use_date
  FROM events
  WHERE event_name = 'ai_feature_execution'
  GROUP BY user_id
),
repeat_use AS (
  SELECT
    fu.user_id,
    COUNT(DISTINCT e.event_date) as repeat_count
  FROM first_use fu
  JOIN events e ON fu.user_id = e.user_id
    AND e.event_name = 'ai_feature_execution'
    AND e.event_date > fu.first_use_date
    AND e.event_date <= fu.first_use_date + INTERVAL 7 DAY
  GROUP BY fu.user_id
)
SELECT
  fu.first_use_date::date as cohort_date,
  COUNT(DISTINCT fu.user_id) as cohort_size,
  COUNT(DISTINCT ru.user_id) as repeat_users,
  ROUND(100.0 * COUNT(DISTINCT ru.user_id) / NULLIF(COUNT(DISTINCT fu.user_id), 0), 2) as d7_repeat_rate
FROM first_use fu
LEFT JOIN repeat_use ru ON fu.user_id = ru.user_id
GROUP BY fu.first_use_date::date
ORDER BY fu.first_use_date DESC;
```

### Python 자동화 스크립트

```python
# ai_adoption_metrics.py
import pandas as pd
import numpy as np
from datetime import datetime, timedelta
import json

class AIAdoptionAnalyzer:
    """AI 채택 메트릭 자동 분석 및 리포팅"""

    def __init__(self, db_connection):
        self.db = db_connection

    def calculate_all_metrics(self, lookback_days: int = 90):
        """모든 메트릭을 한 번에 계산"""
        metrics = {
            "activation_rate": self.activation_rate(),
            "adoption_rate": self.adoption_rate(),
            "trust_score": self.trust_score(),
            "dependency_rate": self.dependency_rate(),
            "repeat_7day": self.repeat_rate(days=7),
            "repeat_30day": self.repeat_rate(days=30),
            "cohort_analysis": self.cohort_analysis(lookback_days=lookback_days),
            "segment_breakdown": self.segment_breakdown(),
        }
        return metrics

    def activation_rate(self) -> dict:
        """활성화율 계산"""
        query = """
        WITH activations AS (
          SELECT COUNT(DISTINCT user_id) as activated
          FROM events
          WHERE event_name = 'ai_feature_first_run'
            AND event_date >= NOW() - INTERVAL 30 DAY
        ),
        signups AS (
          SELECT COUNT(DISTINCT user_id) as signed_up
          FROM users
          WHERE created_at >= NOW() - INTERVAL 30 DAY
        )
        SELECT
          activations.activated,
          signups.signed_up,
          ROUND(100.0 * activations.activated / NULLIF(signups.signed_up, 0), 2) as rate
        FROM activations, signups
        """
        result = self.db.query(query).iloc[0]
        return {
            "rate": result['rate'],
            "activated_users": result['activated'],
            "total_signups": result['signed_up'],
            "health": "good" if result['rate'] >= 25 else "warning" if result['rate'] >= 10 else "critical"
        }

    def adoption_rate(self) -> dict:
        """채택율 계산 (MAU 기반)"""
        query = """
        WITH mau_total AS (
          SELECT COUNT(DISTINCT user_id) as total_mau
          FROM events
          WHERE event_date >= DATE_TRUNC('month', NOW())
        ),
        mau_ai AS (
          SELECT COUNT(DISTINCT user_id) as ai_mau
          FROM events
          WHERE event_name = 'ai_feature_execution'
            AND event_date >= DATE_TRUNC('month', NOW())
        )
        SELECT
          mau_total.total_mau,
          mau_ai.ai_mau,
          ROUND(100.0 * mau_ai.ai_mau / NULLIF(mau_total.total_mau, 0), 2) as rate
        FROM mau_total, mau_ai
        """
        result = self.db.query(query).iloc[0]
        return {
            "rate": result['rate'],
            "ai_mau": result['ai_mau'],
            "total_mau": result['total_mau'],
            "health": "good" if result['rate'] >= 30 else "warning" if result['rate'] >= 15 else "critical"
        }

    def trust_score(self) -> dict:
        """신뢰도 점수 (암묵적 기반)"""
        query = """
        SELECT
          COUNT(*) as total_executions,
          ROUND(100.0 * COUNT(CASE WHEN feedback_type = 'edited' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as editing_rate,
          ROUND(100.0 * COUNT(CASE WHEN feedback_type = 'helpful' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as helpful_rate,
          ROUND(100.0 * COUNT(CASE WHEN feedback_type = 'shared' THEN 1 END) / NULLIF(COUNT(*), 0), 2) as sharing_rate
        FROM events
        WHERE event_name IN ('ai_feature_execution', 'ai_result_feedback')
          AND event_date >= NOW() - INTERVAL 30 DAY
        """
        result = self.db.query(query).iloc[0]

        # Trust score = 100 - editing_rate (사용자가 덜 수정할수록 신뢰도 높음)
        # + helpful_rate + sharing_rate (긍정적 신호)
        trust_numeric = (100 - result['editing_rate']) * 0.5 + result['helpful_rate'] * 0.25 + result['sharing_rate'] * 0.25
        trust_10scale = trust_numeric / 10

        return {
            "score_10scale": round(trust_numeric / 10, 1),
            "editing_rate": result['editing_rate'],
            "helpful_rate": result['helpful_rate'],
            "sharing_rate": result['sharing_rate'],
            "health": "good" if trust_10scale >= 7.5 else "warning" if trust_10scale >= 6.0 else "critical"
        }

    def dependency_rate(self) -> dict:
        """의존도율 (설문 기반)"""
        query = """
        SELECT
          COUNT(*) as total_responses,
          COUNT(CASE WHEN dependency_score >= 3 THEN 1 END) as dependent_users,
          ROUND(100.0 * COUNT(CASE WHEN dependency_score >= 3 THEN 1 END) / NULLIF(COUNT(*), 0), 2) as rate,
          AVG(dependency_score) as avg_dependency
        FROM user_surveys
        WHERE survey_date >= NOW() - INTERVAL 30 DAY
          AND question_id = 'ai_dependency'
        """
        result = self.db.query(query).iloc[0]
        return {
            "rate": result['rate'],
            "avg_score": round(result['avg_dependency'], 2),
            "responses": result['total_responses'],
            "health": "good" if result['rate'] >= 40 else "warning" if result['rate'] >= 20 else "critical"
        }

    def repeat_rate(self, days: int = 7) -> dict:
        """재사용율 계산"""
        query = f"""
        WITH first_use AS (
          SELECT
            user_id,
            MIN(event_date) as first_use_date
          FROM events
          WHERE event_name = 'ai_feature_execution'
          GROUP BY user_id
        ),
        repeat_use AS (
          SELECT
            fu.user_id
          FROM first_use fu
          JOIN events e ON fu.user_id = e.user_id
            AND e.event_name = 'ai_feature_execution'
            AND e.event_date > fu.first_use_date
            AND e.event_date <= fu.first_use_date + INTERVAL {days} DAY
          GROUP BY fu.user_id
        )
        SELECT
          COUNT(DISTINCT fu.user_id) as total_users,
          COUNT(DISTINCT ru.user_id) as repeat_users,
          ROUND(100.0 * COUNT(DISTINCT ru.user_id) / NULLIF(COUNT(DISTINCT fu.user_id), 0), 2) as rate
        FROM first_use fu
        LEFT JOIN repeat_use ru ON fu.user_id = ru.user_id
        """
        result = self.db.query(query).iloc[0]
        return {
            "days": days,
            "rate": result['rate'],
            "total_users": result['total_users'],
            "repeat_users": result['repeat_users'],
            "health": "good" if result['rate'] >= 35 else "warning" if result['rate'] >= 20 else "critical"
        }

    def cohort_analysis(self, lookback_days: int = 90) -> pd.DataFrame:
        """코호트 분석 (신규 사용자 기준)"""
        query = f"""
        WITH cohorts AS (
          SELECT
            DATE_TRUNC('week', user_created_date) as cohort_week,
            COUNT(DISTINCT user_id) as cohort_size
          FROM users
          WHERE created_at >= NOW() - INTERVAL {lookback_days} DAY
          GROUP BY DATE_TRUNC('week', user_created_date)
        ),
        activations AS (
          SELECT
            DATE_TRUNC('week', u.created_at) as cohort_week,
            COUNT(DISTINCT e.user_id) as activated_in_cohort
          FROM events e
          JOIN users u ON e.user_id = u.id
          WHERE e.event_name = 'ai_feature_first_run'
            AND u.created_at >= NOW() - INTERVAL {lookback_days} DAY
          GROUP BY DATE_TRUNC('week', u.created_at)
        )
        SELECT
          c.cohort_week,
          c.cohort_size,
          a.activated_in_cohort,
          ROUND(100.0 * a.activated_in_cohort / NULLIF(c.cohort_size, 0), 2) as activation_rate
        FROM cohorts c
        LEFT JOIN activations a ON c.cohort_week = a.cohort_week
        ORDER BY c.cohort_week DESC
        """
        return self.db.query(query)

    def segment_breakdown(self) -> dict:
        """세그먼트별 분석 (플랜, 지역, 업계)"""
        return {
            "by_plan": self._analyze_by_plan(),
            "by_region": self._analyze_by_region(),
            "by_industry": self._analyze_by_industry(),
        }

    def generate_weekly_report(self) -> str:
        """주간 리포팅 생성"""
        metrics = self.calculate_all_metrics()

        report = f"""
# AI Feature Adoption Report
Generated: {datetime.now().strftime('%Y-%m-%d %H:%M UTC')}

## Weekly Snapshot

### Activation Rate: {metrics['activation_rate']['rate']}%
- Status: {metrics['activation_rate']['health'].upper()}
- {metrics['activation_rate']['activated_users']} / {metrics['activation_rate']['total_signups']} new users activated

### Feature Adoption (MAU): {metrics['adoption_rate']['rate']}%
- Status: {metrics['adoption_rate']['health'].upper()}
- {metrics['adoption_rate']['ai_mau']} / {metrics['adoption_rate']['total_mau']} active users

### Trust Score: {metrics['trust_score']['score_10scale']}/10
- Status: {metrics['trust_score']['health'].upper()}
- Editing Rate: {metrics['trust_score']['editing_rate']}%
- Helpful Rate: {metrics['trust_score']['helpful_rate']}%

### Dependency Rate: {metrics['dependency_rate']['rate']}%
- Status: {metrics['dependency_rate']['health'].upper()}
- Avg Dependency Score: {metrics['dependency_rate']['avg_score']}/4

### 7-Day Repeat Rate: {metrics['repeat_7day']['rate']}%
- Status: {metrics['repeat_7day']['health'].upper()}

### 30-Day Repeat Rate: {metrics['repeat_30day']['rate']}%

## Cohort Analysis
{metrics['cohort_analysis'].to_markdown()}

## Segment Breakdown
{json.dumps(metrics['segment_breakdown'], indent=2, ensure_ascii=False)}

---
Generated by AI Adoption Metrics System
"""
        return report

# 실행 예시
if __name__ == "__main__":
    # db = connect_to_database()
    # analyzer = AIAdoptionAnalyzer(db)
    # report = analyzer.generate_weekly_report()
    # print(report)
    pass
```

### Claude Code CLI 사용

```bash
# 1. 메트릭 대시보드 자동 생성
claude code run analyze-ai-adoption \
  --db-url postgresql://metrics:***@db.prod.example.com/analytics \
  --output-format slack \
  --recipients #product-analytics

# 2. 주간 리포팅 자동화 (cron)
# crontab -e에 추가:
# 0 9 * * MON /usr/bin/python3 /app/ai_adoption_metrics.py --report weekly --send-slack

# 3. 대시보드 데이터 갱신
claude code run update-metrics-dashboard \
  --metrics activation_rate,adoption_rate,trust_score,dependency_rate,repeat_7day \
  --dashboard-url https://metabase.company.com/dashboards/ai-adoption
```

---

## 📊 실행 결과 예시

### 예시 상황: Slack AI 요약 기능 출시 2개월 차

**제품**: Slack Enterprise Grid + AI Summary 피처
**메트릭 스냅샷** (2026년 3월 현재):

```
┌──────────────────────────────────────────────────────────┐
│ AI Summary Feature - Adoption Metrics Report             │
│ Period: 2026-02-01 to 2026-03-10 (38 days)             │
├──────────────────────────────────────────────────────────┤
│                                                          │
│ 1️⃣  ACTIVATION RATE: 28% ✅                            │
│    └─ 450 / 1,600 new users tried AI Summary           │
│    └─ Trend: ↑4% from week 1 (발견 개선 효과)          │
│                                                          │
│ 2️⃣  FEATURE ADOPTION (MAU): 24% ⚠️                    │
│    └─ 3,200 / 13,400 active users used in past 30 days│
│    └─ Trend: ↓2% from week 2 (신뢰도 문제?)           │
│                                                          │
│ 3️⃣  TRUST SCORE: 6.8/10 ⚠️                            │
│    └─ Explicit: 6.9/10 (설문)                          │
│    └─ Implicit: 6.7/10 (행동)                          │
│    └─ Breakdown:                                        │
│       • Editing Rate: 32% (높음 = 신뢰도 낮음)         │
│       • Helpful Rate: 61% (좋음)                        │
│       • Sharing Rate: 18% (낮음 = 신뢰 안 함)          │
│                                                          │
│ 4️⃣  DEPENDENCY RATE: 22% ⚠️                           │
│    └─ "이 기능 없이는 못 쓸 것 같다": 22%             │
│    └─ "편리하지만 필수는 아님": 48%                    │
│    └─ Interpretation: 아직 필수 기능 아님              │
│                                                          │
│ 5️⃣  REPEAT RATES:                                      │
│    └─ 7-Day:  31% ✅ (코호트 성숙함)                  │
│    └─ 30-Day: 22% (retention 안정적)                   │
│                                                          │
├──────────────────────────────────────────────────────────┤
│ 🔴 CRITICAL: Trust Score < 7.0 = 모델 성능 이슈?     │
│ 🟡 WATCH: Adoption Rate 감소 추세 (주간 -2%)         │
│ 🟢 WIN: New users find feature easily (Activation ↑)   │
│                                                          │
│ NEXT STEPS:                                              │
│ 1. 모델 정확도 분석 (editing rate 감소 목표)            │
│ 2. 신뢰도 개선: "불확실한 부분 표시" 기능 추가         │
│ 3. 세그먼트 분석: Enterprise vs SMB 신뢰도 차이 조사   │
└──────────────────────────────────────────────────────────┘
```

### 코호트 분석 (신규 사용자 기준)

```
Cohort Week    | Cohort Size | Activation Rate | 7-Day Repeat | Trust Score
───────────────────────────────────────────────────────────────────────────
2026-02-02     | 450         | 28%             | 31%          | 6.8
2026-02-09     | 520         | 32%             | 35%          | 7.1 ⬆️
2026-02-16     | 480         | 26%             | 28%          | 6.5 ⬇️
2026-02-23     | 610         | 24%             | 25%          | 6.4 ⬇️
2026-03-02     | 550         | 22%             | ongoing      | ongoing

Insight: 신규 코호트일수록 신뢰도 & 재사용율 감소
→ 최근 모델 업데이트(2/25) 후 정확도 저하? 점검 필요
```

### 세그먼트별 성과

```
Plan Type  | Activation | Adoption | Trust | Dependency | Health
──────────────────────────────────────────────────────────────
Enterprise | 35% ✅     | 32%      | 7.4   | 40% ✅     | STRONG
Pro        | 28%        | 26%      | 6.8   | 25%        | OKAY
Starter    | 18%        | 16%      | 6.2   | 12%        | WEAK
Free       | 8%         | 6%       | 5.1   | 2%         | CRITICAL

Region     | Activation | Adoption | Trust | Dependency
──────────────────────────────────────────────────────────
KR (한국)  | 32% 🇰🇷   | 29%      | 7.1   | 28%
APAC       | 25%        | 22%      | 6.7   | 20%
US/EU      | 27%        | 25%      | 6.9   | 24%

Key Finding: Enterprise & Korea market 리드
→ SMB 시장 진출 전략 필요 (Trust 개선)
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 메트릭에서 'Trust Score(AI 결과 수용률)'가 포함되어 있는지 확인하세요 — AI 기능의 핵심 지표입니다
2. **[논쟁 지점]** AI 채택률을 '활성 사용자 비율'로 볼지 '기능 사용 횟수'로 볼지는 제품 성격에 따라 다릅니다
3. **[자기 검증]** 정의된 메트릭 중 1개를 실제로 측정할 수 있는 데이터 파이프라인이 있는지 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|------|-----------|------|
| ✅ Activation/Adoption/Trust 데이터 | `ab-test-design.md` | "신뢰도가 낮은 세그먼트를 위한 A/B 테스트 설계" |
| ✅ 코호트별 신뢰도 분석 | `retention-analysis.md` | "코호트 리텐션 추적으로 기능 개선 효과 측정" |
| ✅ 메트릭 리포팅 | `communicate/stakeholder-alignment.md` | "메트릭 결과를 경영진/팀에 설명하는 프레임" |
| 🔜 대시보드 구축 | Claude Code `--build-dashboard` | SQL + Metabase 대시보드 자동화 |
