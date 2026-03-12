# 📋 의사결정 캔버스 (Decision Canvas)

> 예상 소요: 5분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: `positioning-strategy.md` → (이 파일) → `feature-prioritization.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 제품의 의사결정은 복잡합니다. "이 기능을 빌드할까, 외부 API를 쓸까?" "이번 분기에 추천 엔진을 개선할까, 아니면 성능 최적화에 집중할까?" 같은 결정에서 PM, Designer, Engineer의 관점이 충돌합니다.

**의사결정 캔버스**는 이런 **복잡한 결정을 시각화하고 Product Trio가 함께 협의**하는 도구입니다. 감정이나 권력이 아니라 데이터와 전략에 기반한 의사결정을 지원합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> 복잡한 의사결정이 필요한 모든 상황에서 사용합니다. `problem-framing.md`에서 정의한 문제의 해결 방향을 결정할 때 연결됩니다.

이전 프롬프트 결과에서 **의사결정 주제, 선택지, 제약 조건, 이해관계자**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 복잡한 의사결정을 구조화할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 의사결정 촉진자입니다.

다음 구조로 의사결정 캔버스를 작성하세요:

1. 의사결정: [명확한 질문, Yes/No가 아닌 "어떻게" 형태]
2. 맥락: [이 결정이 왜 필요한가, 언제까지 결정해야 하는가]
3. 옵션:
   - 옵션 A: [구체적 행동]
   - 옵션 B: [구체적 행동]
   - 옵션 C: [구체적 행동]
4. 평가 기준: [PM/Designer/Engineer가 공통으로 동의한 3-4개 기준]
5. 각 옵션별 스코어:
   - PM 관점: [0-10점] 근거
   - Designer 관점: [0-10점] 근거
   - Engineer 관점: [0-10점] 근거
6. 최종 추천: [옵션 선택 + 의존성 + 위험]

{DECISION_CONTEXT}
```

💡 **Quick Tips:**
- "어떻게 할까?" 형태의 질문을 만드세요. "A 할까, B 할까?"는 2분 안에 끝나고 나중에 후회합니다
- 의사결정에 최소 3개 옵션을 포함하세요. 2개만 있으면 무조건 선택 오류가 나옵니다
- 스코어링은 절대 평균을 내지 마세요. 합의된 최종 점수가 있어야 합니다


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 결정이 급함 (오늘 중 결정) | Quick Start만 사용하세요. 3개 옵션, 3개 기준으로 빠르게 비교 |
| 팀원 간 의견 대립 | 각자 독립적으로 스코어링 → 결과 비교 → 차이가 큰 항목만 토론 |
| 정량 데이터가 없음 | "확신도"를 함께 기록하세요. 높음/중간/낮음으로 추정의 신뢰도 표시 |
| 옵션이 2개뿐 | "아무것도 안 하기" 또는 "부분 실행"을 세 번째 옵션으로 추가하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — Product Trio(PM/Designer/Engineer) 관점에서 체계적으로 의사결정하고 싶은 분입니다.
감정이 아닌 데이터 기반 의사결정을 하고 싶다면 이걸 써보세요.

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


```markdown
# 역할
당신은 의사결정 촉진자이자 Product Trio 협의자입니다.
- PM 관점: 비즈니스 임팩트, 고객 니즈, 시장 타이밍
- Designer 관점: 사용자 경험, 브랜드, 학습 곡선
- Engineer 관점: 기술 부채, 인프라 코스트, 유지보수성

# 목표
{DECISION_POINT}에 대해 최소 3개의 옵션을 평가하고,
각 역할의 관점에서 강점과 약점을 명확히 하여
Product Trio가 함께 의사결정하도록 돕습니다.

<!-- 💬 왜 Product Trio 협의인가?
- PM만 결정하면: "고객은 원하지만 구현 불가능"
- Designer만 결정하면: "예쁘지만 비즈니스 가치 없음"
- Engineer만 결정하면: "깔끔하지만 고객이 이해 못함"

3명의 관점을 모두 포함해야 장기적으로 지속 가능한 결정을 할 수 있습니다.
-->

# Reasoning Strategy

## Step 1: 의사결정 정의

### 명확한 질문 설정
```
의사결정을 명확히 정의하세요:

나쁜 예: "AI 모델을 어떻게 할까?"
좋은 예: "고객 문제 분류를 위해 사전 학습 모델(GPT-4)을 사용할지,
        커스텀 파인튜닝 모델을 개발할지, 하이브리드를 사용할지?"

좋은 의사결정 질문의 특징:
1. 특정 도메인(고객 지원, 추천, 예측)을 명시
2. 구체적 시간 범위 (이번 분기, 3개월 내, 우선순위)
3. 실행 가능한 옵션으로 대체 가능

<!-- 💬 의사결정 질문이 나쁜 이유
"우리는 AI를 잘 해야 한다"는 의사결정이 아니라 목표입니다.
의사결정은 "이번 달 안에 A를 할 것인가, B를 할 것인가?"의 형태여야
실행할 수 있습니다.
-->
```

### 맥락 정보 수집
```
다음 정보를 수집하세요:

**비즈니스 맥락:**
- 왜 이 의사결정이 필요한가? (고객 피드백, 경쟁, 내부 기술 부채)
- 의사결정 기한은? (이번 주, 분기 말, 무기한)
- 경제적 영향은? (수익, 비용 절감, TAM 확대)

**기술 맥락:**
- 현재 기술 스택은?
- 팀의 AI/ML 역량은?
- 인프라 제약은?

**마켓 맥락:**
- 경쟁사는 이걸 어떻게 했나?
- 고객 피드백은?
- 시장 트렌드는?

<!-- 💬 맥락 없는 의사결정은 부메랑입니다
3개월 뒤에 "왜 이 결정을 했지?" 하면서 다시 되돌리게 됩니다.
의사결정 배경을 문서화하세요.
-->
```

## Step 2: 옵션 생성

### 최소 3개의 옵션 만들기
```
다음 원칙으로 옵션을 생성하세요:

**옵션 A: 보수적 선택 (Low Risk, Low Reward)**
- 기존 방식을 개선
- 기술 부채 최소화
- 구현 시간 짧음
- 고객 임팩트 작음

**옵션 B: 균형 선택 (Medium Risk, Medium Reward)**
- 부분적 혁신 (예: 일부 기능만 AI 적용)
- 기술 부채와 혁신의 중간
- 구현 시간 중간
- 고객 임팩트 중간

**옵션 C: 공격적 선택 (High Risk, High Reward)**
- 완전한 혁신
- 새로운 기술 도입
- 구현 시간 길음
- 고객 임팩트 큼

<!-- 💬 옵션 생성의 함정
"이 옵션은 우리가 원하는 방향이니까 당연히 선택해야 한다"
는 함정입니다.
실제로는 위험-보상 트레이드오프를 비교하기 위해 의도적으로 옵션을 다양하게 만드세요.
-->

예시 (고객 문제 분류 엔진 개선):

**옵션 A: 규칙 기반 규칙 개선**
- 현재 정규표현식/키워드 기반 로직 개선
- 준비 시간: 1주
- 정확도 개선: 5-10%

**옵션 B: 오픈소스 모델 파인튜닝**
- Hugging Face 한국어 모델(KoBERT) 사용
- 고객사 데이터로 파인튜닝
- 준비 시간: 3주
- 정확도 개선: 20-30%
- 비용: 프리/저비용

**옵션 C: GPT-4 API + 파인튜닝**
- GPT-4 API 활용
- 프롬프트 엔지니어링 + 고급 파인튜닝
- 준비 시간: 4주
- 정확도 개선: 35-45%
- 비용: 월 1,000-5,000달러
- 의존성: OpenAI API 가용성
```

## Step 3: 평가 기준 설정 (Product Trio 합의)

### PM, Designer, Engineer가 공통으로 동의하는 기준
```
다음 기준으로 평가하세요:

**공통 기준 (PM/Designer/Engineer 모두):**
1. 고객 임팩트 (고객이 체감하는 가치)
2. 시간 대비 효과 (ROI, 구현 속도)
3. 기술 지속성 (3년 이상 유지 가능한가)

**PM 주도 기준:**
- 비즈니스 임팩트: 수익, 사용자 확대, 경쟁 우위
- 고객 만족도: NPS, 이탈율, 피드백
- 시장 타이밍: 언제까지 기다릴 수 있는가

**Designer 주도 기준:**
- 사용성: 초기 학습 시간, 오류율
- 브랜드 일관성: 기존 제품과 어울리는가
- 접근성: 모바일, 시각 장애인 등 고려

**Engineer 주도 기준:**
- 구현 가능성: 기술 부채, 레거시 코드와의 호환성
- 확장성: 사용자/데이터 10배 증가 시 대응 가능한가
- 유지보수성: 팀이 유지할 수 있는가

<!-- 💬 기준 설정의 중요성
기준 없이 점수를 매기면 누가 더 큰 소리를 내는지로 결정됩니다.
기준을 먼저 공개하고 합의한 뒤 점수를 매기세요.
-->

**점수 기준:**
- 0-2점: 매우 나쁨 (심각한 문제)
- 3-5점: 보통 (수용 가능하지만 개선 필요)
- 6-8점: 좋음 (충분히 만족)
- 9-10점: 우수 (최고의 선택)
```

## Step 4: 각 옵션 평가 (Product Trio 워크샵)

### 구조화된 평가
```
각 옵션을 다음 형식으로 평가하세요:

**옵션 A: [이름]**

PM 관점:
- 고객 임팩트: [0-10점]
  근거: [구체적 이유]
- 비즈니스 임팩트: [0-10점]
  근거: [구체적 이유]
- 시장 타이밍: [0-10점]
  근거: [구체적 이유]
- **PM 소계**: [평균 또는 가중 합계]
- PM 의견: [의사결정권자의 우려사항/추천]

Designer 관점:
- 사용성: [0-10점]
  근거: [구체적 이유]
- 브랜드 일관성: [0-10점]
  근거: [구체적 이유]
- 접근성: [0-10점]
  근거: [구체적 이유]
- **Designer 소계**: [평균 또는 가중 합계]
- Designer 의견: [의사결정권자의 우려사항/추천]

Engineer 관점:
- 구현 가능성: [0-10점]
  근거: [구체적 이유]
- 확장성: [0-10점]
  근거: [구체적 이유]
- 유지보수성: [0-10점]
  근거: [구체적 이유]
- **Engineer 소계**: [평균 또는 가중 합계]
- Engineer 의견: [의사결정권자의 우려사항/추천]

<!-- 💬 점수의 함정
점수 평균을 절대 내지 마세요.
"PM은 7점인데 Engineer는 2점"이면 이건 합의되지 않은 의사결정입니다.
토론을 통해 차이를 해결하고 합의된 최종 점수를 만드세요.
-->
```

## Step 5: 최종 의사결정

### 선택과 실행 계획
```
다음 형식으로 최종 의사결정을 문서화하세요:

**선택 옵션:** [옵션 B]

**의사결정 근거:**
1. Product Trio가 합의한 이유
2. 위험 허용 수준
3. 시장/고객 피드백

**실행 계획:**
- 담당자: [PM/Designer/Engineer]
- 시간: [예상 소요 시간]
- 성공 지표: [어떻게 성공을 측정할 것인가]
- 의존성: [다른 결정/팀과의 의존성]

**실패 시나리오:**
- 위험 1: [무엇이 잘못될 수 있는가]
  대응: [미리 준비할 조치]
- 위험 2: ...

**재평가 기한:**
- 다음 평가 날짜: [언제 다시 검토할 것인가]
- 변경 신호: [언제 이 결정을 바꿀 것인가]

<!-- 💬 의사결정 후 문서화가 가장 중요합니다
3개월 뒤에 "왜 이 결정을 했지?"를 방지하기 위해
근거, 위험, 실패 시나리오를 문서화하세요.
-->
```

---

## 예시 1: AI 고객 지원 플랫폼의 의사결정

### 의사결정: "이번 분기 핵심 기능은 자동 응답 정확도 개선에 집중할까, 아니면 멀티채널(이메일/Slack/카톡) 지원으로 확대할까?"

**옵션 A: 정확도 개선 (Deep Focus)**
- 현재 70% 정확도 → 90%로 개선
- 고급 파인튜닝, 도메인 특화 학습
- 시간: 8주
- PM 점수: 8/10 (고객 이탈 감소)
- Designer 점수: 7/10 (UI 복잡도 증가 없음)
- Engineer 점수: 9/10 (구현 간단)

**옵션 B: 멀티채널 지원 (Breadth Expansion)**
- 현재 웹/채팅 → 이메일, Slack, 카톡 추가
- 통합 API 개발, UX 어댑터
- 시간: 10주
- PM 점수: 9/10 (TAM 확대)
- Designer 점수: 6/10 (각 채널별 UX 최적화 필요)
- Engineer 점수: 6/10 (기술 부채 증가)

**옵션 C: 점진적 개선 (Balanced)**
- 정확도 80%로 개선 (4주)
- 이메일 + Slack 추가 (4주)
- 시간: 8주
- PM 점수: 8/10
- Designer 점수: 8/10
- Engineer 점수: 7/10

**최종 선택:** 옵션 C (Balanced)
- 근거: Product Trio 모두 8점 이상 동의
- 위험: 두 가지 모두 부분적으로 끝나면 후회할 수 있음
- 대응: 4주 뒤 검토하여 남은 4주를 어디에 할당할지 재결정
```

# 📋 의사결정 캔버스 템플릿

## 의사결정 카드

```
┌─ 의사결정 ID: [DECISION_001]
│
├─ 질문: [명확한 질문]
│
├─ 맥락:
│  ├─ 비즈니스: [왜 필요한가]
│  ├─ 기술: [현재 상태]
│  └─ 시장: [경쟁 상황]
│
├─ 옵션:
│  ├─ A: [보수적]
│  ├─ B: [균형]
│  └─ C: [공격적]
│
├─ 평가:
│  ├─ PM: [점수 + 의견]
│  ├─ Designer: [점수 + 의견]
│  └─ Engineer: [점수 + 의견]
│
├─ 최종 선택: [옵션 B]
│
├─ 실행 계획:
│  ├─ 담당자: [이름]
│  ├─ 시간: [예상 소요]
│  └─ KPI: [성공 지표]
│
├─ 위험 & 대응:
│  └─ [위험 1: 대응]
│
└─ 재평가 기한: [날짜]
```

💡 **Deep Tips:**
- 의사결정 캔버스는 1주일마다 업데이트하세요. 새로운 정보가 들어올 수 있습니다
- PM/Designer/Engineer의 점수가 2점 이상 차이나면 토론을 더 하세요. 합의되지 않은 의사결정은 실패합니다
- "모두가 동의했지만 결과가 나쁜" 의사결정도 기록하세요. 이건 의사결정 프로세스 개선으로 이어집니다
- 한국 AI 스타트업은 의사결정 속도가 빠르지만, 문서화는 적습니다. 느릴지라도 의사결정 과정을 기록하면 3개월 뒤 "왜?"라는 질문을 줄일 수 있습니다
```



### # 🇰🇷 한국 기업 의사결정 특화

```
한국 기업 의사결정 고려사항:

1. **결재 문화**:
   - 합의제 의사결정: 관련 부서 모두 동의 필요
   - → 의사결정 캔버스를 각 부서 관점에서 작성
   - "반대 의견"을 캔버스에 명시 → 결재 속도 향상

2. **데이터 기반 설득**:
   - 한국 임원: "국내 경쟁사가 하는가?" → 경쟁사 벤치마크 필수
   - "글로벌 트렌드 + 한국 시장 적용" 프레임이 효과적
   - DART 공시, 앱스토어 순위 등 공개 데이터 활용
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 의사결정 질문이 모호 | "어떻게"로 시작하는 구체적 질문으로 바꾸세요 |
| 3단계 | 옵션이 비교 불가능 | 같은 기준(비용, 시간, 품질 등)으로 통일해서 비교하세요 |
| 4단계 | 평가 기준 합의 어려움 | "우리가 가장 두려워하는 실패"를 기준에 포함하세요 |
| 6단계 | 결정 후 불안 | "30일 후 재검토 날짜"를 정하면 심리적 안전감이 높아집니다 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 의사결정 프로세스를 자동화하고 이력을 관리합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
의사결정은 기록이 중요합니다. 자동화하면 과거 결정의 이유와 결과를 추적할 수 있어, 같은 실수를 반복하지 않습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 스크립트: 의사결정 캔버스 자동 생성 및 평가

```python
#!/usr/bin/env python3
"""
의사결정 캔버스 자동 생성 및 Product Trio 협의 도구
- 의사결정 질문 정의
- 옵션 자동 생성
- Product Trio 평가 수집
- 최종 의사결정 문서화
"""

import json
from datetime import datetime
from anthropic import Anthropic

client = Anthropic()

class DecisionCanvas:
    def __init__(self, decision_id, question, context):
        self.decision_id = decision_id
        self.question = question
        self.context = context
        self.options = []
        self.evaluations = {}
        self.final_decision = None

    def generate_options(self):
        """AI가 3개의 옵션을 자동 생성"""
        prompt = f"""당신은 의사결정 컨설턴트입니다.

의사결정: {self.question}
맥락: {json.dumps(self.context, ensure_ascii=False, indent=2)}

위의 의사결정에 대해 다음 3가지 옵션을 생성하세요:
1. 보수적 선택 (Low Risk, Low Reward)
2. 균형 선택 (Medium Risk, Medium Reward)
3. 공격적 선택 (High Risk, High Reward)

각 옵션마다:
- 이름
- 설명 (2-3 문장)
- 구현 시간 (주 단위)
- 예상 고객 임팩트 (정성적)

JSON 형식으로 응답하세요."""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        try:
            # JSON 파싱
            text = response.content[0].text
            # JSON 블록 추출 (```json ... ```)
            start = text.find('{')
            end = text.rfind('}') + 1
            json_str = text[start:end]
            options_data = json.loads(json_str)
            self.options = options_data.get('options', [])
            print("✅ 옵션 생성 완료:")
            for i, opt in enumerate(self.options, 1):
                print(f"\n옵션 {i}: {opt.get('name', 'N/A')}")
                print(f"  설명: {opt.get('description', 'N/A')}")
                print(f"  시간: {opt.get('estimated_weeks', 'N/A')}주")
        except json.JSONDecodeError:
            print(f"옵션 생성 실패: {response.content[0].text}")

    def evaluate_option(self, option_index, role):
        """특정 역할(PM/Designer/Engineer)이 옵션을 평가"""
        if not self.options or option_index >= len(self.options):
            return None

        option = self.options[option_index]
        role_prompts = {
            "PM": """당신은 프로덕트 매니저입니다.
다음 옵션을 평가하세요:
- 비즈니스 임팩트 (0-10점)
- 고객 만족도 (0-10점)
- 시장 타이밍 (0-10점)

각 항목마다 점수와 근거를 제시하세요.""",
            "Designer": """당신은 디자이너입니다.
다음 옵션을 평가하세요:
- 사용성 (0-10점)
- 브랜드 일관성 (0-10점)
- 접근성 (0-10점)

각 항목마다 점수와 근거를 제시하세요.""",
            "Engineer": """당신은 엔지니어입니다.
다음 옵션을 평가하세요:
- 구현 가능성 (0-10점)
- 확장성 (0-10점)
- 유지보수성 (0-10점)

각 항목마다 점수와 근거를 제시하세요."""
        }

        prompt = f"""{role_prompts.get(role, '')}

옵션: {option.get('name', 'N/A')}
설명: {option.get('description', 'N/A')}

JSON 형식으로 응답하세요:
{{
  "scores": {{
    "criterion1": score,
    "criterion2": score,
    "criterion3": score
  }},
  "reasoning": "각 점수의 근거",
  "concern": "주요 우려사항",
  "recommendation": "이 역할의 추천"
}}"""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=1000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        try:
            text = response.content[0].text
            start = text.find('{')
            end = text.rfind('}') + 1
            json_str = text[start:end]
            evaluation = json.loads(json_str)

            if role not in self.evaluations:
                self.evaluations[role] = {}
            self.evaluations[role][option_index] = evaluation

            print(f"\n✅ {role} 평가 완료 (옵션 {option_index + 1}):")
            print(f"  평가: {json.dumps(evaluation['scores'], indent=2)}")
            print(f"  우려: {evaluation.get('concern', 'N/A')}")
            print(f"  추천: {evaluation.get('recommendation', 'N/A')}")

            return evaluation
        except json.JSONDecodeError:
            print(f"평가 파싱 실패: {response.content[0].text}")

    def synthesize_decision(self):
        """Product Trio 평가를 종합하여 최종 의사결정"""
        if not self.evaluations:
            print("평가 데이터가 없습니다. 먼저 evaluate_option을 실행하세요.")
            return

        synthesis_prompt = f"""당신은 의사결정 컨설턴트입니다.

다음은 Product Trio (PM, Designer, Engineer)의 평가입니다:
{json.dumps(self.evaluations, ensure_ascii=False, indent=2)}

의사결정: {self.question}

다음을 포함하여 최종 의사결정을 내려주세요:
1. 선택할 옵션 (번호)
2. 의사결정 근거 (Product Trio 합의)
3. 실행 계획 (담당자, 시간, KPI)
4. 위험 요소 및 대응 방안
5. 재평가 기한

JSON 형식으로 응답하세요."""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": synthesis_prompt}
            ]
        )

        try:
            text = response.content[0].text
            start = text.find('{')
            end = text.rfind('}') + 1
            json_str = text[start:end]
            self.final_decision = json.loads(json_str)

            print("\n" + "="*60)
            print("🎯 최종 의사결정")
            print("="*60)
            print(f"선택 옵션: {self.final_decision.get('selected_option', 'N/A')}")
            print(f"근거: {self.final_decision.get('rationale', 'N/A')}")
            print(f"실행 계획: {json.dumps(self.final_decision.get('execution_plan', {}), ensure_ascii=False, indent=2)}")
            print(f"위험 & 대응: {json.dumps(self.final_decision.get('risks', {}), ensure_ascii=False, indent=2)}")
            print(f"재평가 기한: {self.final_decision.get('review_date', 'N/A')}")
            print("="*60)

        except json.JSONDecodeError:
            print(f"최종 의사결정 파싱 실패: {response.content[0].text}")

    def export_canvas(self, filename):
        """의사결정 캔버스를 JSON 파일로 저장"""
        canvas_data = {
            "decision_id": self.decision_id,
            "question": self.question,
            "context": self.context,
            "options": self.options,
            "evaluations": self.evaluations,
            "final_decision": self.final_decision,
            "created_at": datetime.now().isoformat()
        }

        with open(filename, 'w', encoding='utf-8') as f:
            json.dump(canvas_data, f, ensure_ascii=False, indent=2)

        print(f"\n💾 의사결정 캔버스 저장: {filename}")


# 실행 예시
if __name__ == "__main__":
    decision = DecisionCanvas(
        decision_id="DECISION_001",
        question="AI 고객 지원 플랫폼에서 이번 분기 핵심 기능은 자동 응답 정확도 개선에 집중할까, 아니면 멀티채널 지원으로 확대할까?",
        context={
            "business": "고객 지원 플랫폼 (Series A, 월 10만 달러 MRR)",
            "current_metrics": {
                "accuracy": "70%",
                "channels": ["web", "chat"],
                "customer_satisfaction": 4.2
            },
            "market": {
                "competitors": ["Intercom", "Zendesk"],
                "market_trend": "멀티채널 지원 수요 증가 (고객 피드백 90%)"
            },
            "team": {
                "engineers": 5,
                "capacity_weeks": 8
            }
        }
    )

    # Step 1: 옵션 생성
    print("📋 Step 1: 옵션 생성")
    decision.generate_options()

    # Step 2: Product Trio 평가
    print("\n🎯 Step 2: Product Trio 평가")
    for option_idx in range(len(decision.options)):
        print(f"\n--- 옵션 {option_idx + 1} 평가 ---")
        decision.evaluate_option(option_idx, "PM")
        decision.evaluate_option(option_idx, "Designer")
        decision.evaluate_option(option_idx, "Engineer")

    # Step 3: 최종 의사결정
    print("\n✅ Step 3: 최종 의사결정")
    decision.synthesize_decision()

    # Step 4: 저장
    decision.export_canvas("decision_canvas_001.json")
```

### Claude Code CLI 실행
```bash
cd /path/to/ai-pm-prompts
claude code --exec decision-canvas.py --model claude-opus-4-6
```

---

## 📊 실행 결과 예시

### 의사결정 카드

```
┌─ 의사결정 ID: DECISION_001
│
├─ 질문: "AI 고객 지원 플랫폼에서 이번 분기(8주) 핵심 기능은?
│         A) 자동 응답 정확도 70% → 90%
│         B) 멀티채널 지원 추가 (이메일, Slack, 카톡)
│         C) 둘 다 부분적으로 개선"
│
├─ 맥락:
│  ├─ 비즈니스: Series A, 월 MRR 10만 달러, 이탈율 증가세 (5%)
│  ├─ 기술: 현재 웹/채팅만 지원, 정확도 70%, 팀 5명
│  └─ 시장: 경쟁사(Zendesk, Intercom) 모두 멀티채널, 고객 요청 90%는 멀티채널
│
├─ 옵션:
│  ├─ A: 정확도 개선 (Deep Focus)
│  │  └─ PM: 8/10 | Designer: 7/10 | Engineer: 9/10 → 평균 8.0
│  │
│  ├─ B: 멀티채널 확대 (Breadth Expansion)
│  │  └─ PM: 9/10 | Designer: 6/10 | Engineer: 6/10 → 평균 7.0
│  │
│  └─ C: 점진적 개선 (Balanced)
│     └─ PM: 8/10 | Designer: 8/10 | Engineer: 7/10 → 평균 7.7
│
├─ 최종 선택: 옵션 C (Balanced)
│  근거: Product Trio 모두 최소 7점 이상
│        고객 요청(멀티채널)과 기술 부채(정확도) 균형
│
├─ 실행 계획:
│  ├─ 담당자: PM(제품 로드맵) / Designer(UX) / Engineer(API)
│  ├─ 구성: 4주(정확도 80%) + 4주(이메일+Slack)
│  └─ KPI: 정확도 80% 달성 + 채널당 0.1 MRR
│
├─ 위험 & 대응:
│  ├─ 위험 1: 두 가지 모두 부분적 완성으로 고객 만족도 개선 못함
│  │  대응: 4주 뒤 검토하여 남은 4주 할당 결정 (Accuracy vs Slack)
│  │
│  ├─ 위험 2: 이메일 API 통합에 예상보다 시간 소요
│  │  대응: 3주 말 검토, 필요시 Slack만 선택 후 이메일은 Q2로 미루기
│  │
│  └─ 위험 3: 정확도 개선이 80%에 머무르면 고객 불만
│     대응: 초기 5일간 프로토타입 검증, 80% 달성 불가능하면 즉시 옵션 B로 전환
│
└─ 재평가 기한: 4주 뒤 (스프린트 종료 시)
   변경 신호: 고객 5명 이상이 멀티채널 요청 / 정확도 개선 불가능 확인 / 경쟁사 대응
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 캔버스에 '되돌릴 수 있는 결정 vs 되돌릴 수 없는 결정' 구분이 있는지 확인하세요
2. **[논쟁 지점]** 의사결정에서 '데이터 부족 시' 직관을 얼마나 허용할지는 결정의 가역성에 따라 다릅니다
3. **[자기 검증]** 결정의 '최악의 시나리오'를 시뮬레이션하고, 감당 가능한 수준인지 확인하세요

---

## 🔗 다음 단계

| 프롬프트 | 목적 | 연결 |
|---|---|---|
| `positioning-strategy.md` | 포지셔닝에 기반한 의사결정 맥락 정보 제공 | 의사결정 전 포지셔닝 명확화 |
| `feature-prioritization.md` | 선택된 옵션(기능)의 우선순위 결정 | 의사결정 후 실행 계획 |
| `backlog-prioritization.md` | 우선순위화된 기능을 백로그 스토리로 분해 | 스프린트 실행 단위로 변환 |
| `sprint-kickoff.md` | 백로그를 스프린트 계획으로 전환 | 팀 실행 시작 |
