# 🌍 PESTEL 분석 (Macro Environment Analysis)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 30분+ (Build)
> 워크플로우: → `company-profiling.md` → `problem-framing.md`

---

## 🎯 이 프롬프트가 해결하는 문제

산업 전체를 흔들 수 있는 거시 환경 변화를 놓칩니다. 새로운 규제가 나오거나, 기술 트렌드가 바뀌거나, 경제가 흔들릴 때 회사의 전략이 산으로 갑니다. PESTEL 분석은 **정치(Political), 경제(Economic), 사회(Social), 기술(Technology), 환경(Environmental), 법률(Legal)** 6가지 거시 환경을 체계적으로 분석해서 미래 위험과 기회를 찾습니다.

---

## 📥 이전 프롬프트에서 받는 입력

> 단독 사용 가능. `positioning-strategy.md`와 함께 시장 진출 전략 수립 시 연결됩니다.

이전 프롬프트 결과에서 **타겟 시장, 산업, 제품 카테고리**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 제품/사업의 거시 환경 요인을 파악할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
{산업명} 또는 {국가} 시장의 PESTEL을 분석하세요.

6가지 카테고리:
1. Political (정치적): 정부 정책, 선거, 국제 관계
2. Economic (경제적): 금리, 인플레, 환율, GDP
3. Social (사회적): 인구, 소비 트렌드, 가치관
4. Technology (기술): 신기술 등장, 자동화, AI
5. Environmental (환경): 규제, 지속가능성
6. Legal (법률): 새로운 법, 규제, 소송 위험

각 항목에서:
- 현재 상황 1-2줄
- 우리에게 미칠 영향 (기회 vs 위협)
- 대응 방안

예:
Political: 한국 정부가 AI 규제 강화 → 기회: 규제 준수 서비스 개발 가능
          위협: 비용 증가
```

**💡 Quick Tips:**
- 최근 3-6개월 뉴스 헤드라인만 봐도 충분
- 국가/산업별로 PESTEL의 중요도가 다름 (AI는 Tech & Legal 중요)
- "위협"만 보지 말고 "기회"도 찾기


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 산업이 특수해서 PESTEL이 안 맞음 | 6개 요인 중 해당 산업에 관련 없는 것은 건너뛰세요. 대신 관련 요인을 더 깊이 분석 |
| 글로벌 vs 국내 분석 | 시장별로 PESTEL을 따로 작성하세요. 한국 규제와 미국 규제는 매우 다릅니다 |
| 데이터/소스를 모르겠음 | 뉴스 검색, 정부 정책 사이트, 산업 보고서를 AI에게 요약 요청하세요 |
| 결과가 너무 넓음 | "우리 제품에 직접 영향을 주는 요인"만 필터링하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — PESTEL 분석을 AI 산업 맥락에 맞춰 전문적으로 수행하고 싶은 분입니다.
정치, 경제, 사회, 기술, 환경, 법률 각 요인이 제품에 미치는 영향을 분석하고 싶다면 이걸 써보세요.

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
# 역할: 거시경제 & 산업 분석가
# 목표: 6가지 외부 환경 변수를 분석하고, 회사 전략에 미치는 영향 파악

# Reasoning Strategy
<!-- 💬 왜 6가지를 나누나?
     각각 다른 시간 스케일과 불확실성을 가지고 있습니다.
     Political(느림, 높은 영향) vs Technology(빠름, 높은 영향)
     전략 수립 시 각각을 다르게 대응해야 합니다 -->

1단계: Political (정치/정책 환경)
   <!-- 💬 정치는 느리지만 강력합니다. 한 번 정책이 바뀌면 돌이킬 수 없습니다. -->

   - 현 정부의 산업 정책 (예: AI 규제, 스타트업 지원)
   - 차기 정부/야당의 정책 방향 (불확실성)
   - 국제 관계 (한미, 한중 무역 긴장)
   - 정치 안정성 (국정 개입, 정치 파업 등)

   우리에게의 영향:
   - 기회: _____
   - 위협: _____

2단계: Economic (경제 환경)
   <!-- 💬 경제는 가장 빠르게 변합니다. 금리, 인플레, 환율이 급변하면 전략이 흔들립니다 -->

   - 금리 정책 & 인플레율 (고금리 → SaaS 수요 약화 가능)
   - 환율 (달러 강세 → 해외 수입비용 증가)
   - GDP 성장률 (불황 → 채용 및 투자 감소)
   - 고용률 & 임금 (직원 채용 비용)
   - 소비자 신뢰도 (지불 능력)

   우리에게의 영향:
   - 기회: _____
   - 위협: _____

3단계: Social (사회/문화 환경)
   <!-- 💬 사회는 느리지만 깊습니다. 세대 전환, 가치관 변화가 제품 수요를 결정합니다 -->

   - 인구 트렌드 (고령화, 저출산, 도시 쏠림)
   - 소비자 가치관 변화 (MZ세대, ESG 관심)
   - 교육 수준 (디지털 리터러시)
   - 일하는 방식 (재택근무, 자유로운 시간)
   - 신뢰/윤리 (AI 신뢰도, 개인정보보호 의식)

   우리에게의 영향:
   - 기회: _____
   - 위협: _____

4단계: Technology (기술 환경)
   <!-- 💬 기술은 가장 빠르고 예측하기 어렵습니다.
        하지만 AI/ML 업계라면 여기가 가장 중요합니다 -->

   - 신기술 등장 (AI, 양자 컴퓨팅, Web3)
   - 기술 표준 변화 (API, 프로토콜)
   - 인터넷 인프라 (5G, 6G)
   - 사이버 보안 위협
   - 오픈소스 에코시스템 (새로운 프레임워크)

   우리에게의 영향:
   - 기회: _____
   - 위협: _____

5단계: Environmental (환경/지속가능성)
   <!-- 💬 환경은 "먼 미래"처럼 보이지만, 규제로 빠르게 현실화됩니다 -->

   - 탄소 규제 (ESG 강화, 탄소세)
   - 에너지 가격 (재생에너지 전환)
   - 원자재 가격 (수급 부족)
   - 물, 폐기물 관리 규제
   - 공급망 환경 요구사항

   우리에게의 영향:
   - 기회: _____
   - 위협: _____

6단계: Legal (법률/규제 환경)
   <!-- 💬 법률은 Political과 다릅니다. 정치는 방향, 법은 구체적 행동 규제입니다 -->

   - 데이터 보호법 (GDPR, 개인정보보호법)
   - AI 규제 (AI Act, 안전성 규정)
   - 독점금지 규제 (대형테크 기업 규제)
   - 노동법 (최저임금, 근로시간)
   - 지적재산권 (특허, 저작권)
   - 산업별 규제 (금융, 의료 등)

   우리에게의 영향:
   - 기회: _____
   - 위협: _____

7단계: 통합 분석 & 우선순위
   <!-- 💬 6가지를 다 분석했으면, 이제 우리한테 가장 중요한 것을 고르세요 -->

   가장 영향이 큰 3가지:
   1. ____ (이유: ____)
   2. ____ (이유: ____)
   3. ____ (이유: ____)

   각각에 대한 대응 전략:
   - ___ 위험에 대응: ____
   - ___ 기회 활용: ____

8단계: 작성한 분석을 검토하세요.
   <!-- 💬 자기검증:
        [ ] 각 항목이 "현재"와 "미래"를 모두 다루나?
        [ ] 단순 뉴스 보도가 아니라 "우리한테 어떤 영향"인가?
        [ ] 변화의 속도를 고려했나? (정치는 느리고, 기술은 빠르다)
        [ ] "위협 + 대응"이 명확한가? (방어 전략만으론 부족)
        [ ] "기회"도 찾았나? (대부분 위협만 본다)
   -->

# 컨텍스트와 데이터
## 분석 대상:
   - 산업: {산업명}
   - 국가/지역: {한국 / 동아시아 / 글로벌}
   - 회사 규모: {스타트업 / 중견 / 대기업}

## 분석 시간 범위:
   - 현재 상황: 2026년 Q1
   - 미래 전망: 1-3년 (분기/연도별)

## 데이터 소스:
   - 정부 보도 & 정책 문서
   - 경제/금융 뉴스 (머니투데이, 한경, 이투데이)
   - 산업 리포트 (IDC, Gartner, McKinsey)
   - 기술 트렌드 (해커뉴스, 테크크런치, 스트라테지&)
   - 규제 뉴스 (시사in, 법률뉴스)
```

**💡 Deep Tips:**

- **데이터 수집:**
  - 정부 부처 공식 발표 (과기정통부, 중소기업청)
  - 주요 언론 경제/기술 섹션 (최근 3-6개월)
  - 산업 분석 보고서 (gartner.com, statista.com)
  - 규제 데이터베이스 (법제처, 행정규제정보)
  - 전문가 팟캐스트 (Product Thinking, 신문선읽기 등)

- **AI 제품 특화:**
  - **Political**: AI 규제 강화 (EU AI Act, 미국 행정 명령)
  - **Economic**: AI 학습 비용 폭증 (GPU 부족, 전기료)
  - **Social**: AI 신뢰도 부족, 일자리 감소 우려
  - **Technology**: LLM 오픈소스 확산, 모델 비용 하락
  - **Environmental**: AI 학습의 높은 에너지 소비 (탄소)
  - **Legal**: 개인정보 학습 금지, 저작권 소송

- **한국 SaaS 특화:**
  - **Political**: K-스타트업 정부 지원 정책, 규제 (정부 구매)
  - **Economic**: 환율 (글로벌 기업에 유리), 금리 (스타트업 투자 영향)
  - **Social**: 한국인의 기술 선호도 높음, MZ세대 디지털 리터러시 높음
  - **Technology**: 5G 인프라 선진 (한국 먼저 도입), 개발자 수준 높음
  - **Legal**: 개인정보보호법 강화, 방송통신위원회 규제
  - **Environmental**: ESG 추진 중소기업 (비용 증가)

- **Product Trio 확장:**
  - **PM:** 전략 수립 (우리가 이 트렌드에 어떻게 대응할지)
  - **엔지니어:** 기술 로드맵 (새로운 기술을 언제 도입할지)
  - **디자이너:** 사회 트렌드 반영 (UI/UX 트렌드, 접근성)


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 정치(P) 요인 파악 어려움 | "AI 규제", "데이터보호법", "정부 지원 정책" 키워드로 검색하세요 |
| 2단계 | 경제(E) 영향이 불확실 | "기업 IT 예산 트렌드"와 "SaaS 구독 의향" 데이터를 확인하세요 |
| 4단계 | 기술(T) 트렌드가 빠르게 변함 | 6개월 단위로 업데이트하세요. AI 산업은 분기별 추천 |
| 6단계 | 법률(L) 해석이 어려움 | 법률 전문가 검토를 권장. AI가 제공하는 법률 분석은 참고용입니다 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — PESTEL 분석을 자동화하여 거시 환경 변화를 정기 모니터링합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
거시 환경은 계속 변합니다. 뉴스, 규제, 트렌드 데이터를 자동 수집해서 분기별 PESTEL 리포트를 생성하면 전략 업데이트가 빨라집니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python + API 자동화

```python
import requests
from datetime import datetime, timedelta
import json
from typing import Dict, List
from anthropic import Anthropic

class PestelAnalyzer:
    def __init__(self, industry: str, country: str = "Korea"):
        self.industry = industry
        self.country = country
        self.client = Anthropic()
        self.categories = ["political", "economic", "social", "technology", "environmental", "legal"]
        self.analysis = {}

    def fetch_news_data(self, keywords: List[str], days: int = 30) -> List[Dict]:
        """
        뉴스 API에서 관련 기사 수집 (예: NewsAPI)
        """
        news_list = []

        for keyword in keywords:
            try:
                # NewsAPI 예시 (실제 API_KEY 필요)
                url = "https://newsapi.org/v2/everything"
                params = {
                    'q': f"{keyword} {self.industry}",
                    'sortBy': 'publishedAt',
                    'language': 'ko',
                    'from': (datetime.now() - timedelta(days=days)).isoformat(),
                    'apiKey': 'YOUR_NEWS_API_KEY'  # 환경변수로 관리하세요
                }

                response = requests.get(url, params=params, timeout=10)
                articles = response.json().get('articles', [])
                news_list.extend(articles[:5])  # 상위 5개만

            except Exception as e:
                print(f"뉴스 수집 오류 ({keyword}): {e}")

        return news_list

    def analyze_pestel_with_claude(self, context_data: Dict) -> Dict:
        """
        Claude를 사용해서 수집된 뉴스/데이터 분석
        """
        prompt = f"""
당신은 산업 전략 분석가입니다.

{self.industry} 산업 ({self.country} 시장)의 PESTEL 분석을 수행하세요.

수집된 데이터:
{json.dumps(context_data, ensure_ascii=False, indent=2)}

각 항목(Political, Economic, Social, Technology, Environmental, Legal)에 대해:

1. **현재 상황**: 구체적인 변화 또는 이슈 (뉴스/데이터 기반)
2. **우리 산업에 미치는 영향**: 기회 vs 위협 (구체적)
3. **향후 12개월 예상**: 추세 방향
4. **대응 전략**: PM이 취할 수 있는 액션

JSON 형식으로 다음 구조로 응답하세요:
{{
  "categories": {{
    "political": {{"current": "...", "impact": "...", "opportunity": "...", "threat": "...", "action": "..."}},
    ...
  }},
  "top_3_priority": ["...", "...", "..."],
  "immediate_actions": ["...", "...", "..."]
}}
        """

        message = self.client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        try:
            response_text = message.content[0].text
            import re
            json_match = re.search(r'\{.*\}', response_text, re.DOTALL)
            if json_match:
                return json.loads(json_match.group())
        except Exception as e:
            print(f"JSON 파싱 오류: {e}")

        return {}

    def generate_analysis(self) -> Dict:
        """
        전체 PESTEL 분석 생성
        """
        # 1단계: 뉴스 수집 (카테고리별 키워드)
        keywords = {
            'political': [f"{self.industry} 정책", "정부 규제"],
            'economic': [f"{self.industry} 시장", "경제 전망"],
            'social': [f"{self.industry} 소비자", "트렌드"],
            'technology': [f"{self.industry} 기술", "AI", "자동화"],
            'environmental': ["ESG", "탄소 규제"],
            'legal': [f"{self.industry} 법률", "규제"],
        }

        all_news = []
        for category, kws in keywords.items():
            print(f"수집 중: {category}...")
            all_news.extend(self.fetch_news_data(kws))

        # 2단계: Claude 분석
        context_data = {
            'industry': self.industry,
            'country': self.country,
            'collected_news': [
                {
                    'title': article.get('title'),
                    'source': article.get('source', {}).get('name'),
                    'publishedAt': article.get('publishedAt')
                }
                for article in all_news
            ]
        }

        self.analysis = self.analyze_pestel_with_claude(context_data)
        self.analysis['generated_at'] = datetime.now().isoformat()
        self.analysis['industry'] = self.industry
        self.analysis['country'] = self.country

        return self.analysis

    def to_markdown(self) -> str:
        """마크다운 형식으로 내보내기"""
        output = f"# {self.industry} ({self.country}) PESTEL 분석\n\n"
        output += f"분석일시: {self.analysis.get('generated_at')}\n\n"

        categories_data = self.analysis.get('categories', {})

        for category, data in categories_data.items():
            output += f"## {category.upper()}\n\n"
            output += f"**현재 상황**: {data.get('current', 'N/A')}\n\n"
            output += f"**영향**: {data.get('impact', 'N/A')}\n\n"
            output += f"**기회**: {data.get('opportunity', 'N/A')}\n\n"
            output += f"**위협**: {data.get('threat', 'N/A')}\n\n"
            output += f"**대응 전략**: {data.get('action', 'N/A')}\n\n"

        output += "## 🎯 최우선 3가지\n\n"
        for i, item in enumerate(self.analysis.get('top_3_priority', []), 1):
            output += f"{i}. {item}\n"

        output += "\n## 📋 즉시 실행 과제\n\n"
        for item in self.analysis.get('immediate_actions', []):
            output += f"- {item}\n"

        return output

# 사용 예
if __name__ == "__main__":
    analyzer = PestelAnalyzer("AI/LLM SaaS", "Korea")
    analysis = analyzer.generate_analysis()

    with open("pestel-analysis-ai-saas.md", "w", encoding="utf-8") as f:
        f.write(analyzer.to_markdown())

    print("PESTEL 분석이 완료되었습니다!")
    print(json.dumps(analysis, ensure_ascii=False, indent=2))
```

### Claude Code / CLI 연동

```bash
# PESTEL 분석 실행
claude_code \
  --model claude-opus-4-6 \
  --file pestel_analyzer.py \
  --args industry="AI/LLM SaaS" country="Korea" \
  --output pestel-analysis-ai-saas-korea.md

# 여러 산업 비교 분석
for industry in "AI/LLM SaaS" "DevTools" "No-Code Platform"; do
  claude_code \
    --model claude-opus-4-6 \
    --file pestel_analyzer.py \
    --args industry="$industry" country="Korea" \
    --output pestel-${industry// /-}.md
done

# 국가별 PESTEL 비교
for country in "Korea" "US" "Japan"; do
  claude_code \
    --model claude-opus-4-6 \
    --file pestel_analyzer.py \
    --args industry="AI/LLM SaaS" country="$country" \
    --output pestel-ai-${country}.md
done
```

---

## 📊 실행 결과 예시

### Layer 1 실행 결과

```
[Quick Start 프롬프트 사용]

AI/LLM SaaS 산업의 PESTEL 분석...

=== 결과 (5분) ===

Political: 한국 정부의 "AI 초격차 전략" 발표
   기회: 정부 R&D 펀딩 증가, AI 스타트업 지원
   위협: 기술 내재화 요구, 중국 견제 정책

Economic: 글로벌 금리 인상 → SaaS 투자 감소
   기회: 효율성 추구 제품 수요 증가
   위협: 초기 스타트업 자금조달 어려움

Social: MZ세대의 AI 신뢰도 낮음
   기회: 설명가능한 AI 개발로 차별화
   위협: AI 규제 강화 압박

Technology: LLM 오픈소스 (Llama, Mistral) 확산
   기회: 기술 벽 낮아짐, 신규 진입 용이
   위협: 독점적 모델 우위 약화

Environmental: AI 학습의 높은 에너지 소비
   기회: 효율적 AI 솔루션 수요
   위협: 탄소세 부담, ESG 압박

Legal: EU AI Act, 미국 AI 행정명령
   기회: 규제 준수 서비스 개발
   위협: 국내 규제 강화 예상
```

### Layer 2 실행 결과

```
# AI/LLM SaaS 산업 PESTEL 상세 분석 (2026 Q1, 한국)

## Political (정치/정책)

### 현재 상황
- 한국 정부: "2030 AI 초격차 전략" 발표 (2026년)
  → 2조 원대 R&D 투자, AI 인재 양성
- 세계은행: "AI 규제는 피할 수 없다" 선언
- 미국 행정부: "AI 보안 검증" 행정 명령

### 우리 산업에 미치는 영향

**기회**:
- 한국 정부 펀딩 프로그램 확충
- "AI 국산화" 정책으로 로컬 스타트업 이점
- 정부 조달 시 한국 기업 우대 가능성

**위협**:
- "기술 해외 의존도 감소" 정책으로 기술 이전 강요 가능
- AI 산업 통제/감시 강화
- 중국과의 기술 경쟁 심화로 규제 확대

### 향후 12개월 예상
- 상반기: 세부 지원 정책 발표
- 하반기: "AI 안전성 가이드라인" 공개

### 대응 전략
1. 정부 R&D 프로젝트 참여 (기술 신뢰도 + 자금)
2. "한국 기업" 정체성 강조 마케팅
3. 규제 변화 모니터링팀 구성

---

## Economic (경제)

### 현재 상황
- 기준금리: 3.0% (높은 수준 유지)
- 글로벌 SaaS 벤처캐피탈 투자: 35% 감소 (YoY)
- 한국 스타트업 겨울: 펀딩 쉽지 않음
- 환율: 1,200원/$대 (기업 수익성 악화)

### 우리 산업에 미치는 영향

**기회**:
- 기업들이 "비용 절감" 솔루션 찾음 → AI 자동화 수요 급증
- 고금리로 "효율성 중심" 문화 생김 → 우리 제품과 부합

**위협**:
- 초기 스타트업이 자금 조달 어려움 (경쟁사 약화는 우리도 약해짐)
- 글로벌 기업의 한국 시장 철수/축소
- 대기업의 AI 내부 개발로 외부 솔루션 수요 감소 가능

### 대응 전략
1. Series A 이상 기업들에 집중 (자금 여유 있는 회사)
2. "비용 대비 효과" 계량화 마케팅
3. 환율 위험 헤지 (외화 수익 분산)

---

## Social (사회/문화)

### 현재 상황
- "AI 신뢰도" 설문: 한국 47% (OECD 평균 52%)
- MZ세대: "AI가 일자리를 빼앗을까?" 우려 높음
- 워라밸 문화: 자동화 = 업무 부담 증가로 해석하는 경향
- ESG 관심 높음: "도덕적 AI" 요구 증가

### 우리 산업에 미치는 영향

**기회**:
- "설명가능하고 윤리적인 AI" 수요 증가
- 일자리 창출과 함께하는 자동화 스토리 필요
- ESG 투자사, 정부 기관의 AI 솔루션 선호

**위협**:
- AI 규제 강화 압박 (국민 여론)
- "AI가 일자리를 빼앗는다" 이슈로 채용 거부감
- 노조의 AI 도입 반대

### 대응 전략
1. "AI + 인간" 협력 스토리 강조
2. 윤리 리뷰 프로세스 공개 (투명성)
3. 직원 재교육 프로그램 지원 (일자리 유지)

---

## Technology (기술)

### 현재 상황
- LLM 오픈소스 확산: Llama 2, Mistral 7B 성능 급상승
- 모델 가격 하락: GPT-4 대비 오픈소스는 1/100 비용
- AI 안전성 도구 발전: Guardrails, TrustLLM 등
- 멀티모달 모델 전성기: 이미지 + 텍스트 + 음성 통합

### 우리 산업에 미치는 영향

**기회**:
- 오픈소스 기반 빠른 제품 개발 가능
- 진입 장벽 낮아짐 → 니치 시장 점령 가능
- 멀티모달 기능으로 신제품 기회

**위협**:
- OpenAI, Google 같은 거대사들의 독점 위험
- 오픈소스 경쟁 심화 → 가격 압박
- 모델 개선 속도를 따라가기 어려움

### 대응 전략
1. "맞춤형 LLM" 개발 (통용 모델이 아닌 도메인 특화)
2. 라이센스 전략 명확화 (상용화 가능한지)
3. AI Safety 기술에 투자

---

## Environmental (환경)

### 현재 상황
- AI 학습 에너지: ChatGPT 한 번 학습 = 가정 1년 전기료
- ESG 규제: 대기업 탄소 보고 의무화
- 재정 지원: 탄소 중립 기술에 정부 자금

### 우리 산업에 미치는 영향

**기회**:
- "효율적 AI" (작은 모델, 낮은 전력) 수요 증가
- "탄소 중립 AI 솔루션" 마케팅

**위협**:
- 높은 컴퓨팅 비용 (전기료 상승)
- ESG 감시로 "AI 윤리" 엄격한 검토

### 대응 전략
1. 에너지 효율 기술 투자
2. 탄소 배출량 공개 및 감축 목표 설정

---

## Legal (법률/규제)

### 현재 상황
- EU AI Act: 2026년 4월 시행 예정
- 미국 AI 행정명령: 안전성 검증 강화
- 한국 개인정보보호법: 강화 중
- AI 저작권 소송: ChatGPT vs 저자들

### 우리 산업에 미치는 영향

**기회**:
- 규제 준수 서비스 개발 가능 (Compliance-as-a-Service)
- "안전한 AI"를 마케팅 포인트로

**위협**:
- 학습 데이터의 법적 문제 (저작권, 개인정보)
- 규제 강화로 개발 속도 저하
- 해외 진출 시 다중 규제 대응 비용

### 대응 전략
1. 법무팀 구성 (AI 규제 전문가)
2. 학습 데이터 라이센싱 명확화
3. "규제 준수" 인증 취득

---

## 🎯 우리 회사에 가장 영향 큰 3가지

**1순위: Technology (기술 진화)**
- 이유: 우리 산업의 핵심. 오픈소스 확산은 우리 장점 (빠른 개발)
- 대응: 오픈소스 기반 제품으로 빠르게 시장 대응

**2순위: Legal (규제 강화)**
- 이유: AI 규제는 피할 수 없음. 준수하지 않으면 퇴출
- 대응: 규제 변화 모니터링, Compliance 기능 내장

**3순위: Economic (금리/펀딩)**
- 이유: 자금 조달이 어려워지면 회사 생존이 위협
- 대응: 수익성 우선, 조기 흑자 목표

---

## 📋 즉시 실행 과제 (향후 3개월)

1. **AI Act 시뮬레이션**: EU AI Act 요구사항 100% 충족하기
2. **오픈소스 로드맵**: Llama 기반 커스텀 모델 개발 기획
3. **펀딩 전략**: Series A 투자자 집중 공략 (대기업 아님)
4. **정부 사업**: AI 초격차 전략 관련 과제 참여 신청
5. **윤리 리뷰**: "AI 안전성" 프로세스 공식화
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 6개 PESTEL 요인 중 '당장 영향을 미치는 것'과 '장기적으로 영향을 미치는 것'을 구분하세요
2. **[논쟁 지점]** PESTEL에서 'Technology' 요인의 범위를 자사 기술만 볼지, 인접 기술까지 볼지는 목적에 따라 다릅니다
3. **[자기 검증]** 가장 높은 위험도로 평가된 요인 1개의 최근 뉴스를 검색해서 AI 평가가 맞는지 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| 규제 이슈 | → `problem-framing.md` | "우리가 풀어야 할 규제 문제는?" |
| 기술 트렌드 | → `company-profiling.md` | 경쟁사가 이 기술 트렌드에 어떻게 대응? |
| 경제 지표 | → `persona-profiling.md` | 경제 변화가 우리 고객에게 미치는 영향? |
| 시장 기회 | → `feature-prioritization.md` (decide/) | 어떤 기능을 먼저 개발할지 결정 |

---

## 📝 참고자료

- **EU AI Act**: https://ec.europa.eu/information_society/
- **Gartner AI Hype Cycle**: https://www.gartner.com/
- **World Economic Forum Future of Jobs**: https://www.weforum.org/
- **한국 과학기술정보통신부**: https://www.msit.go.kr/ (AI 정책)
- **McKinsey AI Index**: https://www.mckinsey.com/
- **Statista**: https://www.statista.com/ (통계)
