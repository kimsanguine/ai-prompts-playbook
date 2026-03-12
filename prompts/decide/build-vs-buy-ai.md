# 🏗️ AI Build vs Buy 의사결정 (Build vs Buy AI)

> 예상 소요: 5분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: `positioning-strategy.md` → (이 파일) → `feature-prioritization.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 제품 PM의 **가장 중요한 의사결정** 중 하나는 **"Build vs Buy"**입니다:

- "고객 문제 분류를 직접 모델을 개발할까, 아니면 OpenAI API를 쓸까?"
- "추천 엔진을 내재화할까, 아니면 Third-party 솔루션(예: algopix)을 쓸까?"
- "음성인식을 Google Speech-to-Text로 할까, 아니면 Whisper 파인튜닝으로 할까?"

이 의사결정은 **비용, 속도, 품질, 장기 경쟁력, 의존성** 등을 모두 고려해야 하기 때문에 매우 복잡합니다.

**Build vs Buy 의사결정 프롬프트**는 다음을 제공합니다:
- 정량적 비교 틀 (Total Cost of Ownership, 6개월/1년/3년)
- 정성적 고려사항 (기술 의존성, 경쟁력, 팀 역량)
- 의사결정 트리 (상황별 가이드)
- 회사 성장 단계별 권장사항 (Pre-PMF → Series A → Series B)

---

## 📥 이전 프롬프트에서 받는 입력

> `prd-for-ai-feature.md`에서 AI 기능을 직접 만들지 외부 솔루션을 도입할지 결정할 때 연결됩니다.

이전 프롬프트 결과에서 **기능 요구사항, 기술 제약, 예산, 일정**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 AI 기능을 자체 개발할지, 외부 솔루션을 쓸지 판단할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI 제품 의사결정 컨설턴트입니다.

AI 기능: {FEATURE_NAME} ({문제점})

BUILD vs BUY 비교 분석:

BUILD (직접 개발):
- 초기 비용: {금액}
- 월간 운영: {금액}
- 완료 기간: {기간}
- 장점: [3개]
- 단점: [3개]

BUY (외부 API 사용):
- 제공사: {이름}
- 월간 비용: {금액}
- 초기 설정: {기간}
- 장점: [3개]
- 단점: [3개]

HYBRID (부분 외부 + 부분 자체):
- 구성: [설명]
- 월간 비용: {금액}
- 장점/단점: [각 2-3개]

추천: {BUILD/BUY/HYBRID} → 이유: [근거]

추가 고려사항:
- 회사 성장 단계: {Seed/Series A/B}에서 {언제} 전환 가능?
- 팀 역량: {현재 수준}, {6개월 후} 가능?
```

💡 **Quick Tips:**
- "Build가 멋있으니까 Build"라는 선택을 피하세요. 비용과 시간을 먼저 계산하세요
- Buy는 "지금 빠르게" 가능하지만, 장기 비용(per-token 가격 상승)을 고려하세요
- Hybrid는 "Best of Both" 처럼 보이지만 **관리 복잡도가 2배**입니다
- 회사 성장 단계에 따라 선택이 다릅니다. Seed는 Buy, Series B는 Build 검토


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 기술팀이 작아서 Build 역량 의문 | "최소 MVP를 만들 수 있는가?" → 없으면 Buy 후 점진적 내재화 |
| 외부 API 비용이 불확실 | 사용량 시뮬레이션을 하세요. 월 1만 건 vs 10만 건 vs 100만 건 비용 비교 |
| 보안/규정 이슈 | 데이터가 외부로 나가면 안 되는 경우 → Build 우선. 단, 온프레미스 AI 옵션도 검토 |
| 둘 다 해야 할 것 같음 | "핵심 차별화 부분은 Build + 범용 부분은 Buy" 하이브리드 전략 추천 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — AI 기능의 Build vs Buy를 깊이 있게 평가하고 싶은 분입니다.
비용, 기술 역량, 시장 속도, 전략적 차별화를 종합적으로 고려하고 싶다면 이걸 써보세요.

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
당신은 AI 제품의 Build vs Buy 의사결정 전략가이면서,
CEO/CTO/CFO의 관점을 모두 고려하는 조직가입니다.

# 목표
{FEATURE_NAME}에 대해 Build/Buy/Hybrid를 정량적으로 비교하고,
회사 성장 단계와 팀 역량을 고려하여
**가장 현실적이고 장기적으로 지속 가능한 선택**을 제시합니다.

<!-- 💬 왜 Build vs Buy가 중요한가?
AI 스타트업의 실패 이유 중 하나는 "아무것도 Build하지 못했다"입니다.
모든 것을 직접 만들려다 번아웃되거나, 기술 부채로 망하거나,
외부 API에 의존해서 경쟁력을 잃습니다.

올바른 Build vs Buy 선택이 회사의 생존을 결정합니다.
-->

# Reasoning Strategy

## Step 1: 현재 상황 정의

### 당신이 직면한 의사결정
```
명확히 하세요:

1. 무엇을 Build/Buy 할 것인가?
   - 기술 영역: [예: 음성인식, 추천, 분류]
   - 범위: [예: 한국어만 vs 10개 언어]
   - 성능 목표: [예: 정확도 85% 이상]

2. 현재 상황은?
   - 회사 단계: [Seed/Series A/B]
   - 팀 규모: [Engineer 명수]
   - 기간 제약: [3개월 안에 배포? 1년?]
   - 예산 제약: [월 인프라 5만 달러?]

3. 왜 지금 의사결정하는가?
   - 고객 요청? (피드백 기반)
   - 경쟁사 대응? (시장 압박)
   - 기술 부채? (기존 솔루션 문제)

<!-- 💬 상황 정의가 없으면 의사결정이 표류합니다
"자동 분류를 Build할까 Buy할까?" vs
"한국 고객을 위해 정확도 85% 자동 분류를 3개월 안에, 월 인프라 5만 달러로 구현할까?"
→ 두 번째가 의사결정입니다.
-->
```

## Step 2: Build 옵션 분석

### 직접 개발의 전체 비용
```
**초기 개발 비용:**

1. 개발 시간 (Engineer 급여 포함)
   - 예: ML Engineer 2명 × 3개월
   - 급여: $120k/year × 2명 = $240k/year
   - 3개월 비용: $60k

2. 인프라 및 도구
   - GPU 서버: $2,000/month × 3 = $6,000
   - Labeling 도구 (Label Studio 등): $500
   - MLOps (MLflow, Weights&Biases): $1,000
   - 소계: $7,500

3. 데이터 비용
   - 학습 데이터 구입/수집: $5,000
   - 라벨링: $10,000 (1000개 샘플 × $10)
   - 소계: $15,000

**초기 총 비용: $82,500**

<!-- 💬 초기 비용이 보이는 함정
많은 팀이 "개발 비용 $60k"만 본다고 해서 $60k라고 생각합니다.
실제로는 인프라, 데이터, 도구를 모두 포함해야 합니다.
-->

**월간 운영 비용:**

1. 인프라 (배포 후)
   - 추론 GPU: $1,000/month
   - 모니터링/로깅: $500/month
   - 데이터베이스: $300/month

2. 유지보수 (재학습, A/B 테스트)
   - ML Engineer 0.5명: $10k/month
   - 데이터 라벨링 (지속): $2k/month

3. 개선 (새 데이터, 모델 업데이트)
   - R&D: $5k/month

**월간 총 비용: $18,800**

**1년 총 비용:**
- 초기: $82,500
- 운영 (12개월): $225,600
- **합계: $308,100**

**3년 총비용:**
- 초기: $82,500
- 운영 (36개월): $676,800
- **합계: $759,300**

<!-- 💬 Build의 숨겨진 비용
초기 개발 후에도 지속적인 투자가 필요합니다:
- 모델 드리프트 대응 (정확도 하락)
- 새로운 언어/도메인 추가
- 성능 최적화 (응답 시간 단축)
- 규제 대응 (프라이버시, 편향성)

이를 간과하면 "Build했는데 3개월 후 정확도가 70%로 떨어졌다"는 상황을 맞습니다.
-->
```

## Step 3: Buy 옵션 분석

### 외부 API 사용의 전체 비용
```
**제공자 선택 및 가격 비교:**

1. OpenAI API (GPT-4 Classification)
   - 가격: $0.03 per 1K tokens
   - 예상 사용: 월 1,000만 tokens
   - 월간 비용: $300

2. Google Cloud Natural Language
   - 가격: $1 per 1,000 requests
   - 예상 사용: 월 50만 requests
   - 월간 비용: $500

3. Hugging Face Enterprise
   - 가격: $1,000 + $500 per 1,000 requests
   - 월간 비용: $3,500

4. 커스텀 솔루션 (예: Algopix 추천)
   - 가격: $500-5,000/month (회사 규모별)

**초기 통합 비용:**
- 개발 시간: Engineer 1명 × 2주 = $7,500
- 테스트/검증: 1주 = $3,750
- **초기 총 비용: $11,250**

**월간 비용 (OpenAI 기준): $300-500**

**1년 총 비용:**
- 초기: $11,250
- 운영 (API): $3,600 - $6,000
- **합계: $14,850 - $17,250**

**3년 총 비용:**
- 초기: $11,250
- 운영 (API): $10,800 - $18,000
- **합계: $22,050 - $29,250**

<!-- 💬 Buy의 장점: 비용이 명확함
Build는 "3개월 후 정확도가 떨어지면 2개월 더 투자"가 될 수 있습니다.
Buy는 "API 가격이 2배가 되어도" 예측 가능한 비용입니다.

단, 장기 비용을 고려해야 합니다:
- 토큰 가격이 매년 10% 상승하면?
- 사용량이 10배 증가하면?
-->

**실제 제공자별 비용 비교표:**

| 제공자 | 초기 | 월간 | 1년 | 3년 |
|---|---|---|---|---|
| OpenAI API | $11.3k | $300 | $15k | $23k |
| Google NLP | $11.3k | $500 | $17k | $29k |
| HF Enterprise | $11.3k | $3.5k | $53k | $137k |
| Build (내재화) | $82.5k | $18.8k | $308k | $759k |
```

## Step 4: Hybrid 옵션 분석

### 부분 외부 + 부분 자체 개발
```
**Hybrid 모델 예시:**

**Phase 1: Buy (0-3개월)**
- OpenAI API로 빠르게 배포
- 실제 데이터 수집 및 성능 모니터링
- 고객 피드백 기반 문제점 파악

**Phase 2: Build (3-6개월)**
- 정확도가 낮은 케이스(Edge Case) 수집
- 커스텀 모델 개발 시작
- OpenAI와 병렬 운영

**Phase 3: Transition (6-9개월)**
- 커스텀 모델이 충분히 성숙하면 전환
- OpenAI 점진적 축소
- 완전 내재화 또는 혼합 운영

**비용:**
- Phase 1 (0-3개월):
  - OpenAI: $1,000
  - Engineer 0.2명 (모니터링): $5k
  - 소계: $6,000

- Phase 2 (3-6개월):
  - OpenAI: $1,000
  - Engineer 1명 (Build): $30k
  - 인프라: $5,000
  - 소계: $36,000

- Phase 3 (6-9개월):
  - OpenAI: $500 (Fallback용)
  - Engineer 0.5명 (유지보수): $15k
  - 인프라: $3,000
  - 소계: $18,500

**총 비용 (9개월): $60,500**
**연간화: ~$80,600**

<!-- 💬 Hybrid는 "최고"처럼 보이지만...
비용이 저렴해 보이지만, 관리 복잡도가 매우 높습니다:
- 두 시스템을 동시에 운영해야 함
- "언제 전환할지" 의사결정이 어려움
- Fallback 메커니즘 구축 필요 (추가 비용)

Hybrid는 "Series B 이상, Engineer 5명 이상, 월 수입 10만 달러 이상"일 때
효과적입니다.
-->

**Hybrid가 좋을 때:**
- 현재 Buy로 대부분 해결하지만, 일부 정확도 개선이 필요
- 고객이 "당신 알고리즘"을 원함 (차별화)
- 3개월 이상의 시간 여유가 있음
- Engineer 2명 이상의 팀 규모

**Hybrid가 나쁠 때:**
- 현재 Buy로 충분하면 굳이 Build 시작하지 마세요
- Build 준비 없이 "나중에 하자"는 식의 Hybrid는 지옥입니다
- 팀 규모가 작으면 집중력 분산
```

## Step 5: 의사결정 기준

### 정성적 고려사항
```
**비용 외의 중요 요소들:**

1. **기술 자립도 (Technical Independence)**
   - Buy: 100% 외부 의존 (위험 높음)
   - Build: 100% 자립 (단기 비용 높음, 장기 경쟁력 높음)
   - Hybrid: 50-50 (의존도 및 위험 분산)

   평가:
   - Series A 초기: Buy 또는 Hybrid (속도 중요)
   - Series B: Hybrid → Build 전환
   - Series C+: 반드시 Build (경쟁력)

2. **응답 시간 (Latency)**
   - Buy (API 호출): 50-200ms (네트워크 지연)
   - Build (온프레미스): 10-50ms (빠름)
   - 영향: 사용자 경험, 기술 차별점

   고객이 중요하면 Build, 무관하면 Buy

3. **정확도 (Accuracy)**
   - Buy (General-purpose): 85-90% (모든 도메인 평균)
   - Build (도메인 특화): 92-98% (충분한 데이터 필요)
   - 포지셔닝: "높은 정확도"가 핵심이면 Build

4. **장기 비용 (Total Cost of Ownership)**
   - 3년 단위로 비교
   - API 가격 상승률 고려 (+10%/year)
   - 사용량 증가 시나리오

   예: 사용량 10배 증가 시
   - Buy: $50k/month (비용 폭증, 마진 압박)
   - Build: $20k/month (고정비, 마진 개선)

5. **팀 역량 (Team Capability)**
   - Build 가능한가? (ML Engineer 필요)
   - 유지보수 가능한가? (6개월 후에도?)
   - 신입이 온장기 대응 가능한가?

   체크리스트:
   - [ ] ML Engineer 1명 이상?
   - [ ] Data Engineer 1명?
   - [ ] 3개월 집중 가능한가?

6. **의존성 위험 (Vendor Lock-in)**
   - Buy: 높음 (API 가격 상승, 서비스 중단 위험)
   - Build: 낮음 (원천 기술 보유)
   - Hybrid: 중간

   대응:
   - Buy: 2개 이상의 API 제공자 준비
   - Build: 모니터링/알림 시스템 필수
```

## Step 6: 의사결정 트리

### 상황별 권장사항
```
"우리가 AI 기능을 직접 만들어야 할까?"

→ Q1: 회사 수익은 충분한가? (월 $100k 이상)
  No → BUY (자본 부족, 속도 중요)
  Yes → Q2

→ Q2: 이 기능이 차별점인가? (경쟁사와의 차이)
  No → BUY (일반적 기능, 비용 절감 중요)
  Yes → Q3

→ Q3: 팀에 ML Engineer가 있는가?
  No → BUY (역량 부족) + Hybrid 검토 (3개월 후)
  Yes → Q4

→ Q4: 3개월 이상의 개발 시간이 있는가?
  No → BUY + HYBRID 계획 (Series B에서 Build)
  Yes → Q5

→ Q5: 장기 (3년) 비용을 고려했을 때?
  API 비용 < 개발 비용 → BUY (유지)
  API 비용 > 개발 비용 → BUILD (투자)

최종 결정:
- BUY → 3개월 검증 후 재평가
- BUILD → 6개월 스프린트로 내재화
- HYBRID → Phase 기반 전환 계획
```

## Step 7: 회사 성장 단계별 가이드

### 단계별 권장사항
```
**Seed Stage (수익 < $10k/month)**
- 추천: BUY (모든 것)
- 이유: 속도가 생존 결정, 자본 부족
- 예: ChatGPT API로 시작, 고객 피드백 수집
- 목표: Product-market fit 찾기

### 🇰🇷 한국 기업 Build vs Buy 특화

```
한국 기업의 Build vs Buy 의사결정 시 고려사항:

1. **한국 AI 벤더 생태계**:
   - 내재화 시 고려할 국내 솔루션: 네이버 클로바, 카카오 브레인, 업스테이지, 리턴제로
   - 특징: 한글 처리, 도메인 특화 (금융, 법률), 비용 절감 (OpenAI 대비 30-50%)
   - 선택 기준: 기술 성숙도(Naver > Kakao > 스타트업) vs 지원 품질

2. **공공기관 납품 규제 (CSAP, 클라우드 보안 인증제)**:
   - 공공기관 고객: Buy 옵션이 CSAP 인증 필수 (Google, AWS, Naver만 해당)
   - Build 시: 자체 인증 취득 비용 3-6개월, 비용 100만 원+
   - 영향: 공공 시장을 노린다면 Build보다 Buy + 커스터마이징이 현실적

3. **한국 데이터 보호 규정**:
   - 개인정보보호법(PIPA): 민감 정보는 한국 데이터센터 필수 저장
   - Buy 옵션: Openai/Google은 한국 서버 미제공 → 국내 AI 서비스 고려
   - Build 시: 인프라 비용 증가 (온프레미스 또는 KVM 기반 로컬 GPU)

4. **한국 기업 의사결정 문화**:
   - 대기업: 자체 개발 선호 (기술 독립성, 기술 자산화)
   - 스타트업: SaaS/API 선호 (속도, 운영 비용)
   - 의사결정 주체: 기술팀(스타트업) vs 경영진(대기업) → 신뢰도 높은 벤더선택
```

**Pre-Series A ($10k-50k/month)**
- 추천: BUY + 향후 BUILD 계획
- 이유: 자본 여전히 부족, 수익성 시작
- 행동: ML Engineer 채용 시작, 내재화 준비
- 목표: Repeatable business model 확립

**Series A ($50k-200k/month)**
- 추천: HYBRID 또는 BUILD
- 이유: 자본 충분, 차별화 중요, 경쟁 심화
- 행동: Core AI 기능 내재화, 주변 기능은 Buy
- 목표: 경쟁력 확보, 마진 개선

**Series B+ ($200k+/month)**
- 추천: BUILD (모든 핵심 기능)
- 이유: 스케일 시 API 비용 폭증, 독립성 필수
- 행동: 완전 내재화, 특허 추진
- 목표: 기술 경쟁력 → 시장 지배력

<!-- 💬 "성장 단계별 권장"은 정석이지만, 회사마다 다릅니다
예외:
- Seed인데 기술 차별화가 핵심 → BUILD
- Series B인데 API로 충분 → BUY 유지 (마진 우선)
- 자본 풍부 (VC 바꿈) → 더 공격적으로 BUILD

위 가이드는 "평균적 조건"입니다.
본인의 상황에 맞게 조정하세요.
-->
```

# 💡 Deep Tips:

- **"Build는 멋있다"는 감정을 버리세요**: 비용 분석이 먼저입니다
- **API 가격 상승을 고려하세요**: 지금 $500/month가 2년 뒤 $1,000/month일 수 있습니다
- **"나중에 Build"는 거짓말입니다**: Seed에서 Build 준비 없으면 Series B에도 못 합니다
- **Hybrid는 최악일 수 있습니다**: 제대로 된 계획 없으면 두 시스템 모두 망가집니다
- **고객에게 물어보세요**: "우리 알고리즘이 중요한가?" 대답이 Yes면 BUILD, No면 BUY
```


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 비용 비교가 어려움 | 3년 TCO(Total Cost of Ownership)로 비교하세요. Build는 인건비 포함 |
| 2단계 | 기술 평가가 어려움 | PoC(개념 증명)를 2주 안에 해보세요. 못 하면 Buy 쪽으로 |
| 3단계 | 시장 속도 판단 어려움 | 경쟁사가 이미 해당 기능을 출시했다면 Buy로 빠르게 따라가기 |
| 4단계 | 전략적 차별화 판단 | "이 기능이 없으면 고객이 우리를 선택할 이유가 없는가?" → 있으면 Build |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — Build vs Buy 비교 분석을 자동화하고 시나리오 시뮬레이션합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
AI 서비스가 빠르게 변하므로, 정기적으로 Build vs Buy를 재평가해야 합니다. 자동화하면 새 옵션이 나올 때마다 빠르게 비교 가능합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 스크립트: Build vs Buy 비용 계산기

```python
#!/usr/bin/env python3
"""
AI Build vs Buy 의사결정 지원 도구
- Build/Buy/Hybrid 비용 계산
- ROI 분석
- 회사 성장 단계별 추천
"""

import json
from datetime import datetime
from anthropic import Anthropic

client = Anthropic()

class BuildVsBuyAnalyzer:
    def __init__(self, feature_name: str, company_stage: str):
        self.feature_name = feature_name
        self.company_stage = company_stage  # Seed, PreA, SeriesA, SeriesB
        self.scenarios = {}

    def calculate_build_cost(self, months: int, ml_engineers: float,
                            monthly_infrastructure: float,
                            monthly_labeling: float):
        """Build 비용 계산"""
        # 초기 개발 비용
        engineer_cost = (ml_engineers * 120000 / 12) * months  # Annual salary $120k
        initial_infra = monthly_infrastructure * months
        labeling = monthly_labeling * months

        total_cost = engineer_cost + initial_infra + labeling

        return {
            "engineer_cost": engineer_cost,
            "infrastructure": initial_infra,
            "labeling": labeling,
            "total_initial": total_cost,
            "monthly_ongoing": ml_engineers * 10000 + monthly_infrastructure  # Maintenance
        }

    def calculate_buy_cost(self, monthly_api_cost: float,
                          integration_hours: float):
        """Buy 비용 계산"""
        # 통합 비용 (Engineer 1명 * 2주)
        integration_cost = (integration_hours / 160) * 120000  # $120k annual salary

        return {
            "integration": integration_cost,
            "monthly_ongoing": monthly_api_cost,
            "total_initial": integration_cost
        }

    def project_costs(self, build_initial: float, build_monthly: float,
                     buy_initial: float, buy_monthly: float,
                     years: int = 3, annual_growth_rate: float = 0.1):
        """여러 해에 걸친 비용 예측"""
        build_total = build_initial
        buy_total = buy_initial

        for year in range(years):
            # Buy 비용은 매년 상승 (API 가격 인상)
            yearly_api_cost = buy_monthly * 12 * ((1 + annual_growth_rate) ** year)
            build_monthly_adjusted = build_monthly * (1 + (annual_growth_rate * 0.5))  # Build는 천천히 증가

            build_total += build_monthly_adjusted * 12
            buy_total += yearly_api_cost

        return {
            "build": build_total,
            "buy": buy_total,
            "breakeven_month": self._calculate_breakeven(build_initial, build_monthly,
                                                         buy_initial, buy_monthly)
        }

    def _calculate_breakeven(self, build_init: float, build_monthly: float,
                            buy_init: float, buy_monthly: float):
        """손익분기점 (비용이 같아지는 개월) 계산"""
        if build_monthly <= buy_monthly:
            return None  # Build가 항상 비쌈

        months = (buy_init - build_init) / (build_monthly - buy_monthly)
        return max(0, int(months))

    def analyze(self):
        """전체 분석 수행"""
        prompt = f"""당신은 AI 스타트업 CFO입니다.

제품: {self.feature_name}
회사 성장 단계: {self.company_stage}

이 기능에 대해 Build vs Buy 의사결정 분석을 해주세요:

1. Build의 비용
   - 초기 개발 비용 (3개월, ML Engineer 2명)
   - 월간 운영 비용
   - 1년/3년 총 비용

2. Buy의 비용
   - 초기 통합 비용
   - 월간 API 비용 (예상 사용량 기반)
   - 1년/3년 총 비용 (가격 상승 고려)

3. Hybrid의 비용
   - 3단계별 비용

4. 추천 선택
   - Build/Buy/Hybrid 중 하나
   - 이유 (회사 단계, 비용, 경쟁력)
   - 추가 고려사항

JSON 형식으로 응답하세요:
{{
  "build": {{"initial": ..., "monthly": ..., "year1": ..., "year3": ...}},
  "buy": {{"initial": ..., "monthly": ..., "year1": ..., "year3": ...}},
  "hybrid": {{"description": ..., "cost": ...}},
  "recommendation": "BUILD|BUY|HYBRID",
  "reasoning": "...",
  "next_steps": ["step1", "step2", "step3"]
}}"""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2500,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        print("="*70)
        print(f"🤔 Build vs Buy 분석: {self.feature_name}")
        print(f"회사 단계: {self.company_stage}")
        print("="*70)
        print(response.content[0].text)

        return response.content[0].text

    def export_analysis(self, filename: str, analysis_text: str):
        """분석 결과 저장"""
        data = {
            "feature": self.feature_name,
            "company_stage": self.company_stage,
            "analysis": analysis_text,
            "generated_at": datetime.now().isoformat()
        }

        with open(filename, 'w', encoding='utf-8') as f:
            json.dump(data, f, ensure_ascii=False, indent=2)

        print(f"\n💾 분석 결과 저장: {filename}")


# 실행 예시
if __name__ == "__main__":
    # 예시 1: Series A, 자동 분류 기능
    analyzer1 = BuildVsBuyAnalyzer(
        feature_name="고객 이슈 자동 분류 (정확도 85% 목표)",
        company_stage="Series A"
    )
    analysis1 = analyzer1.analyze()
    analyzer1.export_analysis("build_vs_buy_classification.json", analysis1)

    print("\n" + "="*70 + "\n")

    # 예시 2: Seed, 음성인식 기능
    analyzer2 = BuildVsBuyAnalyzer(
        feature_name="한국어 음성인식 (STT)",
        company_stage="Seed"
    )
    analysis2 = analyzer2.analyze()
    analyzer2.export_analysis("build_vs_buy_stt.json", analysis2)

    # 비용 계산 예시
    print("\n" + "="*70)
    print("💰 비용 계산 예시")
    print("="*70)

    analyzer3 = BuildVsBuyAnalyzer("테스트 기능", "Series A")

    # Build: 3개월 개발 (ML Engineer 2명), 월 $3k 인프라
    build = analyzer3.calculate_build_cost(
        months=3,
        ml_engineers=2,
        monthly_infrastructure=3000,
        monthly_labeling=2000
    )

    # Buy: OpenAI API $500/month
    buy = analyzer3.calculate_buy_cost(
        monthly_api_cost=500,
        integration_hours=80  # 2주
    )

    print("\nBuild 비용 (3개월 개발):")
    print(f"  Engineer 급여: ${build['engineer_cost']:,.0f}")
    print(f"  인프라: ${build['infrastructure']:,.0f}")
    print(f"  라벨링: ${build['labeling']:,.0f}")
    print(f"  초기 총합: ${build['total_initial']:,.0f}")
    print(f"  월간 운영: ${build['monthly_ongoing']:,.0f}")

    print("\nBuy 비용 (OpenAI API):")
    print(f"  초기 통합: ${buy['integration']:,.0f}")
    print(f"  월간 API: ${buy['monthly_ongoing']:,.0f}")

    # 3년 비용 예측
    costs_3y = analyzer3.project_costs(
        build_initial=build['total_initial'],
        build_monthly=build['monthly_ongoing'],
        buy_initial=buy['total_initial'],
        buy_monthly=buy['monthly_ongoing'],
        years=3
    )

    print("\n3년 누적 비용:")
    print(f"  Build: ${costs_3y['build']:,.0f}")
    print(f"  Buy: ${costs_3y['buy']:,.0f}")
    print(f"  절감: ${abs(costs_3y['build'] - costs_3y['buy']):,.0f}")

    if costs_3y['breakeven_month']:
        print(f"\n손익분기점: {costs_3y['breakeven_month']}개월")
        print(f"→ {costs_3y['breakeven_month']/12:.1f}년 후에 Build가 더 저렴해집니다")
```

### Claude Code CLI 실행
```bash
cd /path/to/ai-pm-prompts
claude code --exec build-vs-buy-ai.py --model claude-opus-4-6
```

---

## 📊 실행 결과 예시

### Series A 고객 이슈 자동 분류

**Build vs Buy 비용 비교**

| 항목 | Build | Buy (OpenAI) | Hybrid |
|---|---|---|---|
| 초기 비용 | $82.5k | $11.3k | $18.5k |
| 월간 비용 | $18.8k | $500 | $8k |
| **1년 총비용** | $308k | $17.3k | $114.5k |
| **3년 총비용** | $759.3k | $29.3k | $286.5k |

**분석:**

1. **비용만 보면**: Build는 3년간 $730k 더 비쌉니다
2. **하지만 고려사항**:
   - OpenAI 가격이 매년 10% 인상 → 실제로는 $45k (3년)
   - 사용량 5배 증가 시 → Buy는 $150k+

3. **손익분기점**: 약 5년 (60개월)
   - 5년 이상 운영 예정 → BUILD
   - 5년 이내 엑시트 → BUY

4. **Series A 추천**: HYBRID
   - Phase 1 (3개월): OpenAI로 빠르게 배포, $13.5k
   - Phase 2 (3개월): 커스텀 모델 개발, $36k
   - Phase 3 (9개월+): 전환, $18.5k/month
   - 총 비용 (1년): $114.5k (Build보다 60% 저렴)

### 의사결정 트리 결과

```
"고객 이슈 자동 분류를 Build할까?"

Q1: 월 수익 $100k 이상? → YES (Series A)
Q2: 이게 차별점? → YES (경쟁사 대비 한국어 정확도)
Q3: ML Engineer 있나? → YES (1명)
Q4: 3개월 개발 가능? → YES (분기 계획 있음)
Q5: 3년 비용 고려? → API 비용이 높아질 예상

→ 추천: HYBRID
  - 지금: OpenAI로 시작 (빠른 배포, $13k)
  - 3개월 후: 커스텀 모델 개발 (경쟁력, $36k 추가)
  - 9개월: 점진적 전환 (비용 절감, $18k/month)
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 평가 매트릭스에서 '3년 총 비용(TCO)'이 포함되어 있는지 확인하세요 — 초기 비용만 보면 판단이 왜곡됩니다
2. **[논쟁 지점]** Build vs Buy 판단에서 '전략적 중요성'의 가중치를 어떻게 줄지는 조직마다 다릅니다
3. **[자기 검증]** Buy 옵션의 벤더 1개에 실제로 데모를 요청해서 기대치와 일치하는지 확인하세요

---

## 🔗 다음 단계

| 프롬프트 | 목적 | 연결 |
|---|---|---|
| `positioning-strategy.md` | Build vs Buy가 포지셔닝에 미치는 영향 | "고유 기술"이 포지셔닝이면 BUILD |
| `feature-prioritization.md` | 우선순위화된 기능 중 어떤 것을 Build할지 | RICE 점수 + Build/Buy 선택 |
| `decision-canvas.md` | Build vs Buy 의사결정이 필요할 때 활용 | 복잡한 의사결정을 구조화 |
