# 🎯 이해관계자 정렬 (Stakeholder Alignment)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 45분+ (Build)
> 워크플로우: → `press-release.md`, `cross-team-handoff.md`

---

## 🎯 이 프롬프트가 해결하는 문제

AI 기능을 개발했지만 경영진, 엔지니어, 디자이너 각각이 다른 관심사를 가지고 있다. **"왜 이 기능을 만드는가?", "성공의 정의는?", "언제까지 진행할 건가?"** 같은 질문에 팀마다 다른 답을 한다. **크로스팀 합의 없이는 실행이 흐트러진다.** 이해관계자들의 의사결정을 정렬하고, 모두가 같은 목표를 향해 움직이게 해야 한다.

---

## 📥 이전 프롬프트에서 받는 입력

> `feature-prioritization.md`에서 결정된 우선순위를 이해관계자에게 공유하고 합의를 도출할 때 연결됩니다.

이전 프롬프트 결과에서 **우선순위 목록, RICE 점수, 트레이드오프 요약**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 이해관계자별 핵심 커뮤니케이션 문서를 작성할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI PM 커뮤니케이션 전문가다.

{AI 기능명}에 대해 다음 문서를 만드세요:

1. Executive Summary (경영진용, 3분)
   - 비즈니스 기회와 ROI
   - 성공의 정의 (1-2 KPI)
   - 위험 요소와 완화 방안

2. Engineering Alignment (엔지니어용, 10분)
   - 기술 요구사항과 아키텍처 결정
   - "현재 vs 미래 상태"
   - 의존성과 타임라인

3. Design/Product Review (크로스팀용, 20분)
   - 사용자 여정 (User Journey)
   - 성공/실패 시나리오
   - 피드백 루프

4. Decision Log (의사결정 기록)
   - "우리는 왜 이 방식을 선택했나?"
   - 검토한 대안은?
   - 언제 재검토할 건가?

각 문서별로 명확하고 설득력 있게 작성.
```

💡 **Quick Tips:**
- 경영진은 "비즈니스 임팩트", 엔지니어는 "기술 위험", 디자이너는 "사용자 경험" → 같은 내용도 다르게 표현
- "Decision Log"를 남기면 3개월 후 "왜 이렇게 했지?" 하는 재논쟁 방지
- 월 1회 동기화 미팅: 진행 상황 + 우려 사항 공유


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 이해관계자가 10명 이상 | RACI 매트릭스로 핵심 이해관계자를 먼저 분류하세요 |
| 원격/분산 팀 | 비동기 업데이트 문서가 더 중요합니다. 이 프롬프트로 문서화하세요 |
| 갈등 상황 | 감정적 이슈는 1:1 미팅으로, 이 프롬프트는 사실 기반 정렬에 사용 |
| 새 이해관계자가 합류 | "프로젝트 온보딩 문서"를 이 프롬프트로 생성하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 경영진, 엔지니어, 디자이너 각각에게 맞는 커뮤니케이션을 하고 싶은 분입니다.
"같은 프로젝트인데 왜 팀마다 다르게 이해하지?"를 해결하고 싶다면 이걸 써보세요.

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


### 역할 설정

당신은 **AI 제품의 크로스팀 조율자(Alignment Orchestrator)**이다. 당신의 역할:

1. **이해관계자 맵핑**: 누가 이 결정에 영향을 받는가? (경영진, 엔지니어, 디자이너, 고객성공팀 등)
2. **관심사 이해**: 각 이해관계자의 우려 사항과 목표가 뭔가?
3. **공통 언어 찾기**: 비즈니스, 기술, 사용자 관점의 공통 목표 도출
4. **의사결정 기록**: 왜 이 방식을 선택했는지 명확히 남기기

<!-- 💬 [전문가의 눈] 이해관계자 정렬이 안 되면?
     결과: 같은 프로젝트인데 각자 다른 방향으로 작업
     비용: 개발 지연, 재작업, 갈등
     예시: CEO는 "Q3 출시" vs 엔지니어는 "품질 먼저" → 전쟁 상태

     해결: 초기에 "공통 목표"를 명확히 → 큰 지연 방지 -->

<!-- 💬 이해관계자 정렬이 왜 중요한가?
이해관계자 정렬 없음:
- 경영진: "Q3 중 출시해야 한다" (비즈니스 압박)
- 엔지니어: "모델 성능이 80%인데 출시할 수 없다" (품질 우려)
- 디자이너: "신뢰도 표시 UI가 없으면 사용자가 혼란스러울 것" (UX 우려)

→ 결과: 각자 다른 방향으로 일함, 느린 진행, 갈등

이해관계자 정렬 있음:
- "Q3에 Beta(80% 정확도) 출시, Q4에 신뢰도 UI 추가" 합의
- 모두가 같은 방향으로 움직임, 빠른 실행
-->

### 목표

최종 아웃풋:
- **이해관계자별 알림장** (경영진/엔지니어/디자인/고객성공팀)
- **공동 의사결정 문서** (모두가 합의한 목표, 타임라인, 성공 조건)
- **위험 관리 계획** (우려 사항과 해결책)
- **의사결정 로그** (재검토 주기, 변경 이력)

### Reasoning Strategy

<!-- 💬 이해관계자를 어떻게 분류하고 관리할 것인가?

Stakeholder Matrix (영향도 x 관심도):

높은 영향도 + 높은 관심도 = MANAGE
- 경영진 (ROI, 출시 일정)
- 주요 고객 (사용성)
→ 주간 미팅, 상세 보고

높은 영향도 + 낮은 관심도 = INFORM
- 법무팀 (AI 윤리/규정)
- 보안팀 (데이터 보안)
→ 체크인 미팅, 요약 리포트

낮은 영향도 + 높은 관심도 = CONSULT
- 초기 사용자 (피드백)
- 마케팅팀 (포지셔닝)
→ 월간 피드백 세션

낮은 영향도 + 낮은 관심도 = MONITOR
- 다른 팀들
→ 공개 뉴스레터
-->

**Step 1: 이해관계자 맵 만들기**

```
🗺️ Stakeholder Map for "AI 요약 기능"

┌─────────────────────────────────┐
│ 높은 영향도, 높은 관심도         │ ← MANAGE (주간)
│ - 경영진 (CEO, VP Product)      │
│ - 엔지니어 리드                  │
│ - 주요 고객 (Enterprise)        │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 높은 영향도, 낮은 관심도         │ ← INFORM (월간)
│ - Legal (AI 규정, AI기본법)      │
│ - Security (데이터 보안, PIPA)   │
│ - Finance (비용, ROI)           │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 낮은 영향도, 높은 관심도         │ ← CONSULT (월간)
│ - 디자이너 (UX)                 │
│ - 고객성공팀 (온보딩)            │
│ - 마케팅 (포지셔닝)              │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│ 낮은 영향도, 낮은 관심도         │ ← MONITOR (분기)
│ - 다른 팀들                      │
└─────────────────────────────────┘
```

<!-- 💬 [논쟁 지점] "높은 영향도, 낮은 관심도" 그룹 관리
     위험: 이 그룹이 가장 위험 (sudden objection)
     예시: Legal 팀이 프로젝트 중반에 "AI기본법 문제" 제시
     방지: 초기 1회 미팅 + 월간 brief로 "이미 알고 있음" 상태 유지
     한국: "결재" 체계상 법무/보안 동의 없이 출시 불가 -->

**Step 2: 각 이해관계자의 "핫버튼" 파악**

```
구성원별 관심사 (WIFM: What's In For Me)

🏢 경영진
- 핫버튼: "이게 비즈니스에 도움이 되나?"
- 답변할 것:
  • Revenue Impact: "기존 사용자 리텐션 10% 개선"
  • Market Positioning: "경쟁사 대비 차별점"
  • Timeline: "언제 ROI 달성?"
  • Risk: "실패 시 손실은?"

👨‍💻 엔지니어
- 핫버튼: "기술적으로 실행 가능한가?"
- 답변할 것:
  • Architecture: "어떤 모델? 어디에 호스팅?"
  • Dependencies: "다른 시스템과의 의존성?"
  • Timeline: "개발에 얼마나 걸리나?"
  • On-Call: "운영 비용과 모니터링?"

🎨 디자이너
- 핫버튼: "사용자가 이걸 이해할 수 있나?"
- 답변할 것:
  • UX Clarity: "신뢰도를 어떻게 표시?"
  • Onboarding: "처음 사용자가 쉽게 배울 수 있나?"
  • Accessibility: "장애인 사용자도 쓸 수 있나?"
  • Iteration: "피드백 기반 개선 계획?"

🤝 고객성공팀
- 핫버튼: "고객이 이 기능을 채택할 건가?"
- 답변할 것:
  • Adoption: "예상 채택율은?"
  • Support: "새로운 문의/버그 발생?"
  • Training: "고객 교육 자료?"
  • Feedback Loop: "고객 피드백을 어떻게 수집?"

⚖️ Legal/Security
- 핫버튼: "규정/보안 위험은?"
- 답변할 것:
  • Data Privacy: "사용자 데이터 어떻게 처리?"
  • AI Ethics: "편향성 검사?"
  • Liability: "AI 오류로 인한 책임?"
  • Compliance: "GDPR/로컬 규정?"
```

**Step 3: 공통 언어 찾기**

```
같은 목표를 다르게 표현하면 갈등이 생김.
공통 언어로 통일하자:

❌ 각자 다른 언어:
- 경영진: "Q3 출시로 시장 기회 선점"
- 엔지니어: "기술 부채 줄이기"
- 디자이너: "사용자 경험 개선"

✅ 공통 언어:
"AI 요약 기능을 통해:
- 사용자 생산성 30% 증가 (비즈니스)
- 안정적 인프라 (기술)
- 직관적 UX (디자인)
를 달성하고, 3개월 후 성과 평가"
```

<!-- 💬 [자기 검증] 한국 조직의 "합의제 문화"에서 공통 언어 찾기
     현실: 한국은 "상하관계"가 강해서 경영진이 말하면 끝남
     문제: 그럼 엔지니어는 "뭐 하는 건지 모르고" 일함
     해결: PM의 역할 = "경영진의 의도"를 "각 팀의 언어"로 번역
     한국 린품의: 팀장들의 "빠른 합의" → 실행 (위아래 소통은 나중) -->

**Step 4: 의사결정 문서 작성**

```markdown
# [기능명] Stakeholder Alignment Document

## 1. 비즈니스 기회
- 고객 요청: "요약 기능 있으면 시간이 50% 단축될 것 같아요"
- 경쟁 분석: Notion AI, ChatGPT 통합은 이미 요약 기능 제공
- 기회 규모: Enterprise 100개사, 잠재 ARR $2M

## 2. 성공의 정의

### Primary KPI
- Adoption Rate: 월 활성 사용자의 30% 이상 사용
- Trust Score: 7.0/10 이상
- Timeline: Q3 Beta (80% 정확도), Q4 GA (95% 정확도)

### Secondary KPI
- 사용자 만족도: NPS 50+
- 지원 비용: Bug 리포트 < 5 per 1,000 usage
- 모델 성능: Latency < 2초, Error < 0.5%

## 3. 약속과 우려사항

### 엔지니어 약속
- "80% 정확도 모델로 Q3 Beta 가능"
- 우려: "95% 정확도는 데이터 추가 학습 필요, 3주 소요"
- 해결: "Beta 사용자 피드백으로 Q4에 개선"

### 디자이너 약속
- "신뢰도 표시 UI 3주 이내 완성"
- 우려: "사용자 테스트 시간?"
- 해결: "Beta 단계에서 실제 사용자 피드백 수집"

### 경영진 약속
- "Q3 출시로 고객 만족도 증가"
- 우려: "80% 정확도면 고객이 실망할 수 있음"
- 해결: "Beta 라벨 명시 + 정기 개선 공지"

## 4. 위험 관리

| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|-----------|
| 모델 정확도 80% 미만 | 출시 연기 | Medium | 추가 데이터 수집 |
| Beta 사용자 0% 채택 | 개발 낭비 | Low | 사전 사용자 모집 |
| 모니터링 비용 높음 | 손실 발생 | High | 비용 추정 및 예산 배정 |

## 5. 의사결정 로그

**2026-03-11 Decision #1: 80%→95% 정확도 로드맵**
- 선택: Beta(80%), GA(95%) 2단계 릴리스
- 대안: 95% 완성도에서만 출시 (3개월 지연)
- 이유: 고객 기대 vs 개발 속도의 균형
- 재검토: 2026-04-15 (Beta 피드백 수집 후)

**2026-03-11 Decision #2: 신뢰도 UI 필수 여부**
- 선택: Beta부터 신뢰도 점수 표시 (필수)
- 대안: GA에 추가 (Beta는 생략)
- 이유: 80% 정확도에서 신뢰도 표시가 사용자 기대 관리에 필수
- 재검토: Beta 사용자 피드백 기반

## 6. 정기 동기화

- 주간: 경영진 + PM (진행률, 위험)
- 주간: 엔지니어 + PM (기술 이슈)
- 월간: 크로스팀 (전체 검토)
- 월간: 주요 고객 (피드백)

## 7. 문서 버전 관리

| Version | Date | Change | Owner |
|---------|------|--------|-------|
| v1.0 | 2026-03-11 | 초안 작성 | PM |
| v1.1 | 2026-03-12 | 엔지니어 피드백 반영 | PM |
```

### 이해관계자별 알림장 템플릿

```markdown
# Executive Summary: AI 요약 기능
FOR: CEO, VP Product
TIME: 5분

## 기회
- 고객 요청 다수 (100+ 기업)
- 경쟁사 선점 (Notion, ChatGPT+)
- 예상 ARR: $2M

## 계획
| 단계 | 시점 | 정확도 | 채택 목표 | 비용 |
|------|------|--------|---------|------|
| Beta | Q3 | 80% | 20% | $50k |
| GA | Q4 | 95%+ | 35% | $100k |

## 위험
- 정확도 불충분 (80%): Beta 라벨로 기대 관리
- 채택 부진: 2주 후 평가, 필요시 피벗

## 의사결정
- ✅ Q3 Beta 승인 (80% 정확도)
- ❓ 추가 마케팅 예산 ($50k) 필요
- ⏰ 월요일 의사결정 필요

---

# Engineering Brief: AI 요약 기능
FOR: 엔지니어 리드
TIME: 10분

## 기술 요구사항
- 모델: Claude API (또는 자체 Fine-tuned)
- 정확도: Beta 80%, GA 95%
- Latency: < 2초
- Error Rate: < 0.5%

## 아키텍처
```
User Input
  → Validation (한국어 최적화)
  → LLM API Call (Claude 3)
  → Confidence Scoring
  → Response Caching
  → Logging & Monitoring
```

## 타임라인
- Week 1: API Integration
- Week 2: Testing & Tuning
- Week 3: Beta Deploy
- Week 4-12: GA Improvement (모델 Fine-tuning)

## 의존성 & 위험
- Claude API 가용성 (대체: OpenAI GPT-4)
- 한국어 모델 성능 (추가 데이터 필요)
- 비용 모니터링 (예상 $50k/월)

## 제안
- 비용 최적화: Prompt Caching으로 30% 절감 가능
- 성능 개선: 한국어 특화 Fine-tuning 검토

---

# Design Brief: AI 요약 기능
FOR: 디자이너, UX
TIME: 10분

## 사용자 여정
1. 문서 선택
2. "요약" 버튼 클릭
3. 진행률 표시 (2초)
4. 요약 결과 표시 + 신뢰도 점수
5. 편집/공유 옵션

## UI 컴포넌트
- Loading State: Skeleton + 진행률
- Result Card: 요약 + 신뢰도 (7.2/10) + 출처
- Actions: Edit / Share / Regenerate

## 신뢰도 표시 방식 (택 1)
- A안: 숫자 스코어 (7.2/10)
- B안: Visual Indicator (⭐⭐⭐)
- C안: 문구 설명 ("매우 신뢰할 수 있음")
→ A/B 테스트 권장

## 접근성 (WCAG 2.1 AA)
- 신뢰도 점수: 숫자 + 문구 (시각 + 음성)
- 진행률: ARIA labels
- 오류 메시지: 명확한 한국어

## 일정
- Week 1: Wireframes + 사용자 테스트
- Week 2: High-fidelity Design
- Week 3: Implementation Support

---

# Customer Success Brief: AI 요약 기능
FOR: 고객성공팀
TIME: 5분

## 고객 영향
- 예상 채택율: 30% (월 활성 사용자)
- 사용 시간 절감: 문서 읽기 시간 50% 단축

## 온보딩 전략
1. Beta 공지: Beta 라벨 명시 ("실험 기능")
2. 가이드: 5분 튜토리얼 + FAQ
3. 피드백: 주간 피드백 설문
4. 개선: 피드백 기반 매주 개선

## 지원 준비
- FAQ 문서 (10개 항목)
- 모니터링: 신고 채널 (Intercom)
- 버그: 48시간 내 응답 SLA

## 기대 설정
- "Beta 기능: 80% 정확도, 개선 중"
- "완벽하지 않을 수 있으니 중요 문서는 검증 권장"
- "3개월 후 완전 버전으로 업그레이드"

## 요청
- 고객 피드백 채널 연결 (주간 정리)
- 채택 진행률 공유 (주간)
```

💡 **Deep Tips:**
- **의사결정 로그**: 3개월 후 "왜 이렇게 했지?" 하는 재논쟁 방지. 결정의 "context"를 남기자.
- **정기 동기화**: 일회성이 아니라 반복적인 미팅으로 신뢰도 높이기
- **WIFM**: 각 이해관계자에게 "너의 관심사가 반영되었다"는 확신주기


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 이해관계자 식별 어려움 | "이 결정에 영향을 받는 사람은 누구?"로 시작 |
| 2단계 | 관심사 파악 어려움 | 각 이해관계자에게 "이 프로젝트에서 가장 걱정되는 것은?" 직접 질문 |
| 3단계 | 공통 언어 찾기 어려움 | "이 프로젝트의 성공을 한 문장으로 말하면?"에 모두가 동의하는 버전 |
| 5단계 | 합의가 안 됨 | "동의하지 않지만 실행에는 동의한다(Disagree and Commit)" 프레임 사용 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 이해관계자별 커뮤니케이션 문서를 자동 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
프로젝트 진행 중 이해관계자 업데이트는 주간/월간 반복됩니다. 자동화하면 각 대상에 맞는 형식으로 빠르게 생성할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### 이해관계자 정렬 프레임워크 (Python)

```python
# stakeholder_alignment_framework.py
from dataclasses import dataclass
from typing import List, Dict
from enum import Enum
from datetime import datetime, timedelta

class Impact(Enum):
    HIGH = "High"
    MEDIUM = "Medium"
    LOW = "Low"

class Interest(Enum):
    HIGH = "High"
    MEDIUM = "Medium"
    LOW = "Low"

class StakeholderQuadrant(Enum):
    MANAGE = "Manage (주간)"
    INFORM = "Inform (월간)"
    CONSULT = "Consult (월간)"
    MONITOR = "Monitor (분기)"

@dataclass
class Stakeholder:
    """이해관계자 정의"""
    name: str
    role: str
    impact: Impact
    interest: Interest
    hotbuttons: List[str]  # WIFM: "너는 뭐가 중요해?"
    concerns: List[str]
    success_criteria: str

    @property
    def quadrant(self) -> StakeholderQuadrant:
        """이해관계자의 사분면 결정"""
        if self.impact == Impact.HIGH and self.interest == Interest.HIGH:
            return StakeholderQuadrant.MANAGE
        elif self.impact == Impact.HIGH and self.interest == Interest.LOW:
            return StakeholderQuadrant.INFORM
        elif self.impact == Impact.LOW and self.interest == Interest.HIGH:
            return StakeholderQuadrant.CONSULT
        else:
            return StakeholderQuadrant.MONITOR


@dataclass
class Decision:
    """의사결정 기록"""
    decision_id: str
    date: str
    title: str
    chosen_option: str
    alternatives: List[str]
    reasoning: str
    owner: str
    review_date: str  # 언제 다시 검토할 건가?
    impact: str

    def to_markdown(self) -> str:
        return f"""
**{self.date} Decision #{self.decision_id}: {self.title}**
- 선택: {self.chosen_option}
- 대안: {', '.join(self.alternatives)}
- 이유: {self.reasoning}
- Owner: {self.owner}
- 재검토: {self.review_date}
"""


class StakeholderAlignmentManager:
    """이해관계자 정렬 관리"""

    def __init__(self, project_name: str):
        self.project_name = project_name
        self.stakeholders: List[Stakeholder] = []
        self.decisions: List[Decision] = []
        self.meetings: List[Dict] = []

    def add_stakeholder(self, stakeholder: Stakeholder):
        """이해관계자 추가"""
        self.stakeholders.append(stakeholder)

    def add_decision(self, decision: Decision):
        """의사결정 기록"""
        self.decisions.append(decision)

    def schedule_meeting(self,
                        stakeholders: List[str],
                        frequency: str,
                        topics: List[str]):
        """정기 미팅 일정"""
        self.meetings.append({
            "stakeholders": stakeholders,
            "frequency": frequency,
            "topics": topics,
        })

    def generate_stakeholder_map(self) -> str:
        """이해관계자 맵 생성"""
        manage = [s for s in self.stakeholders if s.quadrant == StakeholderQuadrant.MANAGE]
        inform = [s for s in self.stakeholders if s.quadrant == StakeholderQuadrant.INFORM]
        consult = [s for s in self.stakeholders if s.quadrant == StakeholderQuadrant.CONSULT]
        monitor = [s for s in self.stakeholders if s.quadrant == StakeholderQuadrant.MONITOR]

        report = f"""
# {self.project_name} Stakeholder Map

## MANAGE (주간 미팅)
높은 영향도 + 높은 관심도

"""
        for s in manage:
            report += f"- **{s.name}** ({s.role})\n"
            report += f"  - 핫버튼: {', '.join(s.hotbuttons)}\n"
            report += f"  - 우려: {', '.join(s.concerns)}\n"
            report += f"  - 성공: {s.success_criteria}\n\n"

        report += """
## INFORM (월간 리포트)
높은 영향도 + 낮은 관심도

"""
        for s in inform:
            report += f"- **{s.name}** ({s.role}): {s.hotbuttons[0]}\n"

        report += """
## CONSULT (월간 피드백)
낮은 영향도 + 높은 관심도

"""
        for s in consult:
            report += f"- **{s.name}** ({s.role}): {s.hotbuttons[0]}\n"

        report += """
## MONITOR (분기 보고)
낮은 영향도 + 낮은 관심도

"""
        for s in monitor:
            report += f"- **{s.name}** ({s.role})\n"

        return report

    def generate_decision_log(self) -> str:
        """의사결정 로그 생성"""
        report = f"# {self.project_name} Decision Log\n\n"
        for decision in sorted(self.decisions, key=lambda d: d.date, reverse=True):
            report += decision.to_markdown()
        return report

    def generate_meeting_schedule(self) -> str:
        """미팅 일정 생성"""
        report = f"# {self.project_name} Meeting Schedule\n\n"

        for meeting in self.meetings:
            report += f"## {', '.join(meeting['stakeholders'])}\n"
            report += f"**Frequency**: {meeting['frequency']}\n"
            report += f"**Topics**: {', '.join(meeting['topics'])}\n\n"

        return report

    def generate_full_report(self) -> str:
        """전체 정렬 보고서"""
        return (
            self.generate_stakeholder_map() + "\n" +
            self.generate_meeting_schedule() + "\n" +
            self.generate_decision_log()
        )

    def generate_stakeholder_brief(self, stakeholder_name: str) -> str:
        """개별 이해관계자 알림장"""
        stakeholder = next((s for s in self.stakeholders if s.name == stakeholder_name), None)

        if not stakeholder:
            return f"이해관계자 '{stakeholder_name}' 찾을 수 없음"

        brief = f"""
# {self.project_name} Brief for {stakeholder.name}

## 당신의 역할
{stakeholder.role}

## 당신이 신경 쓰는 것 (WIFM)
{', '.join(f"✓ {h}" for h in stakeholder.hotbuttons)}

## 당신의 우려사항
{chr(10).join(f"⚠️  {c}" for c in stakeholder.concerns)}

## 당신이 원하는 성공
{stakeholder.success_criteria}

## 우리의 약속
[개별 이해관계자별 약속 작성]

## 당신의 의견이 필요한 것
[구체적인 피드백 요청]

## 다음 단계
[구체적인 일정 및 액션]
"""
        return brief


# 사용 예시
if __name__ == "__main__":
    # 1. 프로젝트 생성
    manager = StakeholderAlignmentManager("AI 요약 기능")

    # 2. 이해관계자 추가
    manager.add_stakeholder(Stakeholder(
        name="CEO",
        role="경영진",
        impact=Impact.HIGH,
        interest=Interest.HIGH,
        hotbuttons=["ROI", "Market Timing", "Risk"],
        concerns=["정확도 부족 시 고객 신뢰 저하", "개발 지연"],
        success_criteria="Q3 Beta 출시, Q4 GA, ARR $2M"
    ))

    manager.add_stakeholder(Stakeholder(
        name="Engineering Lead",
        role="엔지니어",
        impact=Impact.HIGH,
        interest=Interest.HIGH,
        hotbuttons=["Technical Feasibility", "Quality", "Ops Cost"],
        concerns=["80% 정확도 모델 성능", "비용 모니터링"],
        success_criteria="안정적 API, Latency < 2초, Cost 최적화"
    ))

    manager.add_stakeholder(Stakeholder(
        name="Design Lead",
        role="디자이너",
        impact=Impact.MEDIUM,
        interest=Interest.HIGH,
        hotbuttons=["User Experience", "Trust Display", "Onboarding"],
        concerns=["사용자가 신뢰도를 이해할 수 있나?"],
        success_criteria="직관적 신뢰도 UI, 5분 온보딩"
    ))

    # 3. 의사결정 기록
    manager.add_decision(Decision(
        decision_id="001",
        date="2026-03-11",
        title="2단계 릴리스 계획 (Beta 80% → GA 95%)",
        chosen_option="Beta(80%), GA(95%) 분리",
        alternatives=["95% 완성도부터만 출시 (3개월 지연)", "80% 그대로 GA 출시 (위험)"],
        reasoning="고객 기대 vs 개발 속도의 균형, Beta로 피드백 수집 후 개선",
        owner="PM",
        review_date="2026-04-15",
        impact="일정 확정, 고객 기대 관리"
    ))

    # 4. 미팅 일정
    manager.schedule_meeting(
        stakeholders=["CEO", "Engineering Lead", "PM"],
        frequency="Weekly",
        topics=["Progress", "Blockers", "Risk"]
    )

    manager.schedule_meeting(
        stakeholders=["Design Lead", "PM", "Engineering Lead"],
        frequency="Bi-weekly",
        topics=["UI Review", "Feedback Loop"]
    )

    # 5. 보고서 생성
    print(manager.generate_full_report())
    print("\n" + "="*50 + "\n")
    print(manager.generate_stakeholder_brief("CEO"))
```

### Claude Code CLI 활용

```bash
# 1. 이해관계자 맵 생성
claude code run create-stakeholder-alignment \
  --project-name "AI Summarization" \
  --stakeholders stakeholders.json \
  --output alignment-doc.md

# 2. 의사결정 로그 기록 (자동화)
claude code run log-decision \
  --title "80% vs 95% 정확도 결정" \
  --chosen "Beta(80%) → GA(95%)" \
  --reasoning "빠른 고객 피드백 vs 품질의 균형" \
  --review-date "2026-04-15"

# 3. 정기 미팅 리마인더 생성
claude code run schedule-stakeholder-meetings \
  --project "AI Summarization" \
  --generate-calendar \
  --calendar-format ics

# 4. 개별 이해관계자 알림장 생성 (PDF)
claude code run generate-stakeholder-briefs \
  --project "AI Summarization" \
  --format pdf \
  --recipients ceo@company.com,engineering@company.com
```

---

## 📊 실행 결과 예시

### 이해관계자 맵

```
AI 요약 기능 Stakeholder Map

┌─────────────────────────────────────────────┐
│ MANAGE (주간)                               │
│                                              │
│ 🏢 CEO/VP Product                           │
│    핫버튼: ROI, 출시 일정, 위험             │
│    우려: 정확도 부족 → 고객 신뢰 저하      │
│    성공: Q3 Beta, Q4 GA, ARR $2M           │
│                                              │
│ 👨‍💻 Engineering Lead                        │
│    핫버튼: 기술 실현, 품질, 운영 비용      │
│    우려: 80% 정확도 충분?, 비용 높음?      │
│    성공: 안정적 API, Latency <2초          │
│                                              │
│ 🔐 주요 고객 (Enterprise)                   │
│    핫버튼: 정확도, 신뢰도                   │
│    우려: Beta 버전이 사용 가능?             │
│    성공: 조기 접근, 정기 피드백 반영       │
│                                              │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ INFORM (월간 리포트)                        │
│ - Legal/Security: AI 규정 준수, 데이터 보안│
│ - Finance: 비용 모니터링                    │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ CONSULT (월간 피드백)                       │
│ - Design Lead: 신뢰도 UI, 온보딩           │
│ - Customer Success: 채택, 지원             │
│ - Marketing: 포지셔닝, 커뮤니케이션        │
└─────────────────────────────────────────────┘
```

### 의사결정 로그

```
Decision Log - AI 요약 기능

📋 2026-03-11 Decision #1: 2단계 릴리스 계획
- 선택: Beta(80% 정확도) → GA(95% 정확도) 분리
- 대안 검토:
  1. 95% 완성도부터만 출시 (안전하지만 3개월 지연)
  2. 80% 그대로 GA 출시 (빠르지만 고객 실망 위험)
- 이유: 고객 기대 vs 개발 속도의 균형
  • Beta 라벨로 기대 설정 가능
  • 실제 고객 피드백으로 Q4 개선
  • 경쟁사 선점 시간 확보
- Owner: PM
- 재검토: 2026-04-15 (Beta 2주 피드백 후)
- 영향: 일정 확정 ✅, 고객 기대 관리 ✅, 엔지니어 부담 완화 ✅

📋 2026-03-12 Decision #2: 신뢰도 UI 필수 포함 여부
- 선택: Beta부터 신뢰도 점수 표시 (필수)
- 대안 검토:
  1. Beta는 생략, GA에 추가 (개발 빠름)
  2. Beta부터 포함 (사용자 기대 관리 용이)
- 이유: 80% 정확도에서 신뢰도 표시는 필수
  • "정확도 80%면 충분한가?" → "신뢰도 7/10으로 의사결정"
  • 불확실성 투명성 높임
  • 사용자 신뢰도 상대적으로 높음
- Owner: Design Lead, PM
- 재검토: Beta 피드백 기반 (주간)
- 영향: 사용자 신뢰 ✅, 기대 관리 ✅

⏳ Pending Decision: 추가 마케팅 예산 $50k
- 기간: 월요일 의사결정 필요
- 영향: 채택율, 경쟁 포지셔닝
```

### 이해관계자별 알림장

```
# CEO Brief - AI 요약 기능 (5분)

## 당신의 관심사
✓ ROI 달성 시간
✓ 경쟁사 vs 우리 차별점
✓ 고객 신뢰 영향

## 좋은 소식
- 고객 요청 100+ (확실한 니즈)
- 경쟁사(Notion, ChatGPT+) 선점 기회
- 예상 ARR $2M (신규 ARR 20%)

## 우려사항과 해결책
| 우려 | 현황 | 해결책 |
|-----|------|--------|
| 80% 정확도 충분? | Beta 라벨로 기대 설정 | Q4에 95%로 업그레이드 |
| 개발 지연? | 아니오 (Q3 가능) | 2단계 릴리스로 속도 ↑ |
| 고객 신뢰? | 신뢰도 UI로 투명성 | 실제 데이터 (신뢰도 7.0+ 목표) |

## 의사결정 필요
- ✅ Q3 Beta 승인 (정책)
- ❓ 마케팅 예산 $50k (월요일 결정)
- ⏰ 다음 체크인: 3월 25일 (2주 피드백)

---

# Engineering Lead Brief - AI 요약 기능 (10분)

## 당신의 관심사
✓ 기술 실현 가능성
✓ 품질 (정확도, 안정성)
✓ 운영 비용

## 기술 계획
Architecture:
User Input
  → Claude API 호출
  → 신뢰도 계산 (Fine-tuning)
  → 응답 캐싱
  → 모니터링

Accuracy Roadmap:
- Week 1-3: Claude API 통합, 80% 달성
- Week 4-6: Beta 피드백 수집
- Week 7-12: 추가 데이터로 95% 달성

## 당신의 우려와 해결책
| 우려 | 해결책 |
|-----|--------|
| 한국어 정확도 80% 달성? | Fine-tuning 데이터 추가 (예산 배정) |
| API 비용 예상? | $50k/월 (사용량 기반 최적화 계획) |
| 모니터링 준비? | 주간 메트릭 체크인 |

## 의사결정 필요
- ✅ Claude API 선택 승인
- ✅ 추가 Fine-tuning 데이터 예산
- ⏰ 타임라인: 3주 후 Beta 준비

## 다음 기술 미팅
- 목요일 2pm: 아키텍처 세부 리뷰
- 금요일 3pm: 성능 테스트 플랜
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 이해관계자 맵에서 'High Power + Low Interest' 그룹의 소통 전략이 있는지 확인하세요 — 가장 위험한 그룹입니다
2. **[논쟁 지점]** 이해관계자 합의를 '만장일치'로 할지 '다수결'로 할지는 조직 문화에 따라 다릅니다
   - 한국 대기업: "상무급 동의" = 만장일치와 동일 효과
   - 한국 스타트업: "CEO와 리드 3명 동의" = 충분
   - 서구: Consensus-seeking 또는 RACI 기반
3. **[자기 검증]** 가장 반대 가능성이 높은 이해관계자 1명의 예상 반론에 답할 수 있는지 확인하세요
   - 한국 특화: "보안팀이 PIPA 위반 지적" 가능성은?
   - 대비: AI기본법 준수 근거 사전 준비

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|------|-----------|------|
| ✅ 이해관계자 맵 | `cross-team-handoff.md` | "팀별 역할과 책임 명확화" |
| ✅ 의사결정 로그 | `press-release.md` | "출시 메시지를 의사결정 기반으로 작성" |
| ✅ 정기 미팅 | `ai-ethics-review.md` | "정기 미팅에서 윤리 리뷰 포함" |
| 🔜 자동화 | Claude Code `--sync-stakeholders-weekly` | 매주 자동 브리핑 생성 |
