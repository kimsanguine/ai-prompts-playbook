# 📚 백로그 우선순위 (Backlog Prioritization)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 35분+ (Build)
> 워크플로우: `decision-canvas.md` → (이 파일) → `feature-prioritization.md`

---

## 🎯 이 프롬프트가 해결하는 문제

의사결정을 완료했으면 이제 **에픽과 스토리를 우선순위로 정렬**해야 합니다. "우리는 정확도 개선(옵션 A)과 멀티채널 지원(옵션 B)을 3:1로 나눈다"고 결정했다면, 이제 **RICE 프레임워크(Reach/Impact/Confidence/Effort)를 사용해 에픽별로 점수를 매기고 실행 순서를 결정**하는 과정입니다.

특히 AI 팀에서 자주 발생하는 문제:
- ML 엔지니어는 "모델 개선(정확도)"을 우선하고
- PM은 "고객 요청(멀티채널)"을 우선하고
- Product Designer는 "사용자 경험"을 우선합니다

이 프롬프트는 **RICE + ICE 프레임워크를 비교 교육**하면서 팀이 공통 언어로 우선순위를 결정하도록 돕습니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `feature-prioritization.md`에서 선정된 기능들을 스프린트 단위 백로그로 정리할 때 연결됩니다.

이전 프롬프트 결과에서 **기능 목록, RICE 점수, 의존성 맵**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 백로그 항목들의 우선순위를 정리할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 백로그 우선순위 매니저입니다.

{EPIC_LIST}에 대해 RICE 프레임워크로 우선순위를 매기세요:

R (Reach): 이 에픽이 영향을 미칠 사용자 수 (월간 활성 사용자 기준 백분율)
I (Impact): 영향받는 사용자의 임팩트 (0.25 = Minimal / 0.5 = Minor / 1 = Medium / 2 = Major / 3 = Massive)
C (Confidence): 우리의 확신 도 (0-100%, 불확실하면 낮게)
E (Effort): 예상 노력 (주 단위)

RICE Score = (R * I * C) / E

최종 우선순위:
1. [에픽명] - Score: [점수]
2. [에픽명] - Score: [점수]
...

각 에픽별 근거 1-2 문장:
```

💡 **Quick Tips:**
- Reach는 "모든 사용자"가 아니라 **실제로 이 기능을 써야 하는 비율**입니다 (예: 고객 지원팀만 사용 → 70%)
- Impact는 "얼마나 중요한가"가 아니라 **임팩트 크기의 배수**입니다 (Medium=1배, Major=2배)
- Confidence 70% 미만이면 리서치 에픽을 먼저 추가하세요
- 절대 평균을 내지 마세요. 가장 높은 RICE 스코어가 우선입니다


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 백로그가 100개 이상 | 먼저 "완료/중복/불필요" 항목을 제거하세요. 깨끗한 백로그가 우선 |
| 기술 부채와 기능 요청이 섞여 있음 | 별도 트랙으로 분리하세요. 기술 부채는 20% 룰 (스프린트 20%를 할당) |
| PM과 엔지니어 우선순위 충돌 | 비즈니스 가치 vs 기술 위험 매트릭스로 함께 평가하세요 |
| 긴급 요청이 계속 들어옴 | "P0 긴급 슬롯"을 스프린트에 미리 확보해두세요 (20%) |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 백로그를 체계적으로 정리하고 스프린트 계획에 반영하고 싶은 분입니다.
"무엇을 먼저 할까?"를 데이터로 결정하고 싶다면 이걸 써보세요.

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
당신은 백로그 우선순위 컨설턴트이자 PM/Designer/Engineer 협의자입니다.
- 팀이 RICE 프레임워크를 올바르게 이해하도록 교육
- ICE 프레임워크와 비교하여 상황에 맞는 프레임워크 선택 지원
- AI 팀 특화: 모델 개선 vs 기능 확대의 우선순위 조정

# 목표
{EPIC_LIST}를 RICE 또는 ICE로 우선순위화하고,
각 프레임워크의 강점과 약점을 명확히 하며,
Product Trio가 장기 로드맵에 동의하도록 합니다.

<!-- 💬 왜 백로그 우선순위가 중요한가?
"우리는 정확도 개선을 하기로 했다"고 결정했다면,
그 안에 어떤 스토리를 먼저 할 것인가는 또 다른 의사결정입니다.
잘못된 우선순위는 선택된 옵션마저 실패하게 만듭니다.
-->

# Reasoning Strategy

## Step 1: RICE 프레임워크 이해

### RICE (Reach-Impact-Confidence-Effort)
```
**Reach (도달): 이 에픽이 영향을 미칠 사용자 수**

정의: 월 단위로 이 기능을 실제로 사용할 사용자 수
계산: 전체 MAU 대비 백분율 (0-100%)

나쁜 예: "우리는 100만 사용자가 있으므로 Reach=100만"
좋은 예: "우리 100만 MAU 중 고객 지원팀 3만 명만 사용 → Reach=3%"

<!-- 💬 Reach 계산의 함정
초기 스타트업은 "모든 고객이 이걸 원한다"고 착각하지만,
실제로는 구체적 사용자층(CS팀, 마케팅팀, PM팀 등)만 사용합니다.
과장하지 마세요.
-->

**AI 제품 특화:**
- 추천 엔진: 모든 사용자가 추천을 받음 (100%)
- 이상 탐지: 데이터팀만 활용 (10%)
- 자동 응답: CS팀만 활용 (30%)
```

### Impact (임팩트: 영향의 크기)
```
정의: 영향받는 사용자가 느끼는 가치의 크기

점수:
- 3 = Massive (사용자의 핵심 문제 해결, 새로운 능력)
- 2 = Major (중요한 문제 해결, 사용 흐름 개선)
- 1 = Medium (유용하지만 선택사항)
- 0.5 = Minor (좋지만 필수는 아님)
- 0.25 = Minimal (있으면 좋지만 거의 영향 없음)

나쁜 예: "정확도가 5% 올랐으니 Impact=3"
좋은 예: "정확도 5% 상승으로 수동 검수 시간 20% 감소 → Impact=2"

<!-- 💬 Impact는 상대 평가입니다
절대적 "얼마나 좋은가"가 아니라
현재 상황 대비 "얼마나 개선되는가"입니다.
예: 정확도 70%→75% vs 정확도 90%→95%
→ 첫 번째가 Impact가 더 큽니다 (절대값은 작지만 상대값은 큼)
-->

**AI 제품 특화:**
- 정확도 70% → 85% (큰 개선, Impact=2)
- 정확도 95% → 96% (작은 개선, Impact=0.5)
- 응답 시간 5초 → 2초 (UX 개선, Impact=1)
- 모델 재학습 속도 1일 → 4시간 (운영 편의, Impact=1)
```

### Confidence (확신도: 얼마나 확실한가)
```
정의: 우리가 추정값(Reach, Impact, Effort)에 얼마나 확신하는가 (%)

점수:
- 100% = 과거 유사한 작업이 있음, 데이터 확실함
- 75% = 어느 정도 근거 있음, 일부 불확실
- 50% = 불확실, 리서치 필요
- 25% = 매우 불확실, 가정에 의존

<!-- 💬 Confidence 낮으면 리서치 에픽 추가하세요
"우리는 고객이 이걸 원한다고 생각하는데 Confidence는 30%"
→ "고객 조사 에픽" (1주)을 먼저 추가하고
그 결과에 따라 우선순위를 재조정하세요.
-->

예시:
- 정확도 개선: Confidence 85% (과거 경험, 모델 벤치마크 있음)
- 멀티채널 지원: Confidence 70% (고객 요청 있음, 기술 확실하지 않음)
- 새로운 AI 기능: Confidence 40% (가정에 의존, 검증 필요)
```

### Effort (노력: 예상 소요 시간)
```
정의: 이 에픽을 완료하는 데 필요한 예상 노력 (주 단위)

계산:
- 팀 규모 (Engineer 수)
- 기술 복잡도
- 의존성 (다른 팀, 외부 API)
- 테스트/배포 시간

<!-- 💬 Effort 과소 추정은 가장 흔한 실수입니다
특히 AI 팀은 "모델은 3주, 배포는 1주"라고 가정하는데
실제로는 데이터 정제, 모니터링, A/B 테스트로 2-3배 소요됩니다.
-->

예시:
- 정확도 개선 (파인튜닝): 4주 (모델 학습 2주 + A/B 테스트 2주)
- 멀티채널 기본 지원: 6주 (각 채널 구현 3주 + 통합 3주)
- 새 모델 아키텍처: 12주 (리서치 4주 + 구현 6주 + 테스트 2주)
```

## Step 2: RICE 계산

### 에픽별 점수 계산
```
공식: RICE Score = (R × I × C) / E

예시 1: 정확도 개선 (Deep Focus)
- R (Reach): 70% (CS팀 중 70% 사용자)
- I (Impact): 2 (수동 검수 20% 감소)
- C (Confidence): 85% (과거 경험)
- E (Effort): 4주

RICE = (70 × 2 × 0.85) / 4 = 29.75 → **RICE Score: 30**

예시 2: 멀티채널 지원 (Breadth Expansion)
- R (Reach): 60% (신규 채널 채택률)
- I (Impact): 2 (신규 기회)
- C (Confidence): 70% (고객 요청, 기술 불확실)
- E (Effort): 6주

RICE = (60 × 2 × 0.70) / 6 = 14 → **RICE Score: 14**

예시 3: 고객 조사 (Risk Reduction)
- R (Reach): 100% (모든 고객 영향)
- I (Impact): 0.5 (조사는 직접 가치 아님)
- C (Confidence): 100% (방법론 확실)
- E (Effort): 1주

RICE = (100 × 0.5 × 1.0) / 1 = 50 → **RICE Score: 50**

<!-- 💬 높은 RICE Score는 우선순위가 높다는 뜻입니다
Score 50 (리서치) > Score 30 (정확도) > Score 14 (멀티채널)

하지만 RICE 점수만으로 결정하면 안 됩니다.
전략적 목표, 팀 역량, 의존성을 함께 고려하세요.
-->
```

## Step 3: RICE vs ICE 선택

### ICE 프레임워크 (스타트업 용)
```
ICE는 RICE를 단순화한 버전입니다:
- I (Impact): 0-10점 (임팩트 크기)
- C (Confidence): 0-10점 (확신도)
- E (Ease): 0-10점 (구현 난이도 역순, 높을수록 쉬움)

ICE Score = (I + C + E) / 3

예시:
정확도 개선: (8 + 8 + 4) / 3 = 6.7
멀티채널: (9 + 7 + 3) / 3 = 6.3

RICE vs ICE:
- RICE: 데이터 기반, 정량적, 규모가 있는 팀 (10명+)
- ICE: 빠르고 직관적, 스타트업 (10명 이하)

<!-- 💬 AI 스타트업은 ICE가 나을 수 있습니다
RICE는 "정확한 데이터"를 요구합니다.
하지만 초기 스타트업은 Reach를 정확히 알기 어려우니까
ICE의 "빠른 판단"이 더 유용할 수 있습니다.
-->

선택 기준:
- 데이터가 많고 정량화 가능 → RICE
- 빠른 결정이 필요하고 데이터 부족 → ICE
- 대규모 팀, 명확한 고객 세분화 → RICE
- 초기 스타트업, MVP 단계 → ICE
```

## Step 4: 백로그 정렬 및 의존성 분석

### 에픽 우선순위 리스트
```
RICE 점수 기준으로 정렬하되, 다음을 함께 고려하세요:

1. **의존성 (Dependencies)**
   - 에픽 A가 완료되어야 에픽 B 시작 가능한가?
   - 예: "멀티채널 지원"은 "기본 API 구조 개선"에 의존

2. **전략적 목표**
   - 회사 분기별 목표와 맞는가?
   - 포지셔닝 전략과 일관성 있는가?

3. **팀 역량 (Capacity)**
   - 현재 팀 규모로 병렬 진행 가능한가?
   - 예: PM 1명만으로 3개 에픽 리드 불가능

4. **리스크 (Risk)**
   - 실패하면 비용이 얼마나 높은가?
   - 높은 리스크 에픽은 더 빨리 검증해야 함

<!-- 💬 RICE 점수가 전부가 아닙니다
Score 50인 에픽이 6개월 뒤 마켓에 출시되면 쓸모없을 수 있습니다.
전략, 리스크, 의존성을 함께 고려하여 로드맵을 그리세요.
-->

우선순위 정렬 템플릿:

Q1 (0-4주):
1. [에픽 이름] - RICE: 30 | 의존성: 없음 | 리스크: 낮음
   이유: 가장 높은 점수 + 즉시 시작 가능

2. [에픽 이름] - RICE: 25 | 의존성: 에픽1 완료 필요 | 리스크: 중간
   이유: 에픽1과 병렬 가능 구간 있음

Q2 (4-8주):
1. [에픽 이름] - RICE: 20 | 의존성: 없음 | 리스크: 높음
   이유: 고리스크이므로 Q1 학습 후 Q2에 시작
```

## Step 5: 스토리 분해

### 에픽 → 스토리 분해
```
각 에픽을 2-3주 단위의 스토리로 분해하세요:

에픽: 정확도 개선 (4주)

├─ 스토리 1: 학습 데이터 수집 및 정제 (1주)
│  └─ 작업: 고객 이슈 1,000개 수집 → 카테고리 레이블링 → 데이터 검증
│
├─ 스토리 2: 모델 파인튜닝 (1.5주)
│  └─ 작업: KoBERT 로드 → 파인튜닝 → 검증 세트 테스트
│
├─ 스토리 3: A/B 테스트 설계 및 구현 (1주)
│  └─ 작업: 대조군/실험군 설정 → 메트릭 정의 → 배포
│
└─ 스토리 4: 모니터링 및 최적화 (0.5주)
   └─ 작업: 실시간 메트릭 대시보드 구성 → 성능 모니터링

<!-- 💬 스토리 분해의 중요성
"4주 에픽"과 "1주 스토리 4개"는 완전히 다릅니다.
스토리로 분해하면 주간 진척을 체크할 수 있고
필요시 우선순위를 재조정할 수 있습니다.
-->

스토리 우선순위 규칙 (AI 팀 특화):
1. **Data Preparation** 스토리부터 (모든 ML 작업의 기초)
2. **Model Training** (모델 개선)
3. **Evaluation & Testing** (정확도 검증)
4. **Deployment & Monitoring** (운영 안정성)
5. **Optimization & Refinement** (선택사항, 시간 남을 때)
```

# 💡 Deep Tips:

- RICE 점수가 거의 같은 에픽들은 팀 투표로 결정하세요 (민주적)
- 분기마다 백로그를 재평가하세요. 3개월마다 시장이 변합니다
- "고객이 원한다"는 Reach만 높고 Impact는 낮은 에픽을 조심하세요
- AI 팀에서는 "모델 정확도"와 "기능"의 우선순위가 충돌합니다
  → 정확도가 0.1% 올라도 사용자는 모르는데, UI 개선은 모두 압니다
  → RICE 점수가 낮아도 기능(멀티채널)을 우선하는 게 맞을 수 있습니다
- 한국 SaaS는 보수적이므로 "안정성" 에픽(기술 부채, 모니터링)을 과소평가하기 쉽습니다
  → 정기적으로 기술 부채 에픽(전체의 20%)을 백로그에 포함하세요
```



### # 🇰🇷 한국 SaaS 백로그 우선순위 특화

```
한국 SaaS 시장 우선순위 고려사항:

1. **규제 에픽 우선순위**:
   - 개인정보보호법 개정 대응 → 항상 P0
   - 전자문서/전자서명법 → 계약 기능에 직접 영향
   - AI 기본법 (2026) → 고위험 AI 해당 시 의무사항

2. **한국 고객 특성**:
   - 대기업 고객: "보안 인증(ISO 27001, ISMS)" 없으면 도입 불가
   - → 보안/인증 에픽이 기능 에픽보다 우선
   - "레퍼런스 고객" 확보가 한국 B2B에서 결정적

3. **한국 SaaS 기술 부채 패턴**:
   - 한국 SaaS는 "안정성" 에픽을 과소평가하기 쉬움
   - 네이버 클라우드/AWS 서울 리전 마이그레이션 → 큰 에픽
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 백로그 항목 크기가 제각각 | Epic/Story/Task로 계층화한 후, Story 단위로 우선순위 매기세요 |
| 2단계 | 가치 산정이 어려움 | "이것을 안 하면 무슨 일이 생기나?" 역질문으로 가치를 추정 |
| 3단계 | 의존성이 복잡 | 의존성 그래프를 그리고, 블로커(선행 작업)를 먼저 처리 |
| 4단계 | 팀 용량 산정이 불확실 | 지난 3스프린트 velocity 평균을 기준으로 하세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 백로그 우선순위 평가를 자동화하고 대시보드로 시각화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
스프린트마다 백로그 정리를 반복합니다. 자동화하면 일관된 기준으로 빠르게 우선순위를 매길 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 스크립트: 백로그 우선순위 자동 계산

```python
#!/usr/bin/env python3
"""
백로그 우선순위 자동 계산 및 로드맵 생성
- RICE / ICE 점수 계산
- 의존성 분석
- 스토리 분해 제안
"""

import json
from datetime import datetime, timedelta
from anthropic import Anthropic

client = Anthropic()

class EpicPrioritizer:
    def __init__(self, framework="RICE"):
        self.framework = framework
        self.epics = []
        self.scores = {}
        self.roadmap = {}

    def add_epic(self, epic_id, name, reach=None, impact=None,
                 confidence=None, effort=None, description=""):
        """에픽 추가 (RICE 기준)"""
        epic = {
            "id": epic_id,
            "name": name,
            "description": description,
            "reach": reach,  # 백분율 (0-100)
            "impact": impact,  # 배수 (0.25, 0.5, 1, 2, 3)
            "confidence": confidence,  # 확신도 (0-100)
            "effort": effort,  # 주 단위
            "dependencies": [],
            "stories": []
        }
        self.epics.append(epic)
        return epic_id

    def add_dependency(self, epic_id, depends_on):
        """에픽 간 의존성 추가"""
        epic = next((e for e in self.epics if e["id"] == epic_id), None)
        if epic:
            epic["dependencies"].append(depends_on)

    def calculate_rice_score(self, epic):
        """RICE 점수 계산"""
        if not all([epic["reach"], epic["impact"],
                   epic["confidence"], epic["effort"]]):
            return None

        # Confidence를 백분율에서 소수로 변환
        confidence_decimal = epic["confidence"] / 100.0

        rice_score = (epic["reach"] * epic["impact"] * confidence_decimal) / epic["effort"]
        return round(rice_score, 2)

    def calculate_ice_score(self, epic):
        """ICE 점수 계산 (또는 임팩트/확신/난이도)"""
        # ICE: (I + C + E) / 3, E는 역순 (높을수록 쉬움)
        # 여기서는 간단하게 정규화된 값 사용
        pass

    def prioritize_epics(self):
        """모든 에픽의 점수를 계산하고 정렬"""
        for epic in self.epics:
            if self.framework == "RICE":
                epic["score"] = self.calculate_rice_score(epic)
            # else ICE 계산

        # 점수순 정렬
        self.epics.sort(key=lambda x: x.get("score", 0) or 0, reverse=True)

        print("="*60)
        print(f"📊 백로그 우선순위 ({self.framework})")
        print("="*60)

        for i, epic in enumerate(self.epics, 1):
            print(f"\n{i}. {epic['name']}")
            print(f"   점수: {epic.get('score', 'N/A')}")
            print(f"   설명: {epic['description']}")
            if self.framework == "RICE":
                print(f"   R: {epic['reach']}% | I: {epic['impact']} | C: {epic['confidence']}% | E: {epic['effort']}주")
            if epic['dependencies']:
                print(f"   의존성: {', '.join(epic['dependencies'])}")

    def generate_roadmap(self, max_weeks=12):
        """로드맵 생성 (의존성과 팀 용량 고려)"""
        roadmap = {"Q1": [], "Q2": [], "Q3": [], "Q4": []}
        current_week = 0
        quarter = "Q1"
        weeks_per_quarter = 4

        scheduled = set()

        for epic in self.epics:
            # 의존성 확인
            if all(dep in scheduled for dep in epic["dependencies"]):
                if current_week >= weeks_per_quarter * 4:
                    break

                # 분기 결정
                quarter_num = (current_week // weeks_per_quarter) + 1
                if quarter_num == 1:
                    quarter = "Q1"
                elif quarter_num == 2:
                    quarter = "Q2"
                elif quarter_num == 3:
                    quarter = "Q3"
                else:
                    quarter = "Q4"

                roadmap[quarter].append({
                    "name": epic["name"],
                    "score": epic.get("score"),
                    "effort": epic["effort"],
                    "week_start": current_week + 1,
                    "week_end": current_week + epic["effort"]
                })

                current_week += epic["effort"]
                scheduled.add(epic["id"])

        return roadmap

    def generate_stories(self, epic_id):
        """에픽을 스토리로 분해"""
        epic = next((e for e in self.epics if e["id"] == epic_id), None)
        if not epic:
            return None

        prompt = f"""당신은 AI 제품 PM입니다.

에픽: {epic['name']}
설명: {epic['description']}
예상 소요: {epic['effort']}주

이 에픽을 2-3주 단위의 스토리로 분해하세요.

각 스토리마다:
- 스토리 이름
- 설명 (1-2 문장)
- 예상 소요 (일 단위)
- 담당 역할 (PM/Designer/Engineer)
- 정의된 완료 기준 (DoD)

JSON 형식으로 응답하세요:
{{
  "stories": [
    {{
      "name": "스토리 이름",
      "description": "설명",
      "estimated_days": 5,
      "owner": "Engineer",
      "dod": ["완료 기준 1", "완료 기준 2"]
    }}
  ]
}}"""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        try:
            text = response.content[0].text
            start = text.find('{')
            end = text.rfind('}') + 1
            json_str = text[start:end]
            stories_data = json.loads(json_str)

            print(f"\n📝 에픽 '{epic['name']}' 스토리 분해:")
            for story in stories_data["stories"]:
                print(f"\n  ✓ {story['name']}")
                print(f"    설명: {story['description']}")
                print(f"    시간: {story['estimated_days']}일")
                print(f"    담당: {story['owner']}")
                print(f"    완료 기준: {', '.join(story['dod'])}")

            return stories_data["stories"]

        except json.JSONDecodeError:
            print(f"스토리 생성 실패: {response.content[0].text}")

    def export_roadmap(self, filename):
        """로드맵을 JSON으로 저장"""
        roadmap = self.generate_roadmap()

        export_data = {
            "framework": self.framework,
            "epics": self.epics,
            "roadmap": roadmap,
            "created_at": datetime.now().isoformat()
        }

        with open(filename, 'w', encoding='utf-8') as f:
            json.dump(export_data, f, ensure_ascii=False, indent=2)

        print(f"\n💾 백로그 저장: {filename}")


# 실행 예시
if __name__ == "__main__":
    prioritizer = EpicPrioritizer(framework="RICE")

    # 에픽 추가
    prioritizer.add_epic(
        "EPIC_001",
        "정확도 개선 (Deep Focus)",
        reach=70,
        impact=2,
        confidence=85,
        effort=4,
        description="고객 문제 분류 정확도를 70%에서 85%로 개선"
    )

    prioritizer.add_epic(
        "EPIC_002",
        "멀티채널 지원 (Breadth)",
        reach=60,
        impact=2,
        confidence=70,
        effort=6,
        description="이메일, Slack, 카톡 채널 추가 지원"
    )

    prioritizer.add_epic(
        "EPIC_003",
        "고객 조사 (Risk Reduction)",
        reach=100,
        impact=0.5,
        confidence=100,
        effort=1,
        description="멀티채널 사용 의향 조사"
    )

    # 의존성 설정
    prioritizer.add_dependency("EPIC_002", "EPIC_003")

    # 우선순위 계산
    prioritizer.prioritize_epics()

    # 로드맵 생성
    print("\n" + "="*60)
    print("🗓️  로드맵")
    print("="*60)
    roadmap = prioritizer.generate_roadmap()
    for quarter, epics in roadmap.items():
        if epics:
            print(f"\n{quarter}:")
            for epic in epics:
                print(f"  - {epic['name']} ({epic['effort']}주)")

    # 스토리 분해
    print("\n" + "="*60)
    prioritizer.generate_stories("EPIC_001")

    # 저장
    prioritizer.export_roadmap("backlog_roadmap.json")
```

### Claude Code CLI 실행
```bash
cd /path/to/ai-pm-prompts
claude code --exec backlog-prioritization.py --model claude-opus-4-6
```

---

## 📊 실행 결과 예시

### RICE 점수 계산 예시

| 에픽 | R | I | C | E | RICE Score | 우선순위 |
|---|---|---|---|---|---|---|
| 고객 조사 | 100 | 0.5 | 100 | 1 | **50** | 1순위 |
| 정확도 개선 | 70 | 2 | 85 | 4 | **29.75** | 2순위 |
| 멀티채널 지원 | 60 | 2 | 70 | 6 | **14** | 3순위 |

**해석:**
- 고객 조사는 Reach, Confidence, Effort 모두 좋지만 Impact가 낮음
- 정확도 개선은 Impact와 Confidence 높음, Effort도 적당
- 멀티채널은 Reach, Impact 높지만 Effort가 크고 Confidence 낮음

### 로드맵 예시

```
🗓️ 12주 로드맵

Q1 (0-4주):
├─ 고객 조사 (1주) ✓ 우선 실행
├─ 정확도 개선 (4주) ✓ 병렬 진행 (3주 말부터)
│  ├─ 스토리 1: 데이터 수집 (1주)
│  ├─ 스토리 2: 모델 파인튜닝 (1.5주)
│  └─ 스토리 3: A/B 테스트 (1.5주)
└─ 멀티채널 리서치 (병렬, 고객 조사 결과 기반)

Q2 (4-8주):
├─ 멀티채널 기본 구현 (6주)
│  ├─ 스토리 1: 이메일 통합 (2주)
│  ├─ 스토리 2: Slack 통합 (2주)
│  └─ 스토리 3: 카톡 통합 (2주)
└─ 정확도 최적화 (병렬)

Q3 (8-12주):
├─ 멀티채널 고급 기능 (고객 피드백 기반)
└─ 성능 최적화 및 기술 부채 해결
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 백로그 상위 5개 아이템의 '의존성'이 명확한지 확인하세요 — 의존성 미파악이 일정 지연의 1위 원인입니다
2. **[논쟁 지점]** 백로그 정렬을 'RICE 점수 순'으로 할지 '의존성 순'으로 할지는 팀 상황에 따라 다릅니다
3. **[자기 검증]** 상위 3개 아이템을 개발 리드에게 보여주고 '이 순서가 맞나?'를 확인하세요

---

## 🔗 다음 단계

| 프롬프트 | 목적 | 연결 |
|---|---|---|
| `feature-prioritization.md` | RICE 점수 산정 상세화 및 자동화 | 백로그 우선순위 → 기능별 상세 우선순위 |
| `sprint-kickoff.md` | 우선순위화된 에픽을 스프린트 계획으로 변환 | 로드맵 → 주간 실행 계획 |
| `decision-canvas.md` | 우선순위 결정의 배경 이해 | 의사결정 맥락 제공 |
