# 🌟 경쟁사 감성 분석 (Competitor Sentiment Analysis)

> 예상 소요: 8분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: ← `company-profiling.md` ← `customer-journey-mapping.md` → `problem-framing.md`

---

## 🎯 이 프롬프트가 해결하는 문제

경쟁사의 약점을 모릅니다. "경쟁사가 뭘 못 하는가?"를 정량화하지 못하면, 우리의 차별화도 허술해집니다. 앱스토어, G2, Reddit, 블라인드의 리뷰들은 고객의 **진짜 느낌(감정)**을 담고 있습니다. 이 프롬프트는 경쟁사 고객의 불만을 **구조화된 감성 분석**으로 변환해서:

1. **우리가 차별화할 수 있는 점** 찾기
2. **고객이 정말 원하는 게 뭔지** 파악하기
3. **기회 포착** (경쟁사가 못 채우는 gap)

이 세 가지를 동시에 해결합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> 단독 사용 가능. `company-profiling.md`에서 특정 경쟁사를 선정한 후 사용자 감성을 분석할 때 연결됩니다.

이전 프롬프트 결과에서 **경쟁사명, 제품 카테고리, 분석 대상 플랫폼**(앱스토어/Reddit/블라인드)을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 경쟁사 리뷰 감성 분석 결과를 받을 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

### 🌍 글로벌 기업 분석용

경쟁사가 해외 제품(Notion, Figma, Slack 등)이라면 이 프롬프트를 사용하세요.

```
{경쟁사명}의 사용자 리뷰 감성을 분석하세요.

데이터 소스 우선순위:
1. G2 Reviews (가장 상세)
2. 앱스토어/플레이스토어 (기본 사용자)
3. Reddit / 개발자 커뮤니티 (깊이 있는 피드백)
4. Product Hunt 코멘트 (얼리어답터 의견)
5. 트위터 (실시간 평가)

각 리뷰에서:
- 감정 점수: -1(매우 부정) ~ +1(매우 긍정)
- 주제: {가격 / 기능 / UI/UX / 지원 / 성능 / 기타}
- 인용: "왜 이 감정을 느꼈나?"
- 고객 페르소나: {스타트업 PM? 대기업 엔지니어?}

최소 10-15개 리뷰를 분석하고 패턴을 찾으세요.
```

> **💡 변수 채우기 예시:**
> - `{경쟁사명}` → "Notion" 또는 "Slack" 또는 "Monday.com"

### 🇰🇷 국내 기업 분석용

경쟁사가 국내 서비스(토스, 당근, 리멤버 등)라면 이 프롬프트를 사용하세요.
국내 기업은 G2, Reddit 데이터가 거의 없습니다. **한국 플랫폼 중심으로 분석**해야 합니다.

```
{경쟁사명}의 사용자 리뷰 감성을 분석하세요.

한국 데이터 소스 (우선순위):
1. 앱스토어/플레이스토어 한국 리뷰 (가장 접근 쉬움)
2. 블라인드 — 회사명/제품명 검색 (직원과 실사용자의 솔직한 평가)
3. 네이버 블로그/카페 — "{경쟁사명} 후기" 검색 (일반 사용자 리뷰)
4. 커뮤니티 — 디시인사이드, 클리앙, 뽐뿌 등 관련 갤러리/게시판
5. IT 전문 매체 — 아웃스탠딩, eo, 요즘IT 등의 댓글과 분석 기사

⚠️ 주의할 점:
- 블라인드 리뷰는 직원 관점이므로 "사용자 관점"과 구분하세요
- 네이버 블로그 중 협찬/광고 포스팅은 제외하세요 ("내돈내산"만 사용)
- 앱스토어 리뷰가 가장 순수한 사용자 피드백입니다

각 리뷰에서:
- 감정 점수: -1(매우 부정) ~ +1(매우 긍정)
- 주제: {가격 / 기능 / UI/UX / 지원 / 성능 / 한국어 지원 / 기타}
- 인용: "왜 이 감정을 느꼈나?"
- 고객 페르소나: {개인 사용자? 스타트업? 중견기업? 대기업?}

최소 10-15개 리뷰를 분석하고 패턴을 찾으세요.
```

> **💡 변수 채우기 예시:**
> - `{경쟁사명}` → "토스" 또는 "당근마켓" 또는 "리멤버"
> - 주제에서 "한국어 지원"은 국내 기업이면 제외하고 다른 항목(예: "고객센터 응대")을 추가해도 좋습니다

### 💡 Quick Tips

- 별 5개 리뷰는 "왜 좋은지" 놓치기 쉬움 → **별 3-4개와 별 1-2개에 집중**
- "가격" 불만이 많으면 → 우리는 가격 경쟁력으로 차별화 가능
- "지원이 느림" 불만이 많으면 → 우리는 빠른 한글 지원으로 차별화 가능
- 패턴이 명확할수록 우리 전략이 명확해집니다

### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 리뷰가 10개 미만 | 데이터 소스를 추가하세요. 앱스토어 + 블라인드 + 네이버 블로그를 합치면 됩니다 |
| 영어 리뷰만 있음 | 글로벌 기업용 프롬프트를 쓰되, "한국 시장 관점에서 해석하세요"를 마지막에 추가 |
| B2B 제품이라 공개 리뷰가 없음 | "해당 기업의 세일즈 자료, 케이스 스터디, 고객 인터뷰에서 감성을 추론하세요"로 변경 |
| 경쟁사가 5개 이상 | 핵심 경쟁사 2-3개만 골라서 먼저 분석하세요. 분석 품질이 떨어집니다 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 감성 분석을 전문가 수준으로 수행하고 싶은 분입니다.
> Layer 1의 결과물이 "표면적"이라고 느꼈다면 이걸 써보세요.

### 📌 진행 방식

이 프롬프트는 **9단계 CoT(Chain of Thought)** 구조입니다. 두 가지 방식으로 쓸 수 있습니다:

**방식 A: 한 번에 넣기 (추천)**
- 아래 전체를 통째로 복사해서 AI에 붙여넣으세요
- AI가 9단계를 순서대로 실행합니다
- 결과가 한 번에 나옵니다 (길지만 완결적)

**방식 B: 단계별로 넣기 (더 깊은 분석)**
- 1-2단계를 먼저 넣고 결과를 확인하세요
- 결과가 만족스러우면 3-4단계를 이어서 넣으세요
- 중간에 AI에게 "리뷰를 더 찾아줘" 등 추가 요청 가능
- 시간이 더 걸리지만, 각 단계를 직접 검증할 수 있습니다

**`<!-- 💬 -->` 교육 주석이란?**
- 프롬프트 안에 `<!-- 💬 ... -->` 형태의 주석이 있습니다
- 이건 **여러분을 위한 설명**이지, AI에게 보내는 지시가 아닙니다
- AI에 붙여넣을 때 포함해도 되고 빼도 됩니다 (결과에 영향 없음)
- "왜 이렇게 설계했는가?"를 이해하면 더 좋은 프롬프트를 만들 수 있습니다

### 프롬프트 본문

```
# 역할: 고객 감성 분석가 & 기회 포착 전문가
# 목표: 경쟁사 고객의 불만을 "우리의 기회"로 변환

# Reasoning Strategy: 구조화된 감성 분석
<!-- 💬 왜 감성 분석인가?
     리뷰는 사실(fact)과 감정(feeling)이 섞여 있습니다.
     "가격이 비싸다" (fact) ← "돈이 아깝다고 느낀다" (feeling)

     감정을 파악하면:
     1. 고객의 진짜 고통 (심리적)
     2. 우리가 해결할 수 있는 것
     3. 마케팅 메시지 (감정에 호소)
     를 모두 얻을 수 있습니다 -->

1단계: 리뷰 수집 & 감성 분류
   <!-- 💬 "감성"은 이진법이 아닙니다. -1 ~ +1 스펙트럼입니다 -->

   각 리뷰마다:
   - 감성 점수: -1 (매우 부정) ~ 0 (중립) ~ +1 (매우 긍정)
   - 감성 강도: 약함 / 중간 / 강함
   - 주제 카테고리: {가격, 기능, UI/UX, 지원, 성능, 보안, 통합, 기타}
   - 고객 페르소나 추론: {직책, 회사 규모, 사용 목적}
   - 구체적 인용: "고객이 정확히 뭐라고 말했나?"

   분석 템플릿:
   ```
   리뷰 1:
   - 출처: G2, 별 2개
   - 감성: -0.7 (강한 부정)
   - 주제: 가격 + 지원
   - 고객: 스타트업 PM, 팀 5명
   - 인용: "가격 대비 기능이 떨어지고, 지원이 이틀 늦음"
   - 해석: "비용 대비 가치 부족" + "시간이 중요"
   ```

2단계: 감성 분포 분석
   <!-- 💬 개별 리뷰도 중요하지만, "전체 분포"가 더 중요합니다 -->

   리뷰 20개의 감성을 그래프로:
   ```
   긍정 (+1) ▓▓▓▓▓▓▓▓
   (+0.5)   ▓▓▓▓▓▓▓▓▓▓▓
   중립 (0) ▓▓▓▓▓▓▓
   (-0.5)   ▓▓▓▓▓▓▓▓▓
   부정 (-1) ▓▓▓▓▓
   ```

   평균 감성 점수 계산 (중앙값도 구하기)
   → "이 경쟁사 고객들이 전반적으로 만족하나?"를 정량화

3단계: 주제별 감성 분해
   <!-- 💬 "전반적 감성"보다 "주제별 감성"이 더 유용합니다 -->

   주제별로 감성을 분류:
   ```
   가격:    평균 -0.6 (강한 부정) ← 가장 불만 많음
   지원:    평균 -0.3 (약한 부정)
   기능:    평균 +0.2 (약한 긍정)
   UI/UX:   평균 +0.4 (중간 긍정)
   성능:    평균 +0.3 (약한 긍정)
   ```

   → "경쟁사의 가장 약한 부분은 가격"이 명확해집니다

4단계: 고객 페르소나별 감성 분석
   <!-- 💬 같은 제품도 고객마다 다르게 평가합니다 -->

   리뷰어의 페르소나 추론:
   - 스타트업 PM: 감성 -0.2 (가격 중시)
   - 대기업 PO: 감성 +0.1 (지원 중시, 가격 덜 중시)
   - 개발자: 감성 +0.3 (기능 좋음)
   - 마케터: 감성 -0.5 (분석 기능 부족)

   → "어떤 세그먼트가 더 불만족하나?"가 보입니다

5단계: 불만의 원인 분석 (감정 ← 이유)
   <!-- 💬 "왜 불만족하나?"의 근저에는 감정이 있습니다

        표면: "비싸다"
        심층: "돈이 아깝다" (품질 대비 가격)
              "성장 단계에서 써줄 돈이 없다" (경제 상황)
              "다른 경쟁사는 더 싸다" (상대적 박탈감)
   -->

   감정-이유 맵핑:
   - "화남 😠" ← "내 예산으로 못 씀" (경제적 고통)
   - "답답함 😐" ← "지원이 느려서 문제 못 푼다" (시간 손실)
   - "실망 😞" ← "기능이 약해서 원하는 걸 못 한다" (기능 부족)
   - "불신 😒" ← "가격 대비 품질이 떨어진다" (신뢰 부족)

6단계: 고객이 바라는 "대안" 파악
   <!-- 💬 리뷰에서 "더 나았으면..." 힌트를 찾으세요 -->

   명시적:
   - "가격이 50% 싸면 쓰겠다"
   - "24시간 지원이 있으면 쓰겠다"

   암시적:
   - "경쟁사 B는 이 기능이 있는데..."
   - "다른 팀은 이 도구로 쉽게 하는데..."

   → "우리가 메시지할 포인트" 발견

7단계: 기회 매트릭스 작성
   <!-- 💬 "감성 분석"을 "사업 기회"로 변환하는 최고의 도구 -->

   |                    | 많은 고객 불만 | 적은 고객 불만 |
   |--------------------|-----------------|-----------------|
   | **우리가 해결 쉬움** | 🔴 **우선순위 1** | 🟡 우선순위 3 |
   | **우리가 해결 어려움** | 🟠 우선순위 2 | ⚫ 투자 X |

   예:
   ```
   🔴 가격 불만 (많음) + 우리는 저가 모델 가능 → "가격으로 공략"
   🔴 지원 불만 (많음) + 우리는 한글 지원 가능 → "한글 지원으로 공략"
   🟡 API 복잡 불만 (적음) + 우리는 해결 쉬움 → "나중에"
   🟠 AI 정확도 (많음) + 우리도 해결 어려움 → "일단 인정하고 다른 강점 강조"
   ```

8단계: 최종 기회 발굴
   <!-- 💬 "경쟁사의 약점" = "우리의 강점" (기획해야 함) -->

   기회 #1:
   - 경쟁사 불만: "가격이 비싸다" (-0.6)
   - 우리의 차별화: "50% 저가 플랜" + "세 번째 등급 추가"
   - 마케팅 메시지: "비용 걱정 없이 시작하세요"
   - 예상 효과: 스타트업 세그먼트에서 경쟁사 고객 전환 30-50%

   기회 #2:
   - 경쟁사 불만: "지원이 느리다" (-0.3)
   - 우리의 차별화: "24시간 한글 지원" + "Slack 연동 빠른 응답"
   - 마케팅 메시지: "한국 팀이 직접 지원합니다"
   - 예상 효과: 중견기업에서 경쟁사 이탈 고객 20-30%

   기회 #3:
   - 경쟁사 불만: "온보딩이 복잡하다" (-0.4)
   - 우리의 차별화: "5분 빠른 시작" + "인터랙티브 튜토리얼"
   - 마케팅 메시지: "복잡한 설정 없이, 지금 바로 시작하세요"
   - 예상 효과: 신규 사용자 시도 전환율 +20%

9단계: 작성한 분석을 검토하세요.
   <!-- 💬 자기검증:
        [ ] 리뷰 샘플이 대표적인가? (최신 리뷰 포함하나?)
        [ ] 감성 점수가 일관되게 부여됐나? (주관적 편향 없나?)
        [ ] "우리가 해결할 수 있는" 기회만 선택했나?
        [ ] 마케팅 메시지가 실제로 가능한가? (거짓 약속은 안 했나?)
        [ ] 경쟁사 다른 리뷰도 봤나? (한 플랫폼만은 위험)
   -->

# 컨텍스트와 데이터
## 분석 대상 경쟁사:
   - 경쟁사 1: {회사명, 제품명}
   - 경쟁사 2: {회사명, 제품명}
   - 경쟁사 3: {회사명, 제품명}

## 데이터 소스:
   글로벌:
   - G2 리뷰 (최신 50개)
   - 앱스토어/플레이스토어 (평점 4.5 이하 리뷰 중심)
   - Reddit / Product Hunt 코멘트

   국내:
   - 앱스토어/플레이스토어 한국어 리뷰
   - 블라인드 / 개발자 커뮤니티
   - 네이버 블로그/카페 "{경쟁사명} 후기" 검색

## 분석 기간:
   - 최근 3개월 ~ 12개월 (트렌드 파악)
   - 우리 업데이트 이후 리뷰는 별도 분석

## 초점:
   - "왜 고객이 경쟁사를 싫어하는가?"
   - "우리는 그걸 어떻게 잘할 것인가?"
```

### 💡 Deep Tips

**데이터 수집 — 글로벌 기업:**
- G2: 각 경쟁사당 별 4.5 이하 리뷰 20-30개 (최신순)
- 앱스토어/플레이스토어: "도움됨" 높은 부정 리뷰 중심
- Reddit: r/[industry], r/ProductManagement 검색
- Product Hunt: 각 제품의 코멘트 100+ 읽기

**데이터 수집 — 국내 기업:**
- 앱스토어: "최신순" + "별 1-3개" 필터링. 한국어 리뷰만 사용
- 블라인드: 회사명 검색 → "현직자 리뷰" 탭. 단, 직원 관점이므로 사용자 관점과 구분
- 네이버 블로그: `"{제품명} 후기" -협찬 -광고 -체험단` 으로 검색하면 순수 리뷰 확보
- 네이버 카페: 관련 산업 카페 내 제품명 검색 (가장 솔직한 피드백)
- IT 매체 댓글: 아웃스탠딩, eo, 요즘IT 등 기사 댓글에 실사용 경험이 많음
- 오픈카톡/슬랙 커뮤니티: PM, 디자이너, 개발자 커뮤니티에서 제품 언급 검색

**AI 제품이라면:**
- "AI 정확도 부족" vs "속도가 느림" 감성 구분
- "할루시네이션" 불만 (신뢰도 감정 = 매우 중요)
- "가격이 비싼데 정확도는..." (가성비 감정)
- "API 문서가 부족해서" (개발자 경험 감정)
- "데이터 프라이버시 정책 불명확" (신뢰 감정)

**한국 SaaS 특화:**
- "한글 지원 없다" (리뷰에 자주 나옴)
- "한국 고객 지원이 없다" (시간대 차이 → 답답함)
- "결제 방법이 제한적" (신용카드만 → 이탈)
- "개인정보보호법 준수 여부" (국내 기업 필수)
- "블라인드/커뮤니티에서 평판이 안 좋다" (입소문 효과 큼)

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | AI가 "실시간 데이터 접근 불가"라고 답함 | 리뷰를 직접 복사해서 프롬프트에 붙여넣으세요. "다음 리뷰 데이터를 분석하세요:" 뒤에 텍스트 추가 |
| 2단계 | 리뷰가 편향됨 (부정만 있거나 긍정만 있음) | "별 1-2개 10개, 별 4-5개 10개를 균형 있게 수집해서 다시 분석하세요"라고 재지시 |
| 3단계 | 주제 분류가 너무 뭉뚱그려짐 | "주제를 더 세분화하세요. 예: '기능' → '검색 기능', 'AI 기능', '협업 기능'"으로 세분화 요청 |
| 4단계 | 페르소나 추론이 불가능 | 리뷰에 직책/회사 정보가 없으면, "사용 패턴 기반으로 추론하세요 (예: API 언급 → 개발자)"로 안내 |
| 7단계 | "우리가 해결할 수 있는지" 판단 불가 | 기회 매트릭스의 "해결 가능성" 열은 AI가 판단하기 어려움. 팀 내부에서 직접 채우세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 감성 분석을 반복 가능한 자동화 파이프라인으로 만들고 싶은 분입니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 "리뷰 수집 → 감성 분석 → 기회 매트릭스" 과정을 Python 스크립트로 자동화합니다. 경쟁사를 입력하면, 리뷰 수집부터 리포트 생성까지 원스텝으로 실행됩니다.

**왜 자동화하나?**
- 경쟁사 감성 분석은 한 번이 아니라 **월간/분기별 반복** 작업입니다
- 수동으로 하면 30분+ 걸리는 작업이 코드로 5분에 끝납니다
- 시간 경과에 따른 감성 변화 트렌드를 추적할 수 있습니다

**전제조건:**
- Python 3.8+ 설치
- `pip install anthropic requests` 실행
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`
- (선택) G2, AppStore 등의 리뷰 데이터를 CSV로 준비하면 더 정확합니다

**아키텍처 개요:**
```
[리뷰 데이터 수집]  →  [Claude API 감성 분석]  →  [기회 매트릭스 생성]  →  [마크다운 리포트]
  - G2 스크래핑           - 감성 점수 부여          - 주제별/페르소나별       - 자동 저장
  - 앱스토어 API          - 페르소나 추론            기회 도출
  - 블라인드 크롤링       - 주제 분류
  (국내 기업용)
```

### Python + API 자동화

```python
import requests
from datetime import datetime, timedelta
import json
from typing import Dict, List, Tuple
from anthropic import Anthropic
from collections import defaultdict

class CompetitorSentimentAnalyzer:
    """
    경쟁사 감성 분석 자동화 파이프라인

    사용법:
        analyzer = CompetitorSentimentAnalyzer(["Notion", "Confluence"])
        report = analyzer.generate_report()

    국내 기업 분석 시:
        analyzer = CompetitorSentimentAnalyzer(
            ["토스", "카카오뱅크"],
            market="kr"  # 한국 시장 데이터 소스 사용
        )
    """

    def __init__(self, competitors: List[str], market: str = "global"):
        """
        Args:
            competitors: 분석할 경쟁사 리스트
            market: "global" (G2/Reddit 중심) 또는 "kr" (블라인드/네이버 중심)
        """
        self.competitors = competitors
        self.market = market
        self.client = Anthropic()
        self.reviews = defaultdict(list)
        self.sentiment_analysis = {}

    def collect_reviews(self, competitor_name: str, limit: int = 30) -> List[Dict]:
        """
        시장 유형에 따라 적절한 소스에서 리뷰 수집

        global: G2, AppStore, Reddit
        kr: 앱스토어 한국 리뷰, 블라인드, 네이버 블로그
        """
        if self.market == "kr":
            return self._collect_kr_reviews(competitor_name, limit)
        else:
            return self._collect_global_reviews(competitor_name, limit)

    def _collect_global_reviews(self, competitor_name: str, limit: int = 30) -> List[Dict]:
        """
        글로벌 리뷰 수집 (G2, AppStore, Reddit)
        실제 구현 시 Selenium/Playwright 또는 각 플랫폼 API 활용
        """
        reviews = []

        try:
            # G2 API 또는 웹스크래핑 (예시)
            url = f"https://www.g2.com/products/{competitor_name.lower().replace(' ', '-')}/reviews"

            # 실제 구현: Selenium + BeautifulSoup 또는 Playwright
            # response = requests.get(url, headers={"User-Agent": "..."})
            # soup = BeautifulSoup(response.content, 'html.parser')

            # 샘플 데이터 (실제로는 스크래핑 결과로 대체)
            sample_reviews = [
                {
                    'source': 'G2',
                    'rating': 2,
                    'text': '가격이 너무 비싸고 지원이 느려요',
                    'date': '2024-11-15',
                    'reviewer_title': 'PM at Startup'
                },
                {
                    'source': 'G2',
                    'rating': 4,
                    'text': '기능은 좋은데 온보딩이 복잡함',
                    'date': '2024-11-10',
                    'reviewer_title': 'CTO at Mid-size'
                }
            ]

            return sample_reviews[:limit]

        except Exception as e:
            print(f"글로벌 리뷰 수집 오류: {e}")
            return []

    def _collect_kr_reviews(self, competitor_name: str, limit: int = 30) -> List[Dict]:
        """
        한국 시장 리뷰 수집 (앱스토어 한국, 블라인드, 네이버)

        국내 기업 분석 시 주요 데이터 소스:
        1. 앱스토어/플레이스토어 한국어 리뷰
        2. 블라인드 (직원/사용자 리뷰)
        3. 네이버 블로그/카페 (일반 사용자 후기)
        """
        reviews = []

        # --- 1. 앱스토어 한국 리뷰 수집 ---
        try:
            # Apple RSS Feed (한국 앱스토어)
            # 실제 구현: https://itunes.apple.com/kr/rss/customerreviews/id={app_id}/json
            pass
        except Exception as e:
            print(f"앱스토어 수집 오류: {e}")

        # --- 2. 블라인드 리뷰 수집 ---
        try:
            # 블라인드 검색 API (비공식)
            # 주의: 블라인드 리뷰는 "직원 관점"이므로 태그로 구분
            # review['perspective'] = 'employee'  # vs 'user'
            pass
        except Exception as e:
            print(f"블라인드 수집 오류: {e}")

        # --- 3. 네이버 블로그 검색 ---
        try:
            # 네이버 검색 API (공식)
            # https://developers.naver.com/docs/serviceapi/search/blog/blog.md
            # query = f'"{competitor_name}" 후기 -협찬 -광고'
            pass
        except Exception as e:
            print(f"네이버 블로그 수집 오류: {e}")

        # 샘플 데이터 (실제로는 위 수집 결과로 대체)
        sample_reviews = [
            {
                'source': '앱스토어(KR)',
                'rating': 2,
                'text': '업데이트 후 앱이 너무 느려졌어요. 예전이 좋았는데.',
                'date': '2024-11-20',
                'reviewer_title': '일반 사용자',
                'perspective': 'user'
            },
            {
                'source': '블라인드',
                'rating': 3,
                'text': '내부에서도 이 기능 문제 알고 있는데 리소스가 없어서 못 고침',
                'date': '2024-11-18',
                'reviewer_title': '현직 개발자',
                'perspective': 'employee'
            },
            {
                'source': '네이버 블로그',
                'rating': 2,
                'text': '내돈내산 후기인데, 고객센터 전화 연결이 30분 넘게 걸림. 챗봇은 쓸모없음.',
                'date': '2024-11-12',
                'reviewer_title': '블로거',
                'perspective': 'user'
            }
        ]

        return sample_reviews[:limit]

    def analyze_sentiment_with_claude(self, reviews: List[Dict]) -> Dict:
        """
        Claude를 사용한 감성 분석 (한국어 포함)
        """
        reviews_text = "\n\n".join([
            f"리뷰 {i+1} (별 {r.get('rating')}개, {r.get('source')}):\n{r.get('text')}"
            for i, r in enumerate(reviews)
        ])

        prompt = f"""
당신은 고객 감성 분석 전문가입니다.

다음은 경쟁사에 대한 고객 리뷰들입니다:

{reviews_text}

각 리뷰를 분석하고 다음을 JSON으로 제시하세요:

1. **감성 점수**: -1 (매우 부정) ~ +1 (매우 긍정)
2. **감정**: 화남, 실망, 불만족, 중립, 만족, 감동 등
3. **주제**: 가격, 기능, UI/UX, 지원, 성능, 보안, 통합, 기타
4. **고객 페르소나 추론**: 직책, 회사 규모, 산업
5. **핵심 이유**: 왜 이런 감정을 느꼈나?
6. **대안 바람**: 고객이 원하는 개선점?

그리고 전체 리뷰의:
- 평균 감성 점수
- 주제별 감성 평균
- 페르소나별 감성 평균
- 가장 빈번한 불만 TOP 3

JSON 형식으로 정리하세요.
        """

        message = self.client.messages.create(
            model="claude-sonnet-4-6",
            max_tokens=2500,
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
            print(f"감성 분석 오류: {e}")

        return {}

    def identify_opportunities(self, sentiment_data: Dict) -> List[Dict]:
        """
        감성 분석에서 비즈니스 기회 도출
        """
        prompt = f"""
다음은 경쟁사 고객의 감성 분석 결과입니다:

{json.dumps(sentiment_data, ensure_ascii=False, indent=2)}

이를 기반으로 우리가 공략할 수 있는 기회를 찾으세요:

1. **경쟁사의 약점** (가장 불만이 많은 3개 주제)
2. **우리의 차별화** (우리가 해결할 수 있는 것)
3. **마케팅 메시지** (고객에게 어떻게 어필할지)
4. **예상 효과** (전환율, 시장 점유 증가)
5. **실행 우선순위** (어떤 기회부터 공략할지)

기회 매트릭스를 작성하세요:
- 많은 고객 불만 + 우리가 해결 쉬움 = 🔴 최우선
- 많은 고객 불만 + 우리가 해결 어려움 = 🟠 투자 고려
- 적은 고객 불만 + 우리가 해결 쉬움 = 🟡 나중에
- 적은 고객 불만 + 우리가 해결 어려움 = ⚫ 투자 X

JSON 형식으로 응답하세요.
        """

        message = self.client.messages.create(
            model="claude-sonnet-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        return message.content[0].text

    def generate_report(self) -> Dict:
        """
        전체 경쟁사 감성 분석 리포트 생성

        실행 순서:
        1. 시장 유형에 따른 리뷰 수집 (global/kr)
        2. Claude API로 감성 분석
        3. 기회 도출 및 매트릭스 작성
        4. 마크다운 리포트 생성
        """
        report = {
            'generated_at': datetime.now().isoformat(),
            'market': self.market,
            'competitors_analyzed': self.competitors,
            'analyses': {}
        }

        for competitor in self.competitors:
            print(f"분석 중: {competitor} (시장: {self.market})...")

            # 1단계: 리뷰 수집
            reviews = self.collect_reviews(competitor, limit=30)
            self.reviews[competitor] = reviews

            # 2단계: 감성 분석
            sentiment_result = self.analyze_sentiment_with_claude(reviews)
            self.sentiment_analysis[competitor] = sentiment_result

            # 3단계: 기회 도출
            opportunities = self.identify_opportunities(sentiment_result)

            report['analyses'][competitor] = {
                'review_count': len(reviews),
                'sentiment_analysis': sentiment_result,
                'opportunities': opportunities
            }

        return report

    def to_markdown(self, report: Dict) -> str:
        """마크다운 형식으로 내보내기"""
        market_label = "한국 시장" if report.get('market') == 'kr' else "글로벌 시장"
        output = f"# 경쟁사 감성 분석 리포트 ({market_label})\n\n"
        output += f"분석일시: {report['generated_at']}\n"
        output += f"분석 대상: {', '.join(report['competitors_analyzed'])}\n\n"

        for competitor, analysis in report['analyses'].items():
            output += f"## {competitor} 분석\n\n"
            output += f"**수집 리뷰**: {analysis['review_count']}개\n\n"

            output += "### 감성 분석\n\n"
            output += json.dumps(
                analysis['sentiment_analysis'],
                ensure_ascii=False,
                indent=2
            )

            output += "\n### 기회 도출\n\n"
            output += analysis['opportunities']

            output += "\n---\n\n"

        return output


# ============================================================
# 사용 예시
# ============================================================

if __name__ == "__main__":

    # --- 글로벌 기업 분석 ---
    print("=== 글로벌 경쟁사 분석 ===")
    global_analyzer = CompetitorSentimentAnalyzer(
        competitors=["Notion", "Confluence", "Asana"],
        market="global"
    )
    global_report = global_analyzer.generate_report()

    with open("competitor-sentiment-global.md", "w", encoding="utf-8") as f:
        f.write(global_analyzer.to_markdown(global_report))

    # --- 국내 기업 분석 ---
    print("\n=== 국내 경쟁사 분석 ===")
    kr_analyzer = CompetitorSentimentAnalyzer(
        competitors=["토스", "카카오뱅크"],
        market="kr"
    )
    kr_report = kr_analyzer.generate_report()

    with open("competitor-sentiment-kr.md", "w", encoding="utf-8") as f:
        f.write(kr_analyzer.to_markdown(kr_report))

    print("\n경쟁사 감성 분석이 완료되었습니다!")
```

### Claude Code / CLI 연동

```bash
# 글로벌 경쟁사 감성 분석
python sentiment_analyzer.py --market global --competitors "Notion,Confluence,Asana"

# 국내 경쟁사 감성 분석
python sentiment_analyzer.py --market kr --competitors "토스,카카오뱅크,뱅크샐러드"

# 여러 경쟁사 병렬 분석
for competitor in "Notion" "Confluence" "Asana"; do
  python sentiment_analyzer.py \
    --market global \
    --competitors "$competitor" \
    --output sentiment-${competitor}.md &
done
wait

# 최종 통합 분석 및 차별화 포인트 도출
claude --print "다음 경쟁사 분석을 종합해서, 우리의 최고 차별화 3가지를 찾으세요: $(cat sentiment-*.md)" \
  > our-differentiation.md
```

---

## 📊 실행 결과 예시

<details>
<summary><b>Layer 1 실행 결과 (글로벌 — Notion 경쟁사 분석)</b></summary>

```
Notion 경쟁사 (Confluence, Asana)의 리뷰 감성 분석

=== 결과 (8분) ===

[출처: G2, AppStore, Reddit]

Confluence 리뷰 감성:
  별 5개 (긍정): "회사에서 강요해서 씀"
  별 4개: "기능은 많은데 복잡"
  별 3개: "로딩이 느려서 답답"
  별 2개: "가격 비싸고 옵션 많아서 머리 아픔"
  별 1개: "왜 이렇게 느린가? 회사가 비용 낭비"

패턴:
  ❌ 부정 (56%): 가격 + 속도 + 복잡도
  ➡️ 중립 (28%): 기능은 많음
  ✅ 긍정 (16%): 엔터프라이즈 기능

우리의 기회:
  1. "간단하면서도 강력" (Confluence 대비)
  2. "저가 플랜으로 시작" (Asana 대비)
  3. "한글 지원 완벽" (모두 영어만)
```

</details>

<details>
<summary><b>Layer 1 실행 결과 (국내 — 토스 경쟁사 분석)</b></summary>

```
토스 경쟁사 (카카오뱅크, 뱅크샐러드)의 리뷰 감성 분석

=== 결과 (8분) ===

[출처: 앱스토어(KR), 블라인드, 네이버 블로그]

카카오뱅크 앱스토어 리뷰 감성:
  별 5개 (긍정): "통장 개설이 너무 편해요"
  별 4개: "UI는 깔끔한데 이체 한도가 아쉬움"
  별 3개: "고객센터 연결이 잘 안 됨"
  별 2개: "앱 업데이트 후 자꾸 튕겨요"
  별 1개: "대출 심사 기준이 불투명"

패턴:
  ❌ 부정 (38%): 고객센터 + 앱 안정성 + 대출 심사
  ➡️ 중립 (32%): 기본 기능은 양호
  ✅ 긍정 (30%): UI/UX + 간편 개설

블라인드 리뷰 (직원 관점):
  "내부에서도 고객센터 인력 부족 인지하고 있음"
  "AI 챗봇 도입 검토 중이지만 진행이 느림"

우리의 기회:
  1. "AI 기반 24시간 고객 상담" (고객센터 불만 대응)
  2. "투명한 심사 과정 공개" (대출 심사 불만 대응)
  3. "앱 안정성 강조" (업데이트 후 오류 이탈 고객 흡수)
```

</details>

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 감성 점수가 가장 낮은 페르소나의 '실제 리뷰'를 3개 읽어보세요 — 숫자 뒤의 맥락을 놓치고 있을 수 있습니다
2. **[논쟁 지점]** 감성 분석에서 '중립(0)' 리뷰를 어떻게 분류할지는 분석 목적에 따라 다릅니다 — 기회로 볼지, 무시할지
3. **[자기 검증]** 기회 매트릭스의 상위 1개 기회가 실제 시장에서 해결 시도가 있었는지 Product Hunt에서 검색하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| 경쟁사 약점 | → `problem-framing.md` | "우리가 풀어야 할 문제는?" (경쟁사 약점 기반) |
| 차별화 포인트 | → `positioning-strategy.md` (decide/) | 마케팅 포지셔닝 결정 |
| 고객 기회 | → `customer-journey-mapping.md` | 경쟁사 이탈 고객의 여정 |
| 가격 전략 | → `feature-prioritization.md` (decide/) | 가격 대비 기능 결정 |

---

## 📝 참고자료 및 도구

**글로벌:**
- [G2.com](https://www.g2.com) — 기업용 소프트웨어 리뷰
- [Product Hunt](https://www.producthunt.com) — 초기 사용자 피드백
- [Reddit](https://www.reddit.com) — r/[industry], r/ProductManagement

**국내:**
- 앱스토어/플레이스토어 — 한국어 리뷰 필터링
- [블라인드](https://www.teamblind.com) — 직원 리뷰 (직원 관점 ≠ 사용자 관점 주의)
- [네이버 검색 API](https://developers.naver.com/docs/serviceapi/search/blog/blog.md) — 블로그/카페 자동 수집

**감성 분석 도구:**
- MonkeyLearn, Hugging Face Transformers, Claude API
