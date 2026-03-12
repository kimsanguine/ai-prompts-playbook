# 📖 스토리텔링 (Product Storytelling)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 35분+ (Build)
> 워크플로우: ← `press-release.md` → `cross-team-handoff.md`

---

## 🎯 이 프롬프트가 해결하는 문제

프레스 릴리즈와 다르게, **스토리텔링은 "고객의 감정 여정"을 보여준다.** "전: 고통, 중: 시도, 후: 성공"의 스토리보드를 통해 고객이 공감하고, 제품의 가치를 직관적으로 이해하게 한다. 특히 **한국 시장은 "스토리"를 중시하므로**, 단순 기능 설명보다 "이야기"가 훨씬 더 강하게 작동한다.

---

## 📥 이전 프롬프트에서 받는 입력

> `stakeholder-alignment.md`에서 정렬된 메시지를 스토리 형태로 전달해야 할 때 연결됩니다.

이전 프롬프트 결과에서 **핵심 메시지, 청중, 전달 목적**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 제품/기능에 대한 설득력 있는 스토리를 만들 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 제품 스토리텔러다.

{AI 기능}의 스토리보드를 만드세요:

구조:
1. 주인공: 누구인가? (구체적 직책, 업계)
2. Before: 현재 고통 (구체적 장면, 감정)
3. Turning Point: "아, 이런 게 필요했어!"
4. After: 변화 (구체적 수치, 감정)
5. New Habit: 이제 어떻게 일하나?

각 단계별로:
- 구체적 장면을 영상화할 수 있게
- 시간, 공간, 감정을 담아
- 한국 기업 현장의 리얼리티 반영

결과물: 텍스트 스토리보드 (웹, 영상 제작용)
```

💡 **Quick Tips:**
- 추상적이 아니라 "구체적 장면" (예: "월요일 아침 8시, 회의실에서...")
- 감정 중심 (효율성보다 "일이 재미있어졌다"는 감정)
- 한국식 스토리: 수직 관계, 신뢰, 검증 과정 반영


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 청중이 데이터 중심 | 스토리에 반드시 데이터를 포함하세요. 감정만으로는 설득 불가 |
| 문화적 차이 | 한국: 맥락과 관계 중시, 미국: 직접적 설득 중시. 청중에 맞게 조정 |
| 민감한 주제 | 사실 기반으로 신중하게. 과장은 역효과 |
| 시간이 1분뿐 | "고객 한 명의 변화" 스토리를 1문장으로 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 데이터와 논리만으로 설득이 안 될 때 스토리텔링을 활용하고 싶은 분입니다.
"왜 이걸 해야 하는지"를 감정적으로 전달하고 싶다면 이걸 써보세요.

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

당신은 **AI 제품의 감정 스토리텔러**이다. 당신의 역할:

1. **공감 유도**: 고객의 현재 고통을 "내 일처럼" 느끼게
2. **변화의 여정**: "아, 이거 없이는 못 쓸 것 같다"는 인식 변화
3. **문화 반영**: 한국 기업, 한국인의 일하는 방식 중심

<!-- 💬 [전문가의 눈] 왜 감성 스토리텔링이 필요한가?
     기업과 마케팅팀은 "기능"을 이야기하려고 합니다.
     하지만 고객의 구매 결정은 "감정"에서 납니다.
     논리만으로는 설득력 부족 → 스토리를 통해 감정 연결 → 강한 기억 형성 -->

<!-- 💬 좋은 스토리와 나쁜 스토리의 차이

나쁜 스토리 (기능 중심):
"AI 요약 기능은 자동으로 문서를 정리합니다.
정확도는 95%입니다."
→ 기술 스펙, 공감 없음

좋은 스토리 (감정 중심):
"월요일 아침, 박과장은 금요일부터 쌓인 보고서 50개를 봅니다.
시선이 흐려집니다. '또 이 반복인가...'
그때 'AI 요약' 버튼을 눌렀고, 50개가 한눈에 정리됩니다.
'어? 이게 가능해?'
지금 박과장은 아침 30분을 오늘의 전략 수립에 씁니다."
→ 장면, 감정, 변화가 생생함
-->

### 목표

최종 아웃풋:
- **고객 여정 스토리보드** (텍스트 + 시각 프레임)
- **감정 곡선** (Before/During/After)
- **장면별 대사 & 비주얼** (영상 제작용)
- **한국 버전 (기업 문화 반영)**

### Reasoning Strategy

**Step 1: 주인공(Persona) 정의**

구체적이어야 함:

```
❌ 일반적: "PM이 있다"
✅ 구체적: "박수진, 금융 스타트업 Product Manager, 35세, 2년 직무 경력"

세부:
- 이름: 박수진
- 직책: PM (금융팀)
- 회사: Series B 핀테크
- 고민: "시장 변화를 빠르게 따라가야 하는데, 보고서 읽기에 시간이 많이..."
- 가치관: "신속함", "정확성", "팀 신뢰"
```

**Step 2: Before 장면 (현재 고통)**

```
구체적 시간, 공간, 감정:

월요일 오전 8시.
박수진은 금요일부터 나온 정책 변경 보고서 20개를 읽어야 한다.
각 보고서는 10-30페이지.

"또 이걸 다 읽고 요약해서 팀 미팅에서 설명해야 하나..."

2시간을 보고서 읽기에만 쓴다.
그럼 팀 미팅은 오후 2시.
결국 오전 중 전략 수립 시간은 0분.

느낌: "왜 자꾸 이 일만 하는 거야..."
(일의 의미 상실)
```

<!-- 💬 [논쟁 지점] Before 장면을 얼마나 구체적으로 그릴 것인가?
     너무 구체적 → 특정 산업/직책만 공감
     너무 추상적 → 설득력 저하
     균형: "구체적 시간과 감정" + "공통의 경험" 혼합 -->

**Step 3: Turning Point (문제 해결의 순간)**

```
그 순간을 dramatic하게:

화면에 "AI 요약" 버튼이 보인다.
박수진은 반신반의하며 클릭한다.

"2초에 이게 가능해?"

요약이 완성된다:
- 요약: 핵심 3줄
- 신뢰도: 8.2/10 (높음)
- 액션 아이템: 2개

"어? 진짜네..."

박수진은 다음 보고서도 누른다.
한 번, 또 한 번.

10분이 지났을 때, 20개 보고서의 요약이 모두 완료되었다.

느낌: "이게 되면... 게임이 완전히 달라지는데?"
```

**Step 4: After 장면 (새로운 일의 방식)**

```
같은 월요일 오전, 같은 시간대.
But: "정책 요약" 10분 완료 ✅

이제 박수진은:
- 8:00-8:10: AI 요약 처리, 정책 큠만 정리
- 8:10-9:00: 팀과 "정책의 영향도" 토론 (전략 회의)
- 9:00-10:00: 제품 로드맵 수정 (high-value work)

느낌: "아, 이럴 때 PM이 하는 일이지..."

팀 미팅에서:
팀원: "박과장, 정책 변경 뭐 있어요?"
박수진: "정책 3개 핵심 변경 있는데..." (자신감 있는 설명)

(vs Before: "어... 너무 많아서 정리 못했어요...")

일주일 후:
박수진의 팀이 경쟁사보다 정책 변화에 1주일 먼저 대응한다.
→ 제품 차별점 확보
```

**Step 5: New Habit (습관화된 모습)**

```
이제 박수진은:
- 매일 아침 "정책/시장 뉴스 AI 요약"을 본다 (5분)
- 핵심 변화를 즉시 팀과 공유한다 (민첩성)
- 자신의 "의사결정 시간"이 30% 증가했다 (생산성)

일의 의미:
Before: "서류 정리 담당"
After: "시장 변화 감지자, 전략 수립자"

박수진은 이제 자신을 다시 소개한다:
"저는 PM인데, AI와 함께 시장 변화를 선제적으로 대응합니다."
```

<!-- 💬 [자기 검증] New Habit 부분이 실제 가능한가?
     "매일 5분"은 현실적인가? 실제 사용자에게 검증했는가?
     이 습관이 지속되려면 무엇이 필요한가?
     (기술 차원: 프로토타입 검증, 사회학 차원: 팀 문화 변화) -->

### 스토리보드 작성 가이드

```markdown
# [주인공] 스토리: AI 요약으로 일의 의미를 찾다

---

## 1️⃣ Before: 월요일 오전 (문제 장면)

**시간/장소**: 월요일 오전 8:00, 사무실 박수진의 자리

**시각적 요소**:
- 책상에 쌓인 종이: 정책 보고서 20개 스택
- 박수진의 표정: 한숨, 지쳐 있음
- 시계: 8:00

**박수진의 독백**:
"매주 이러네... 정책 변경 보고서가 20개?
이거 다 읽고 팀에 설명하려면 2시간은...
그럼 아침 미팅에 집중할 시간이 없네."

**감정 곡선**: ⬇️ (지침, 무의미함)

**이 장면이 보여주는 것**:
- 한국 기업의 "정보 과부하" 현실
- PM의 진정한 일이 아닌, "문서 정리"만 하는 현실
- 시간 부족으로 인한 전략적 사고 불가능

---

## 2️⃣ Turning Point: AI 요약 발견 (변화의 순간)

**시간/장소**: 같은 자리, 8:02

**시각적 요소**:
- 화면에 "AI 요약" 버튼
- 버튼을 누르는 손가락
- 로딩 화면 (2초 애니메이션)

**효과음**: 미묘한 "ding" 소리 (완료 신호)

**박수진의 반응**:
"어? 정말 되네?"

**감정 곡선**: ⬆️ (놀라움, 기대)

**이 장면이 보여주는 것**:
- "아, 이런 게 가능했구나" 깨달음
- 문제에 대한 즉각적 해결책

---

## 3️⃣ After: 같은 월요일 오전 9:00 (변화된 모습)

**시간/장소**: 같은 오전, 다른 시간. 회의실 회의 중.

**시각적 요소**:
- 화면에: 정책 변경 3개 항목 (AI 요약)
- 팀원들: 주의깊게 듣는 모습
- 박수진: 자신감 있는 표정

**박수진의 발언**:
"정책 3가지가 바뀌었는데, 우리 제품에 영향이 큰 건 2번 항목입니다.
이걸 대응하려면 우리도 이번 분기 안에 수정이 필요합니다."

**팀원 반응**:
"박과장이 이렇게 빨리 캐치했어? 경쟁사는 몰라도 우린 먼저 대응하겠네."

**감정 곡선**: ⬆️⬆️ (성취감, 자신감, 팀 신뢰)

**이 장면이 보여주는 것**:
- PM으로서의 "진정한 역할" (문서 정리가 아니라 전략)
- 팀의 신뢰 획득
- 조직의 민첩성 향상

---

## 4️⃣ New Habit: 3개월 후 (습관화)

**시간/장소**: 이번엔 일상적 장면. 박수진이 AI 요약을 루틴처럼 사용

**시각적 요소**:
- 아침 일과: 뉴스 → AI 요약 (5분)
- 백슬래시: 팀 슬랙에 정책 변경 공유
- 시간 절감: 지표 그래프 (보고서 읽기 2시간 → 10분)

**박수진의 변화**:
- 자신을 설명할 때: "저는 PM인데, 시장 변화를 가장 먼저 감지하고 대응합니다"
- 조직에서의 역할: "시장 안테나" 역할로 인정받음

**감정 곡선**: ⬆️ (지속적인 만족감)

**비즈니스 임팩트**:
- 정책 대응 속도: -80% (2주 → 2일)
- 팀 생산성: +30%
- 제품 차별점: 경쟁사 대비 +8주 우위

---

## 감정 곡선 (한눈에)

```
감정 수준
  9 |                    ⬆️⬆️⬆️
  8 |                   / (After)
  7 |                  /
  6 |                 /
  5 |    ⬇️ ⬇️ ⬇️  <- Turning Point -> 새로운 기준
  4 |   /
  3 |  / (Before)
  2 |_/
  1 |
    +--+--+--+--+--+--+--+--+
    월 화 수 목 금 토 일 월
```

---

## 🇰🇷 한국 기업 문화 반영 포인트

### 1. "신뢰"의 중요성
- Before: 박수진이 제대로 파악 못 한 건 아닐까? (상사의 의심)
- After: AI + 박수진의 검증으로 100% 신뢰성 확보
- 한국 조직의 "확인 문화": 결재라인을 거칠 때 "검증된 정보"를 요구

### 2. "정보 정확성"의 중시
- AI 요약에 "신뢰도 점수" (8.2/10) 표시
- "틀릴 수도 있으니, 이 부분은 직접 확인" 강조
- 한국식 "더블 체크" 문화 반영
- 대기업 의사결정 구조: 결재 전 여러 단계의 검증 필수

### 3. "팀 신뢰"의 구축
- AI가 박수진을 대신해 "정확하게" 정리
- 박수진이 그 위에 "판단"을 더함
- 팀원들은 "박수진의 능력" + "AI의 정확성"을 모두 신뢰
- 린품의 및 합의제 문화에서 "누군가의 신뢰"가 의사결정의 핵심

### 4. "의사결정 속도"의 강조
- 한국 기업은 빨리 움직여야 한다는 강박
- "AI 덕분에 우리가 경쟁사보다 1주 먼저 움직였다"
- 이는 "비용 절감"이 아니라 "경쟁 우위" 프레임
- 한국 SaaS 스타트업의 생존은 속도에 달려 있음

### 5. "보고선(Reporting Line)" 최적화
- Before: "보고서 100개 검토" → 팀장에게 보고 지연
- After: "정책 3개 핵심만 정리" → 빠른 보고 + 높은 신뢰도
- 한국 조직의 보고문화에 완벽히 맞는 프레이밍

### 6. "린품의(린 피칭)" 문화
- 스타트업: "아이디어 → 1주일 의사결정" 문화
- AI 요약으로 "의사결정에 필요한 정보"를 빠르게 확보
- "동의/부동의"를 빠르게 결정할 수 있게 지원

---

## 다른 페르소나 스토리 (참고)

### Law Firm 변호사 (김변호사)

**Before**: "계약서 100페이지 검토에 3시간"
**Turning Point**: "AI 요약 + 신뢰도로 위험 신호만 집중"
**After**: "30분 만에 완료, 놓칠 부분 없음"

### Startup CEO (정대표)

**Before**: "매주 10개 투자 제안서... 다 읽을 수 없다"
**Turning Point**: "AI가 2분 안에 핵심을 정리해줌"
**After**: "의사결정 속도가 3배 빨라졌다"

### Customer Success Manager (이매니저)

**Before**: "고객 계약서 50개를 일일이 읽고 갱신 알림"
**Turning Point**: "AI가 자동으로 '갱신 필요' 플래그"
**After**: "갱신율 95% → 98%, 체류율 상승"
```

💡 **Deep Tips:**
- **구체성**: "효율성이 올라간다" (X) → "월요일 아침 2시간이 1시간으로" (O)
- **감정 중심**: 숫자보다 "느낌의 변화" 강조
- **한국 특화**: "신뢰", "검증", "팀 신뢰" 같은 한국식 가치 반영


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 스토리 소재 부족 | 고객 인터뷰, 지원 티켓, 리뷰에서 실제 사례를 추출 |
| 2단계 | 내러티브 구조 어려움 | "문제 → 시도 → 실패 → 해결 → 결과" 5단계 구조 사용 |
| 3단계 | 데이터와 스토리 연결 어려움 | "이 데이터 뒤에 있는 사람은 누구?"로 인간화 |
| 4단계 | 설득력 부족 | "비교"를 사용하세요. Before/After 또는 경쟁사와의 차이 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 데이터에서 자동으로 내러티브를 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
같은 데이터도 스토리가 있으면 설득력이 4배 높아집니다. 자동화하면 메트릭 변화를 자동으로 스토리로 변환할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### 스토리보드 생성 프레임워크 (Python)

```python
# storytelling_framework.py
from dataclasses import dataclass
from typing import List, Dict
from enum import Enum

class EmotionLevel(Enum):
    VERY_LOW = 1
    LOW = 2
    NEUTRAL = 3
    HIGH = 4
    VERY_HIGH = 5

@dataclass
class Persona:
    """페르소나 정의"""
    name: str
    role: str
    company: str
    age: int
    tenure: int
    pain_points: List[str]  # 현재 고통
    values: List[str]  # 중요하게 생각하는 것

@dataclass
class StoryScene:
    """스토리의 한 장면"""
    title: str
    time: str
    location: str
    visual_elements: List[str]
    dialogue: str
    internal_monologue: str
    emotion_level: EmotionLevel
    business_impact: str = None

@dataclass
class CustomerStory:
    """완전한 고객 스토리"""
    persona: Persona
    before_scene: StoryScene
    turning_point: StoryScene
    after_scene: StoryScene
    new_habit: StoryScene

class StorytellingGenerator:
    """고객 스토리 자동 생성"""

    def __init__(self, product_name: str):
        self.product_name = product_name

    def generate_story(self, story: CustomerStory) -> str:
        """스토리 텍스트 생성"""

        output = f"""
# {story.persona.name}의 스토리: {self.product_name}로 일의 의미를 찾다

---

## 1️⃣ Before: 현재의 고통

**인물**: {story.persona.name} ({story.persona.role}, {story.persona.company})

**시간/장소**: {story.before_scene.time}, {story.before_scene.location}

**시각적 요소**:
"""

        for element in story.before_scene.visual_elements:
            output += f"- {element}\n"

        output += f"""

**독백**:
> "{story.before_scene.dialogue}"

**내면의 목소리**:
> {story.before_scene.internal_monologue}

**감정**: {'⬇️ ' * story.before_scene.emotion_level.value} (낮음)

---

## 2️⃣ Turning Point: 변화의 순간

**시간/장소**: {story.turning_point.time}, {story.turning_point.location}

**시각적 요소**:
"""

        for element in story.turning_point.visual_elements:
            output += f"- {element}\n"

        output += f"""

**반응**:
> "{story.turning_point.dialogue}"

**감정**: {'⬆️ ' * story.turning_point.emotion_level.value} (상승)

---

## 3️⃣ After: 변화된 모습

**시간/장소**: {story.after_scene.time}, {story.after_scene.location}

**시각적 요소**:
"""

        for element in story.after_scene.visual_elements:
            output += f"- {element}\n"

        output += f"""

**발언**:
> "{story.after_scene.dialogue}"

**감정**: {'⬆️ ' * story.after_scene.emotion_level.value} (높음)

**비즈니스 임팩트**:
{story.after_scene.business_impact}

---

## 4️⃣ New Habit: 습관화된 모습

**변화**:
{story.new_habit.dialogue}

**감정**: {'⬆️ ' * story.new_habit.emotion_level.value} (지속적 만족감)

**조직에서의 역할 변화**:
{story.new_habit.internal_monologue}

---

## 한국 기업 문화에서의 의미

### 신뢰의 구축
{story.persona.values[0] if story.persona.values else "신뢰"}

### 팀 신뢰
AI의 정확성 + PM의 판단 → 100% 신뢰성

### 의사결정 속도
경쟁 우위 획득 기간: 단축 (구체 수치)
"""

        return output

    def generate_emotion_curve(self, story: CustomerStory) -> str:
        """감정 곡선 시각화"""

        emotions = [
            ("Before", story.before_scene.emotion_level.value),
            ("Turning Point", story.turning_point.emotion_level.value),
            ("After", story.after_scene.emotion_level.value),
            ("New Habit", story.new_habit.emotion_level.value),
        ]

        max_val = 5
        chart = "\n감정 곡선 (한눈에)\n\n```\n"
        chart += "감정 수준\n"

        for level in range(max_val, 0, -1):
            chart += f"  {level} |"
            for name, val in emotions:
                if val >= level:
                    chart += "  ⬆️ "
                else:
                    chart += "     "
            chart += "\n"

        chart += "    +" + "+".join(["--"] * len(emotions)) + "+\n"
        chart += "    " + "  ".join([name.ljust(10) for name, _ in emotions]) + "\n```"

        return chart


# 사용 예시
if __name__ == "__main__":
    # Persona 정의
    persona = Persona(
        name="박수진",
        role="PM (금융팀)",
        company="Series B 핀테크",
        age=35,
        tenure=2,
        pain_points=["정책 보고서 과다", "전략 수립 시간 부족", "팀 신뢰 구축"],
        values=["신속함", "정확성", "팀 신뢰"],
    )

    # 스토리 구성
    before = StoryScene(
        title="월요일 오전 - 문제",
        time="월요일 오전 8:00",
        location="사무실 박수진의 자리",
        visual_elements=[
            "책상에 쌓인 정책 보고서 20개",
            "박수진의 피곤한 표정",
            "시계: 8:00",
        ],
        dialogue="매주 이러네... 정책 변경 보고서가 20개?",
        internal_monologue="이거 다 읽고 팀에 설명하려면 2시간은 필요할 텐데...",
        emotion_level=EmotionLevel.LOW,
    )

    turning_point = StoryScene(
        title="AI 요약 발견",
        time="같은 자리, 8:02",
        location="모니터 앞",
        visual_elements=[
            "'AI 요약' 버튼",
            "마우스 커서",
            "로딩 화면",
        ],
        dialogue="어? 정말 되네?",
        internal_monologue="2초 만에... 이게 가능했구나.",
        emotion_level=EmotionLevel.VERY_HIGH,
    )

    after = StoryScene(
        title="변화된 모습",
        time="같은 오전, 9:00",
        location="회의실",
        visual_elements=[
            "정책 변경 3개 항목 (AI 요약)",
            "팀원들의 주의깊은 표정",
            "박수진의 자신감 넘친 표정",
        ],
        dialogue="정책 3가지가 바뀌었는데, 우리 제품에 가장 큰 영향은 2번 항목입니다.",
        internal_monologue="이제 나는 PM으로서의 진정한 역할을 한다.",
        emotion_level=EmotionLevel.VERY_HIGH,
        business_impact="- 정책 대응 속도: -80% (2주 → 2일)\n- 팀 생산성: +30%",
    )

    new_habit = StoryScene(
        title="3개월 후 - 일상화",
        time="아침 루틴",
        location="사무실",
        visual_elements=[
            "AI 요약을 기본처럼 사용",
            "팀 슬랙에 정책 변경 공유",
            "시간 지표 그래프",
        ],
        dialogue="저는 PM인데, 시장 변화를 가장 먼저 감지하고 대응합니다.",
        internal_monologue="이제 이게 내 일의 기본이 되었다.",
        emotion_level=EmotionLevel.VERY_HIGH,
        business_impact="- 지속적 경쟁 우위\n- 팀의 '시장 안테나' 역할",
    )

    story = CustomerStory(
        persona=persona,
        before_scene=before,
        turning_point=turning_point,
        after_scene=after,
        new_habit=new_habit,
    )

    generator = StorytellingGenerator("AI 요약")
    story_text = generator.generate_story(story)
    print(story_text)
    print(generator.generate_emotion_curve(story))
```

### Claude Code CLI 활용

```bash
# 1. 고객 스토리 생성
claude code run generate-customer-story \
  --persona-file personas.json \
  --product "AI Summarization" \
  --output customer_stories.md

# 2. 감정 곡선 시각화
claude code run generate-emotion-curves \
  --stories customer_stories.md \
  --format svg \
  --output emotion_curves.svg

# 3. 스토리 기반 마케팅 자료 생성
claude code run generate-marketing-from-stories \
  --stories customer_stories.md \
  --format video-script,social-media,email-sequence

# 4. 한국 문화 특화 스토리
claude code run culturalize-stories \
  --base-language english \
  --target-culture korean \
  --emphasize "신뢰,팀신뢰,의사결정속도"
```

---

## 📊 실행 결과 예시

### 최종 스토리보드

```
# 박수진의 스토리: AI 요약으로 PM의 일의 의미를 찾다

---

## 1️⃣ Before: 월요일 오전 (문제 장면)

**인물**: 박수진, PM (금융팀), Series B 핀테크

**시간/장소**: 월요일 오전 8:00, 사무실 박수진의 자리

**시각적 요소**:
- 책상에 쌓인 정책 보고서 20개의 스택
- 박수진의 피곤한 표정, 한숨
- 시계: 8:00
- 배경: 회의실이 보이고, 팀원들이 카페인 마시며 대기 중

**독백**:
> "매주 금요일 오후가 되면 정책 변경 보고서가 쌓인다.
> 월요일 아침이 되면 20개, 30개씩.
> 이거 다 읽고 팀 미팅에서 설명해야 해."

**내면의 목소리**:
> "2시간을 그냥 읽기만 했는데, 정작 중요한 의사결정은?
> 이게 내가 하는 일인가..."

**감정**: ⬇️⬇️⬇️ (무의미함, 피로, 답답함)

---

## 2️⃣ Turning Point: AI 요약 발견 (8:02)

**시간/장소**: 같은 자리, 모니터 앞

**시각적 요소**:
- 화면에 밝은 버튼: "🤖 AI 요약"
- 박수진의 손이 마우스를 집어 들기
- 클릭하는 순간
- 로딩 애니메이션 (2초)
- "ding" 소리

**반응**:
> "어? 정말 되네?"

**감정**: ⬆️⬆️⬆️⬆️ (놀라움, 기대, 설렘)

---

## 3️⃣ After: 같은 월요일 아침 9:00 (변화된 모습)

**시간/장소**: 같은 오전, 9:00, 회의실 미팅 중

**시각적 요소**:
- 대형 모니터에 정책 변경 3개 항목 (AI 요약 결과)
- 팀원들: 노트북을 열고 주의깊게 듣는 모습
- 박수진: 자신감 넘친 표정, 앞으로 기댈 수 있게 선 자세

**박수진의 발언**:
> "금요일부터 나온 정책 변경 3가지를 정리했습니다.
> 우리 제품에 가장 큰 영향은 2번 항목입니다.
> 이를 대응하려면 이번 분기 안에 수정이 필요합니다."

**팀원 반응**:
> "박과장이 이렇게 빨리 캐치했어? 경쟁사는 몰라도 우린 먼저 움직이겠네."

**감정**: ⬆️⬆️⬆️⬆️⬆️ (성취감, 자신감, 팀 신뢰, 자부심)

**비즈니스 임팩트**:
- 정책 대응 속도: 2주 → 2일 (-80%)
- 팀 생산성: +30% (전략 수립 시간 증가)
- 경쟁 우위: +1주 선제 대응

---

## 4️⃣ New Habit: 3개월 후 (습관화)

**변화**:
박수진은 이제 매일 아침 "AI 요약"을 루틴처럼 사용한다.
- 아침 8:00: 뉴스/정책 보고서 AI 요약 (5분)
- 8:05: 팀 슬랙에 핵심 변화 공유 (3분)
- 8:10: 팀과 "영향도" 토론 시작 (30분)

**조직에서의 역할 변화**:
Before: "문서 정리 담당"
After: "시장 변화 감지자, 전략 수립자"

박수진은 이제 이렇게 소개한다:
> "저는 금융팀 PM인데, AI와 함께 시장 변화를 가장 먼저 감지하고,
> 우리 제품을 빠르게 대응시킵니다."

**감정**: ⬆️⬆️⬆️⬆️⬆️ (지속적 만족감)

---

## 한국 기업 문화에서의 의미

### 신뢰의 구축
AI 요약 결과 + 박수진의 검증 → "100% 신뢰할 수 있다"
(한국식 "더블 체크" 문화 완벽 부합)

### 팀 신뢰
"박과장이 이렇게 빨리 캐치했어?" → 팀원들의 박수진에 대한 신뢰 증가
(한국식 "신뢰 경영" 강화)

### 의사결정 속도
경쟁사 대비 +1주 선제 대응 → 시장 리더십 확보
(한국 기업의 "빠른 움직임" 중시 충족)

### 일의 의미
"서류 정리" → "전략 수립" 로의 이동
(직원 만족도, 이직률 개선)
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 스토리에 '갈등(conflict)'이 있는지 확인하세요 — 갈등 없는 스토리는 기억되지 않습니다
2. **[논쟁 지점]** 제품 스토리텔링에서 '데이터 중심'과 '감성 중심' 중 어디에 무게를 둘지는 청중에 따라 다릅니다
3. **[자기 검증]** 스토리의 핵심 데이터 포인트 1개를 실제 소스에서 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|------|-----------|------|
| ✅ 고객 스토리보드 | `cross-team-handoff.md` | "스토리를 바탕으로 팀별 실행 계획" |
| ✅ 감정 곡선 | `ai-ethics-review.md` | "윤리 관점: 자동화가 인간의 일의 의미는?" |
| ✅ 마케팅 자료 | `press-release.md` | "스토리를 프레스 릴리즈와 통합" |
| 🔜 영상화 | Claude Code `--generate-video-script` | 유튜브/틱톡용 스토리 영상 스크립트 |
