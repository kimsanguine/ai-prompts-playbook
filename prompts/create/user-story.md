# 📖 유저 스토리 작성 (User Story Writing Guide)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 30분+ (Build)
> 워크플로우: → `user-story-mapping.md` → `user-story-splitting.md` → `user-story-ai-enhanced.md`

---

## 🎯 이 프롬프트가 해결하는 문제

엔지니어와 제품팀 간 요구사항 격차를 줄이기 위해 **효과적인 유저 스토리**를 작성해야 합니다.
3C's(Card, Conversation, Confirmation) + INVEST 원칙을 기반으로 품질 높은 스토리를 체계적으로 생성하세요.
이는 팀의 협업 효율과 제품 품질을 직접 향상시킵니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `prd-for-ai-feature.md`의 PRD를 스프린트에서 실행 가능한 유저 스토리로 분해할 때 연결됩니다.

이전 프롬프트 결과에서 **기능 설명, 타겟 페르소나, 수용 기준**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 INVEST 원칙을 따르는 유저 스토리를 작성할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
다음 정보로 유저 스토리를 작성하세요.
- 페르소나: [예: "데이터 분석가 민지"]
- 하고 싶은 일: [예: "대시보드에서 월별 매출 추이를 본다"]
- 이유: [예: "경영진 보고서를 빠르게 준비하고 싶어"]

형식:
**As a** [페르소나], **I want to** [행동], **So that** [가치]

**수용 기준:**
1. [구체적 조건]
2. [측정 가능한 결과]
3. [엣지 케이스]
```

💡 **Quick Tips:**
- "역할"과 "가치"를 명확히 하면 나머지는 자동으로 따라옵니다
- 5분 안에 끝낼 수 있는 가장 핵심적인 스토리부터 시작하세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 스토리가 너무 큼 | [user-story-splitting.md](user-story-splitting.md)로 분할하세요 |
| 수용 기준 작성이 어려움 | "Given-When-Then" 형식으로 작성하면 쉽습니다 |
| 기술 스토리와 사용자 스토리 구분 | 사용자 가치가 있으면 유저 스토리, 없으면 Technical Task로 분류 |
| 여러 페르소나가 관련 | 주요 페르소나 기준으로 작성하고, 나머지는 수용 기준에 포함 |

> **📚 유저 스토리 시리즈 (4개 프롬프트)**
> 이 프롬프트는 유저 스토리 시리즈의 **허브**입니다. 상황에 따라 연결하세요:
>
> | 상황 | 연결 프롬프트 |
> |------|-------------|
> | 스토리를 전체 제품 맥락에서 배치 | → [유저 스토리 맵핑](user-story-mapping.md) |
> | 스토리가 너무 커서 분할 필요 | → [유저 스토리 분할](user-story-splitting.md) |
> | AI Acceptance Criteria 필요 | → [AI 기준 유저 스토리](user-story-ai-enhanced.md) |
> | 스토리로 스프린트 계획 | → [스프린트 킥오프](../decide/sprint-kickoff.md) |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 유저 스토리를 3C's + INVEST 원칙으로 체계적으로 작성하고 싶은 분입니다.
엔지니어와 디자이너가 바로 이해할 수 있는 스토리를 만들고 싶다면 이걸 써보세요.

### 📌 진행 방식

이 프롬프트는 **4단계 CoT(Chain of Thought)** 구조입니다. 두 가지 방식으로 쓸 수 있습니다:

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

프로덕트 매니저, 스크럼 마스터, 백엔드/프론트엔드 엔지니어

### # 목표

**INVEST 원칙을 따르는 고품질 유저 스토리 작성**

- **Independent**: 다른 스토리와 독립적
- **Negotiable**: 세부사항은 협상 가능
- **Valuable**: 사용자에게 직접 가치 제공
- **Estimable**: 스프린트 내에 추정 가능
- **Small**: 1~3일 내 완료 가능
- **Testable**: 수용 기준이 명확함

<!-- 💬 [전문가의 눈] INVEST는 단순한 체크리스트가 아닙니다.
이 원칙들은 스토리가 "협업 가능"하고 "완료 가능"하도록 설계된 것입니다.
스토리가 너무 크거나 협상 불가능하면, 팀의 속도와 품질이 떨어집니다.

각 원칙이 실패하면 어떤 문제가 생기는지 봅시다:
- Independent 실패 → "A 스토리 안 끝나서 B도 못 시작해요" (병렬 작업 불가)
- Negotiable 실패 → "PM이 정해준 대로만 해야 해요" (팀 자율성 상실)
- Valuable 실패 → "이거 왜 만드는 거예요?" (동기부여 상실)
- Estimable 실패 → "이거 얼마나 걸릴지 모르겠어요" (계획 불가)
- Small 실패 → "이번 스프린트에 안 끝났어요" (완료감 상실)
- Testable 실패 → "이거 다 된 건가요?" (완료 기준 불명확) -->

#### ❌ 나쁜 유저 스토리 vs ✅ 좋은 유저 스토리

```
❌ 나쁜 예시 1: 너무 큼 (Small 위반)
"사용자로서 AI 기반 문서 관리 시스템을 사용하고 싶다"
→ 문제: 3개월짜리 프로젝트. 스프린트에 안 들어감.
→ 해결: user-story-splitting.md로 분할

❌ 나쁜 예시 2: 테스트 불가 (Testable 위반)
"사용자로서 더 나은 경험을 원한다"
→ 문제: "더 나은"의 기준이 없음. QA가 테스트 불가.
→ 해결: "요약 결과 로딩 시간이 2초 이내"처럼 측정 가능하게

❌ 나쁜 예시 3: 가치 없음 (Valuable 위반)
"개발자로서 데이터베이스를 PostgreSQL에서 MongoDB로 마이그레이션하고 싶다"
→ 문제: 사용자 가치가 없음. 기술 작업은 Technical Task로 분류.
→ 해결: "사용자로서 검색 결과를 0.5초 내에 보고 싶다 (DB 최적화 필요)"

✅ 좋은 예시:
"고객 성공 담당자 박진수로서,
 AI 요약에 '신뢰도 점수'가 표시되길 원한다.
 그래야 고객에게 요약을 공유할 때 신뢰할 수 있는 정보인지 판단할 수 있다."

→ Independent: 다른 스토리 없이 독립 구현 가능
→ Negotiable: 신뢰도 표시 방식(숫자/색상/아이콘)은 협상 가능
→ Valuable: 고객 신뢰도 향상이라는 명확한 가치
→ Estimable: 프론트엔드 UI 변경 + API 연동 = 약 2일
→ Small: 스프린트 내 완료 가능
→ Testable: "신뢰도 점수가 0~10 사이로 표시되는가?"
```

### # Reasoning Strategy

#### 1단계: 3C's로 스토리 구성

**Card (카드)**
```
제목: [2-3단어 동작 중심]
설명: As a [페르소나], I want to [행동], So that [가치]
```

<!-- 💬 이 포맷이 왜 효과적인가?
- "역할"은 컨텍스트를 제공합니다 (누가 쓸 것인가)
- "행동"은 구체성을 줍니다 (무엇을 할 것인가)
- "가치"는 의도를 명시합니다 (왜 필요한가)
이 세 가지가 모두 있어야 팀이 "이 스토리를 왜 만드는지" 이해합니다. -->

**Conversation (대화)**
```
Q: 이 기능을 누가 사용하나요?
A: 마케팅 담당자, 영업 팀

Q: 성공의 지표는?
A: 리포트 생성 시간 50% 단축

Q: 제약사항이 있나요?
A: 기존 DB 스키마 변경 불가
```

<!-- 💬 스토리 작성 후 대화가 시작되어야 합니다.
이 대화를 통해:
- 엔지니어는 숨겨진 요구사항을 찾습니다
- PM은 기술적 제약을 이해합니다
- 팀 전체가 같은 목표를 봅니다 -->

**Confirmation (확인)**
```
수용 기준:
[ ] 사용자가 [조건1]일 때 [결과1]을 본다
[ ] [조건2]일 때도 [결과2]를 본다
[ ] 에러 처리: [엣지케이스]일 때 [예상동작]
```

<!-- 💬 수용 기준은 "QA 체크리스트"가 아닙니다.
이것은 "완료"의 정의입니다.
수용 기준이 명확하지 않으면:
- 엔지니어는 "충분히 했다"고 생각합니다
- PM은 "부족하다"고 생각합니다
- 이 갈등이 반복 업무(rework)를 만듭니다 -->

#### 2단계: 페르소나 기반 검증

```
페르소나: 마케팅 담당자 "김경미" (3년 경력, 엑셀 능숙)

질문:
- 경미는 이 기능으로 "뭐"를 할 수 있나요? [구체적 작업]
- 경미의 일상에서 이게 얼마나 자주 필요한가요? [빈도]
- 경미가 이 기능을 못 쓰면 어떤 일이 생기나요? [Pain Point]
```

#### 3단계: 크기와 범위 검증

```
이 스토리는 다음을 포함합니까?
- [ ] UI/UX (프론트엔드)
- [ ] API (백엔드)
- [ ] DB (데이터)
- [ ] 테스트
- [ ] 문서

포함된 항목이 3개 이상이면: 이 스토리를 분할하세요 (user-story-splitting.md 참고)
```

### # 데이터 수집 포인트

- **사용자 행동 데이터**: 현재 유사 기능 사용 비율
- **문제점 인터뷰**: 최소 3명 사용자와의 대화
- **경쟁사 벤치마크**: 유사 기능의 사용성

### # AI 제품 특화

AI 기반 기능의 경우:
```
As a [페르소나],
I want to [행동]
**using AI to** [AI 모델/능력]
So that [가치]

Example:
As a 고객 지원 담당자,
I want to 고객 이메일을 자동으로 분류하기를
**using AI sentiment analysis**
So that 긴급한 이슈에 먼저 대응할 수 있습니다.
```

### # 한국 SaaS 특화

- **한글 기술 용어**: "정산" vs "Settlement", "결산" vs "Financial Close"
- **규정 준수**: ISMS, 개인정보보호법 고려
- **지역화**: 날짜 형식, 통화 단위, 문화적 관례


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 페르소나가 불명확 | persona-profiling.md를 먼저 활용하세요 |
| 2단계 | 3C's 대화(Conversation)가 어려움 | "이 스토리에 대해 엔지니어가 물어볼 질문 5개"를 AI에 요청 |
| 3단계 | 수용 기준이 너무 많음 | 핵심 3-5개만 유지. 나머지는 "추가 고려사항"으로 분리 |
| 4단계 | INVEST 검증 실패 | 가장 흔한 문제는 "Too Big" → 분할하세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 유저 스토리 생성과 품질 검증을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
스프린트마다 스토리 작성을 반복합니다. PRD에서 자동으로 스토리를 추출하면 시간을 절약하고 일관성을 유지할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### 스토리 생성 Python 스크립트

```python
#!/usr/bin/env python3
"""
유저 스토리 자동 생성기
Claude API를 사용하여 페르소나/행동/가치에서 완전한 유저 스토리 생성
"""

import anthropic
import json
from typing import Optional

def generate_user_story(
    persona: str,
    action: str,
    value: str,
    context: Optional[str] = None,
    ai_feature: bool = False
) -> dict:
    """
    입력값으로부터 INVEST 원칙을 따르는 유저 스토리 생성

    Args:
        persona: 사용자 역할 (예: "데이터 분석가")
        action: 하려는 행동 (예: "대시보드 만들기")
        value: 얻을 수 있는 가치 (예: "신속한 보고")
        context: 추가 컨텍스트 (선택사항)
        ai_feature: AI 기능 특화 여부

    Returns:
        생성된 스토리, 수용 기준, INVEST 검증 결과
    """

    client = anthropic.Anthropic()

    prompt = f"""당신은 경험 많은 프로덕트 매니저입니다.
다음 정보로 고품질의 INVEST 원칙을 따르는 유저 스토리를 작성하세요.

**입력:**
- 페르소나: {persona}
- 행동: {action}
- 가치: {value}
{f'- 추가 컨텍스트: {context}' if context else ''}
{f'- AI 기능 포함: 예' if ai_feature else ''}

**필수 산출물:**

1. **유저 스토리 (한글)**
As a [페르소나], I want to [행동], So that [가치]

2. **수용 기준 (한글, 최소 3개)**
[ ] 조건1일 때 결과1을 본다
[ ] 조건2일 때 결과2를 본다
[ ] 엣지케이스 처리

3. **INVEST 원칙 검증**
- Independent: [예/아니오, 이유]
- Negotiable: [예/아니오]
- Valuable: [예/아니오]
- Estimable: [예/아니오]
- Small: [예/아니오]
- Testable: [예/아니오]

4. **추가 고려사항**
- 예상 복잡도: [낮/중/높]
- 분할 필요: [예/아니오]
- 관련 스토리: [있으면 나열]

JSON 형식으로 응답하세요.
"""

    message = client.messages.create(
        model="claude-opus-4-6",
        max_tokens=1500,
        messages=[{"role": "user", "content": prompt}]
    )

    return {
        "persona": persona,
        "action": action,
        "value": value,
        "generated_story": message.content[0].text,
        "model": "claude-opus-4-6",
        "tokens_used": message.usage.output_tokens
    }


def generate_multiple_stories(requirements: list) -> list:
    """
    여러 요구사항으로부터 복수의 유저 스토리 생성

    Args:
        requirements: 딕셔너리 리스트, 각각 persona/action/value 포함

    Returns:
        생성된 스토리 리스트
    """
    stories = []
    for req in requirements:
        story = generate_user_story(
            persona=req.get("persona"),
            action=req.get("action"),
            value=req.get("value"),
            context=req.get("context"),
            ai_feature=req.get("ai_feature", False)
        )
        stories.append(story)

    return stories


if __name__ == "__main__":
    # 예제: 단일 스토리 생성
    result = generate_user_story(
        persona="데이터 분석가 민지",
        action="대시보드에서 월별 매출 추이를 본다",
        value="경영진 보고서를 빠르게 준비할 수 있다",
        context="기존 스프레드시트로는 30분 소요",
        ai_feature=False
    )

    print(json.dumps(result, ensure_ascii=False, indent=2))

    # 예제: 복수 스토리 생성
    batch = [
        {
            "persona": "마케팅 담당자",
            "action": "캠페인 성과를 자동으로 분석한다",
            "value": "의사결정 속도를 높일 수 있다",
            "ai_feature": True
        },
        {
            "persona": "고객 지원팀",
            "action": "이전 상담 기록을 빠르게 검색한다",
            "value": "고객 만족도를 높일 수 있다"
        }
    ]

    stories = generate_multiple_stories(batch)
    for i, story in enumerate(stories, 1):
        print(f"\n=== Story {i} ===")
        print(json.dumps(story, ensure_ascii=False, indent=2))
```

### Claude Code CLI 사용법

```bash
# 유저 스토리 생성
claude run user-story-generator.py \
  --persona "영업 관리자" \
  --action "고객 파이프라인을 시각화한다" \
  --value "거래 가능성을 빠르게 파악할 수 있다"

# 배치 실행 (CSV 입력)
claude run batch-story-generator.py --input requirements.csv --output stories.json

# 수용 기준 자동 생성
claude run acceptance-criteria-generator.py \
  --story "As a PM, I want to..."
```

---

## 📊 실행 결과 예시

### Input
```
페르소나: 고객 성공 담당자 "박진수" (2년 경력)
행동: 고객 건강도 점수를 한눈에 본다
가치: 위험 고객을 조기에 발견할 수 있다
컨텍스트: 현재 수동으로 5개 메트릭을 조사해야 함
```

### Output
```markdown
## 유저 스토리

As a 고객 성공 담당자,
I want to 고객 건강도 대시보드에서 점수를 본다,
So that 위험 고객을 조기에 발견하고 개입할 수 있다.

## 수용 기준

- [ ] 대시보드 로딩 후 3초 내에 모든 고객의 건강도 점수가 보인다
- [ ] 빨강(위험) 점수 고객은 목록 상단에 표시된다
- [ ] 클릭 시 건강도 계산에 사용된 5개 메트릭을 확인할 수 있다
- [ ] 지난 30일 건강도 추이 그래프를 본다
- [ ] 엣지케이스: 데이터 없는 신규 고객은 "조사 중" 표시

## INVEST 검증

| 원칙 | 상태 | 이유 |
|------|------|------|
| Independent | ✓ | 다른 스토리와 무관 |
| Negotiable | ✓ | 메트릭 선택 협상 가능 |
| Valuable | ✓ | 직접적 비즈니스 가치 |
| Estimable | ✓ | 1~2일 추정 가능 |
| Small | ✓ | 대시보드 구현만 포함 |
| Testable | ✓ | 수용 기준이 명확 |

## 복잡도 & 의존성

- 예상 복잡도: 중간 (API + UI + 캐싱)
- 분할 필요: 아니오
- 선행 스토리: "건강도 계산 엔진" (완료됨)
- 후행 스토리: "건강도 알림 설정", "건강도 리포트 내보내기"
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 스토리에 'So that (가치)'가 구체적인지 확인하세요 — '편리해진다'는 불충분
2. **[논쟁 지점]** 유저 스토리의 '적절한 크기'를 1일 vs 3일 vs 1주로 잡을지는 팀마다 다릅니다
3. **[자기 검증]** INVEST 검증에서 'Independent'가 실제로 독립적인지 — 다른 스토리 없이 배포할 수 있는지 확인하세요

---

## 🔗 다음 단계

1. **`user-story-mapping.md`** → 여러 스토리를 Jeff Patton 방식의 맵으로 연결
2. **`user-story-splitting.md`** → 큰 스토리를 SPIDR로 분할
3. **`user-story-ai-enhanced.md`** → AI 특화 수용 기준 추가
4. **스프린트 계획** → 선별된 스토리를 스프린트에 배정
