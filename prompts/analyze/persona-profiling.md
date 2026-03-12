# 👤 페르소나 프로파일링 (Persona Profiling)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 30분+ (Build)
> 워크플로우: → `customer-journey-mapping.md` → `jobs-to-be-done.md` → `problem-framing.md`

---

## 🎯 이 프롬프트가 해결하는 문제

고객을 일반적으로만 이해합니다. "PM", "엔지니어", "스타트업"이라는 범주로는 기능 설계나 마케팅 메시지가 맞지 않습니다. 실제 고객은 "30대 서울 거주 스타트업 CTO로 팀이 5명, 예산 제약 있지만 빠른 속도를 원함" 정도의 상세도가 필요합니다. 이 프롬프트는 **데이터 기반 페르소나**를 만들어서 모든 기획/마케팅 결정을 구체화합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `competitor-sentiment.md`에서 발견된 페르소나를 더 깊이 프로파일링할 때 연결됩니다.

이전 프롬프트 결과에서 **페르소나 클러스터, 감성 점수, 핵심 니즈**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 타겟 사용자의 페르소나를 정의할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
{대상 고객 세그먼트}의 페르소나를 만드세요.

다음을 포함하세요:
1. 이름, 나이, 직책, 회사 규모
2. 월급/예산 (실제 구매력)
3. 업무 목표 (뭘 하려고 우리 제품을 찾나?)
4. 주요 고통점 (pain point) 3가지
5. 성공 지표 (이 사람이 "성공했다"고 느끼는 조건)
6. 사용 시간 & 빈도
7. 선호 커뮤니케이션 (이메일? Slack? 전화?)

한 명의 구체적인 인물을 상상하고 쓰세요.
일반적인 표현 X, 이름 O.
```

**💡 Quick Tips:**
- "평균적인 사람" X, "실제로 있을 법한 사람" O
- 나이, 위치, 회사 규모는 구체적 숫자로
- "행복하다" X, "월급이 5000만원인데 좋은 도구에 $100/월 쓸 수 있다" O


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 사용자 데이터가 부족 | 초기 단계면 경쟁사 리뷰와 커뮤니티 분석으로 가설 페르소나를 먼저 만드세요 |
| 페르소나가 너무 많아짐 | 핵심 페르소나 3-4개만 유지하세요. "주요" vs "보조" 구분 |
| B2B라서 복잡 | 의사결정자, 사용자, 관리자 페르소나를 각각 만드세요 |
| 페르소나가 너무 일반적 | "구체적 행동 패턴"과 "정확한 목표 수치"를 추가하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 페르소나를 데이터 기반으로 깊이 있게 구축하고 싶은 분입니다.
"가상의 인물"이 아니라 "실제 데이터에서 추출한 대표 유형"을 만들고 싶다면 이걸 써보세요.

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


```
# 역할: 사용자 심리학자 & 마케팅 기획자
# 목표: 구체적이고 측정 가능한 페르소나를 데이터 기반으로 구축

# Reasoning Strategy
<!-- 💬 왜 상세한 페르소나가 필요한가?
     고객을 일반화하면: "PM을 위한 도구" (너무 넓음)
     구체화하면: "5명 스타트업의 기술 CTO, 예산 부족, 속도 필요" (명확)

     같은 "PM"이어도:
     - 포춘 500 기업 PM: 보안, 규정 준수 우선
     - 스타트업 PM: 속도, 가격 우선
     마케팅 메시지도 기능도 완전히 다릅니다 -->

1단계: 데이터 수집
   <!-- 💬 페르소나는 추측이 아니라 데이터에 기반해야 합니다 -->

   - 고객 인터뷰 (5-10명, 깊이 있게)
   - 사용자 세그먼트 분석 (GA, Mixpanel)
   - 고객 지원 데이터 (문의 유형, 흔한 질문)
   - 영업팀 피드백 (실제 대화 기록)
   - 경쟁사 리뷰 (G2, ProductHunt에서 고객 말)

2단계: 기본 인구통계 (Demographics)
   <!-- 💬 기본부터: 누구인가? -->

   - 이름 (가상 이름, 실제 고객 이름도 가능)
   - 나이 & 세대
   - 직책 (VP vs Manager vs Individual Contributor)
   - 회사 규모 & 산업
   - 위치 (한국? 서울? 강남?)
   - 경력 (몇 년?)

3단계: 심리그래픽 (Psychographics) — 진짜 중요
   <!-- 💬 인구통계만으로는 부족합니다.
        같은 나이, 직급이어도 가치관/목표가 다르면 고객이 아닙니다 -->

   - 업무 목표 (구체적)
     * "팀 생산성 30% 향상"
     * "월 10시간 반복 작업 자동화"
     * "고객 이탈율 5% → 2%로"

   - 성공의 정의
     * "분기 OKR 달성"
     * "팀에서 신뢰받기"
     * "경영진에게 좋은 평가받기"

   - 개인적 가치관
     * "속도와 효율" 중시 vs "품질과 안정성" 중시
     * "혁신" vs "안정"
     * "협력" vs "개인 업적"

4단계: 구매 행동 (Buying Behavior)
   <!-- 💬 이 사람은 어떻게 제품을 찾고 구매하나? -->

   - 의사결정 방식 (혼자 결정? 팀과 함께? 경영진 허가?)
   - 의사결정 속도 (1주? 1개월? 분기?)
   - 구매력 (월급, 팀 예산 범위)
   - 가격 민감도 (100만원 vs 1000만원 차이가 큰가?)
   - 신뢰 기준 (리뷰? 입소문? 직접 데모?)
   - 구매 후 기대 (즉시 효과? 장기 ROI?)

5단계: 사용 패턴 (Usage)
   <!-- 💬 사는 것과 쓰는 것은 다릅니다 -->

   - 사용 빈도 (daily / weekly / monthly?)
   - 사용 시간 (몇 분? 몇 시간?)
   - 사용 목적 (몇 가지 기능만? 전체?)
   - 팀 내 역할 (처음 도입한 사람? 강제로 쓰는 사람?)
   - 성공/실패 케이스 (언제 우리 제품이 도움? 언제 도움 안 됨?)

6단계: 채널 & 커뮤니케이션
   <!-- 💬 어디서 만날 것인가? -->

   - 정보 습득 채널
     * "Product Hunt 체크하는 사람"
     * "Hacker News 읽는 사람"
     * "블라인드에서 정보 얻는 사람" (한국)
     * "구글 검색"
     * "동료 추천"

   - 선호 커뮤니케이션
     * 이메일 vs Slack vs 전화 vs LinkedIn
     * 긴 문서 vs 짧은 영상
     * 기술 용어 vs 비유

   - 신뢰 대상
     * 리뷰 사이트
     * 업계 인플루언서
     * 동료/선배
     * 공식 데모

7단계: 고통점 & 동기 (Pains & Motivations)
   <!-- 💬 왜 우리 제품이 필요한가? -->

   **고통점 (Pain)**:
   - 현재 상황의 문제
   - 감정적 고통 (스트레스, 불안)
   - 비즈니스 영향 (비용, 속도 손실)
   - 기술적 문제 (통합 어려움, 복잡함)

   **동기 (Motivation)**:
   - 이 문제를 해결하면 얻는 이득
   - 감정적 보상 (만족감, 신뢰)
   - 비즈니스 보상 (비용 절감, 수익 증가)
   - 경력상 보상 (평가, 승진)

8단계: 경쟁사 vs 우리
   <!-- 💬 이 페르소나는 경쟁사를 선택할까? 아니면 우리를 선택할까? -->

   - 고려 중인 대안 (경쟁사? 손수 만들기? 아무것도 안 하기?)
   - 각 대안 대비 우리의 장점
   - 우리 단점 (이것 때문에 포기할까?)
   - 구매 결정 기준 (가격? 기능? 지원?)

9단계: 작성한 페르소나를 검토하세요.
   <!-- 💬 자기검증:
        [ ] 이 페르소나는 실제로 우리 고객인가? (아니면 이상적인 고객?)
        [ ] 구체적인가? (이름, 회사, 월급, 업무 목표가 명확한가?)
        [ ] 편향이 없는가? (우리 가정만 담지 않았나?)
        [ ] 실제 데이터로 검증했나? (고객 인터뷰, 사용 데이터)
        [ ] 다른 페르소나는? (1개만으로 부족 — 보통 2-4개)
   -->

# 컨텍스트와 데이터
## 회사 & 제품: {회사명}, {제품명}
## 타겟 세그먼트: {세그먼트명}
## 데이터 소스:
   - 고객 인터뷰: {몇 명, 어떻게}
   - 분석 데이터: {GA, 고객 지원 데이터 등}
   - 경쟁사 리뷰: {G2, ProductHunt 등}
## 분석 대상 기간: {최근 분기, 6개월 등}
```

**💡 Deep Tips:**

- **데이터 수집:**
  - 고객 인터뷰 (예: "지난주 스타트업 CTO 3명과 1시간씩 대화")
  - GA 세그먼트 분석 (어떤 사용자층이 활동적인가?)
  - Zendesk/Intercom 데이터 (고객 지원 문의 패턴)
  - 영업/CS팀 피드백 (실제 판매 대화 기록)
  - 취소/이탈 고객 인터뷰 (왜 떠났는가?)

- **AI 제품이라면:**
  - AI 신뢰도 (이 페르소나는 AI를 얼마나 믿나?)
  - 기술 리터러시 (AI 이해도, 프롬프트 엔지니어링 능력)
  - 규제 관심도 (데이터 보안, AI 윤리 얼마나 신경 쓰나?)
  - 비용 감수 (API 비용이 비싸도 괜찮나?)

- **한국 SaaS 특화:**
  - 예산 (평균 한국 PM의 도구 연간 예산 = 500만원 정도)
  - 신뢰도 (한국은 "입소문" "블라인드" "동료 추천" 매우 중요)
  - 지원 언어 (한글 지원 필수)
  - 결제 방법 (신용카드, 계좌이체, 무통장입금)
  - 규제 민감도 (개인정보 보호법, 정부 심사)

- **Product Trio 확장:**
  - **PM:** 세그먼트별 업무 목표, 성공 지표, 고통점
  - **엔지니어:** 기술 리터러시, 통합 요구사항, 성능 기대치
  - **디자이너:** 선호하는 UI 복잡도, 접근성 요구, 커뮤니케이션 스타일


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 데이터 소스가 없음 | 최소한 앱 리뷰 + 지원 티켓으로 시작하세요 |
| 2단계 | 클러스터가 명확하지 않음 | 행동 패턴(사용 빈도, 주요 기능)으로 그룹핑하세요 |
| 3단계 | 페르소나 검증이 어려움 | 팀 내에서 "이 사람 아는 것 같다"는 공감대가 있는지 확인 |
| 4단계 | 페르소나별 전략이 겹침 | 각 페르소나의 "가장 큰 고통"이 다른지 확인. 같으면 합치세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 사용자 데이터에서 자동으로 페르소나를 클러스터링합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
수동 페르소나는 주관적이고 업데이트가 안 됩니다. 코드로 데이터 기반 페르소나를 만들면 분기별 자동 갱신이 가능합니다.

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
from anthropic import Anthropic

class PersonaGenerator:
    def __init__(self, product_name: str):
        self.product_name = product_name
        self.client = Anthropic()
        self.personas = []

    def analyze_customer_data(self, interview_transcripts: List[str],
                             analytics_data: Dict,
                             support_data: List[Dict]) -> List[Dict]:
        """
        고객 인터뷰, 분석 데이터, 지원 데이터에서 페르소나 자동 추출
        """
        combined_context = f"""
고객 인터뷰:
{chr(10).join(interview_transcripts)}

분석 데이터:
{json.dumps(analytics_data, ensure_ascii=False, indent=2)}

고객 지원 문의 유형:
{json.dumps(support_data[:10], ensure_ascii=False, indent=2)}
        """

        prompt = f"""
당신은 사용자 리서치 전문가입니다.

{self.product_name}의 고객 데이터에서 2-3개의 주요 페르소나를 추출하세요.

각 페르소나마다 다음을 포함하세요:
1. 이름, 나이, 직책, 회사 규모
2. 월급 범위 (구매력)
3. 업무 목표 (구체적)
4. 고통점 TOP 3
5. 성공 지표
6. 선호 커뮤니케이션
7. 고려 중인 대안
8. 우리 제품을 선택할 확률 (%)

JSON 형식으로 응답하세요.
        """

        message = self.client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": f"{prompt}\n\n{combined_context}"}
            ]
        )

        try:
            response_text = message.content[0].text
            import re
            json_match = re.search(r'\[.*\]', response_text, re.DOTALL)
            if json_match:
                personas = json.loads(json_match.group())
                return personas
        except Exception as e:
            print(f"페르소나 추출 오류: {e}")

        return []

    def segment_analytics_data(self, analytics_events: List[Dict]) -> Dict:
        """
        GA 이벤트 데이터에서 사용자 세그먼트 자동 분류
        """
        # 간단한 세그먼트: 활동성 기반
        segments = {
            'highly_active': [],
            'moderate': [],
            'inactive': []
        }

        for user in analytics_events:
            event_count = user.get('event_count', 0)
            if event_count > 100:
                segments['highly_active'].append(user)
            elif event_count > 10:
                segments['moderate'].append(user)
            else:
                segments['inactive'].append(user)

        return {
            'highly_active_count': len(segments['highly_active']),
            'moderate_count': len(segments['moderate']),
            'inactive_count': len(segments['inactive']),
            'avg_session_duration': {
                'highly_active': '45분',
                'moderate': '15분',
                'inactive': '3분'
            }
        }

    def generate_persona_report(self, personas: List[Dict]) -> str:
        """
        페르소나들을 비교하는 리포트 생성
        """
        prompt = f"""
다음은 {self.product_name}의 주요 페르소나들입니다:

{json.dumps(personas, ensure_ascii=False, indent=2)}

각 페르소나에 대한 마케팅 및 기능 개발 전략을 제시하세요:

1. **각 페르소나별 가치제안** (이들에게 어떤 메시지로 어필할 것인가?)
2. **공통 고통점** (모든 페르소나가 공통으로 원하는 기능)
3. **차별화 기능** (특정 페르소나만을 위한 기능)
4. **우선순위** (어느 페르소나에 집중할 것인가?)
5. **마케팅 채널** (각 페르소나를 어디서 만날 것인가?)

마크다운 형식으로 상세히 작성하세요.
        """

        message = self.client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        return message.content[0].text

    def to_markdown(self, personas: List[Dict], report: str) -> str:
        """마크다운 형식으로 내보내기"""
        output = f"# {self.product_name} 페르소나 프로파일\n\n"
        output += f"생성일시: {datetime.now().isoformat()}\n\n"

        for i, persona in enumerate(personas, 1):
            output += f"## 페르소나 {i}: {persona.get('name', 'Unnamed')}\n\n"
            output += f"- **나이/직책**: {persona.get('age')}세, {persona.get('title')}\n"
            output += f"- **회사**: {persona.get('company_size')} 규모\n"
            output += f"- **월급**: {persona.get('salary_range')}\n\n"

            output += f"### 업무 목표\n"
            output += f"{persona.get('goals', 'N/A')}\n\n"

            output += f"### 고통점\n"
            for pain in persona.get('pain_points', []):
                output += f"- {pain}\n"
            output += "\n"

            output += f"### 성공 지표\n"
            output += f"{persona.get('success_metrics', 'N/A')}\n\n"

            output += f"### 우리 선택 확률\n"
            output += f"{persona.get('selection_probability', 'N/A')}%\n\n"

            output += "---\n\n"

        output += f"## 전략 분석\n\n{report}"
        return output

# 사용 예
if __name__ == "__main__":
    generator = PersonaGenerator("Notion")

    # 샘플 데이터
    interviews = [
        "인터뷰 1: 스타트업 PM, 팀 5명, 속도 중요...",
        "인터뷰 2: 대기업 PO, 규정 준수 중요...",
    ]

    analytics_data = {
        'total_users': 1000,
        'daily_active': 350,
        'avg_session_duration': '20분'
    }

    support_data = [
        {'topic': '가격', 'frequency': 15},
        {'topic': '기능 요청', 'frequency': 30},
        {'topic': '기술 지원', 'frequency': 10},
    ]

    # 페르소나 생성
    personas = generator.analyze_customer_data(interviews, analytics_data, support_data)
    report = generator.generate_persona_report(personas)

    # 마크다운으로 내보내기
    with open("personas-notion.md", "w", encoding="utf-8") as f:
        f.write(generator.to_markdown(personas, report))

    print("페르소나 프로파일이 생성되었습니다!")
```

### Claude Code / CLI 연동

```bash
# 페르소나 프로파일 생성
claude_code \
  --model claude-opus-4-6 \
  --file persona_generator.py \
  --args product_name="Figma" \
  --input customer-data.json \
  --output personas-figma.md

# 여러 제품의 페르소나 비교
for product in "Figma" "Sketch" "Adobe XD"; do
  claude_code \
    --model claude-opus-4-6 \
    --file persona_generator.py \
    --args product_name="$product" \
    --input customer-data-${product// /-}.json \
    --output personas-${product// /-}.md
done
```

---

## 📊 실행 결과 예시

### Layer 1 실행 결과

```
[Quick Start 프롬프트 사용]

Notion의 타겟 페르소나를 만드세요...

=== 결과 (5분) ===

페르소나 1: "빨간 머리 민수"
- 나이: 32세
- 직책: 스타트업 기술 리더 (CTO)
- 회사: 10명 규모 AI 스타트업
- 월급: 4500만원
- 월 도구 예산: 100만원 정도

업무 목표:
- 팀이 같은 정보를 보게 하기
- 회의록 자동화
- 제품 스펙 관리

고통점:
1. 팀원들이 어디에 뭘 저장했는지 자꾸 까먹음
2. Google Docs + Slack + 노션 3개를 쓰고 있어서 정보 흩어짐
3. 새 팀원 온보딩할 때마다 "여기 봐, 저기 봐" 반복

성공 지표:
- "팀이 Notion만 쓰는 상황"
- 월 10시간 정보 정리 시간 절감

선호 커뮤니케이션:
- Product Hunt, Hacker News 체크
- 블라인드에서 정보 얻음
- 동료 추천 신뢰

---

페르소나 2: "대기업 미영"
- 나이: 37세
- 직책: 대기업 PM
- 회사: 5000명 규모
- 월급: 6000만원
- 월 도구 예산: 무제한

업무 목표:
- 규정 준수 + 보안
- 팀 협업 (보통 20명 이상)
- 정기 보고

고통점:
1. 보안/규정 준수 (개인정보, 감사)
2. 복잡한 권한 설정 필요
3. 엔터프라이즈 SLA 필요

성공 지표:
- "감사 통과"
- "팀 협업이 순식간"

선호 커뮤니케이션:
- 영업사원이랑 대면 미팅
- 계약서, SLA 명확함
- 한글 지원 필수
```

### Layer 2 실행 결과

```
# Notion 페르소나 프로파일 (한국 SaaS 특화)

## 페르소나 1: "빨간 머리 민수" (스타트업 기술 리더)

### 기본 정보
- **이름**: 민수 (가명)
- **나이/성별**: 32세, 남성
- **직책**: CTO (기술 리더)
- **회사**: 10명 규모 AI 스타트업
- **경력**: 10년 (전직: 네이버)

### 재정 상황
- **월급**: 4,500만원 (초기 스톡옵션 포함)
- **개인 도구 예산**: 월 ~100만원
- **회사 예산**: 분기 ~300만원 (협상 가능)
- **가격 민감도**: 중간 (효율성 있으면 비용 증가 허용)

### 업무 목표 (Functional)
1. **팀 정보 일원화**: "Google Docs + Slack 분산 → Notion 한 곳"
2. **온보딩 자동화**: 새 팀원 온보딩 2시간 → 30분
3. **제품 스펙 관리**: PRD, 기술 요구사항, 마크다운 모두 한 곳에

### 감정적 목표 (Emotional)
- "체계적인 리더" 이미지 ("와, 우리 팀 정보 관리 진짜 잘되네")
- 팀원들에게 신뢰받기 ("민수가 전체 그림을 봐야 우리가 일한다")
- 경영진에게 인상주기 ("투명한 운영")

### 고통점 (Pains) — TOP 3

**1순위: 정보 분산 (가장 심함)**
- 현상: 요구사항이 이메일, Slack, 노션, 한 팀원 머리에만 있음
- 영향: 매주 1-2시간 "어디에 뭐 있더라" 찾기
- 감정: 답답함, 불안감 ("혹시 뭘 놓친 건 아닐까?")
- 비용: 월 ~10시간 손실 (시간 × 평균 임금 = 월 ~300만원 손실)

**2순위: 온보딩 시간 낭비**
- 현상: 새 팀원올 때마다 "여기는 이렇게, 저기는 저렇게" 설명 반복
- 영향: 월 1-2명 새 팀원 × 2시간 = 월 ~4시간
- 감정: 번거로움, 나만 병목인 기분

**3순위: 버전 관리 혼란**
- 현상: "이건 최신 버전인가?" 확인이 어려움
- 예: PR에서 5개월 된 PRD 참고해서 삽질
- 영향: 개발 이슈로 이어짐 (개발자가 2시간 낭비)

### 성공의 정의

**기능적 성공**:
- "Notion만 쓰는 상황" (1개 소스 오브 트루스)
- 온보딩 시간 50% 단축 (2시간 → 1시간)
- "최신 버전 확인" 0초 (자동)

**감정적 성공**:
- "우리 팀 정보가 정말 깔끔하다는 신뢰감"
- 경영진 보고 시 "투명하고 전문적" 느낌

**측정 지표**:
- 주 1회 "정보 찾으러 시간" → 월 10시간 → 월 2시간
- 새 팀원 "Notion에서만 배움" 비율 → 90%
- "회의에서 정보 못 찾음" 사건 → 0건/월

### 사용 패턴
- **빈도**: 거의 매일 (아침 일어나서 확인, 회의 때, 개발 전)
- **시간**: 주 ~3-5시간
- **주요 기능**: Database (할일, 버그), Wiki (문서화), Calendar (일정)
- **팀 규모**: 개인 + 팀 공유 (모두가 접근)
- **성공 케이스**:
  - "스프린트 계획이 한 페이지에" ✓
  - "팀원이 자동으로 체크인" ✓
- **실패 케이스**:
  - "API 복잡해서 Zapier 연동 포기" ✗
  - "권한이 세분화 안 돼서 민감 정보 공개 걱정" ✗

### 선호 커뮤니케이션
- **정보 출처**:
  - Product Hunt (매주 체크)
  - Hacker News (매일)
  - 블라인드 (매일 봄 — "한국 개발자들 평가")
  - 동료 추천 (가장 신뢰도 높음)
- **선호 포맷**:
  - 짧은 트위터 스타일 (길면 안 봄)
  - 유튜브 튜토리얼 (글 안 읽음)
  - 데모 영상 (2-3분, 핵심만)
- **신뢰 대상**:
  - 같은 CTO들의 후기
  - 실제 사용하는 팀의 리뷰
  - 공식 문서 (한글)

### 고려 중인 대안
1. **Confluence** (대기업용, 너무 복잡)
2. **Asana** (프로젝트 관리 특화, Notion만큼 유연하지 않음)
3. **Google Docs + Sheets 조합** (지금 쓰고 있음 — 불만족)

### 우리(Notion) 선택할 확률
**85%** (매우 높음)
- 이유:
  - 무료로 시작 가능 (심리적 진입장벽 낮음)
  - 유연함 (스타트업이 필요한 모든 걸 할 수 있음)
  - 커뮤니티 활발 (템플릿, 팁, 블라인드 공유 많음)
- 안 할 확률 15%:
  - 너무 느려지면 (성능 이슈)
  - API 복잡 + 한글 지원 부족
  - Confluence 같은 엔터프라이즈급 기능 필요 (팀 30명 이상 확장)

---

## 페르소나 2: "대기업 미영" (엔터프라이즈 PM)

[유사하게 상세 작성...]

---

## 페르소나 3: "학생 지현" (개인 사용자)

[유사하게 상세 작성...]

---

## 페르소나별 마케팅 & 기능 전략

### 페르소나 1 (민수): 스타트업 기술 리더
**가치제안**:
- "정보 산란에서 벗어나, 팀이 한곳만 보게 하세요"
- "온보딩 시간 50% 단축, 팀이 자동으로 정보 입력"

**우선 기능**:
1. Database 템플릿 (할일, 버그, 스펙)
2. 권한 (Private/Public 명확)
3. API (외부 도구와 연동)

**마케팅 채널**:
- Product Hunt, Hacker News
- 개발자 커뮤니티 (블라인드, 개발자 행사)
- "CTO들 이야기" 콘텐츠

---

### 페르소나 2 (미영): 대기업 PM
**가치제안**:
- "규정 준수하면서도 팀 협업 빠르게"
- "감사 통과, 권한 세분화"

**우선 기능**:
1. 권한 (팀, 페이지, 속성 레벨)
2. 감사 로그
3. SSO 연동 (회사 계정 통합)

**마케팅 채널**:
- LinkedIn B2B
- 영업 미팅 (데모, SLA)
- 엔터프라이즈 케이스 스터디

---

## 🎯 우선순위
1. **페르소나 1 (민수)**: 우리 핵심 고객 (무료 → 유료 전환율 높음)
2. **페르소나 3 (지현)**: 입소문 시발점 (개인 → 기업으로)
3. **페르소나 2 (미영)**: LTV 높지만 영업 비용도 높음 (중기 전략)
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 페르소나가 '인구통계'만으로 정의되어 있다면 '행동 패턴'과 '동기'를 추가하세요
2. **[논쟁 지점]** 페르소나 수를 3개로 할지 5개로 할지는 제품 단계에 따라 다릅니다 — 초기에는 1개로 집중
3. **[자기 검증]** 핵심 페르소나 1명이 실제 고객 DB에서 몇 %를 차지하는지 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| 페르소나별 고통점 | → `problem-framing.md` | "각 페르소나의 가장 큰 문제는?" |
| 사용 패턴 | → `customer-journey-mapping.md` | 페르소나의 여정 맵 재구성 |
| 가치제안 | → `positioning-strategy.md` (decide/) | 페르소나별 포지셔닝 메시지 |
| 마케팅 채널 | → `storytelling.md` (communicate/) | 각 페르소나별 콘텐츠 전략 |

---

## 📝 참고자료

- **"The Personas Manifesto"** (Alan Cooper)
- **"Lean UX"** by Jeff Gothelf (린 페르소나 방법론)
- **Xtensio**: https://xtensio.com/personas (페르소나 템플릿)
- **Userinterviews.com**: 고객 인터뷰 리크루팅
- **Respondent.io**: 타겟 인터뷰이 찾기 (유료)
