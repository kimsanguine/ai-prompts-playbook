# 📊 경영진 브리핑 (Executive Briefing for AI Strategy)

> 예상 소요: 15분 (Quick) / 40분 (Deep) / 50분+ (Build)
> 워크플로우: ← `prd-for-ai-feature.md` → 경영진 의사결정
> 🆕 **오리지널 Phase 2** → 전략적 의사결정 도구

---

## 🎯 이 프롬프트가 해결하는 problem

경영진(CEO, CFO, CTO)은 **기술 세부사항을 원하지 않습니다**.
그들이 원하는 것은:
- **이 AI 투자가 얼마나 수익을 낼 것인가?**
- **위험은 뭔가?**
- **언제쯤 ROI를 볼 것인가?**
- **경쟁사는 뭘 하고 있나?**
- **우리는 뭘 해야 하나?**

**경영진 수준의 브리핑**으로 AI 전략을 **3분 안에 이해**시키고 **빠른 의사결정**을 가능하게 하세요.
이는 단순한 "보고"가 아니라, **전략적 선택**을 위한 도구입니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `stakeholder-alignment.md`의 이해관계자 맵 + `ai-adoption-metrics.md`의 성과 데이터를 경영진용으로 정리할 때 연결됩니다.

이전 프롬프트 결과에서 **핵심 메트릭, 전략적 의사결정 사항, 리스크 요약**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 경영진을 위한 핵심 브리핑 문서를 작성할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
제품팀의 상세 PRD를 입력하세요.

자동으로 생성됩니다:
1. Executive Summary (1쪽)
   - 문제, 솔루션, 가치, 기간, 비용, ROI

2. Financial Impact
   - 3년간 예상 수익/비용
   - 손익분기점 (Break-even) 시점
   - IRR, NPV 계산

3. Risk & Mitigation
   - 기술적 위험
   - 시장 위험
   - 운영 위험
   - 대응책

4. Competitive Landscape
   - 우리는 뭘 할 건가?
   - 경쟁사는 뭘 하고 있나?
   - 우리의 차별점

5. Decision & Timeline
   - 의사결정 아이템
   - 상세 실행 로드맵
```

💡 **Quick Tips:**
- 경영진의 시간은 귀합니다: 최대 3쪽, 5분
- 숫자로 말하세요 ("좋을 것 같다" 금지)
- 최악의 시나리오도 준비하세요 (낙관주의 위험)


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 경영진이 기술적 세부사항을 원함 | 부록(Appendix)으로 기술 상세를 첨부하세요. 본문은 비즈니스 관점 유지 |
| 나쁜 뉴스를 전해야 함 | "문제 → 원인 → 해결 계획 → 지원 요청" 순서로 구성하세요 |
| 브리핑 시간이 3분뿐 | "핵심 메시지 1개 + 데이터 1개 + 요청 1개"로 압축 |
| 여러 프로젝트를 한 번에 보고 | 프로젝트별 Traffic Light (🔴🟡🟢) 상태 요약으로 시작 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 경영진 보고를 전략적으로 구성하고 싶은 분입니다.
"3분 안에 의사결정을 이끌어내는" 브리핑을 만들고 싶다면 이걸 써보세요.

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

CEO/COO, CFO, CTO, 전략 담당자

### # 목표

**경영진이 AI 투자를 의사결정할 때 필요한 모든 정보를 명확하고 간결하게 제시**

- 재무적 임팩트 (ROI, 손익분기점)
- 위험 요소와 대응책
- 경쟁 우위 확보
- 실행 가능성 확인
- 의사결정 가속화

<!-- 💬 경영진 브리핑이 왜 어려운가?

일반적인 실수:
"AI 모델의 정확도를 85% 달성했으므로..."
→ CEO: "정확도가 뭐하는 건데? 비즈니스에는 뭐가 좋은데?"

좋은 브리핑:
"이 AI로 고객 이탈을 30% 줄였으므로, 연 $400K 절감"
→ CEO: "우리가 이걸 경쟁사보다 먼저 하는 건가? 언제까지 걸려?"

같은 성과를 다르게 프레이밍합니다.
-->

### # Reasoning Strategy: 경영진 의사결정 프레임

#### Section 1: Executive Summary (1쪽, 5분)

<!-- 💬 [전문가의 눈] Executive Summary가 왜 "1쪽"이어야 하는가?
CEO의 평균 의사결정 시간은 5분입니다. 2쪽 이상이면 안 읽습니다.
따라서 "상황 → 제안 → 금액 → 시간 → 위험 → 다음 → 추천"을 1쪽에 압축해야 합니다.
핵심은 "숫자"입니다. "좋을 것 같다"는 경영진을 움직이지 못합니다.
-->

**이 한 쪽으로 모든 것이 결정됩니다.**

```
구조:

┌─ 제목
│  "고객 이탈 AI: 연 $400K 절감, 4주 후 ROI 확인"
│
├─ 상황 (The Situation)
│  "우리는 연 $2M 고객 이탈로 손실 중입니다.
│   현재 분석팀이 수동으로 대응하고 있으며 3주 지연 발생."
│
├─ 제안 (Our Proposal)
│  "AI 모델로 고객 이탈을 30일 전에 자동 감지.
│   고객 성공팀이 우선 개입.
│   비용: $300K (1년) / 수익: $400K~600K (1년)"
│
├─ 기간 & 비용 (Timeline & Investment)
│  Timeline: 4주 MVP → 12주 정식 출시
│  Investment: $300K (개발 + 운영 1년)
│
├─ ROI & Break-even
│  Year 1: 손익분기점 달성 (6개월)
│  Year 2: $300K~500K 순이익
│  Year 3: $500K~700K 순이익 (확대)
│
├─ 위험 (Key Risks)
│  - 기술: 모델 정확도 미달 가능성 (완화: 철저한 테스트)
│  - 시장: 팀의 사용 거부 (완화: 강한 변화 관리)
│
├─ 다음 단계 (Next Steps)
│  1. 의사결정: 진행/보류/중단
│  2. 승인 시: 팀 배정 및 프로젝트 킥오프
│  3. 4주 후: MVP 검증 및 고민
│
└─ 추천 (Recommendation)
   "신뢰도 높은 프로젝트. 진행을 추천."
```

#### Section 2: Financial Impact (3년 전망)

<!-- 💬 [논쟁 지점] ROI 계산 방식은 회사마다 다르다.
학파 1: "초기 투자만 나누기" → ROI = (수익 - 초기투자) / 초기투자
학파 2: "연간 투자 포함" → ROI = (수익 - 연간투자) / 연간투자 (더 보수적)
한국 기업은 보통 학파 2를 선호. 경영진의 신뢰를 얻으려면 "보수적 계산"을 먼저 제시하세요.
-->

**돈으로 말하세요.**

```
Year-by-Year 분석:

Year 0 (Launch Year, 2024년):
- 투자:
  ├─ 개발 비용: $150K (팀 비용 포함)
  ├─ 운영 비용: $50K (인프라, 모니터링)
  └─ 소계: $200K

- 수익:
  ├─ 고객 이탈 방지: $400K (유지 고객 매출)
  ├─ 비용 절감: $100K (분석팀 시간 단축)
  └─ 소계: $500K

- 순이익: $300K (투자 회수 완료!)
- Break-even: Month 6 (6개월)

Year 1 (2025년, 정상화):
- 투자: $100K (운영만)
- 수익: $600K (확대된 고객 대상)
- 순이익: $500K
- 누적 순이익: $800K

Year 2 (2026년):
- 투자: $100K
- 수익: $700K (신 기능 추가)
- 순이익: $600K
- 누적 순이익: $1.4M

재무 메트릭:
- ROI (Year 1): 300% / 250% / 600% (연쇄 투자)
- Break-even: 6개월
- NPV (3년): $1.2M (할인율 10%)
- IRR: 145% (매우 높음)

현금흐름:
```
        Year 0    Year 1    Year 2    Year 3
투자    -$200K    -$100K    -$100K    -$100K
수익    $500K     $600K     $700K     $800K
순현금  $300K     $500K     $600K     $700K
누적    $300K     $800K    $1.4M    $2.1M
```

#### Section 3: Risk Assessment & Mitigation

<!-- 💬 [자기 검증] Risk Assessment 작성 후 꼭 확인할 사항:
1. "모든 Red 리스크에 대한 완화 계획이 있는가?" → "계획 없음"은 절대 금지
2. "최악의 시나리오를 명시했는가?" → 경영진은 "숨겨진 위험"을 가장 두려워함
3. "리스크와 완화 계획의 비용이 명시되어 있는가?" → "하면 된다"는 안 통함
한국 기업의 의사결정: 기술 위험은 무시하지만, "사람(팀) 위험"은 매우 심각하게 본다.
-->

**최악을 가정하세요.**

```
Risk Matrix (영향도 × 가능성):

                    가능성 (Likelihood)
                    낮음      중간      높음
             ┌─────────┬──────────┬──────────┐
영향도 (Impact) │       │          │          │
             │ 낮음    │ Green    │ Yellow   │ Green
             │         │          │          │
             ├─────────┼──────────┼──────────┤
             │ 중간    │ Yellow   │ Yellow   │ Red
             │         │          │          │
             ├─────────┼──────────┼──────────┤
             │ 높음    │ Red      │ Red      │ Red
             │         │          │          │
             └─────────┴──────────┴──────────┘

주요 위험:

1️⃣ 기술적 위험 (Medium Impact, Low Likelihood) = Yellow

문제: 모델 정확도가 85% 목표 미달 (75%만 달성)
영향: ROI 30% 감소 ($100K 손실), 프로젝트 6개월 연기
가능성: 10% (이전 성공 사례 많음)

완화 전략:
- Step 1: 엄격한 데이터 품질 검증
- Step 2: 독립적 검증팀의 성능 확인
- Step 3: Pilot 프로젝트 (작은 규모 먼저)
- Step 4: 정확도 미달 시 증분 배포 (느린 롤아웃)

2️⃣ 시장 위험 (High Impact, Medium Likelihood) = Red

문제: 팀이 AI 알림을 신뢰하지 않거나 사용하지 않음
영향: 수익 0 (실제 이탈 방지 효과 없음)
가능성: 30% (변화 저항 흔함)

완화 전략:
- Step 1: 강한 변화 관리 (팀 교육, 공동 개발)
- Step 2: 초기 성공 가시화 (파일럿에서 성과 입증)
- Step 3: 인센티브 구조 (팀의 이탈 방지 목표와 연결)
- Step 4: 선택적 도입 (강제 아님, 선택권 제공)

3️⃣ 운영 위험 (Medium Impact, Medium Likelihood) = Yellow

문제: 데이터 품질 저하, 규정 위반 (개인정보보호법)
영향: 프로젝트 중단, 규제 과태금
가능성: 20% (철저한 준비로 방지 가능)

완화 전략:
- Step 1: Compliance 팀 참여 (설계 단계부터)
- Step 2: 정기 감시 (월간 공정성 테스트)
- Step 3: 고객 동의 확보 (투명한 커뮤니케이션)

최악의 시나리오 (Worst Case):
정확도 60%, 팀 사용 안 함, 규제 경고
→ 프로젝트 중단, $200K 손실
→ 가능성: 5%
→ 시나리오 계획: 있음 (비상 예산 100K 보유)
```

#### Section 4: Competitive Landscape

**우리가 리더가 되어야 하는 이유**

```
경쟁 현황:

회사 A (Salesforce):
- Einstein AI (고객 이탈 예측)
- 우리 고객도 사용 가능
- 월 $100~500 비용 (규모별)

우리의 입장:
- 경쟁사 솔루션은 일반적 (모든 산업 대상)
- 우리는 우리 산업 특화 (높은 정확도)
- 우리가 구축 시: 100% 우리 것 (라이선스 비용 0)

우리의 차별점:

1. 비용 효율
   - 외부 솔루션: 연 $300K (Salesforce)
   - 우리 솔루션: 연 $200K (개발/운영)
   - 절감: 연 $100K

2. 맞춤화
   - 우리 비즈니스 모델에 최적화
   - 빠른 반응 (외부는 6개월)

3. 전략적 자산
   - 우리의 AI 모델 = 경쟁 자산
   - 향후 다른 제품으로 확대 가능 (플랫폼화)

전략:
- 지금 구축 (6개월 선행)
- 내부 최적화 완료 (Year 1)
- 외부 시장 진출 (Year 2, "우리의 AI 솔루션 판매")

경쟁사가 따라오기: 1년
우리의 이득: 연 $300K~500K (초기 선발 이점)

결론:
"우리가 지금 움직이면, 경쟁사는 따라올 수 없다."
```

#### Section 5: Implementation & Timeline

**실행 가능한가?**

```
고수준 로드맵:

Month 1 (4주): MVP 구축
├─ Week 1~2: 데이터 준비, 모델 개발
├─ Week 3: 테스트
├─ Week 4: 내부 검증 (CEO 직접 테스트?)
└─ Milestone: 정확도 75% 이상 달성

Month 2 (4주): 성능 최적화
├─ 정확도 85% 목표 달성
├─ 레이턴시 최적화
└─ Milestone: 정확도 85%, 프로덕션 준비

Month 3 (4주): 베타 배포 & 검증
├─ 10% 트래픽 (내부 팀)
├─ 실제 이탈 방지 효과 검증
└─ Milestone: 팀 만족도 > 7/10

필요 리소스:
- Data Scientist: 2명 (풀타임)
- ML Engineer: 1명 (풀타임)
- PM: 1명 (풀타임)
- Data Engineer: 1명 (50%)
- 합계: 4.5 FTE × $150K/년 = $675K

아, 이건 Year 0에만 필요 (구축 비용).
Year 1부터는 운영만 ($200K).

예산:
- 인력: $675K (Year 0), $300K (Year 1+)
- 인프라/도구: $50K (연)
- 총: Year 0 $725K

하지만 기대 수익: $500K (Year 0)
= 초기 투자 $225K 추가 필요

이건 합리적인가?
Yes.
- 초기 추가 투자: $225K
- 수익: $500K (Year 0), $600K (Year 1+)
- Break-even: 3개월
```

#### Section 6: Decision & Recommendation

**이제 의사결정하세요.**

```
의사결정 아이템:

□ 이 AI 프로젝트를 진행할 것인가?
  Yes / No / Conditional (조건부)

조건부라면?
- "정확도 85% 달성해야만 진행"
- "1개월 안에 MVP 검증 완료 필수"

Governance & Approvals:

의사결정자: CEO + CFO
정보 제공자: CTO, PM
검증자: 외부 컨설턴트? (선택사항)

최종 추천:

"매우 높은 ROI, 낮은 위험.
 지금 진행을 강하게 추천합니다.

 근거:
 1. 재무: Year 0에 300% ROI
 2. 위험: 관리 가능, 완화책 준비
 3. 속도: 4주 MVP, 12주 정식
 4. 전략: 경쟁 우위 확보 (6개월 선행)
 5. 확장: Year 2부터 플랫폼화 가능

 의사결정: 진행"
```

### # 경영진 스타일별 맞춤형 메시지

```
CEO (Revenue 중심):
"이 AI로 연 $400K 매출 증가.
 고객 이탈을 30% 줄입니다.
 경쟁사는 아직 못 하는 것.
 지금 진행하면, 6개월 선행 확보."

CFO (Cost & Risk 중심):
"$300K 투자 → $500K 수익 (Year 0).
 6개월 내 손익분기점.
 3년 누적 순이익 $1.4M.
 위험은 관리 가능 (완화책 준비).
 Go."

CTO (Technical 중심):
"85% 정확도 달성 가능한 모델.
 우리 데이터로 최적화 (80% 아님).
 Year 1부터 플랫폼 확대 가능.
 개발팀 역량 증강 (AI 경험)."

Board (Strategy 중심):
"시장 리더십 확보.
 첫 AI 제품 (향후 확장 가능).
 경쟁 진입 장벽 높음 (선행).
 $1.4M NPV (3년)."
```



### # 🇰🇷 한국 기업 경영진 브리핑 특화

```
한국 기업 임원 보고 시 고려사항:

1. **보고 문화**:
   - 한국 대기업: "두괄식" (결론 먼저) + 숫자 증거
   - 스타트업 C-Level: 글로벌 벤치마크 + 한국 시장 데이터 병행
   - "왜 지금 해야 하는가?" → 경쟁사 동향이 강력한 근거

2. **한국 시장 데이터 소스**:
   - 시장 규모: 한국IDC, 한국소프트웨어산업협회(KOSA)
   - 경쟁사: DART 공시, 잡플래닛 채용동향, 앱애니 순위
   - 트렌드: 과학기술정보통신부 AI 현황 보고서

3. **의사결정 프로세스**:
   - 한국 대기업: 품의서 → 팀장 → 본부장 → 임원 결재
   - 각 레벨별 관심사가 다름:
     * 팀장: 실행 가능성, 리소스
     * 본부장: 부서 간 영향, KPI
     * 임원: ROI, 시장 포지션, 리스크
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 핵심 메시지 선정 어려움 | "경영진이 이 미팅 후 기억할 1가지"를 정하세요 |
| 2단계 | 데이터가 너무 많음 | "So what?"을 통과하는 데이터만 포함. 나머지는 부록 |
| 3단계 | 리스크 전달이 민감 | 정량적으로 전달하세요. "위험하다" → "현재 X%, 목표 대비 Y% 미달" |
| 5단계 | 의사결정 요청이 모호 | "A안 vs B안, 추천은 A안, 이유는 X" 형식으로 명확히 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 데이터에서 자동으로 경영진 브리핑을 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
주간/월간 경영진 보고는 반복 작업입니다. 메트릭 데이터를 입력하면 자동으로 브리핑 문서가 생성됩니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Executive Briefing 자동 생성 도구 (300+ 라인)

```python
#!/usr/bin/env python3
"""
경영진 브리핑 자동 생성 도구 (PHASE 2)
AI PRD를 경영진 수준의 요약본으로 변환

입력: 상세 AI PRD (Section 1-9)
출력: 경영진 브리핑 (Executive Summary + Financial + Risk + Strategy)
"""

import anthropic
import json
from datetime import datetime, timedelta
from typing import Optional, Dict
from dataclasses import dataclass


@dataclass
class ExecutiveContext:
    """경영진 의사결정 컨텍스트"""
    product_name: str
    business_problem: str  # 해결하려는 문제
    expected_revenue_impact: int  # 연 절감/증가액 (단위: $)
    investment_required: int  # 필요 투자액 (단위: $)
    timeline_weeks: int  # 구현 기간 (주)
    key_risks: list[str]  # 주요 위험
    competitive_advantage: Optional[str] = None
    market_window: Optional[str] = None  # 시장 기회 윈도우


def generate_executive_briefing(
    ai_prd: Dict,
    context: ExecutiveContext
) -> Dict:
    """
    AI PRD에서 경영진 브리핑 생성

    Args:
        ai_prd: 완전한 AI PRD JSON (prd-for-ai-feature.md에서 생성)
        context: 경영진 의사결정 컨텍스트

    Returns:
        경영진 브리핑 (1쪽 요약 + 재무 + 위험 + 전략)

    생성되는 섹션:
    1. Executive Summary (1쪽, 5분)
    2. Financial Impact (3년 전망)
    3. Risk Assessment & Mitigation
    4. Competitive Landscape
    5. Decision & Recommendation
    """

    client = anthropic.Anthropic()

    # ROI 계산 (자동)
    expected_roi_year0 = ((context.expected_revenue_impact - context.investment_required)
                          / context.investment_required * 100)
    breakeven_months = (context.investment_required
                        / (context.expected_revenue_impact / 12))

    prompt = f"""당신은 경영진을 위한 전략 브리핑 전문가입니다.
복잡한 AI PRD를 경영진(CEO, CFO, CTO)이 5분 안에 이해할 수 있도록
명확하고 설득력 있게 요약하세요.

**AI PRD 요약:**
- 제품: {context.product_name}
- 문제: {context.business_problem}
- 예상 효과: 연 ${context.expected_revenue_impact:,}
- 필요 투자: ${context.investment_required:,}
- 기간: {context.timeline_weeks}주
- 주요 위험: {', '.join(context.key_risks)}
- 경쟁 우위: {context.competitive_advantage or 'TBD'}
- 시장 윈도우: {context.market_window or 'N/A'}

**자동 계산:**
- Year 0 ROI: {expected_roi_year0:.0f}%
- Break-even: {breakeven_months:.1f}개월

**생성할 내용:**

1. **Executive Summary** (1쪽, 5분)
   - 상황 (The Situation)
   - 제안 (Our Proposal)
   - 기간 & 투자
   - ROI & Break-even
   - 위험 (3개 주요)
   - 다음 단계
   - 추천 (Go/No-Go)

2. **Financial Impact** (3년 예측)
   - Year 0, 1, 2 별 투자/수익/순이익
   - 누적 현금흐름
   - Break-even 시점 명시
   - NPV, IRR 계산

3. **Risk Assessment** (위험 매트릭스)
   - 기술적 위험
   - 시장/조직 위험
   - 운영 위험
   - 각 위험별 완화책
   - 최악의 시나리오

4. **Competitive Landscape**
   - 경쟁사 벤치마크
   - 우리의 차별점
   - 시장 우위 기간
   - 전략적 의미

5. **Decision & Recommendation**
   - 의사결정 아이템
   - 최종 추천
   - 필요 승인
   - 조건부 항목

**JSON 응답 형식:**

{{
  "executive_summary": {{
    "situation": "현재 상황 (1-2문장)",
    "proposal": "AI 솔루션 (1-2문장)",
    "business_value": "비즈니스 가치 (1-2문장)",
    "timeline": "{context.timeline_weeks}주",
    "investment": "${context.investment_required:,}",
    "expected_roi": "{expected_roi_year0:.0f}%",
    "breakeven": "{breakeven_months:.1f}개월",
    "key_risks": [
      {{"risk": "위험명", "impact": "영향도", "mitigation": "대응책"}}
    ],
    "recommendation": "Go / No-Go / Conditional"
  }},

  "financial_projection": {{
    "year_0": {{
      "investment": ${context.investment_required:,},
      "revenue": "${context.expected_revenue_impact:,}",
      "net_profit": "수익 - 투자",
      "breakeven_month": "{breakeven_months:.0f}"
    }},
    "year_1": {{"investment": ..., "revenue": ..., "net_profit": ...}},
    "year_2": {{"investment": ..., "revenue": ..., "net_profit": ...}},
    "three_year_summary": {{
      "total_investment": "3년 누적",
      "total_revenue": "3년 누적",
      "net_profit": "3년 순이익",
      "roi_percentage": "누적 ROI %",
      "npv": "NPV @ 10% discount",
      "irr": "내부 수익률"
    }}
  }},

  "risk_assessment": {{
    "risk_matrix": [
      {{
        "risk": "위험명",
        "category": "기술/시장/운영",
        "impact": "High/Medium/Low",
        "likelihood": "High/Medium/Low",
        "severity": "Red/Yellow/Green",
        "mitigation": ["대응책1", "대응책2"]
      }}
    ],
    "worst_case_scenario": {{
      "description": "최악의 경우 설명",
      "financial_impact": "손실액",
      "probability": "가능성 %",
      "contingency_plan": "비상 계획"
    }}
  }},

  "competitive_landscape": {{
    "competitors": [
      {{
        "company": "경쟁사명",
        "product": "제품명",
        "approach": "전략",
        "strengths": ["강점1"],
        "weaknesses": ["약점1"]
      }}
    ],
    "our_differentiation": [
      {{"dimension": "비용/속도/정확도", "advantage": "우리의 우위"}}
    ],
    "time_to_market": "경쟁사 따라오기까지 소요 시간",
    "strategic_implication": "장기 전략적 의미"
  }},

  "decision": {{
    "recommendation": "추천사항",
    "decision_items": [
      {{"item": "의사결정 아이템", "required_approval": "누가 승인?"}}
    ],
    "next_steps": [
      {{"step": "다음 단계", "owner": "담당자", "timeline": "시간"}}
    ],
    "success_criteria": [
      "성공 기준1 (측정 가능)",
      "성공 기준2"
    ]
  }}
}}

각 섹션은 경영진 수준의 명확성과 설득력을 가져야 합니다.
전문 용어는 최소화하고, 숫자와 비즈니스 임팩트로 말하세요.
"""

    message = client.messages.create(
        model="claude-opus-4-6",
        max_tokens=4000,
        messages=[{"role": "user", "content": prompt}]
    )

    try:
        import re
        json_match = re.search(r'\{.*\}', message.content[0].text, re.DOTALL)
        if json_match:
            briefing = json.loads(json_match.group())
        else:
            briefing = {"raw": message.content[0].text}
    except json.JSONDecodeError:
        briefing = {"raw": message.content[0].text}

    return {
        "product_name": context.product_name,
        "generated_at": datetime.now().isoformat(),
        "executive_briefing": briefing,
        "tokens_used": message.usage.output_tokens
    }


def generate_briefing_presentation(briefing: Dict) -> str:
    """경영진 브리핑을 프리젠테이션 포맷으로 생성"""

    output = []

    # 타이틀
    output.append("=" * 80)
    output.append("EXECUTIVE BRIEFING")
    output.append("=" * 80)
    output.append("")

    # 요약
    summary = briefing.get("executive_summary", {})
    output.append("[PAGE 1: EXECUTIVE SUMMARY - 5 MINUTES]")
    output.append("-" * 80)
    output.append(f"Situation:\n{summary.get('situation', 'N/A')}\n")
    output.append(f"Proposal:\n{summary.get('proposal', 'N/A')}\n")
    output.append(f"Business Value:\n{summary.get('business_value', 'N/A')}\n")
    output.append(f"Timeline: {summary.get('timeline', 'N/A')}")
    output.append(f"Investment: {summary.get('investment', 'N/A')}")
    output.append(f"Expected ROI: {summary.get('expected_roi', 'N/A')}")
    output.append(f"Break-even: {summary.get('breakeven', 'N/A')}")
    output.append(f"\nRecommendation: {summary.get('recommendation', 'TBD')}")
    output.append("")

    # 재무
    output.append("[PAGE 2: FINANCIAL IMPACT - 3 YEARS]")
    output.append("-" * 80)
    financial = briefing.get("financial_projection", {})
    for year in ["year_0", "year_1", "year_2"]:
        y = year.replace("_", " ").title()
        yr_data = financial.get(year, {})
        output.append(f"{y}:")
        output.append(f"  Investment: {yr_data.get('investment', 'N/A')}")
        output.append(f"  Revenue: {yr_data.get('revenue', 'N/A')}")
        output.append(f"  Net Profit: {yr_data.get('net_profit', 'N/A')}")
        output.append("")

    summary_data = financial.get("three_year_summary", {})
    output.append("3-Year Summary:")
    output.append(f"  Total Investment: {summary_data.get('total_investment', 'N/A')}")
    output.append(f"  Total Revenue: {summary_data.get('total_revenue', 'N/A')}")
    output.append(f"  Net Profit: {summary_data.get('net_profit', 'N/A')}")
    output.append(f"  ROI: {summary_data.get('roi_percentage', 'N/A')}")
    output.append(f"  NPV: {summary_data.get('npv', 'N/A')}")
    output.append(f"  IRR: {summary_data.get('irr', 'N/A')}")
    output.append("")

    # 위험
    output.append("[PAGE 3: RISK ASSESSMENT]")
    output.append("-" * 80)
    risks = briefing.get("risk_assessment", {})
    for risk in risks.get("risk_matrix", []):
        output.append(f"Risk: {risk.get('risk', 'N/A')}")
        output.append(f"  Severity: {risk.get('severity', 'N/A')}")
        output.append(f"  Mitigation: {', '.join(risk.get('mitigation', []))}")
        output.append("")

    worst = risks.get("worst_case_scenario", {})
    output.append("Worst Case Scenario:")
    output.append(f"  {worst.get('description', 'N/A')}")
    output.append(f"  Probability: {worst.get('probability', 'N/A')}")
    output.append("")

    # 경쟁
    output.append("[PAGE 4: COMPETITIVE LANDSCAPE]")
    output.append("-" * 80)
    comp = briefing.get("competitive_landscape", {})
    output.append("Our Differentiation:")
    for diff in comp.get("our_differentiation", []):
        output.append(f"  • {diff.get('dimension')}: {diff.get('advantage')}")
    output.append(f"\nTime to Market: {comp.get('time_to_market', 'N/A')}")
    output.append("")

    # 의사결정
    output.append("[PAGE 5: DECISION & RECOMMENDATION]")
    output.append("-" * 80)
    decision = briefing.get("decision", {})
    output.append(f"RECOMMENDATION: {decision.get('recommendation', 'TBD')}")
    output.append("\nNext Steps:")
    for step in decision.get("next_steps", []):
        output.append(f"  • {step.get('step')} ({step.get('owner')}, {step.get('timeline')})")
    output.append("")

    return "\n".join(output)


if __name__ == "__main__":
    # 예제: 고객 이탈 AI의 경영진 브리핑 생성

    context = ExecutiveContext(
        product_name="고객 이탈 예측 AI",
        business_problem="연 $2M 고객 이탈 손실, 반응 시간 3주",
        expected_revenue_impact=500000,  # $500K 절감
        investment_required=300000,  # $300K 투자
        timeline_weeks=12,  # 3개월
        key_risks=[
            "모델 정확도 미달 (85% 목표)",
            "팀의 AI 신뢰 부족",
            "규정 준수 위험"
        ],
        competitive_advantage="우리 데이터 특화, 빠른 구현",
        market_window="경쟁사 진입 전 6개월"
    )

    # 더미 PRD (실제는 prd-for-ai-feature.md에서 생성)
    dummy_prd = {
        "product_name": context.product_name,
        "sections": {"business_case": {}}
    }

    # 브리핑 생성
    result = generate_executive_briefing(dummy_prd, context)

    print(json.dumps(result, ensure_ascii=False, indent=2))

    # 프리젠테이션 포맷 생성
    if "executive_briefing" in result:
        presentation = generate_briefing_presentation(
            result["executive_briefing"]
        )
        print("\n" + "=" * 80)
        print(presentation)

        # 파일 저장
        with open("executive_briefing.txt", "w", encoding="utf-8") as f:
            f.write(presentation)

    print("\n✅ 경영진 브리핑 생성 완료!")
    print("파일: executive_briefing.txt")
```

### Claude Code CLI 사용법

```bash
# 경영진 브리핑 생성
claude run executive-briefing-generator.py \
  --prd ai_prd_output.json \
  --expected-revenue 500000 \
  --investment 300000 \
  --timeline 12 \
  --output briefing.json

# 프리젠테이션 생성
claude run briefing-presenter.py \
  --input briefing.json \
  --output briefing.md

# 파워포인트 생성 (선택)
claude run briefing-to-powerpoint.py \
  --input briefing.json \
  --output briefing.pptx
```

---

## 📊 실행 결과 예시

### Generated Executive Briefing

```
═══════════════════════════════════════════════════════════════════════════
EXECUTIVE BRIEFING: 고객 이탈 예측 AI
═══════════════════════════════════════════════════════════════════════════

[PAGE 1: EXECUTIVE SUMMARY - 5분]
───────────────────────────────────────────────────────────────────────────

**상황 (Situation)**
우리는 매년 $2M의 고객 이탈로 손실을 입고 있습니다.
현재 분석팀이 수동으로 대응하고 있으나, 반응 시간이 3주로 길어서
이미 이탈한 고객을 붙잡으려 하고 있습니다.

**제안 (Proposal)**
AI 모델을 도입하여 고객 이탈을 30일 전에 자동 감지합니다.
고객 성공팀이 사전에 개입하여 이탈을 방지합니다.

**비즈니스 가치**
─────────────────────────────────────────────────────────────────
투자: $300K (개발 + 운영 1년)
기대 수익: $500K (고객 유지)
Year 0 ROI: 67% (Year 0 만으로도 이미 수익!)
Break-even: 6개월
3년 누적 순이익: $1.4M

**위험 및 대응**
─────────────────────────────────────────────────────────────────
위험 1: 모델 정확도 미달
  → 대응: 엄격한 테스트, 점진적 배포

위험 2: 팀의 신뢰 부족 (AI 알림을 안 봄)
  → 대응: 강한 변화 관리, 초기 성공 가시화

위험 3: 규정 위반 (개인정보보호법)
  → 대응: Compliance 팀 참여, 정기 감시

**다음 단계**
1. 의사결정: 진행 여부 (2024년 2월 말까지)
2. 승인 시: 팀 배정 및 프로젝트 킥오프
3. 4주 후: MVP 검증 및 고민
4. 12주 후: 정식 출시

**최종 추천**
✅ GO

근거:
✓ 매우 높은 ROI (Year 0에 67%, Year 3에 300%+)
✓ 관리 가능한 위험 (완화책 준비)
✓ 빠른 구현 (4주 MVP)
✓ 전략적 우위 (경쟁사 대비 6개월 선행)
✓ 확장 가능성 (Year 2부터 다른 제품에 적용)

───────────────────────────────────────────────────────────────────────────

[PAGE 2: 3년 재무 전망]
───────────────────────────────────────────────────────────────────────────

Year 0 (2024 - 초기 구축):
  투자: $300K
  수익: $500K (절감된 이탈 손실)
  순이익: $200K
  누적: $200K

Year 1 (2025 - 정상화):
  투자: $100K (운영만)
  수익: $600K (더 많은 고객, 신 기능)
  순이익: $500K
  누적: $700K

Year 2 (2026 - 확대):
  투자: $100K
  수익: $700K (추가 기능, 플랫폼화)
  순이익: $600K
  누적: $1.3M

3년 요약:
  총 투자: $500K
  총 수익: $1,800K
  순이익: $1.3M
  누적 ROI: 260%
  NPV (10% 할인): $1.2M
  내부 수익률 (IRR): 145%

현금흐름:
        2024      2025      2026      2027
        ────      ────      ────      ────
투자    -$300K    -$100K    -$100K    -$100K
수익    $500K     $600K     $700K     $800K
─────────────────────────────────────────
순현금  $200K     $500K     $600K     $700K
누적    $200K     $700K    $1.3M     $2.0M

───────────────────────────────────────────────────────────────────────────

[PAGE 3: 위험 평가 및 대응]
───────────────────────────────────────────────────────────────────────────

위험 매트릭스:

┌─────────────────────────────────────────────────────┐
│ 위험                    │ 심각도 │ 가능성 │ 심각성 │
├─────────────────────────────────────────────────────┤
│ 1. 정확도 미달 (75%)    │ 중간  │ 낮    │ ⚠️  │
│ 2. 팀 신뢰 부족         │ 높음  │ 중간  │ 🔴  │
│ 3. 규정 위반            │ 중간  │ 낮    │ ⚠️  │
│ 4. 데이터 품질 악화     │ 낮음  │ 낮    │ ✅  │
└─────────────────────────────────────────────────────┘

위험 1️⃣: 모델 정확도 (85% 목표 vs 75% 실제)
  영향: ROI 30% 감소 ($100K 손실), 6개월 연기
  가능성: 10%
  대응책:
    • 엄격한 데이터 검증
    • 독립적 테스트팀의 성능 검증
    • Pilot로 작은 규모부터 시작
    • 실패 시 아치텍처 변경 계획 준비

위험 2️⃣: 팀의 AI 불신 (알림 무시)
  영향: 수익 0 (실제 이탈 방지 효과 없음)
  가능성: 30%
  대응책:
    • 강한 변화 관리 (팀 교육, 공동 개발)
    • 파일럿에서 성과 입증 (초기 성공 사례)
    • 팀 인센티브 (이탈 방지와 보상 연결)
    • 선택적 도입 (강제 아님)

위험 3️⃣: 규정 준수 (GDPR, 개인정보보호법)
  영향: 프로젝트 중단, 규제 과태금
  가능성: 15%
  대응책:
    • Compliance 팀 조기 참여
    • 설계부터 규정 준수 체크
    • 월간 공정성 감시 (그룹별 성능 검증)
    • 설명 가능성 보장 (SHAP 값 제공)

최악의 시나리오 (Worst Case):
  상황: 정확도 60%, 팀 사용 안 함, 규제 경고
  재무 영향: $200K 손실
  확률: 5%
  비상 계획: 프로젝트 중단, $100K 비상 예산 보유

───────────────────────────────────────────────────────────────────────────

[PAGE 4: 경쟁 환경]
───────────────────────────────────────────────────────────────────────────

경쟁 현황:

Salesforce Einstein:
  • 일반적인 고객 이탈 예측 (모든 산업)
  • 월 $100~500 (규모별)
  • 우리 고객도 사용 가능

우리의 차별점:
  ✓ 비용 효율: Salesforce $300K vs 우리 $200K/년 (33% 저렴)
  ✓ 맞춤화: 우리 비즈니스 모델에 최적화 (85% 정확도)
  ✓ 속도: 6개월 선행 (경쟁사는 아직 못 함)
  ✓ 전략 자산: 우리 소유 (라이선스 비용 X, 향후 재사용 가능)

전략적 의미:

현재           6개월 후          12개월 후
우리 선점      경쟁사 따라옴     우리 = 업계 리더

초기 선발 이득: 연 $300K~500K 추가 수익
기간: 6개월 (경쟁사가 따라오기까지)

결론:
"지금 움직이면, 경쟁사는 따라올 수 없다."

───────────────────────────────────────────────────────────────────────────

[PAGE 5: 의사결정]
───────────────────────────────────────────────────────────────────────────

최종 추천:
✅ GO (강력 추천)

근거:
  1. 재무: Year 0 ROI 67%, 3년 $1.4M 순이익
  2. 위험: 관리 가능, 완화책 준비
  3. 속도: 12주 정식 출시 (경쟁사 대비 6개월 선행)
  4. 전략: 경쟁 우위 확보, 플랫폼화 가능 (Year 2)
  5. 조직: 팀 역량 강화 (AI 경험)

의사결정 아이템:

[ ] 이 프로젝트를 진행할 것인가?
   선택지: Yes / No / Conditional

조건부라면?
   • "정확도 85% 달성 필수"
   • "4주 내 MVP 검증 완료"
   • "팀 만족도 > 7/10"

다음 단계:

1. 의사결정 (2024년 2월 말까지)
   담당자: CEO + CFO
   산출물: Go/No-Go 결정

2. 팀 배정 (승인 후 1주)
   담당자: CTO
   팀: DS 2명, ML Eng 1명, Data Eng 1명, PM 1명

3. 프로젝트 킥오프 (2024년 3월)
   담당자: PM
   산출물: 상세 로드맵

4. MVP 검증 (4주 후, 2024년 4월)
   담당자: PM + Data Scientist
   산출물: 정확도 보고서, 고민 사항

5. 정식 출시 (12주 후, 2024년 6월)
   담당자: ML Eng + PM
   산출물: 프로덕션 시스템

성공 기준 (정량화):
  ✓ 정확도: 85% 이상
  ✓ 대응 시간: 24시간 (3주 → 1일)
  ✓ 이탈 방지율: 30% 개선
  ✓ ROI: Year 0에 $200K+
  ✓ 팀 만족도: > 7/10 (사용성)

═══════════════════════════════════════════════════════════════════════════
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 브리핑에 'So What? (그래서 뭘 해야 하나?)'가 명확한지 확인하세요
2. **[논쟁 지점]** 경영진 브리핑의 '적절한 길이'는 조직마다 다릅니다 — 1페이지 vs 5페이지
3. **[자기 검증]** 브리핑의 핵심 수치 1개를 원본 데이터에서 확인하세요

---

## 🔗 다음 단계

1. **의사결정 회의** → CEO + CFO와 함께 검토 (30분)
2. **승인** → Go/No-Go 결정
3. **팀 배정** → 프로젝트 시작
4. **4주 후** → MVP 검증 (의사결정 2차)
5. **12주 후** → 정식 출시 (의사결정 3차)

---

## 💡 Tips for Executive Persuasion

```
1. 숫자로 말하세요
   ❌ "AI는 우리를 경쟁 우위에 놓을 거예요"
   ✅ "AI로 연 $400K 절감, 3년 $1.4M 순이익"

2. 위험을 인정하세요
   ❌ "완벽할 거예요, 문제 없어요"
   ✅ "3가지 위험이 있지만, 모두 완화책을 준비했습니다"

3. 경쟁을 강조하세요
   ❌ "좋은 프로젝트예요"
   ✅ "지금 안 하면 경쟁사가 6개월 선행합니다"

4. 의사결정을 쉽게 하세요
   ❌ "이 기술이 있고 저 기술이 있고..."
   ✅ "Go/No-Go? Go를 강력 추천합니다."

5. 다음 단계를 명확히 하세요
   ❌ "진행되면 뭔가 할 것 같아요"
   ✅ "4주 후 MVP 검증, 12주 후 정식 출시. 명확합니다."
```
