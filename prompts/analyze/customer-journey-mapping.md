# 🗺️ 고객 여정 맵핑 (Customer Journey Mapping)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 40분+ (Build)
> 워크플로우: → `persona-profiling.md` → `problem-framing.md` → `jobs-to-be-done.md`

---

## 🎯 이 프롬프트가 해결하는 문제

고객이 우리 제품을 발견하고, 구매하고, 사용하고, 추천하기까지의 전체 경로를 모릅니다. 각 단계에서 어느 것이 막혔는지, 어느 감정에 공감해야 하는지 불명확해서 기능 개선 방향을 잃게 됩니다. 이 프롬프트는 고객 여정을 **시간순 + 감정+ 터치포인트 기준**으로 구조화해서 개선점을 찾을 수 있게 합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `persona-profiling.md`에서 정의한 핵심 페르소나의 여정을 맵핑할 때 연결됩니다.

이전 프롬프트 결과에서 **페르소나명, 핵심 JTBD, 사용 맥락**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 고객의 핵심 여정 단계를 시각화할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.

<!-- 복사해서 바로 쓰세요. -->

```
{제품명}의 고객 여정을 5개 단계로 그리세요:

1단계: 인식 (제품을 알게 됨)
   - 어떻게 알았나? (광고, 입소문, 검색 등)
   - 감정: ___

2단계: 검토 (비교 및 평가)
   - 어디서 정보를 찾나? (웹사이트, 리뷰, 데모 등)
   - 감정: ___

3단계: 구매 (결정 및 가입)
   - 의사결정 시간: ___
   - 감정: ___

4단계: 사용 (일상적 활용)
   - 주요 기능은? 주요 문제는?
   - 감정: ___

5단계: 추천 (입소문)
   - 다른 사람에게 어떻게 추천하나?
   - 감정: ___

각 단계의 감정을 😊😕😡 이모지로 표현하세요.
```

**💡 Quick Tips:**
- {제품명}: SaaS, 앱, 또는 물리 제품 모두 적용 가능
- 감정 3단계만: 긍정(😊), 중립(😐), 부정(😕) 정도로 충분
- 실제 고객 인터뷰나 지난 회의 기록이 있다면 참고하되, 없어도 팀의 경험으로 충분


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 터치포인트가 너무 많음 | 핵심 5-7단계만 먼저 정의하세요. 세부 단계는 나중에 추가 |
| 오프라인 터치포인트 포함 | 온/오프라인 모두 포함하세요. 전화, 매장 방문도 여정입니다 |
| B2B 고객 여정 | 구매 프로세스가 길고 여러 의사결정자 관여 → 역할별로 여정을 나누세요 |
| 데이터가 없어서 감정 추측 불가 | 고객 인터뷰 또는 앱 리뷰에서 감정 단서를 추출하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 고객 여정을 전문가 수준으로 분석하고 싶은 분입니다.
각 단계의 감정, 터치포인트, 이탈 원인까지 깊이 파악하고 싶다면 이걸 써보세요.

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


```
# 역할: 고객 경험 기획자 (CX Designer)
# 목표: 고객이 제품을 인식하고 사용하기까지의 감정 변화와 터치포인트 맵핑

# Reasoning Strategy
<!-- 💬 왜 7단계로 나누나?
     고객 여정을 너무 단순하게 (3단계) 보면 중요한 전환점을 놓칩니다.
     7단계: 인식→검토→구매→온보딩→활용→재구매→추천
     각 전환점의 드롭오프 비율을 30%씩 개선하면 LTV는 3배 증가합니다. -->

1단계: 고객 세그먼트 정의
   - 주요 페르소나 2-3개 (타겟/틈새/확장)
   - 각 세그먼트의 문제점 (Pain)
   <!-- 💬 여정은 세그먼트별로 다릅니다.
        CTO와 마케팅 담당자의 여정은 완전히 다릅니다 -->

2단계: 인식 (Awareness)
   - 고객이 문제를 느끼는 순간
   - 우리 제품을 발견하는 경로 (상위 3-5개)
   - 터치포인트: Google Search, Product Hunt, 추천, 광고 등
   - 감정: (지금 모르는 상태) → 희망 / 의심

3단계: 검토 (Consideration)
   - 우리 웹사이트 도착 → 경쟁사 비교 시간
   - 정보 수집 채널: 문서, 리뷰, 데모, 커뮤니티
   - 의사결정자 (CEO? CTO? 재무담당?) 관여 시점
   - 감정: 의심 → 관심 / 우려
   <!-- 💬 이 단계에서 이탈하는 사람이 가장 많습니다. (전환율 3-15%)
        "왜 봤는데 안 샀나"를 분석하는 핵심 단계 -->

4단계: 구매 (Purchase)
   - 가입 프로세스 (몇 단계? 몇 분?)
   - 결제 방법 선택
   - 온보딩 자료 제공 시점
   - 감정: 우려 → 기대 / 불안

5단계: 온보딩 (Onboarding)
   - 첫 로그인 경험 (튜토리얼, 가이드)
   - 첫 번째 성공 경험까지 걸리는 시간 (Aha Moment)
   - 초기 설정 복잡도
   - 감정: 기대 → 흥미 / 혼란
   <!-- 💬 "Aha Moment까지 24시간 내 도달"이 리텐션 70% vs 30% 결정점입니다 -->

6단계: 활용 & 확대 (Expansion)
   - 일상적 사용 빈도 (daily, weekly, monthly?)
   - 점진적으로 더 많은 기능 사용
   - 팀 내 확산 (1명 → N명)
   - 감정: 흥미 → 신뢰 / 체증

7단계: 충성도 & 추천 (Advocacy)
   - 재구매 / 구독 갱신 의사
   - NPS (Net Promoter Score) — 추천 의향
   - 입소문, 리뷰 쓰기, 케이스 스터디 참여
   - 감정: 신뢰 → 애정 / 무관심
   <!-- 💬 추천하는 고객은 그냥 사용하는 고객보다 LTV 5배 높습니다 -->

8단계: 작성한 여정을 검토하세요.
   - 각 단계의 전환율이 현실적인가? (벤치마크와 비교)
   - "떨어져나가는 이유"가 구체적인가?
   - AI/데이터 기능이 있다면 특화된 터치포인트 추가?
   - 누락된 단계나 터치포인트가 있나?
   <!-- 💬 "왜 떨어져나가는가"의 근거가 약하면 개선책도 약합니다.
        실제 고객 피드백 또는 분석 데이터(GA, Mixpanel 등)로 검증하세요 -->

# 컨텍스트와 데이터
## 제품 / 서비스: {제품명, 카테고리}
## 주요 고객 세그먼트: {페르소나 1}, {페르소나 2}, {페르소나 3}
## 현재 전환율 데이터 (있다면):
   - 인식→검토: ___%
   - 검토→구매: ___%
   - 구매→활용: ___%
   - 활용→추천: ___%
## 분석 기간: {지난 분기 데이터 / 신규 고객 인터뷰 / 사용자 테스트}
```

**💡 Deep Tips:**

- **데이터 수집:**
  - 구글 애널리틱스 (사이트 방문자 흐름)
  - Mixpanel / Amplitude (인앱 행동)
  - Intercom / Zendesk (고객 지원 데이터, 문의 패턴)
  - 고객 인터뷰 (5-10명 깊이있게 들으면 80% 패턴 파악)
  - 이탈한 고객 설문 (취소 사유)

- **AI 제품이라면:**
  - AI 기능의 "Aha Moment" 명확화 (언제 가치를 느끼나?)
  - 할루시네이션 / 부정확성으로 인한 이탈 지점
  - 모델 응답 시간이 감정에 미치는 영향 (너무 느리면 이탈)
  - 데이터 프라이버시/보안에 대한 신뢰 구축 필요성
  - API 접근성 (개발자 온보딩 경로)

- **한국 SaaS:**
  - 국내 무료 체험 기간 기대치 (해외 14일 vs 한국 30일)
  - 신용카드 등록 필수 vs 선택 (심리적 장벽)
  - 로컬라이제이션 (한글화, 원화 가격, 로컬 결제)
  - 블라인드, 네이버 카페 입소문이 중요 터치포인트
  - 고객 지원 한글 - 응답 속도 → NPS에 큰 영향

- **Product Trio 확장:**
  - **PM:** 각 단계의 전환율, KPI, 이탈 사유
  - **엔지니어:** 기술적 마찰점 (로딩 속도, API 복잡도, 오류율)
  - **디자이너:** UI/UX 사용성, 온보딩 프로세스, 감정 변화 시각화


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 여정 범위가 불명확 | "첫 인지"부터 "재구매/추천"까지를 기본 범위로 하세요 |
| 2단계 | 감정 매핑이 주관적 | NPS 점수나 리뷰 감성 데이터가 있으면 활용하세요 |
| 3단계 | Pain Point가 너무 많음 | "이탈에 직접 영향을 주는" 것만 우선순위 1로 선택 |
| 5단계 | 개선 기회 평가 어려움 | 영향도(High/Low) × 실행 난이도(Easy/Hard) 매트릭스로 정리 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 고객 행동 데이터에서 자동으로 여정 맵을 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
수동 여정 맵은 한 번 만들면 업데이트가 안 됩니다. 행동 로그 데이터를 입력하면 실시간 여정 분석이 가능합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python + API 자동화

```python
import json
from datetime import datetime
from typing import Dict, List
import requests

class CustomerJourneyMapper:
    def __init__(self, product_name: str):
        self.product_name = product_name
        self.stages = [
            "awareness",
            "consideration",
            "purchase",
            "onboarding",
            "expansion",
            "advocacy"
        ]
        self.journey_data = {}

    def fetch_analytics_data(self, api_key: str, property_id: str) -> Dict:
        """
        Google Analytics 4 API에서 단계별 사용자 흐름 데이터 추출
        """
        headers = {
            'Authorization': f'Bearer {api_key}',
            'Content-Type': 'application/json'
        }

        query = {
            "date_ranges": [
                {
                    "start_date": "30daysAgo",
                    "end_date": "today"
                }
            ],
            "metrics": [
                {"name": "sessions"},
                {"name": "conversions"}
            ],
            "dimensions": [
                {"name": "eventName"}
            ]
        }

        try:
            response = requests.post(
                f'https://analyticsdata.googleapis.com/v1beta/properties/{property_id}:runReport',
                headers=headers,
                json=query
            )
            return response.json()
        except Exception as e:
            print(f"Analytics API 오류: {e}")
            return {}

    def fetch_support_tickets(self, zendesk_url: str, api_key: str) -> List[Dict]:
        """
        Zendesk에서 고객 지원 데이터 추출
        (이탈 사유, 자주 묻는 질문)
        """
        headers = {
            'Authorization': f'Bearer {api_key}',
            'Content-Type': 'application/json'
        }

        try:
            response = requests.get(
                f'{zendesk_url}/api/v2/tickets.json?query=type:problem',
                headers=headers
            )
            tickets = response.json().get('tickets', [])

            # 이탈 관련 키워드 필터링
            churn_keywords = ['cancel', '탈퇴', '문제', '불만']
            relevant_tickets = [
                t for t in tickets
                if any(kw in t.get('description', '').lower()
                       for kw in churn_keywords)
            ]
            return relevant_tickets
        except Exception as e:
            print(f"Zendesk API 오류: {e}")
            return []

    def analyze_journey_with_claude(self, context_data: Dict) -> str:
        """
        Claude API를 호출해서 여정 데이터 분석 및 인사이트 도출
        """
        from anthropic import Anthropic

        client = Anthropic()

        prompt = f"""
당신은 고객 경험 전략가입니다.

다음 {self.product_name}의 고객 여정 데이터를 분석하세요:

수집된 데이터:
{json.dumps(context_data, ensure_ascii=False, indent=2)}

다음을 포함한 상세 분석을 제시하세요:

1. 각 단계별 전환율 및 드롭오프 분석
2. "가장 큰 병목" — 가장 많은 고객이 떨어져나가는 지점
3. 각 단계에서의 감정 변화 추정
4. 개선 기회 (상위 3개)
5. AI 제품이라면: AI 기능과의 인터랙션 포인트
6. 추천 액션 아이템 (우선순위 포함)

마크다운 형식으로 정리하세요.
        """

        message = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )
        return message.content[0].text

    def generate_journey_report(self, analytics_data: Dict = None,
                                support_data: List[Dict] = None) -> Dict:
        """
        전체 여정 맵 생성
        """
        self.journey_data = {
            'product': self.product_name,
            'generated_at': datetime.now().isoformat(),
            'stages': {},
            'analysis': ''
        }

        # 각 단계별 기본 정보 초기화
        for stage in self.stages:
            self.journey_data['stages'][stage] = {
                'touchpoints': [],
                'emotion': None,
                'conversion_rate': None,
                'key_issues': [],
                'improvement_ideas': []
            }

        # 수집된 데이터로 분석
        context_data = {
            'analytics': analytics_data or {},
            'support_tickets': support_data or []
        }

        # Claude 분석
        self.journey_data['analysis'] = self.analyze_journey_with_claude(context_data)

        return self.journey_data

    def to_markdown(self) -> str:
        """마크다운 형식으로 내보내기"""
        output = f"# {self.product_name} 고객 여정 맵\n\n"
        output += f"생성일시: {self.journey_data['generated_at']}\n\n"
        output += "## 여정 단계별 분석\n\n"

        for stage, data in self.journey_data['stages'].items():
            output += f"### {stage.upper()}\n"
            output += f"- 감정: {data['emotion']}\n"
            output += f"- 전환율: {data['conversion_rate']}\n"
            output += f"- 주요 이슈: {', '.join(data['key_issues'])}\n"
            output += f"- 개선 아이디어: {', '.join(data['improvement_ideas'])}\n\n"

        output += f"\n## Claude 분석\n\n{self.journey_data['analysis']}"
        return output

# 사용 예
if __name__ == "__main__":
    mapper = CustomerJourneyMapper("Notion")

    # 분석 실행 (실제 API는 자신의 키로 대체)
    report = mapper.generate_journey_report()

    # 마크다운으로 내보내기
    with open("journey-map-notion.md", "w", encoding="utf-8") as f:
        f.write(mapper.to_markdown())

    print("고객 여정 맵이 생성되었습니다!")
```

### Claude Code / CLI 연동

```bash
# 제품의 고객 여정 분석
claude_code \
  --model claude-opus-4-6 \
  --file customer_journey_mapper.py \
  --args product_name="Figma" \
  --output journey-map-figma.md

# 여러 제품의 여정 비교
for product in "Figma" "Sketch" "Adobe XD"; do
  claude_code \
    --model claude-opus-4-6 \
    --file customer_journey_mapper.py \
    --args product_name="$product" \
    --output journey-map-${product// /-}.md
done

# 결과 통합 및 비교 분석
claude_code \
  --model claude-opus-4-6 \
  --prompt "다음 3개 제품의 여정을 비교분석: $(cat journey-map-*.md)" \
  --output competitive-journey-analysis.md
```

### Agent 워크플로우 연결

```
1️⃣ customer-journey-mapping.md 실행
   → journey-map.json 생성

2️⃣ persona-profiling.md로 연결
   → 입력: journey-map의 세그먼트
   → 작업: 각 세그먼트의 페르소나 상세 정의

3️⃣ problem-framing.md로 연결
   → 입력: 각 단계의 "병목점"
   → 작업: "우리가 해결할 가장 중요한 문제는?"

4️⃣ 최종 결과
   → persona + journey + problem = 제품 전략의 기초
```

---

## 📊 실행 결과 예시

### Layer 1 실행 결과

```
[ChatGPT에 위 Quick Start 프롬프트 복사]

Figma의 고객 여정을 5개 단계로 그리세요...

=== 결과 (5분) ===

1단계: 인식
   - 어떻게 알았나: ProductHunt, 디자이너 입소문, Google
   - 감정: 😊 (새로운 도구를 발견한 기쁨)

2단계: 검토
   - 정보 처리: 웹사이트, YouTube 튜토리얼, Sketch 비교
   - 감정: 😕 (결정 어려움, 비용이 비싼 건 아닌지)

3단계: 구매
   - 가입: 이메일 → 무료 플랜 시작
   - 감정: 😊 (기대감)

4단계: 사용
   - 첫 프로젝트 생성 및 협업
   - 감정: 😕 → 😊 (처음엔 혼란, 사용하다 보니 편함)

5단계: 추천
   - 팀 동료에게 초대
   - 감정: 😊 (자신감 있게 추천)
```

### Layer 2 실행 결과

```
# Figma 고객 여정 맵 (상세)

## 1. 인식 (Awareness)
**감정**: 🤔 → 😊 (호기심 → 기대감)

**터치포인트**:
- 소셜 미디어 (X/드리블, ProductHunt)
- 디자이너 커뮤니티 (한국: 블라인드, 당근마켓)
- Google 검색 ("협업 디자인 툴", "Figma vs Sketch")
- 입소문 (팀 동료 권유)

**드롭오프**: ~5% (이 정도는 정상)

---

## 2. 검토 (Consideration)
**감정**: 😕 → 🤔 (의심 → 관심)

**주요 활동**:
- figma.com 방문 (3-5분)
- Sketch, Adobe XD와 비교
- YouTube 튜토리얼 시청 (10-20분)
- 리뷰 읽기 (G2, ProductHunt)

**병목점**: "정말 Sketch보다 나은가?" 불확실성
**드롭오프**: ~40% (여기서 가장 많이 떨어져나감)

**개선 기회**:
- 대면 비교 도구 ("Figma vs Sketch" 이동형 가이드)
- 데모 영상 (2분 단위, 핵심만)
- 무료 세미나 (입소문)

---

## 3. 구매 (Purchase)
**감정**: 😊 (결정함)

**프로세스**:
1. figma.com 가입 (이메일 또는 Google/Slack SSO)
2. 무료 플랜으로 시작 (결제 X)
3. 프로젝트 생성 시작

**특징**: "무료 시작 → 필요시 유료 업그레이드"는 심리적 이점 큼

**드롭오프**: ~10% (가입 단계는 낮음)

---

## 4. 온보딩 (Onboarding)
**감정**: 😕 → 🤔 → 😊 (혼란 → 학습 → 쾌감)

**Aha Moment**: "첫 협업 초대 후 동료가 실시간으로 같은 파일 편집하는 순간"

**프로세스**:
1. 빈 캔버스 (처음에는 막막함)
2. 튜토리얼 팝업 가이드 (좋음)
3. 첫 프로젝트 생성
4. 팀원 초대 (협업의 힘을 느낌) ← Aha Moment!

**병목점**: "3D 기능, 프로토타입이 복잡" (초보자 입장)
**드롭오프**: ~20% (이 단계에서 떨어져나가는 사람들)

---

## 5. 확대 (Expansion)
**감정**: 😊 (신뢰감)

**활동**:
- 프로젝트 수 증가 (3개 → 10개+)
- 더 많은 팀원 추가
- 고급 기능 활용 (프로토타입, 디자인 시스템)
- 유료 플랜 업그레이드 시점

**드롭오프**: ~5% (이미 가치를 느낀 사람들)

---

## 6. 추천 (Advocacy)
**감정**: 😍 (애정)

**활동**:
- 새 팀원에게 초대
- 커뮤니티 글 작성 ("Figma로 바뀐 팀 문화")
- G2 리뷰 작성
- 블라인드 추천글

**NPS**: +70점 (매우 높음)
**LTV 증가**: 추천받은 고객의 리텐션 80% (평균 50% vs)

---

## 최고 병목점 분석

**가장 많이 떨어져나가는 지점**: 검토 단계 (40% 이탈)

**원인**:
1. Sketch vs Figma 선택 불확실성
2. 가격 비교 (Sketch: 연 $99 vs Figma: 월 $15)
3. 호환성 우려 (지금의 Sketch 파일은?)

**해결책**:
- "무료로 시작하고 필요시 유료" 메시지 강화
- Sketch→Figma 마이그레이션 툴/가이드
- 30일 무료 체험 (Sketch 비교용)
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 여정 맵에서 '감정 곡선이 가장 낮은 단계'가 실제 이탈 데이터와 일치하는지 확인하세요
2. **[논쟁 지점]** 여정 맵의 단계 수를 5단계로 할지 7단계로 할지는 제품 복잡도에 따라 다릅니다
3. **[자기 검증]** 여정 맵의 핵심 터치포인트 1개를 실제 사용자 세션 리플레이로 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| 여정 단계 정의 | → `persona-profiling.md` | 각 단계별 주요 고객 페르소나 심화 |
| 병목점 리스트 | → `problem-framing.md` | "해결할 가장 중요한 문제는?" 재정의 |
| 감정 변화 | → `jobs-to-be-done.md` | 각 단계에서 고객이 "고용"하는 진짜 이유 |
| 전환율 데이터 | → `competitor-sentiment.md` | 경쟁사 여정과 비교 분석 |

---

## 📝 참고자료 및 도구

- **Google Analytics 4**: https://analytics.google.com (단계별 흐름)
- **Mixpanel**: https://mixpanel.com (고급 행동 분석)
- **Amplitude**: https://amplitude.com (코호트, 퍼널 분석)
- **Intercom**: https://intercom.com (고객 행동 + 지원)
- **Zendesk**: https://zendesk.com (고객 지원 데이터)
- **Hotjar**: https://hotjar.com (사용자 녹화, 히트맵)
- **Figma Jam**: 팀과 협업해서 여정 맵 그리기
