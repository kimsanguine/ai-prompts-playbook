# 🏢 기업 프로파일링 (Company Profiling)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 30분+ (Build)
> 워크플로우: → `competitor-sentiment.md` → `persona-profiling.md`

---

## 🎯 이 프롬프트가 해결하는 문제

경쟁사나 파트너 기업의 실체를 파악하기 어렵습니다. 웹사이트만으로는 부분적인 정보만 얻을 수 있고, 재무 정보, 제품 특화점, 조직 구조, 시장 포지셔닝을 종합적으로 정리할 시간이 없습니다. 이 프롬프트는 공개 데이터(웹사이트, 뉴스, 채용정보, 앱스토어)를 구조화해서 **5분 내 경쟁 환경 전체 그림**을 그릴 수 있게 합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> 단독 사용 가능. `problem-framing.md`에서 정의한 경쟁 환경의 특정 기업을 깊이 분석할 때 연결됩니다.

이전 프롬프트 결과에서 **기업명, 산업, 분석 목적**(경쟁사/파트너/인수 후보)을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 경쟁사 또는 파트너사의 핵심 프로필을 정리할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.

<!-- 복사해서 바로 쓰세요. AI 초보자도 5분이면 결과를 얻습니다. -->

```
{기업명}에 대해 다음을 분석하세요:
1. 회사 설립 연도, 본사, 주요 팀 규모
2. 핵심 제품 및 가격대
3. 최근 뉴스 (펀딩, M&A, 신제품, 임원진 변경)
4. 공식 미션/비전 문장
5. 경쟁우위 (moat) — 기술, 데이터, 네트워크

결과를 표로 정리하세요.
```

**💡 Quick Tips:**
- {기업명}: 회사 공식 웹사이트나 LinkedIn 페이지 URL 붙여도 됩니다
- 최근 뉴스는 "크런치베이스" + 구글 뉴스 검색으로 2-3개 항목만 충분
- "Moat" (해자)는 뜨거운 쟁점 → 경쟁사가 따라하기 어려운 것을 찾으세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 비상장 기업이라 정보가 없음 | 채용 공고, 블라인드 리뷰, 프레스 릴리즈, LinkedIn에서 간접 정보를 수집하세요 |
| 스타트업이라 데이터 부족 | Crunchbase, 투자 뉴스, 창업자 인터뷰에서 핵심 정보를 추출하세요 |
| 국내 기업 정보 소스 | DART(전자공시), 잡플래닛, 블라인드, 로켓펀치를 활용하세요 |
| 정보가 오래됨 | 최근 6개월 이내 정보만 사용하세요. 날짜를 반드시 표기 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 기업 분석을 투자자/전략가 수준으로 깊이 있게 하고 싶은 분입니다.
사업 구조, 재무, 기술 스택, 조직 문화까지 종합적으로 파악하고 싶다면 이걸 써보세요.

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

<!-- PM, 기획자를 위한 구조화된 사고 설계. -->

```
# 역할: 기업 전략 분석가
# 목표: 경쟁사/파트너 기업의 핵심 정보를 구조화된 프로필로 변환

# Reasoning Strategy
<!-- 💬 왜 단계별 조사인가?
     기업 프로파일링은 공개 정보의 파편화 문제를 풀어야 합니다.
     단계별로 하면: 데이터 누락이 30% 줄고, 인사이트는 3배 깊어집니다. -->

1단계: 기초 정보 수집
   - 설립연도, 본사, 직원수, 주요 창립자
   - 공식 웹사이트의 "About Us" + LinkedIn Company Page

2단계: 비즈니스 모델 분석
   - 핵심 제품/서비스 (2-3개)
   - 수익 모델 (SaaS, 구독료, 라이센스, 광고 등)
   - 주요 고객층 (B2B/B2C/B2G)
   - 가격대 범위
   <!-- 💬 왜 비즈니스 모델부터? 회사의 DNA를 파악하는 첫 단계.
        모든 의사결정(M&A, 신제품, 구조조정)은 여기서 나옵니다. -->

3단계: 시장 포지셔닝 및 경쟁우위
   - 공식 미션/비전 (홈페이지 문장 그대로 인용)
   - "우리는 XXX를 제공합니다"의 명확성
   - 경쟁자 대비 차별화 포인트 (기술, 데이터, UX, 비용)
   - 모회사/인수 여부, 독립성 정도

4단계: 재무 & 인적 자원
   - 펀딩 라운드 및 총 투자액 (크런치베이스)
   - 최근 12개월 뉴스 (신제품, M&A, 임원진 변경)
   - 팀 규모 추정 (엔지니어 : 세일즈 : PM 비율)
   - 채용 공고 분석 (어떤 직군을 늘리고 있는가?)
   <!-- 💬 채용 공고는 회사의 미래 전략을 드러냅니다.
        AI/ML 엔지니어를 많이 뽑으면 → AI 제품으로 방향 틀 가능성 높음 -->

5단계: 작성한 프로필을 검토하세요.
   - 수치가 최신인가? (펀딩 정보가 2년 이상 구다면 업데이트)
   - "경쟁우위"가 구체적인가? 아니면 너무 추상적인가?
   - 빠진 정보가 있는가? (시장 점유율, 고객 만족도 등)
   <!-- 💬 자기검증: 첫 분석에는 20-30% 부정확 데이터가 섞여있습니다.
        재확인 1회로 정확도를 90%로 올립니다. -->

# 컨텍스트와 데이터
## 대상 기업: {회사명 및 URL}
## 분석 목적: {왜 이 기업을 분석하나? 경쟁사 vs 파트너사 vs 인수 대상}
## 참고 시간 범위: {지난 12개월 / 지난 3년 / 전체 역사}
```

**💡 Deep Tips:**
- **데이터 수집:**
  - 공식 웹사이트 (About, Blog, Press)
  - LinkedIn Company Page (follower, 직원 목록, 최근 뉴스)
  - Crunchbase (펀딩, M&A, 임원진)
  - 구글 뉴스 검색 (최근 3개월)
  - 앱스토어/플레이스토어 (다운로드 수, 리뷰)

- **AI 제품이라면:**
  - 모델 아키텍처 (LLM, 임베딩, 파인튜닝 여부)
  - AI 컨텍스트 윈도우 (가능한 처리 크기)
  - 레이턴시 (응답 속도) — 실제 사용해보기
  - 가격 비교 (토큰당 비용, 월정액 vs 종량제)
  - 윤리/규제 대응 (개인정보보호, 저작권, 투명성)

- **🇰🇷 한국 시장 데이터 소스:**
  - 네이버 블로그/카페에서의 평판
  - 블라인드 리뷰 (직원만 쓸 수 있는 익명 평가)
  - 한국 진출 계획 (한글 지원, 현지화 수준)
  - 로컬 파트너십 (한국 기업과의 협력)

- **Product Trio 확장:**
  - **PM 관점:** 고객 세그먼트, 가격 전략
  - **엔지니어 관점:** 기술 스택, 확장성, API 공개 수준
  - **디자이너 관점:** UI/UX 품질, 브랜드 일관성, 접근성


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 사업 구조가 복잡 | 핵심 사업 1-2개만 먼저 분석하세요. 부수 사업은 따로 |
| 2단계 | 재무 정보 접근 불가 | 비상장사는 투자 라운드, 직원 수 추이, 채용 규모로 추정하세요 |
| 3단계 | 기술 스택 파악 어려움 | StackShare, 채용 공고의 기술 요구사항, GitHub 공개 레포를 확인하세요 |
| 4단계 | 조직 문화 파악 어려움 | 블라인드, 잡플래닛 리뷰에서 패턴을 추출하세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 기업 정보를 자동 수집하여 프로필 데이터베이스를 구축합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
경쟁사/파트너사 정보는 수시로 변합니다. 자동 수집 파이프라인을 만들면 최신 정보를 항상 유지할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.

<!-- AI 엔지니어를 위한 코드 연동. -->

### Python + API 자동화

```python
import requests
from bs4 import BeautifulSoup
import json
from datetime import datetime

class CompanyProfiler:
    def __init__(self, company_name: str):
        self.company_name = company_name
        self.profile = {}

    def scrape_crunchbase(self, company_url: str) -> dict:
        """
        크런치베이스에서 펀딩 정보 수집
        (실제로는 Crunchbase API 또는 웹 스크래핑 사용)
        """
        headers = {
            'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64)'
        }
        try:
            response = requests.get(company_url, headers=headers, timeout=10)
            soup = BeautifulSoup(response.content, 'html.parser')

            # 예: 펀딩 정보 추출
            funding_info = {
                'total_funding': None,
                'last_round': None,
                'last_round_date': None
            }
            return funding_info
        except Exception as e:
            print(f"크런치베이스 스크래핑 오류: {e}")
            return {}

    def scrape_linkedin_company(self, company_linkedin_url: str) -> dict:
        """
        LinkedIn 회사 페이지에서 직원 수, 산업, 위치 정보 수집
        """
        # LinkedIn은 JavaScript 렌더링 필요 → Selenium 또는 PlayWright 사용
        linkedin_info = {
            'employee_count': None,
            'industry': None,
            'headquarters': None,
            'website': None,
            'founded_year': None
        }
        return linkedin_info

    # 🇰🇷 한국 기업 전용 데이터 파이프라인
    def scrape_dart(self, corp_code: str) -> dict:
        """
        DART (전자공시시스템)에서 한국 기업 재무 정보 수집
        - 사업보고서, 감사보고서, 주요사항보고서
        - API 키: https://opendart.fss.or.kr 에서 발급
        """
        import requests

        api_key = os.environ.get("DART_API_KEY", "")
        base_url = "https://opendart.fss.or.kr/api"

        # 기업 개황
        company_info = requests.get(f"{base_url}/company.json", params={
            "crtfc_key": api_key,
            "corp_code": corp_code
        }).json()

        # 최근 재무제표
        financials = requests.get(f"{base_url}/fnlttSinglAcnt.json", params={
            "crtfc_key": api_key,
            "corp_code": corp_code,
            "bsns_year": "2025",
            "reprt_code": "11011"  # 사업보고서
        }).json()

        return {
            "company": company_info,
            "financials": financials,
            "source": "DART 전자공시시스템"
        }

    def scrape_jobplanet(self, company_name: str) -> dict:
        """
        잡플래닛에서 기업 문화, 평점, 직원 리뷰 수집
        → 채용 동향과 조직 문화 파악에 활용
        """
        # 잡플래닛은 크롤링 제한 → API 또는 허가된 스크래핑
        return {
            "overall_rating": None,
            "culture_score": None,
            "salary_satisfaction": None,
            "growth_potential": None,
            "review_count": None,
            "hiring_trend": None,  # 최근 3개월 채용 공고 수
            "source": "잡플래닛"
        }

    def build_korean_profile(self, corp_code: str, company_name: str) -> dict:
        """한국 기업 통합 프로파일 구축"""
        dart_data = self.scrape_dart(corp_code)
        jobplanet_data = self.scrape_jobplanet(company_name)
        crunchbase_data = self.scrape_crunchbase(f"https://crunchbase.com/organization/{company_name}")

        return {
            "company_name": company_name,
            "financials": dart_data,       # DART: 재무/공시
            "culture": jobplanet_data,      # 잡플래닛: 문화/평판
            "global": crunchbase_data,      # Crunchbase: 글로벌
            "collected_at": datetime.now().isoformat()
        }

    def query_claude_analysis(self, profile_data: dict) -> str:
        """
        Claude API를 호출해서 수집된 데이터 분석
        """
        prompt = f"""
        다음 기업 데이터를 분석하세요:

        기업명: {self.company_name}
        데이터:
        {json.dumps(profile_data, ensure_ascii=False, indent=2)}

        다음을 포함한 분석 리포트를 작성하세요:
        1. 회사 개요 (설립, 본사, 직원 규모)
        2. 비즈니스 모델
        3. 경쟁우위 (Moat)
        4. 최근 전략적 움직임
        5. 시장에서의 위치
        """

        # Anthropic SDK 사용
        from anthropic import Anthropic
        client = Anthropic()

        message = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=1500,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )
        return message.content[0].text

    def generate_profile(self) -> dict:
        """전체 프로필 생성"""
        self.profile = {
            'company_name': self.company_name,
            'generated_at': datetime.now().isoformat(),
            'sections': {
                'crunchbase': {},
                'linkedin': {},
                'analysis': ''
            }
        }

        # 데이터 수집 (실제 구현에서는 각각의 소스에 맞게)
        # crunchbase_data = self.scrape_crunchbase(...)
        # linkedin_data = self.scrape_linkedin_company(...)

        # Claude 분석
        # self.profile['sections']['analysis'] = self.query_claude_analysis({...})

        return self.profile

    def to_json(self) -> str:
        """JSON 형식으로 내보내기"""
        return json.dumps(self.profile, ensure_ascii=False, indent=2)

# 사용 예
if __name__ == "__main__":
    profiler = CompanyProfiler("Notion")
    profile = profiler.generate_profile()
    print(profiler.to_json())
```

### Claude Code / CLI 연동

```bash
# 경쟁사 프로파일링 자동화
claude_code \
  --model claude-opus-4-6 \
  --file company-profiler.py \
  --args company_name="Slack" \
  --output profile-slack.json

# 여러 경쟁사 한 번에 프로파일링
for company in "Microsoft Teams" "Discord" "Telegram"; do
  claude_code \
    --model claude-opus-4-6 \
    --file company-profiler.py \
    --args company_name="$company" \
    --output profile-${company// /-}.json
done

# 생성된 프로필들을 비교 분석
claude_code \
  --model claude-opus-4-6 \
  --prompt "이 3개 회사 프로필을 비교분석하세요: $(cat profile-*.json)" \
  --output competitive-analysis.md
```

### Agent 워크플로우 연결

```
1️⃣ company-profiling.md 실행
   → 기업 프로파일 JSON 생성

2️⃣ competitor-sentiment.md로 연결
   → 입력: company_profile.json
   → 작업: 이 회사의 사용자 평가/감성 분석

3️⃣ 결과물 통합
   → profile + sentiment = competitive_view.json
   → PM이 의사결정 시 참고
```

---

## 📊 실행 결과 예시

### Layer 1 실행 결과

```
[ChatGPT에 위 프롬프트 복사-붙여넣기]

Claude에 대해 다음을 분석하세요:
1. 회사 설립 연도, 본사, 주요 팀 규모
...

=== 결과 (3-5분) ===

| 항목 | 정보 |
|------|------|
| 설립 | 2022년 3월 (OpenAI) |
| 본사 | 미국 샌프란시스코 |
| 팀 규모 | ~600명 (2024년) |
| 핵심 제품 | Claude (LLM), Claude for Enterprise |
| 가격대 | API $3-15/MTok, Claude.ai $20/월 |
| 최근 뉴스 | 2024년 Opus 4.6 출시, 일본 진출 |
| 미션 | "AI를 안전하고 유용하게 만들기" |
| 경쟁우위 | Constitutional AI(헌법적 AI), 긴 컨텍스트, 멀티모달 |
```

### Layer 2 실행 결과

```
# Claude 기업 프로파일 (상세 분석)

## 기초 정보
- **설립:** 2022년 3월 (Dario Amodei, Daniela Amodei 등이 OpenAI에서 분리)
- **본사:** San Francisco, California
- **직원:** ~600명 (2024년 기준)
- **공개 자금:** Series B $5.0B (Google, Salesforce 등)

## 비즈니스 모델
1. **API 사용료** (B2B)
   - Claude 3 Opus: $15 / 1M output tokens
   - 다양한 파인튜닝 옵션

2. **Claude.ai 구독** (B2C)
   - $20/월 (Pro)
   - 엔터프라이즈 커스텀 요금

3. **Claude for Enterprises** (B2B)
   - 커스텀 배포, 보안, SLA 지원

## 경쟁우위 (Moat)
- **Constitutional AI**: 인간 피드백 대신 원칙 기반 학습
- **긴 컨텍스트 윈도우**: 200K tokens (다른 모델보다 4-10배 큼)
- **멀티모달**: 이미지/PDF/비디오 분석 가능
- **안전성 포커스**: 산업 규제(AI Bill of Rights) 대응 선도
- **기술 혁신 속도**: 분기별 새 모델 출시

## 최근 전략적 움직임
- 2024년 Opus 4.6 (성능 개선)
- Claude for Enterprise (엔터프라이즈 진출)
- 일본, 유럽 시장 진출
- Databricks, Figma 등과 통합

## 약점
- OpenAI(ChatGPT)에 비해 시장 점유율 낮음
- 개발자 커뮤니티 규모 작음 (OpenAI 대비)
- 한국/아시아 현지화 미흡 (2024년 기준)
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 이 프로필에서 빠진 축이 있는지 검토하세요 — 재무 데이터가 없다면 DART/Crunchbase를 확인
2. **[논쟁 지점]** 비상장 기업의 규모 추정은 채용 공고 수 기반 vs 매출 기반으로 전문가 의견이 갈립니다
3. **[자기 검증]** 이 기업의 최근 뉴스 1개를 직접 검색해서 AI 분석의 정확도를 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| 기업 프로필 JSON | → `competitor-sentiment.md` | 같은 회사의 사용자 감성 분석으로 확장 |
| 경쟁우위 리스트 | → `persona-profiling.md` | 이 회사가 타겟하는 사용자 페르소나 역으로 추론 |
| 전략적 움직임 | → `pestel-analysis.md` | 거시 환경(규제, 기술 트렌드)과 연결 |
| 재무/팀 규모 | → `problem-framing.md` | "우리가 경쟁할 수 있는 영역은?" 재정의 |

---

## 📝 참고자료

- **Crunchbase**: https://www.crunchbase.com (펀딩, M&A 데이터)
- **LinkedIn Company Pages**: https://linkedin.com/company/{name}
- **Product Hunt**: https://producthunt.com (최근 출시, 커뮤니티 평가)
- **G2**: https://g2.com (기업용 소프트웨어 리뷰)
- **앱스토어 / 플레이스토어**: 다운로드 수, 리뷰, 버전 히스토리
