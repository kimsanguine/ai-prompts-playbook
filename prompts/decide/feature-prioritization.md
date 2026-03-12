# 🎯 기능 우선순위 결정 (Feature Prioritization with RICE)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 40분+ (Build)
> 워크플로우: `backlog-prioritization.md` → (이 파일) → `sprint-kickoff.md`

---

## 🎯 이 프롬프트가 해결하는 문제

로드맵은 에픽 단위로 우선순위가 정해졌습니다. 이제 **각 에픽 내에서 어떤 기능을 먼저 빌드할지** 결정해야 합니다.

예를 들어, "멀티채널 지원" 에픽이 선택되었다면:
- 이메일 채널을 먼저 할까, 아니면 Slack을 먼저 할까?
- 기본 기능만 할까, 아니면 고급 기능(자동 분류, 응답 제안)까지 할까?
- 한국 사용자 특화(문자, 카톡)를 포함할까?

**RICE 프레임워크**는 이런 기능 단위 우선순위를 **데이터 기반으로 산정**하는 도구입니다. 특히 AI 제품에서는:
- "정확도 1% 개선"과 "사용자 경험 10% 개선" 중 어떤 게 더 가치 있는가?
- "모델 재학습 속도"와 "UI 사용성" 중 어디에 집중할까?
- "기술적 완벽함"과 "빠른 출시" 중 무엇을 선택할까?

이 프롬프트는 **RICE 점수를 자동화**하면서, AI 제품만의 특수한 상황(모델 정확도 vs 사용자 경험)을 반영합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `problem-framing.md`에서 정의한 문제를 해결하는 기능 후보들의 우선순위를 결정할 때 연결됩니다.

이전 프롬프트 결과에서 **기능 후보 목록, 문제 정의, 비즈니스 목표**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 기능 백로그의 우선순위를 정리할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI 제품의 기능 우선순위 전문가입니다.

다음 기능 목록에 대해 RICE 프레임워크로 우선순위를 매기세요:

{FEATURE_LIST}

각 기능마다:
- R (Reach): 영향 대상 사용자 비율 (%)
- I (Impact): 임팩트 크기 (0.25/0.5/1/2/3)
- C (Confidence): 확신도 (%)
- E (Effort): 예상 노력 (주)

RICE = (R × I × C) / E

우선순위 (높은 점수 순):
1. [기능] RICE: [점수]
2. [기능] RICE: [점수]
...

각 기능별 선택 이유:
```

💡 **Quick Tips:**
- AI 제품의 Reach는 "모든 사용자"가 아니라 "실제로 이 기능을 쓰는 세분화된 사용자"입니다
- Impact는 "얼마나 좋을까"가 아니라 "현재 대비 몇 배 개선"인가입니다 (상대값)
- Confidence가 70% 미만이면 "검증" 기능을 먼저 추가하세요
- AI 팀은 기술 완벽함을 추구하지만, 사용자는 "빠른 배포 + 작은 개선"을 더 선호합니다


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 기능이 너무 많음 (50개+) | 먼저 카테고리로 그룹핑한 후, 카테고리 단위로 우선순위를 매기세요 |
| 평가 기준에 합의가 안 됨 | 팀에서 "가장 중요한 기준 3개"를 먼저 투표로 정하세요 |
| 데이터 없이 추정만 해야 함 | 추정치라도 넣으세요. "없음"보다 "추정 70%"가 낫습니다. 나중에 교정 |
| 경영진이 특정 기능을 밀어붙임 | 프레임워크 결과를 보여주면서 "데이터 기반 의사결정"으로 설득하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — RICE, ICE 등 프레임워크를 활용해 체계적으로 우선순위를 매기고 싶은 분입니다.
"감"이 아닌 "데이터"로 우선순위를 정하고 싶다면 이걸 써보세요.

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


```markdown
# 역할
당신은 AI 제품의 기능 우선순위 전문가이면서,
Product Trio (PM/Designer/Engineer)가 함께 의사결정하도록 돕는 촉진자입니다.

# 목표
{FEATURE_LIST}를 RICE 프레임워크로 정량화하고,
각 기능의 강점과 약점을 명확히 하며,
**"기술적 완벽함 vs 빠른 출시"** 의 트레이드오프를 명시적으로 다루어
팀이 일관된 선택을 하도록 합니다.

<!-- 💬 왜 기능 우선순위가 중요한가?
같은 에픽 내에서도 기능 선택이 성공을 결정합니다.
예: "멀티채널 지원" 에픽에서
- 이메일 + Slack 기본 기능만 (2주) vs
- 이메일 + Slack + 카톡 + 자동 분류 (6주)

후자가 "더 낫다"고 느껴지지만,
빠르게 시장 피드백을 받고 반복하는 첫 번째가
장기적 성공 확률이 높습니다.
-->

# Reasoning Strategy

## Step 1: 기능 목록 정의

### 기능을 작은 단위로 분해
```
나쁜 예: "멀티채널 지원"
좋은 예:
- 이메일 채널 기본 지원 (수신/송신)
- Slack 채널 기본 지원
- 자동 분류 (이메일/Slack 통합)
- 카톡 채널 지원
- 채널별 우선순위 필터링

기능은 **2주 이내에 완료 가능한 크기**여야 합니다.
너무 크면 RICE 점수가 의미가 없습니다.

<!-- 💬 기능 분해의 함정
많은 팀이 "기능"을 에픽 수준으로 정의합니다.
"추천 엔진", "실시간 이상 탐지" 같은 큰 기능은
10-15개의 작은 기능으로 분해해야 합니다.
-->

기능 분해 체크리스트:
- [ ] 각 기능이 2주 안에 완료 가능한가?
- [ ] 기능이 독립적인가? (의존성 최소화)
- [ ] 고객이 단독으로 가치를 느낄 수 있는가?
- [ ] 측정 가능한가? (KPI 정의 가능)
```

## Step 2: Reach (도달 범위) 계산

### 실제 사용자 비율 파악
```
**정의:** 이 기능을 실제로 사용할 것으로 예상되는 사용자 비율

**계산 방법:**

Step 1: 총 사용자 수 파악
- 전체 MAU (Monthly Active User): 예: 10,000명

Step 2: 기능을 사용할 세분화 그룹 파악
- 기능의 대상층 정의
- 예: "이메일 채널" → 이메일로 고객사와 소통하는 CS팀

Step 3: 세분화 그룹 내 채택률 추정
- "이메일 채널이 있으면 CS팀의 몇 %가 사용할 것인가?"
- 보수적: 60% (초기 채택)
- 낙관적: 85% (3-6개월 후)
- 평균: 75%

Step 4: 최종 Reach 계산
- Reach = (세분화 그룹 / 전체 사용자) × (채택률)
- 예: (3,000 CS팀 / 10,000) × 75% = 22.5% → 23%

<!-- 💬 Reach 과소/과대 추정의 함정
팀이 자주 하는 실수:
- 과대 추정: "모든 사용자가 이걸 원한다" (실제 30%)
- 과소 추정: "일부만 쓴다" (실제 60%)

과거 유사 기능의 도입률 데이터를 참고하세요.
데이터 없으면 고객 조사를 먼저 해야 합니다.
-->

**AI 제품별 예시:**

| 기능 | 대상층 | 세분화율 | 예상 채택률 | Reach |
|---|---|---|---|---|
| 자동 응답 (CS용) | CS팀 | 30% | 75% | 22.5% |
| 감정 분석 (관리자용) | 관리자 | 5% | 100% | 5% |
| 실시간 이상 탐지 | Data팀 | 10% | 60% | 6% |
| 배치 분석 (리포트) | PM/Manager | 20% | 80% | 16% |
| 모바일 앱 | 모든 사용자 | 100% | 40% | 40% |

**Korean SaaS 특화 고려:**
- 한국은 문자(SMS), 카톡, 톡톡 등 채널 다양
- 글로벌 기준(이메일)보다 국내 채널이 더 높은 Reach (카톡: 90%)
- 대기업은 보안 규정 때문에 특정 채널만 사용 (예: 이메일만)
```

## Step 3: Impact (임팩트) 측정

### 사용자에게 미치는 가치의 크기
```
**정의:** 영향받는 사용자가 느끼는 가치의 상대적 크기

**점수 기준:**

3 = Massive (사용자의 핵심 문제 해결, 새로운 능력 획득)
  예: 자동 응답으로 CS 팀 응답 시간 50% 단축
  → 수작업 불가능했던 일을 이제 가능

2 = Major (중요한 개선, 주요 workflow 변경)
  예: 멀티채널 통합으로 채널 전환 시간 80% 단축
  → 좋은 개선이지만 "없으면 불가능" 수준은 아님

1 = Medium (유용한 개선, 효율성 증대)
  예: 필터링 기능으로 찾는 시간 20% 단축
  → 있으면 좋지만 필수는 아님

0.5 = Minor (좋은 기능, 하지만 주변적)
  예: 다크 모드, 폰트 커스터마이징
  → 일부 사용자는 사랑하지만 전체 만족도에 큰 영향 없음

0.25 = Minimal (있으면 좋지만 거의 영향 없음)
  예: 배경음악, 스킨 효과
  → 사용자가 원하지 않으면 불만 없음

<!-- 💬 Impact 측정의 가장 흔한 실수
"우리가 원하는 것" vs "사용자가 필요한 것" 혼동

PM: "자동 분류 정확도 5% 올리면 대단할 텐데"
사용자: "솔직히 정확도 5% 차이는 느낄 수 없어요.
        지금 UI가 너무 복잡하면 정확도 0%여도 쓸 거예요"

Impact는 사용자 관점에서만 측정하세요.
-->

**측정 방법:**

1. 정성적 피드백 (고객 인터뷰)
   "이 기능이 없으면 업무가 얼마나 어려워질까?"
   → Massive: "완전히 불가능해질 것 같다"
   → Major: "훨씬 더 오래 걸릴 것"
   → Medium: "좀 더 번거로울 것"

2. 정량적 KPI 변화
   - 시간 절감: 월 8시간 이상 → Impact 2 이상
   - 비용 절감: 월 1,000달러 이상 → Impact 2 이상
   - 사용자 만족도(NPS): +5점 이상 → Impact 1.5 이상

3. 기회비용
   "이 기능 대신 다른 기능을 하면 어떻게 될까?"
   → 다른 기능이 훨씬 낫다면 Impact 낮음
```

## Step 4: Confidence (확신도)

### 우리 추정값에 얼마나 확신하는가
```
**정의:** Reach/Impact/Effort 추정값의 정확도에 대한 확신도 (%)

**점수 기준:**

100% = 과거 유사 데이터가 충분함
- 예: "이전에 유사한 기능을 출시했고 정확한 데이터가 있음"
- 예: "고객 500명 설문에서 80% 확정 구매 의향"

75% = 어느 정도 근거가 있음
- 예: "고객 조사 (30명) 했고 추세 명확"
- 예: "경쟁사 벤치마크 데이터 참고"

50% = 중간 정도 확실성
- 예: "고객 피드백 (5명) 있고 팀 합의"
- 예: "시장 트렌드는 명확하지만 우리 제품 적용 불확실"

25% = 매우 불확실
- 예: "가정과 직관에 의존, 데이터 없음"
- 예: "새로운 기술/시장, 검증 필요"

<!-- 💬 Confidence가 낮으면 "검증" 먼저
Confidence 50% 미만 → 기능 개발 전에 "고객 조사" 또는 "PoC" 에픽을 먼저 추가하세요.

예: 멀티채널 지원 (Confidence 40%)
→ "멀티채널 고객 요구사항 조사" 에픽 (1주)
→ 결과에 따라 어느 채널부터 할지 결정
-->

**AI 제품 특화:**

| 기능 | Confidence 높은 이유 | Confidence 낮은 이유 |
|---|---|---|
| 정확도 개선 | 과거 모델 벤치마크 데이터 | 새로운 모델 아키텍처 |
| 멀티채널 | 고객 요청 명확함 | 각 채널 통합 복잡도 불확실 |
| UI 개선 | 사용자 테스트 데이터 있음 | 새로운 디자인 패턴 (검증 필요) |
| 성능 최적화 | 현재 병목 지점 명확 | 최적화 결과 예측 어려움 |
```

## Step 5: Effort (노력) 추정

### 예상 개발 시간
```
**정의:** 기능을 완료하는 데 필요한 예상 노력 (주 단위)

**포함 항목:**
- 설계 및 계획 (Design, Technical Design)
- 개발 및 테스트 (Development, QA)
- 배포 및 모니터링 (Deployment, Monitoring)
- 문서화 (Documentation)

**제외 항목:**
- PM의 관리 시간 (별도 항목)
- 회의/회고 시간 (팀 오버헤드)

<!-- 💬 Effort 과소 추정은 스프린트 실패의 가장 흔한 원인
특히 AI 팀은:
- 모델 학습 시간을 과소 평가 (실제: 2배 소요)
- 데이터 준비 시간을 무시 (전체 노력의 40%)
- 배포 및 모니터링 시간을 과소 평가

"기술만" 개발 시간이 아니라 "완전히 배포된 상태"까지의 시간을 추정하세요.
-->

**예시 (각 기능별 Effort 추정):**

| 기능 | 개발 | QA | 배포 | 모니터링 | 합계 |
|---|---|---|---|---|---|
| 이메일 기본 지원 | 3주 | 0.5주 | 0.5주 | 1주 | **5주** |
| Slack 기본 지원 | 2주 | 0.5주 | 0.5주 | 0.5주 | **3.5주** |
| 자동 분류 | 4주 | 1주 | 0.5주 | 1.5주 | **7주** |
| 카톡 지원 | 2주 | 0.5주 | 0.5주 | 0.5주 | **3.5주** |
| 필터링/검색 | 1주 | 0.5주 | 0.5주 | 0.5주 | **2.5주** |

**Effort 추정 방법:**

1. 팀 경험 기반
   - "이전에 유사한 기능을 했는데 3주 걸렸다"
   - 현재 프로젝트의 복잡도 고려하여 ±50%

2. 태스크 분해
   - 기능을 세부 태스크로 분해
   - 각 태스크 추정 (일 단위)
   - 합계 (주 단위)

3. 전문가 의견
   - 해당 기술 전문가에게 질문
   - 보수적 추정과 낙관적 추정의 평균

4. 버퍼 추가
   - 예상 시간 × 1.2 (20% 버퍼)
   - 복잡도 높으면 × 1.3-1.5
```

## Step 6: RICE 점수 계산

### 최종 우선순위
```
**공식:**
RICE Score = (R × I × C) / E

**예시 계산:**

기능 1: 이메일 기본 지원
- R = 23% (CS팀 중 이메일 사용자)
- I = 2 (응답 시간 30% 단축)
- C = 80% (고객 요청 명확)
- E = 5주

RICE = (23 × 2 × 0.8) / 5 = 36.8 / 5 = **7.36**

기능 2: 자동 분류
- R = 23% (CS팀 모두)
- I = 3 (자동 분류로 수동 개입 80% 감소)
- C = 70% (정확도 75% 달성 불확실)
- E = 7주

RICE = (23 × 3 × 0.7) / 7 = 48.3 / 7 = **6.9**

기능 3: 카톡 채널
- R = 45% (모든 사용자가 카톡 사용)
- I = 1.5 (편의성 개선, 필수는 아님)
- C = 60% (카톡 API 통합 불확실)
- E = 3.5주

RICE = (45 × 1.5 × 0.6) / 3.5 = 40.5 / 3.5 = **11.57** ← 높다!

<!-- 💬 RICE 점수로 놀란 팀들의 반응
"자동 분류가 핵심인데 RICE 점수가 낮다?"

이유:
1. I (Impact)가 높지만 C (Confidence)가 70%
   → 정확도 75% 달성이 보장되지 않음

2. 기술 Impact는 크지만 비즈니스 Reach는 23%
   → 모든 사용자가 자동 분류를 사용하는 건 아님

3. Effort가 7주로 길어서 점수 분모가 큼

실제로는 "정확도를 먼저 검증"하고 (RICE 낮음)
검증 후 자동 분류를 개발 (RICE 높아짐)하는 게 맞습니다.
-->

**최종 우선순위 (RICE 점수 순):**

1. 카톡 채널 - 11.57
2. 이메일 기본 지원 - 7.36
3. Slack 기본 지원 - 5.91
4. 자동 분류 - 6.9 (먼저 검증 필요)
5. 필터링/검색 - 4.2

**하지만 순수 RICE 점수만으로 결정하면 안 됩니다:**

추가 고려사항:
- 전략적 목표: "멀티채널"이 분기 목표면 이메일/Slack 우선
- 기술 의존성: "자동 분류는 이메일/Slack 기본이 필요"
- 고객 체류: "핵심 고객 5명이 카톡 필수"라고 요청
```

### 🇰🇷 한국 기업 기능 우선순위 특화

```
한국 SaaS 시장에서의 기능 우선순위 결정 고려사항:

1. **한국 SaaS 시장 특성 (플랫폼 의존성)**:
   - 네이버/카카오 의존도 높음: 네이버 클로바, 카카오 아이, 톡톡 필수 지원
   - Reach 계산: 글로벌 이메일(60%) vs 한국 카톡(90%), 문자(85%)
   - 결제 시스템: 한국 결제사(INICIS, PG사) Reach 추정 30-50% (높음)
   - Impact: 카톡/문자 미지원 시 한국 고객 Reach 0% → 우선순위 상향

2. **한국 기업 우선순위 결정 문화 (의사결정 구조)**:
   - 합의제: 팀별 우선순위 동의 필수 → 스탠드알론 의사결정 불가
   - 품의서 기반: "이 기능을 왜 먼저 할까?" 근거 자료 필요
   - 리더십 스타일: 데이터(RICE)보다 "경영진 지시"가 우선될 수 있음
   - 조정 전략: RICE 데이터 + 경영 메시지 조합으로 설득

3. **한국 시장 데이터 소스 (근거 데이터)**:
   - DART (정보공개): 상장사 고객의 구매력 확인 (공개정보)
   - 잡플래닛: 한국 기업 규모/구조/IT 성숙도 파악
   - 앱애니 한국: 한국 앱 사용 패턴, 기능별 선호도
   - Google Trends 한국: 검색 트렌드 (기능 수요)
   - Confidence 판단: 데이터 기반 > 추정 기반

4. **한국 사용자 특성 (사용 패턴)**:
   - 모바일 퍼스트: PC 웹(30%) vs 모바일 앱(70%), 반응형 디자인 필수
   - 카카오톡 연동 기대: 인증(카톡 로그인), 공유, 알림 기능 기본 요청
   - 속도 민감도 높음: 초 단위 응답 지연 → 사용자 이탈 (Reach 감소)
   - 가격 민감도: 선택 기능보다 기본 기능 무료 여부가 Reach 결정

5. **한국 규제 고려사항**:
   - 전자상거래법: 전자결제 시스템 → 구매/결제 기능 필수 (Impact 높음)
   - 전자금융거래법: 계좌이체 지원 → 금융 기능 필요 (Effort/Confidence 복잡)
   - 개인정보보호법(PIPA): 개인정보 처리 기능 → 규제 팀 검수 시간 추가 (Effort +2-3주)
```

## Step 7: 의존성과 병렬화

### 기능 간 의존성 맵
```
**의존성 분석:**

카톡 채널 (독립적)
├─ 개발: Week 1-2
└─ 배포: Week 3

이메일 기본 지원 (독립적)
├─ 개발: Week 1-3
└─ 배포: Week 4

Slack 기본 지원 (이메일 기본과 부분 공유 API)
├─ 개발: Week 2-4 (이메일과 병렬)
└─ 배포: Week 5

자동 분류 (이메일/Slack 기본 후 필요)
├─ 선행 조건: 이메일/Slack 배포 완료
├─ 개발: Week 5-7
└─ 배포: Week 8

필터링/검색 (독립적)
├─ 개발: Week 3-4
└─ 배포: Week 4

**병렬화 가능:**
- 카톡, 이메일, 필터링 동시 진행 (Week 1-2)
- Slack은 이메일과 부분 병렬 (Week 2-4)

**순차 필수:**
- 자동 분류는 이메일/Slack 완료 후

이를 고려하면:
- 최단 시간: 8주
- 최대 병렬: 5주 (자동 분류 포함 시 8주)
```

# 💡 Deep Tips:

- **Reach와 Impact는 독립적입니다**: 높은 Reach, 낮은 Impact도 있고 그 반대도 있습니다
- **AI 팀의 함정**: 모델 정확도 개선(기술 Impact)과 사용자 경험(UX Impact) 혼동. RICE는 사용자 임팩트만 측정하세요
- **Confidence가 가장 중요**: RICE 점수가 높아도 Confidence 50% 미만이면 먼저 검증하세요
- **한국 특화**: 문자/카톡/톡톡의 Reach가 이메일보다 높을 수 있습니다. 데이터로 확인하세요
- **스프린트 중 조정**: RICE는 고정이 아닙니다. 매주 새로운 데이터(고객 피드백, 기술 복잡도)로 재계산하세요
```


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | Reach 추정이 어려움 | MAU의 몇 %가 이 기능을 쓸지 추정. 유사 기능 사용률 참고 |
| 2단계 | Impact 점수가 주관적 | NPS 변화 or 리텐션 영향으로 정량화하세요 |
| 3단계 | Effort 산정 불확실 | 엔지니어에게 T-shirt 사이징(S/M/L/XL)을 요청하세요 |
| 5단계 | 결과에 팀이 동의 안 함 | 가중치를 조정해서 시뮬레이션해보세요. 어떤 가중치든 1위인 기능이 진짜 1위 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 우선순위 평가를 자동화하고 시뮬레이션합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
기능 우선순위는 스프린트마다 반복됩니다. 자동화하면 기준의 일관성을 유지하고, 시나리오별 시뮬레이션이 가능합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 스크립트: RICE 점수 자동 계산 및 시각화

```python
#!/usr/bin/env python3
"""
기능 우선순위 RICE 점수 자동 계산
- RICE 점수 계산 및 정렬
- 의존성 분석
- 시간축 로드맵 생성
- AI 제품 특화 분석 (정확도 vs UX)
"""

import json
from datetime import datetime
from typing import List, Dict
from anthropic import Anthropic

client = Anthropic()

class Feature:
    def __init__(self, feature_id: str, name: str, description: str):
        self.id = feature_id
        self.name = name
        self.description = description
        self.reach = None  # 0-100
        self.impact = None  # 0.25, 0.5, 1, 2, 3
        self.confidence = None  # 0-100
        self.effort = None  # weeks
        self.dependencies = []  # 의존성 feature_id 리스트
        self.rice_score = None
        self.type = None  # "ml_accuracy", "ux", "infrastructure"

    def calculate_rice(self):
        """RICE 점수 계산"""
        if all([
            self.reach is not None,
            self.impact is not None,
            self.confidence is not None,
            self.effort is not None
        ]):
            confidence_decimal = self.confidence / 100.0
            self.rice_score = (
                (self.reach * self.impact * confidence_decimal) / self.effort
            )
            return round(self.rice_score, 2)
        return None

    def to_dict(self):
        return {
            "id": self.id,
            "name": self.name,
            "description": self.description,
            "r": self.reach,
            "i": self.impact,
            "c": self.confidence,
            "e": self.effort,
            "rice_score": self.rice_score,
            "dependencies": self.dependencies,
            "type": self.type
        }


class FeaturePrioritizer:
    def __init__(self, product_name: str):
        self.product_name = product_name
        self.features: List[Feature] = []
        self.prioritized_features: List[Feature] = []

    def add_feature(self, feature_id: str, name: str, description: str,
                   reach: float, impact: float, confidence: float, effort: float,
                   dependencies: List[str] = None, feature_type: str = "ux"):
        """기능 추가"""
        feature = Feature(feature_id, name, description)
        feature.reach = reach
        feature.impact = impact
        feature.confidence = confidence
        feature.effort = effort
        feature.dependencies = dependencies or []
        feature.type = feature_type
        feature.calculate_rice()

        self.features.append(feature)

    def prioritize(self):
        """RICE 점수로 정렬"""
        self.prioritized_features = sorted(
            self.features,
            key=lambda f: f.rice_score or 0,
            reverse=True
        )

        print("="*70)
        print(f"🎯 {self.product_name} - 기능 우선순위 (RICE)")
        print("="*70)

        for i, feature in enumerate(self.prioritized_features, 1):
            print(f"\n{i}. {feature.name}")
            print(f"   설명: {feature.description}")
            print(f"   RICE: ({feature.reach}% × {feature.impact} × {feature.confidence}%) / {feature.effort}주 = {feature.rice_score:.2f}")
            print(f"   타입: {feature.type}")
            if feature.dependencies:
                print(f"   의존성: {', '.join(feature.dependencies)}")

    def analyze_ai_tradeoff(self):
        """AI 제품 특화: 정확도 vs UX 트레이드오프 분석"""
        ml_features = [f for f in self.features if f.type == "ml_accuracy"]
        ux_features = [f for f in self.features if f.type == "ux"]

        if not ml_features or not ux_features:
            return

        ml_score = sum(f.rice_score or 0 for f in ml_features)
        ux_score = sum(f.rice_score or 0 for f in ux_features)

        print("\n" + "="*70)
        print("🤖 AI 제품 특화 분석: 모델 정확도 vs UX")
        print("="*70)

        print(f"\n📊 모델 정확도 (ML) 기능들:")
        for f in ml_features:
            print(f"  - {f.name} (RICE: {f.rice_score:.2f})")
        print(f"  합계 RICE 점수: {ml_score:.2f}")

        print(f"\n🎨 사용자 경험 (UX) 기능들:")
        for f in ux_features:
            print(f"  - {f.name} (RICE: {f.rice_score:.2f})")
        print(f"  합계 RICE 점수: {ux_score:.2f}")

        print(f"\n⚡ 분석:")
        if ml_score > ux_score:
            print(f"  → 모델 정확도에 집중 (격차: {ml_score - ux_score:.2f})")
            print("  ⚠️ 주의: UX 개선도 병렬로 진행하세요. 정확도만 높으면 사용자는 안 씁니다.")
        else:
            print(f"  → UX 개선에 집중 (격차: {ux_score - ml_score:.2f})")
            print("  ✓ 좋은 선택. 빠른 배포로 사용자 피드백을 받으세요.")

    def generate_roadmap(self):
        """의존성을 고려한 로드맵 생성"""
        if not self.prioritized_features:
            self.prioritize()

        roadmap = {}
        current_week = 0
        scheduled = set()

        print("\n" + "="*70)
        print("📅 로드맵 (의존성 고려)")
        print("="*70)

        for feature in self.prioritized_features:
            # 의존성 확인
            if all(dep in scheduled for dep in feature.dependencies):
                week_start = current_week + 1
                week_end = current_week + int(feature.effort)

                roadmap[feature.id] = {
                    "name": feature.name,
                    "week_start": week_start,
                    "week_end": week_end,
                    "effort": feature.effort
                }

                print(f"\nWeek {week_start}-{week_end}: {feature.name}")
                print(f"  노력: {feature.effort}주 | RICE: {feature.rice_score:.2f}")

                current_week = week_end
                scheduled.add(feature.id)

        return roadmap

    def export_json(self, filename: str):
        """JSON으로 내보내기"""
        export_data = {
            "product": self.product_name,
            "generated_at": datetime.now().isoformat(),
            "features": [f.to_dict() for f in self.prioritized_features],
            "summary": {
                "total_features": len(self.features),
                "total_effort_weeks": sum(f.effort for f in self.features),
                "highest_rice_score": max((f.rice_score or 0) for f in self.features)
            }
        }

        with open(filename, 'w', encoding='utf-8') as f:
            json.dump(export_data, f, ensure_ascii=False, indent=2)

        print(f"\n💾 결과 저장: {filename}")

    def get_ai_recommendations(self):
        """AI를 활용한 우선순위 추천"""
        features_summary = "\n".join([
            f"{f.name} (RICE: {f.rice_score:.2f}, Type: {f.type})"
            for f in self.prioritized_features
        ])

        prompt = f"""당신은 AI 제품 전략가입니다.

다음 기능들이 RICE 점수로 우선순위화되었습니다:

{features_summary}

다음을 고려하여 추천을 제시하세요:
1. 스프린트별 추천 기능 (2주 단위)
2. 이 순서가 최적인 이유
3. 리스크 요소
4. 대체 전략

마크다운 형식으로 응답하세요."""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        print("\n" + "="*70)
        print("🤖 AI 추천")
        print("="*70)
        print(response.content[0].text)


# 실행 예시
if __name__ == "__main__":
    prioritizer = FeaturePrioritizer("CustomerAI - 고객 지원 플랫폼")

    # 기능 추가
    prioritizer.add_feature(
        "FEAT_001",
        "이메일 기본 지원",
        "이메일 채널 수신/송신 기능",
        reach=23,
        impact=2,
        confidence=80,
        effort=5,
        feature_type="ux"
    )

    prioritizer.add_feature(
        "FEAT_002",
        "자동 분류",
        "CS 요청 자동 분류 (정확도 75% 목표)",
        reach=23,
        impact=3,
        confidence=70,
        effort=7,
        dependencies=["FEAT_001"],
        feature_type="ml_accuracy"
    )

    prioritizer.add_feature(
        "FEAT_003",
        "Slack 기본 지원",
        "Slack 채널 통합",
        reach=15,
        impact=2,
        confidence=80,
        effort=3.5,
        feature_type="ux"
    )

    prioritizer.add_feature(
        "FEAT_004",
        "카톡 채널",
        "카톡 채널 지원 (국내 고객 맞춤)",
        reach=45,
        impact=1.5,
        confidence=60,
        effort=3.5,
        feature_type="ux"
    )

    prioritizer.add_feature(
        "FEAT_005",
        "필터링/검색",
        "이슈 필터링 및 검색 기능",
        reach=30,
        impact=1,
        confidence=85,
        effort=2.5,
        feature_type="ux"
    )

    # 우선순위 계산
    prioritizer.prioritize()

    # AI vs UX 분석
    prioritizer.analyze_ai_tradeoff()

    # 로드맵 생성
    prioritizer.generate_roadmap()

    # AI 추천
    prioritizer.get_ai_recommendations()

    # 내보내기
    prioritizer.export_json("feature_prioritization.json")
```

### Claude Code CLI 실행
```bash
cd /path/to/ai-pm-prompts
claude code --exec feature-prioritization.py --model claude-opus-4-6
```

---

## 📊 실행 결과 예시

### RICE 점수 계산 결과

| 우선순위 | 기능 | R | I | C | E | RICE | 이유 |
|---|---|---|---|---|---|---|---|
| 1 | 카톡 채널 | 45% | 1.5 | 60% | 3.5주 | **11.57** | 높은 Reach (한국 사용자) |
| 2 | 이메일 기본 | 23% | 2 | 80% | 5주 | **7.36** | 높은 Confidence |
| 3 | 자동 분류 | 23% | 3 | 70% | 7주 | **6.90** | 높은 Impact, 낮은 Confidence |
| 4 | Slack 기본 | 15% | 2 | 80% | 3.5주 | **5.91** | 의존성 고려 |
| 5 | 필터링/검색 | 30% | 1 | 85% | 2.5주 | **4.20** | 낮은 Impact |

### 스프린트 로드맵

```
🚀 Sprint 1 (Week 1-3):
├─ 카톡 채널 (RICE: 11.57)
├─ 이메일 기본 (Week 1-2 설계, Week 3 개발 시작)
└─ 필터링/검색 (RICE: 4.20)

🚀 Sprint 2 (Week 4-7):
├─ 이메일 기본 (완료)
├─ Slack 기본 (Week 4-5)
└─ 자동 분류 (Week 5-7 시작, Confidence 검증 필요)

🚀 Sprint 3+ (Week 8+):
├─ 자동 분류 (계속)
└─ 고급 기능 (고객 피드백 기반 재우선순위)
```

### AI vs UX 트레이드오프 분석

```
📊 모델 정확도 (ML) 기능들:
  - 자동 분류 (RICE: 6.90)
  합계: 6.90

🎨 사용자 경험 (UX) 기능들:
  - 카톡 채널 (RICE: 11.57)
  - 이메일 기본 (RICE: 7.36)
  - Slack 기본 (RICE: 5.91)
  - 필터링/검색 (RICE: 4.20)
  합계: 29.04

⚡ 분석:
  → UX 개선에 집중 (격차: 22.14)
  ✓ 좋은 선택! 빠른 배포로 사용자 피드백을 받으세요.

⚠️ 주의:
  - 카톡은 Reach 높지만 Confidence 60% (통합 복잡도 확인 필요)
  - 자동 분류 Confidence 70% (먼저 검증 필수)
  → Week 2-3에 "기술 검증" 스프린트 추가 권장
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** RICE 점수에서 'Confidence'를 객관적으로 평가했는지 확인하세요 — 자신감 과잉이 가장 흔한 함정입니다
2. **[논쟁 지점]** RICE vs ICE vs WSJF 중 어떤 프레임워크가 적합한지는 팀 규모와 데이터 가용성에 따라 다릅니다
3. **[자기 검증]** 1위 기능의 'Impact' 추정치를 과거 유사 기능의 실제 임팩트와 비교하세요

---

## 🔗 다음 단계

| 프롬프트 | 목적 | 연결 |
|---|---|---|
| `sprint-kickoff.md` | 우선순위화된 기능을 스프린트 계획으로 변환 | 기능 우선순위 → 팀 실행 계획 |
| `decision-canvas.md` | RICE 점수 차이가 크면 의사결정 재검토 | 의사결정 필요 시 활용 |
| `backlog-prioritization.md` | 기능 우선순위를 에픽 수준으로 통합 | 전체 로드맵 확인 |
