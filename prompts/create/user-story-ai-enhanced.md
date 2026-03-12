# 🤖 AI 강화 유저 스토리 (User Story AI-Enhanced Acceptance Criteria)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 35분+ (Build)
> 워크플로우: ← `user-story.md` ← `user-story-splitting.md` → `prd-for-ai-feature.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 기능의 수용 기준은 일반 소프트웨어와 근본적으로 다릅니다.
정확도(accuracy), 신뢰도(confidence), 편향(bias) 같은 ML 메트릭과 사용자 경험을 균형잡아야 합니다.
**AI Acceptance Criteria 패턴**으로 AI 기능을 마치 일반 기능처럼 측정 가능하게 정의하세요.

---

## 📥 이전 프롬프트에서 받는 입력

> `user-story.md`에서 생성된 스토리에 AI 특화 수용 기준을 추가할 때 연결됩니다.

이전 프롬프트 결과에서 **유저 스토리, AI 기능 설명, 정확도 요구사항**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 AI 기능 특화 유저 스토리를 작성할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
AI 기능 스토리를 입력하세요:
"As a [user], I want to [AI 기능], So that [가치]"

자동으로 추가할 수용 기준:
1. 정확도 (Accuracy): [X% 이상]
2. 신뢰도 (Confidence): [Y% 미만 reject]
3. 편향 (Bias): [그룹별 공정성]
4. 성능 (Performance): [응답 시간]
5. 폴백 (Fallback): [실패 시 대응]
6. 피드백 루프 (Feedback): [사용자 개선]
```

💡 **Quick Tips:**
- 정확도는 "비즈니스 영향"으로 결정하세요 (의료 95%, 추천 70%)
- 신뢰도는 "거짓 긍정"의 비용으로 결정하세요
- 폴백은 필수입니다 (AI가 100% 완벽할 수 없으므로)


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| AI 기술 이해 부족 | "사용자 관점"에서 작성하세요. 기술 세부사항은 엔지니어와 별도 정의 |
| 정확도 목표를 모르겠음 | "현재 수동 작업 대비 최소한 동등해야 한다"부터 시작 |
| AI 실패 시나리오가 다양 | "가장 빈번한 실패 3가지"에 대한 대안만 먼저 정의 |
| 일반 스토리와의 차이를 모르겠음 | 핵심 차이: 결과의 불확실성. "항상 같은 결과"가 아님을 전제로 작성 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — AI 기능의 유저 스토리에 신뢰도, 실패 처리, 모델 요구사항을 포함하고 싶은 분입니다.
AI 특유의 불확실성을 스토리에 반영하고 싶다면 이걸 써보세요.

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


### # 역할

AI 제품 매니저, ML 엔지니어, 데이터 사이언티스트, 제품 설계자

### # 목표

**AI 기능을 측정 가능하고 검증 가능하게 정의**

- ML 메트릭(accuracy, precision, recall)을 비즈니스 메트릭으로 번역
- 사용자 경험 기준(latency, UI feedback)과 ML 기준 균형
- 편향과 공정성을 명시적으로 테스트
- 개선 루프와 모니터링을 처음부터 설계

<!-- 💬 AI 기능이 왜 다른가?
일반 기능: "버튼을 누르면 데이터가 저장된다" → 100% 또는 0% (일어나거나 안 일어나거나)
AI 기능: "모델이 고객을 분류한다" → 80% 정확도... 그런데 "80%"는 어느 그룹에서?
          어느 타입의 에러? (False Positive vs False Negative)

이 모호함을 해결하지 않으면:
- 엔지니어는 "모델 학습 완료"라고 생각
- PM은 "기능이 작동하지 않음"이라고 생각
- 사용자는 "AI가 나를 무시한다"고 생각
-->

### # 6가지 AI Acceptance Criteria 패턴

#### 1. 정확도 (Accuracy)

<!-- 💬 [전문가의 눈] 정확도 기준을 정할 때 가장 흔한 실수:
PM: "정확도는 95%이면 좋을 것 같아"
엔지니어: "95%는 뭘 기준으로?"
정확도 95%는 다를 수 있다:
- 전체 샘플의 95%가 맞는 것인가? (Accuracy)
- 양성 예측의 95%가 맞는 것인가? (Precision)
- 실제 양성의 95%를 잡는 것인가? (Recall)
따라서 "Accuracy 95%, Precision 90%, Recall 85%"처럼 세 가지를 모두 명시해야 한다.
-->

모델이 **올바른 예측**을 해야 하는 기준입니다.

```
패턴:
[ ] 모델은 [테스트 셋]에서 최소 [X]% 정확도를 달성한다
[ ] 수행하는 작업: [구체적 분류/회귀/순위 작업]
[ ] 평가 기준: [비즈니스 메트릭]

예시: 고객 이탈 예측
[ ] 모델은 테스트 셋에서 최소 85% 정확도를 달성한다
[ ] 고객을 "이탈 위험", "정상" 2가지로 분류한다
[ ] 평가 기준: 마케팅 개입 성공률이 최소 70% 이상이어야 함

왜 85%인가?
- 의료/금융: 95%+ (높은 비용의 에러)
- 분류/추천: 80-90% (중간 비용)
- 검색 순위: 70-80% (사용자가 다시 검색 가능)
```

<!-- 💬 정확도 기준 결정 방법:
1. 비즈니스 임팩트를 계산하세요
   - False Positive의 비용: "이탈하지 않은 고객을 대상으로 비싼 캠페인"
   - False Negative의 비용: "실제 이탈 고객을 놓침"
2. 어느 쪽이 더 비싼가?
3. 그 비용을 허용할 수 있는 수준의 정확도 설정
-->

#### 2. 신뢰도 (Confidence Score & Threshold)

<!-- 💬 [논쟁 지점] 신뢰도 임계값(Confidence Threshold)은 제품 성향에 따라 다르다.
보수적 제품 (금융, 의료): 신뢰도 90% 이상만 사용 → 거절 많음 → 정확도 높음, 커버리지 낮음
공격적 제품 (추천, 마케팅): 신뢰도 60% 이상 사용 → 더 많이 자동화 → 일부 틀림, 커버리지 높음
한국 기업의 특성: 안정성을 선호하므로 "보수적" 쪽으로 가는 경향. 초기에는 높은 임계값에서 시작해서 점진적으로 낮추는 전략 권장.
-->

모델이 **확신하지 못한 예측**은 거부해야 합니다.

```
패턴:
[ ] 모델이 신뢰도 [Y]% 이하인 예측은 거부한다
[ ] 거부된 경우 [폴백 액션]을 수행한다

예시: 고객 감정 분석
[ ] 모델이 신뢰도 70% 이하인 감정은 "판단 불가"로 반환한다
[ ] 판단 불가인 경우 고객 지원팀이 수동으로 검토한다

왜 필요한가?
- 모든 예측이 같은 "신뢰도"를 가지진 않습니다
- 신뢰도가 낮으면, 틀릴 확률이 높으므로 사람이 개입해야 합니다
```

#### 3. 편향 & 공정성 (Bias & Fairness)

<!-- 💬 [자기 검증] 편향 테스트를 설계한 후 꼭 확인할 사항:
1. "테스트할 민감 속성(sensitive attributes)이 모두 포함되었는가?" (성별, 나이, 지역, 종교 등)
2. "각 그룹의 샘플 크기가 충분한가?" → 소수 그룹은 샘플 부족 가능성
3. "공정성 메트릭의 정의가 명확한가?" → "5% 이하 차이"는 어떻게 측정할 것인가?
4. "공정성과 정확도의 트레이드오프를 인정했는가?" → 완벽한 공정성은 정확도 손실 가능
한국은 장애인차별금지법, 성차별금지법이 있어서 편향 검사가 법적 의무로 강화되는 추세.
-->

모델이 **특정 그룹**에 대해 차별하지 않아야 합니다.

```
패턴:
[ ] [Group A]와 [Group B] 간의 성능 차이가 [Z]% 이하다
[ ] 성능 메트릭: [무엇을 측정할 것인가]

예시: 신용 대출 심사 모델
[ ] 남성과 여성 승인율의 차이가 5% 이하여야 한다
[ ] 연령대별로도 성능 차이가 5% 이하여야 한다
[ ] 거주 지역별로도 차별이 없어야 한다

측정 방법:
- 각 그룹별 Accuracy
- 각 그룹별 False Positive Rate (FPR)
- 각 그룹별 False Negative Rate (FNR)
- 각 그룹별 Positive Prediction Rate (PPR)
```

<!-- 💬 편향 테스트가 왜 필수인가?
1. 법적 의무: 많은 국가에서 알고리즘 차별 금지
2. 윤리적 책임: AI의 영향을 받는 사람들에게
3. 사용자 신뢰: 공정하지 않은 AI는 사용 거부당함
4. 장기 비즈니스: 스캔들이 되면 브랜드 훼손
-->

#### 4. 성능 & 레이턴시 (Performance)

<!-- 💬 [전문가의 눈] 응답 시간(Latency) 요구사항을 정할 때는 "사용자 컨텍스트"를 고려해야 한다.
실시간 채팅: 500ms 이내 (안 그러면 이상함)
배경 처리 (야간): 10초 이상 가능 (사용자가 기다리지 않음)
모바일 환경: PC보다 1.5-2배 느림 허용 (네트워크 지연)
따라서 "응답 시간 200ms"는 "평균 응답 시간 200ms, 모바일 상에서 300ms, P95 레이턴시 500ms"처럼 분명히 명시해야 한다.
-->

사용자는 AI 기능을 **빠르게** 경험해야 합니다.

```
패턴:
[ ] 모델 추론 시간은 [L] ms 이하여야 한다
[ ] p95 레이턴시 (95%의 요청)는 [L2] ms 이하여야 한다
[ ] 동시 요청 [C]개를 처리할 수 있어야 한다

예시: 실시간 감정 분석
[ ] 평균 추론 시간 200ms 이하
[ ] p95 레이턴시 500ms 이하
[ ] 초당 100개 요청 동시 처리

왜 필요한가?
- AI 기능이 정확해도 느리면 사용 안 함
- 사용자 기준: "3초 이내에 결과"
- 서버 비용: 더 빠를수록 GPU 필요성 낮아짐
```

#### 5. 폴백 & 에러 처리 (Fallback)

AI가 **실패했을 때**의 사용자 경험입니다.

```
패턴:
[ ] 모델이 에러를 반환하면 [Fallback Action]을 수행한다
[ ] 사용자에게 [메시지]를 표시한다
[ ] 실패 사유를 로깅하고 개선 데이터로 사용한다

예시: 자동 이미지 태깅
[ ] 이미지 태그 모델이 실패하면, 기본 태그 ("일반")를 할당
[ ] 사용자에게 "자동 태깅 실패. 수동으로 입력해주세요"라고 안내
[ ] 실패 이미지를 데이터셋에 수집, 모델 학습에 사용

왜 필요한가?
- 100% 정확한 AI는 없습니다
- 사용자가 막혀있으면 안 됩니다
- 실패 사례가 모델 개선 데이터입니다
```

#### 6. 피드백 & 학습 루프 (Feedback Loop)

**실시간**으로 모델을 개선할 수 있어야 합니다.

```
패턴:
[ ] 사용자가 [피드백 액션]을 취할 수 있다 (예: "이건 틀렸어", "좋아요")
[ ] 피드백은 [수집 방식]으로 저장된다
[ ] 최소 [주기]마다 모델을 재학습한다

예시: 추천 시스템
[ ] 사용자가 "이 추천 마음에 안 들어요" 버튼을 클릭 가능
[ ] 피드백은 DynamoDB에 저장되고 Firehose로 S3로 전달
[ ] 매주 새로운 데이터로 모델을 재학습
[ ] 매월 A/B 테스트로 성능 검증

왜 필요한가?
- 사용 패턴이 변함 (모델은 정적)
- 사용자 피드백이 진짜 신호 (레이블 없는 데이터보다 정확)
- 지속적 개선만이 경쟁력
```

### # 패턴 통합: 완전한 AI User Story

```
원본 스토리:
As a 고객 지원팀,
I want to 고객 이메일을 자동으로 분류하기를
(Support, Billing, Feature Request, Bug Report)
So that 각 팀에 빠르게 라우팅할 수 있다.

AI-Enhanced 수용 기준:

## 1. 정확도 (Accuracy)
[ ] 모델은 테스트 셋에서 최소 90% 정확도를 달성한다
    (Support, Billing, Feature, Bug 4가지 카테고리)
[ ] 평가 기준: 각 카테고리 F1 스코어가 0.85 이상

## 2. 신뢰도 (Confidence)
[ ] 신뢰도가 80% 미만인 이메일은 "검토 필요"로 표시된다
[ ] 검토 필요 이메일은 Support 매니저에게 우선 할당된다

## 3. 편향 (Fairness)
[ ] 영어와 한글 이메일 간 성능 차이가 5% 이하여야 한다
[ ] 길이 (짧은 vs 긴 이메일)에 따른 성능 차이가 5% 이하여야 한다

## 4. 성능 (Performance)
[ ] 한 이메일 분류 시간: 평균 100ms, p95 300ms
[ ] 초당 최소 50개 이메일 동시 처리

## 5. 폴백 (Fallback)
[ ] 모델이 에러를 반환하면 "General Support" 카테고리로 할당
[ ] 사용자에게 "분류 실패. 수동으로 배정됩니다" 알림

## 6. 피드백 & 학습 (Feedback Loop)
[ ] Support 팀이 "이 분류 틀렸어" 버튼을 클릭 가능
[ ] 피드백은 매주 수집되어 모델 학습 데이터로 사용
[ ] 매월 새 모델을 배포하고, 정확도를 모니터링

이렇게 하면:
✓ 엔지니어는 뭘 만들어야 하는지 명확
✓ PM은 성공 여부를 측정 가능
✓ 사용자는 "거의 작동하는" 기능을 얻음
✓ 팀은 지속적으로 개선할 수 있음
```

### # 한국 SaaS AI 유저 스토리 특화

```
한국 시장 AI 기능의 수용 기준 작성 시 추가 고려사항:

1. **한국어 유저 스토리 작성 패턴**:
   - 기본 패턴: "As a [역할], I want to [기능], So that [가치]"
   - 한국식 추가: "When [상황], Then [결과를 한글로 명확히]"
   - 예시: "직원이 고객 피드백을 읽을 때, 감정 분석 결과가 '긍정/부정/중립' 3가지로 명확히 분류되어야 한다"
   - 주의: 영어 스토리를 번역하지 말고, 한국 사용자의 실제 업무 프로세스에서 시작

2. **한국 AI 서비스의 사용자 페르소나 특성**:
   - IT 리터러시 양극화: 매우 높음 vs 매우 낮음 (중간 없음)
   - 보수적 성향: AI 결과를 의심 (100% 믿지 못함) → 설명 가능성 필수
   - 품질 기준 높음: "약간 부정확"하면 즉시 포기 → 95%+ 정확도 필요
   - 애프터 서비스 기대: AI가 틀렸을 때 고객센터 지원 기대

3. **한국 접근성 기준 (장애인차별금지법, 웹접근성 인증)**:
   - AI 결과가 시각 장애자도 이해할 수 있어야 함 (음성 설명)
   - AI 기능이 마우스 없이도 키보드만으로 작동
   - 색상만으로 정보 전달 금지 (색약자 고려)
   - Acceptance Criteria 예시: "시각 장애자가 스크린 리더로 AI 추천 결과를 읽을 수 있어야 한다"

4. **한국 시장 수용 기준(Acceptance Criteria) 패턴**:
   - 글로벌: "정확도 85%" (단순)
   - 한국: "정확도 85% + 신뢰도 70% 이상만 사용 + 틀린 항목은 3초 내 수정 가능" (구체적)
   - 한국 기업은 "예외 처리"를 매우 중요하게 봄
   - Criteria 작성 시 "실패 시나리오"를 명시적으로 포함

5. **한국 개인정보보호법(PIPA) 반영**:
   - Acceptance Criteria에 "동의 관리" 항목 필수
   - 예시: "[ ] 사용자가 AI 학습을 위한 데이터 수집에 명시적으로 동의해야 한다"
   - 예시: "[ ] 사용자는 언제든 피드백 데이터 삭제를 요청할 수 있어야 한다"

6. **한국식 협업 문화 반영**:
   - User Story를 작성할 때 법무팀, 보안팀, CS팀도 참여해야 함
   - 이해관계자별 Acceptance Criteria:
     * PM: "비즈니스 성공 기준" (채택율, 수익 기여도)
     * 엔지니어: "기술 기준" (정확도, 응답 시간, 데이터 파이프라인)
     * 법무: "규정 준수" (개인정보, 차별 금지)
     * CS: "고객 만족" (쉬운 폴백, 설명 가능성)
```


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | AI 사용자 시나리오 정의 어려움 | "AI가 없었을 때 사용자는 어떻게 했나?"에서 시작 |
| 2단계 | 신뢰도 기준 정의 어려움 | "사용자가 이 결과를 믿고 행동할 수 있는가?"로 판단 |
| 3단계 | AI 수용 기준이 복잡 | "정확도 + 응답 시간 + 실패 시 대안" 3가지만 필수 |
| 4단계 | 비기능 요구사항 누락 | "데이터 프라이버시", "편향 검사" 항목을 체크하세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — AI 기능 스토리 생성과 품질 검증을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
AI 기능은 일반 기능보다 수용 기준이 복잡합니다 (정확도, 응답 시간, 실패 처리 등). 자동화하면 필수 항목 누락을 방지합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### AI Acceptance Criteria 생성기

```python
#!/usr/bin/env python3
"""
AI User Story의 수용 기준 자동 생성
6가지 AI 메트릭 패턴 기반
"""

import anthropic
import json
from typing import Optional
from dataclasses import dataclass


@dataclass
class AIAcceptanceCriteria:
    """AI 수용 기준"""
    accuracy: Optional[dict]
    confidence: Optional[dict]
    bias: Optional[dict]
    performance: Optional[dict]
    fallback: Optional[dict]
    feedback_loop: Optional[dict]


def generate_ai_acceptance_criteria(
    ai_task: str,
    ai_model_type: str,  # "classification", "regression", "nlp", "cv"
    business_impact: str,  # "high", "medium", "low"
    target_users: str,
    constraints: Optional[str] = None
) -> dict:
    """
    AI 기능을 위한 수용 기준 자동 생성

    Args:
        ai_task: AI 작업 설명 (예: "이메일 분류")
        ai_model_type: 모델 타입
        business_impact: 비즈니스 영향도 ("high" → 95% 정확도, "low" → 75%)
        target_users: 대상 사용자
        constraints: 추가 제약사항

    Returns:
        6가지 패턴별 수용 기준
    """

    client = anthropic.Anthropic()

    accuracy_threshold = {
        "high": "95%",      # 의료, 금융
        "medium": "85-90%",  # 분류, 추천
        "low": "70-80%"      # 검색, 순위
    }.get(business_impact, "85%")

    prompt = f"""당신은 AI 제품 관리 전문가입니다.
다음 AI 기능을 위한 수용 기준을 생성하세요.

**AI 기능:**
- 작업: {ai_task}
- 모델 타입: {ai_model_type}
- 비즈니스 영향도: {business_impact}
- 대상 사용자: {target_users}
{f'- 제약: {constraints}' if constraints else ''}

**6가지 AI 수용 기준 패턴으로 작성:**

1. **정확도 (Accuracy)**
   - 정확도 목표: {accuracy_threshold}
   - 측정 방법: [구체적 메트릭]
   - 테스트 셋: [어떤 데이터]

2. **신뢰도 (Confidence Score & Threshold)**
   - 신뢰도 임계값 설정
   - 거부 시 폴백 액션

3. **편향 & 공정성 (Bias & Fairness)**
   - 그룹별 성능 차이 허용도
   - 테스트할 그룹: [예: 성별, 나이, 지역]

4. **성능 & 레이턴시 (Performance)**
   - 평균 추론 시간
   - p95 레이턴시
   - 동시 처리 용량

5. **폴백 & 에러 처리 (Fallback)**
   - 실패 시 대응 방안
   - 사용자 메시지

6. **피드백 & 학습 루프 (Feedback Loop)**
   - 피드백 수집 방식
   - 재학습 주기
   - 모니터링 방법

JSON 형식으로 작성하세요. 한글입니다.

{{
  "accuracy": {{
    "target": "X%",
    "metrics": ["metric1", "metric2"],
    "test_data": "설명",
    "justification": "왜 이 정확도인가"
  }},
  "confidence": {{
    "threshold": "Y%",
    "fallback_action": "거부 시 액션",
    "user_message": "사용자에게 보여줄 메시지"
  }},
  "bias": {{
    "test_groups": ["그룹1", "그룹2"],
    "performance_gap_tolerance": "Z%",
    "metrics_to_check": ["accuracy", "fpr", "fnr"]
  }},
  "performance": {{
    "average_latency_ms": "X",
    "p95_latency_ms": "Y",
    "concurrent_requests": "Z/sec"
  }},
  "fallback": {{
    "error_handling": "실패 시 동작",
    "user_experience": "사용자 경험",
    "logging": "로깅 방법"
  }},
  "feedback_loop": {{
    "collection_method": "피드백 수집 방식",
    "retraining_frequency": "재학습 주기",
    "monitoring": "모니터링 메트릭"
  }}
}}
"""

    message = client.messages.create(
        model="claude-opus-4-6",
        max_tokens=2000,
        messages=[{"role": "user", "content": prompt}]
    )

    try:
        import re
        json_match = re.search(r'\{.*\}', message.content[0].text, re.DOTALL)
        if json_match:
            criteria = json.loads(json_match.group())
        else:
            criteria = {"raw": message.content[0].text}
    except json.JSONDecodeError:
        criteria = {"raw": message.content[0].text}

    return {
        "ai_task": ai_task,
        "model_type": ai_model_type,
        "business_impact": business_impact,
        "acceptance_criteria": criteria,
        "tokens_used": message.usage.output_tokens
    }


def generate_test_plan(acceptance_criteria: dict) -> dict:
    """
    수용 기준으로부터 테스트 계획 자동 생성
    """
    tests = {
        "accuracy_tests": [
            f"Dataset 테스트 (정확도: {acceptance_criteria.get('accuracy', {}).get('target')})",
            "각 클래스별 성능 검증",
            "에지 케이스 테스트"
        ],
        "confidence_tests": [
            f"신뢰도 임계값 검증 ({acceptance_criteria.get('confidence', {}).get('threshold')})",
            "저신뢰도 예측 처리",
            "거짓 양성(False Positive) 분석"
        ],
        "bias_tests": [
            "그룹별 성능 격차 측정",
            "공정성 메트릭 계산",
            "규정 준수 검증"
        ],
        "performance_tests": [
            f"레이턴시 측정 (목표: {acceptance_criteria.get('performance', {}).get('average_latency_ms')}ms)",
            "부하 테스트 (동시 요청 처리)",
            "메모리 사용량 모니터링"
        ],
        "integration_tests": [
            "실제 프로덕션 데이터로 테스트",
            "폴백 액션 동작 확인",
            "모니터링 대시보드 검증"
        ]
    }

    return tests


if __name__ == "__main__":
    # 예제
    result = generate_ai_acceptance_criteria(
        ai_task="고객 이메일을 Support/Billing/Feature/Bug 4가지로 자동 분류",
        ai_model_type="classification",
        business_impact="high",
        target_users="고객 지원팀",
        constraints="초당 50개 이메일 처리, 한글/영어 모두 지원"
    )

    print(json.dumps(result, ensure_ascii=False, indent=2))

    # 테스트 계획 생성
    if "acceptance_criteria" in result:
        test_plan = generate_test_plan(result["acceptance_criteria"])
        print("\n=== TEST PLAN ===")
        print(json.dumps(test_plan, ensure_ascii=False, indent=2))
```

### Claude Code CLI 사용법

```bash
# AI 수용 기준 생성
claude run ai-criteria-generator.py \
  --task "고객 이메일 분류" \
  --model-type classification \
  --impact high \
  --users "고객 지원팀" \
  --output ai_criteria.json

# 테스트 계획 생성
claude run test-planner.py --criteria ai_criteria.json --output test_plan.md

# 편향 테스트 실행
claude run bias-testing.py --model-path ./model.pkl --test-data fairness_dataset.csv
```

---

## 📊 실행 결과 예시

### Input

```
AI 기능: 신용카드 승인 여부 자동 심사
모델 타입: Binary Classification
비즈니스 영향도: High (금융 상품)
대상 사용자: 신용 심사팀, 고객
제약: 한국 ISMS 준수, 설명 가능성 필수
```

### Output: AI 수용 기준

```markdown
## AI Acceptance Criteria

### 1. 정확도 (Accuracy)
[ ] 모델은 테스트 셋에서 최소 95% 정확도를 달성한다
    - Precision: 94% 이상 (거짓 승인 최소화)
    - Recall: 93% 이상 (진정한 고객 승인)
    - F1 Score: 0.935 이상

[ ] 평가 데이터: 지난 1년 실제 심사 결과 10,000건

왜 95%인가?
- False Positive (거짓 승인): 대손 리스크 $$$$
- False Negative (거짓 거부): 좋은 고객 이탈 $$$
- 금융 상품이므로 높은 정확도 필수

### 2. 신뢰도 (Confidence Score)
[ ] 신뢰도 85% 미만인 심사는 "전문가 검토 필요"로 표시
[ ] 전문가 검토 건수는 전체의 10% 이하여야 함

예시:
- 신뢰도 95% → 자동 승인/거부
- 신뢰도 75% → 전문가 검토
- 신뢰도 60% → 거부 + 이의 신청 안내

### 3. 편향 & 공정성 (Bias & Fairness)
[ ] 성별(남/여) 간 승인율 차이: 5% 이하
[ ] 연령대(20대/30대/40대/50대+) 간 차이: 3% 이하
[ ] 지역(서울/지방/해외) 간 차이: 5% 이하
[ ] 직업(임직원/프리랜서/자영업) 간 차이: 5% 이하

검증 방법:
- 각 그룹별 Precision, Recall 측정
- Statistical Parity Difference < 5%
- Equalized Odds Difference < 5%

### 4. 성능 (Performance)
[ ] 한 신청서 심사 시간: 평균 50ms, p95 150ms
[ ] 동시 요청 처리: 초당 1,000건
[ ] 모델 응답률: 99.9% (오류율 0.1% 이하)

인프라:
- GPU 서버 2대 (부하 분산)
- 캐시: Redis (최근 심사 내역)
- 모니터링: CloudWatch (실시간)

### 5. 폴백 (Fallback)
[ ] 모델이 에러를 반환하면 "전문가 검토" 큐에 추가
[ ] 사용자에게 "신청 접수됨. 1-2일 내 검토 결과 안내" 메시지

에러 사유 기록:
- 데이터 불일치
- 모델 에러
- 시스템 오류

### 6. 피드백 & 학습 (Feedback Loop)
[ ] 전문가가 "모델 판단이 틀렸다"는 피드백 입력 가능
[ ] 피드백은 데이터베이스에 저장되고, 매주 자동 수집

재학습:
- 주기: 매월 (또는 피드백 1,000건 도달 시)
- 데이터: 지난 1개월 피드백 + 실제 심사 결과
- 검증: 테스트 셋으로 정확도 재검증 (95% 이상 필수)
- 배포: A/B 테스트 후 점진적 트래픽 증가 (10% → 50% → 100%)

모니터링:
- 일일: 정확도, 신뢰도 분포, 에러율
- 주간: 그룹별 공정성 메트릭
- 월간: 전체 성능 리뷰 + 모델 업데이트

## 시간표

Week 1: 모델 개발, 정확도 95% 달성
Week 2: 편향 테스트, 공정성 검증
Week 3: 성능 최적화, 레이턴시 목표 달성
Week 4: 테스트, 심사팀 교육, 베타 출시
Week 5: 피드백 수집, 모니터링 설정
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** AI 수용 기준에 'fallback 시나리오'가 있는지 확인하세요 — AI가 실패했을 때 사용자 경험
2. **[논쟁 지점]** AI 수용 기준의 '정확도 임계값'을 어디로 잡을지는 사용 맥락에 따라 다릅니다
3. **[자기 검증]** AI 수용 기준을 QA 엔지니어에게 보여주고 '이걸로 테스트 케이스를 만들 수 있나?'를 확인하세요

---

## 🔗 다음 단계

1. **`prd-for-ai-feature.md`** → 전체 AI 기능 PRD 작성
2. **테스트 계획** → 자동 정확도/편향 테스트 구현
3. **모니터링 대시보드** → 실시간 모델 성능 추적
4. **피드백 시스템** → 사용자 피드백 수집 및 재학습 자동화
