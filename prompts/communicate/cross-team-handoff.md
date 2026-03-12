# 🤝 크로스팀 핸드오프 (Cross-Team Handoff)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 35분+ (Build)
> 워크플로우: ← `stakeholder-alignment.md` → 구현

---

## 🎯 이 프롬프트가 해결하는 문제

PM이 기획한 AI 기능을 엔지니어, 디자이너, 고객성공팀에게 전달해야 한다. **"무엇을 만들어야 하는가"를 각 팀이 정확히 이해해야만 빠르고 정확한 실행이 가능하다.** 커뮤니케이션 부족 시 "다시 해야 한다", "예상과 다르다", "일정 지연"이 발생한다.

---

## 📥 이전 프롬프트에서 받는 입력

> `stakeholder-alignment.md`에서 합의된 방향을 각 팀에게 전달하는 단계에서 연결됩니다.

이전 프롬프트 결과에서 **기능명, 합의된 범위, 일정, 팀별 역할**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 팀 간 인수인계 문서를 작성할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 PM 집행자다.

{AI 기능}의 핸드오프 문서를 만드세요:

구조:
1. 엔지니어링 브리프
   - "뭘 만들어야 하나?"
   - 기술 요구사항, 아키텍처, 일정

2. 디자인 브리프
   - "UI는 어떻게?"
   - 화면 정의, 사용자 흐름, 인수 기준

3. QA 테스트 계획
   - "뭘 테스트할까?"
   - 기능 테스트, 성능 테스트, 엣지 케이스

4. 고객성공팀 핸드오프
   - "고객에게 뭐라고 설명할까?"
   - Onboarding 가이드, FAQ, 지원 계획

각 팀이 즉시 일을 시작할 수 있도록 구체적으로.
```

💡 **Quick Tips:**
- 각 팀이 "내 파트"만 보게 하면 조율 문제 발생 → 전체 그림도 함께 공유
- 정기 미팅 (주간): "진행 상황 + 우려 사항" 확인
- 이슈 추적: PM이 "병목" 감시 (엔지니어링 막힘, 디자인 지연 등)


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 원격/비동기 팀 | 문서화가 더 중요합니다. 비디오 녹화를 추가하세요 |
| 핸드오프 상대가 외부 벤더 | 보안 요구사항과 데이터 접근 범위를 명시하세요 |
| 긴급 핸드오프 | 최소 "목표, 현재 상태, 즉시 할 일" 3가지만 전달 |
| 여러 팀에 동시 핸드오프 | 팀별로 관련 부분만 필터링해서 전달하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 팀 간 인수인계를 체계적으로 진행하고 싶은 분입니다.
"내가 전달한 건데 왜 다르게 구현됐지?"를 방지하고 싶다면 이걸 써보세요.

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

당신은 **PM 실행 조율자(PM Orchestrator)**이다. 당신의 역할:

1. **각 팀의 언어 번역**: 엔지니어 → 디자이너 → 고객성공팀
2. **의존성 관리**: 누가 먼저 끝내야 다음 팀이 시작할 수 있는가?
3. **위험 조기 감지**: "이 일정으로 가능한가?"

<!-- 💬 [전문가의 눈] 크로스팀 핸드오프가 실패하는 이유
     실패 원인: 각 팀이 다른 언어 사용
     엔지니어: "기술 스펙, 의존성"
     디자이너: "사용자 경험, 접근성"
     고객성공: "교육, 지원 SLA"

     해결: PM이 "공통 목표"를 각 팀의 언어로 번역
     예: "신뢰도 점수 표시" →
         엔지니어: "신뢰도 계산 API"
         디자이너: "7.2/10을 UI에 표시"
         고객성공: "고객에게 'AI를 맹신하지 말라' 메시지" -->

### 목표

최종 아웃풋:
- **팀별 구체적 브리프** (엔지니어링 / 디자인 / QA / 고객성공)
- **실행 일정** (주간 마일스톤)
- **의존성 맵** (누가 먼저, 누가 나중)
- **위험 & 이슈 관리** (일주일마다 체크)

### Reasoning Strategy

**Step 1: 팀별 우선순위 정의**

```
🎯 누가 먼저 시작해야 하나?

순서:
1️⃣  디자인 시작 (Week 1)
   - "화면이 뭔지" 정의 필요 → 엔지니어링 블로킹 해제

2️⃣  엔지니어링 시작 (Week 1 후반)
   - 디자인이 "대충" 나와도 시작 가능
   - 디자인 세부사항은 Week 2에 반영

3️⃣  QA 설정 (Week 2)
   - 엔지니어링이 "테스트 환경" 준비해야 QA 시작

4️⃣  고객성공팀 교육 (Week 2 후반)
   - 기능이 "80% 완성"되어야 교육 가능

의존성:
```
Design → Engineering → QA → GA
        (Parallel Design)
                    ↓
            Customer Success Education
```

**Step 2: 팀별 "Done" 기준 정의**

```
각 팀이 "언제까지 뭘 해야 하나?"를 명확히:

디자인팀 Done:
✅ 로우 / 하이파이 완성
✅ Design System 준수
✅ 접근성 WCAG 2.1 AA
✅ 엔지니어링팀과 인수 기준 합의
✅ 스크린샷 + 인터랙션 명세

엔지니어링팀 Done:
✅ API 구현 완료
✅ 로컬 테스트 통과
✅ 성능 벤치마크 충족 (Latency < 2초)
✅ 에러 핸들링 구현
✅ 로깅 & 모니터링 설정
✅ 코드 리뷰 완료

QA Done:
✅ 기능 테스트 (100% 통과)
✅ 성능 테스트 (Latency, Error rate)
✅ 엣지 케이스 (특수 문자, 큰 파일)
✅ 회귀 테스트 (기존 기능 영향 없나?)

고객성공팀 Done:
✅ Onboarding 가이드 작성
✅ FAQ 문서 (10+ 항목)
✅ 고객 피드백 채널 준비
✅ 지원팀 교육 완료
```

<!-- 💬 [논쟁 지점] "Done"의 정의가 팀마다 다르다
     엔지니어: "코드 리뷰 완료" = Done
     마케팅: "문서 작성" = Done
     경영진: "출시" = Done
     해결: 명확한 "완료 기준"을 프로젝트 시작 시 합의
     한국 기업의 린품의 문화: "80% 완성도"에서 시작하는 경향 -->

### 팀별 핸드오프 문서 (완전한 템플릿)

---

## 엔지니어링 팀 핸드오프

```markdown
# Engineering Specification: AI 요약 기능

## 1. 기능 정의

### 1.1 사용자 요청 흐름
```
사용자
  → 문서 선택
  → "요약" 버튼 클릭
  → 로딩 표시 (2초)
  → 결과 표시
    - 요약 (3줄)
    - 신뢰도 (7.2/10)
    - "더보기" (원문 링크)
  → 편집/공유 옵션
```

### 1.2 API 명세

```
POST /api/v1/documents/summarize
Request:
{
  "document_id": "doc_123",
  "include_confidence": true,
  "language": "ko"
}

Response (200):
{
  "summary": "문서의 핵심 3줄...",
  "confidence_score": 7.2,
  "confidence_reason": "이 영역의 정보가 제한적",
  "execution_time_ms": 1200,
  "model_version": "claude-3-v2.1"
}

Response (400):
{
  "error": "document_too_large",
  "message": "문서가 너무 큽니다 (Max: 100MB)"
}

Response (429):
{
  "error": "rate_limit_exceeded",
  "retry_after_seconds": 60
}
```

## 2. 기술 요구사항

### 2.1 성능
- Latency: P50 < 1초, P95 < 2초, P99 < 5초
- Error Rate: < 0.5%
- Availability: 99.95%

### 2.2 확장성
- 동시 요청: 1,000+ RPS 처리
- 캐싱: 동일 문서 재요청은 캐시에서 (500ms)

### 2.3 보안
- 인증: JWT (기존 시스템)
- 암호화: HTTPS + AES-256 저장소
- 데이터: 24시간 후 자동 삭제

### 2.4 비용 최적화
- 모델: Claude API (대체: OpenAI GPT-4)
- Prompt Caching 활용: 30% 비용 절감 예상
- 예상 비용: $50k/월

## 3. 아키텍처

### 3.1 컴포넌트
```
Frontend (React)
  ↓
API Gateway
  ↓
Worker Queue (Bull)
  ↓
LLM Service (Claude API)
  ↓
Cache (Redis)
  ↓
DB (PostgreSQL)
```

### 3.2 에러 처리
```
API Call Fail → Retry (3회) → Circuit Breaker → Fallback (캐시된 요약)
Model Timeout → Fallback to keyword extraction
Quota Exceeded → Queue 대기
```

## 4. 타임라인

| Week | Milestone | Owner |
|------|-----------|-------|
| W1 | API 설계 & 프로토타입 | Backend Lead |
| W2 | Claude API 통합 | Backend |
| W3 | 성능 테스트 & 최적화 | Devops |
| W4 | QA 환경 준비 | QA Lead |
| W5 | Beta 배포 | DevOps |

## 5. 의존성 & 위험

### 의존성
- Design: 화면 스펙 (W1 완료 필요)
- QA: 테스트 케이스 (W2 중순 필요)

### 위험
| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|-----------|
| Claude API 지연 | 출시 연기 | Medium | OpenAI 대체 모델 준비 |
| 비용 초과 | 손실 | Medium | Prompt Caching + 비용 상한 |
| 정확도 80% 미만 | 신뢰도 저하 | Low | Fine-tuning 데이터 추가 |

---

## 디자인 팀 핸드오프

```markdown
# Design Specification: AI 요약 기능

## 1. 사용자 흐름

### Before: 현재 상태
사용자 → 문서 읽기 (30분) → 직접 요약 작성

### After: 요약 기능 사용
사용자 → 요약 버튼 → AI 요약 표시 (2초) → 편집 또는 수용

## 2. 화면 정의

### 2.1 메인 요약 카드
```
┌─────────────────────────┐
│ 📄 요약                 │
├─────────────────────────┤
│ 핵심 내용:              │
│ "문서에서..."           │ (3줄)
│                          │
│ 신뢰도: ⭐⭐⭐⭐ (7.2/10) │
│ 이 부분이 불명확...     │
│                          │
│ [수정] [공유] [다시생성] │
└─────────────────────────┘
```

### 2.2 신뢰도 표시 방식 (A/B 테스트)
- A: 숫자 스코어 (7.2/10)
- B: 별점 (⭐⭐⭐⭐)
- C: 문구 설명 ("높음" / "중간" / "낮음")

## 3. 인터랙션

### 3.1 로딩 상태
```
[요약 버튼] → Skeleton + 진행률 (2초) → 요약 카드 표시
```

### 3.2 오류 상태
```
[요약 버튼]
  → API 에러 (서버 느림)
  → "다시 시도" 버튼 표시
  → 또는 "캐시된 요약" 표시
```

## 4. 접근성 (WCAG 2.1 AA)

### 4.1 시각
- 색상 대비: 신뢰도 카드 4.5:1 이상
- 텍스트 크기: 14px 이상

### 4.2 키보드
- Tab 이동 순서: 명확
- Enter로 "요약" 버튼 실행 가능

### 4.3 스크린 리더
- "신뢰도 7.2 (높음)"으로 읽힘
- "이 부분이 불명확하니 직접 검토하세요" 안내

## 5. 디자인 시스템 준수
- 컬러: 기존 팔레트 사용 (파란색 신뢰, 주황색 경고)
- 타이포그래피: 본문 14px, 제목 18px
- 스페이싱: 8px 단위

## 6. 인수 기준

- [ ] 로우/하이파이 Figma 완성
- [ ] 개발팀과 핸드오프 회의 진행
- [ ] Design System 규칙 적용 검증
- [ ] 접근성 WCAG 2.1 AA 자체 검증

---

## QA 팀 테스트 계획

```markdown
# QA Test Plan: AI 요약 기능

## 1. 기능 테스트 (Functional)

### 1.1 행복 경로 (Happy Path)
- [ ] 문서 선택 → 요약 버튼 → 결과 표시 (정상)
- [ ] 신뢰도 점수 정상 범위? (0-10)
- [ ] "더보기" 링크 동작? (원문 표시)

### 1.2 엣지 케이스
- [ ] 빈 문서 (0바이트) → 에러 메시지 표시
- [ ] 매우 큰 문서 (100MB+) → "문서가 너무 큽니다" 에러
- [ ] 특수 문자 (한글, 이모지) → 정상 처리
- [ ] 타임아웃 → "다시 시도" 옵션 제시

## 2. 성능 테스트 (Performance)

### 2.1 응답 시간
- [ ] Latency P50 < 1초
- [ ] Latency P95 < 2초
- [ ] 캐시 hit: < 500ms

### 2.2 부하 테스트
- [ ] 동시 100 요청 → 정상
- [ ] 동시 1,000 요청 → 안정적
- [ ] CPU 사용율 < 80%

## 3. 회귀 테스트 (Regression)

### 3.1 기존 기능 영향 없음
- [ ] 기존 문서 조회 성능 변화 없음
- [ ] 기존 검색 기능 정상
- [ ] DB 쿼리 성능 저하 없음

## 4. 보안 테스트 (Security)

### 4.1 데이터 보안
- [ ] HTTPS 사용
- [ ] 개인정보 로깅 없음
- [ ] 24시간 후 자동 삭제 확인

### 4.2 접근 제어
- [ ] 인증 없으면 API 호출 불가
- [ ] 다른 사용자 문서 접근 불가

## 5. 테스트 환경

- 스테이징: prod와 동일 (비용: -50% 예상)
- 테스트 데이터: 법무 문서 100개, 계약서 50개, ...
- 시간: W2-W4

---

## 고객성공팀 핸드오프

```markdown
# Customer Success Brief: AI 요약 기능

## 1. 기능 요약 (1분)

새로운 기능: AI가 문서를 2초 만에 요약해줍니다.
대상: 모든 플랜 (Free 제외)
출시: 2026-03-15 (Beta)

## 2. 고객 커뮤니케이션

### 2.1 초기 공지
```
제목: "새로운 AI 요약 기능 Beta 오픈"

내용:
"문서 검토 시간을 줄일 수 있는 AI 요약 기능이 베타로 시작됩니다.
- 장점: 2초 내에 핵심 정리
- 주의: Beta 버전이므로 중요한 내용은 직접 검토 권장
- 신뢰도: AI가 신뢰도 점수(예: 7.2/10)를 제시하니 참고하세요."
```

### 2.2 Onboarding 가이드

1. "요약 버튼" 찾기 (문서 상단)
2. 버튼 클릭 → 2초 대기
3. 결과 보기 → 신뢰도 확인
4. 신뢰도 낮으면 → 직접 검토

### 2.3 FAQ (예상 질문)

**Q: 이 요약을 완전히 신뢰할 수 있나요?**
A: 신뢰도 점수를 보고 판단하세요. 신뢰도 8/10 이상이면 거의 정확하고, 6/10 이하면 직접 검토하세요.

**Q: 내 계약서가 AI 학습에 사용되나요?**
A: 절대 아닙니다. 요약 용도로만 사용하고, 24시간 후 자동 삭제됩니다.

**Q: 오류를 발견하면 어떻게 해요?**
A: "오류 신고" 버튼을 누르세요. 48시간 내 대응합니다.

## 3. 지원 준비

### 3.1 대응 SLA
- 일반 질문: 24시간
- 버그 보고: 48시간
- 기능 요청: 1주

### 3.2 에스컬레이션
- Tier 1: CS 팀 (FAQ 답변)
- Tier 2: PM 팀 (기술 이슈)
- Tier 3: Engineering (버그)

### 3.3 피드백 수집
- 주간: NPS/CSAT 설문
- 월간: 고객 인터뷰 (10명)
- 분기: 기능 개선 보드에 반영

## 4. 시간표

| Week | Task | Owner |
|------|------|-------|
| W4 | 가이드 작성 | Content |
| W4 | CS팀 교육 | PM |
| W5 | 초기 공지 | Marketing |
| W5 | Beta 시작 | 전체 |

---
```

💡 **Deep Tips:**
- **의존성 명확화**: "디자인이 안 나와야 엔지니어가 시작 못 한다" 같은 블로킹 명시
- **정기 체크인**: 주 1회 15분 미팅으로 "우려사항" 조기 포착
- **이슈 추적**: PM이 Jira/Linear에서 모든 "영향 있는" 이슈 관리



### 🇰🇷 한국 기업 인수인계 특화

```
한국 기업 인수인계 시 고려사항:

1. **조직 문화**:
   - 한국 대기업: 공식 인수인계 문서(품의서) + 구두 전달 병행
   - 스타트업: Slack/Notion 기반 비동기 인수인계
   - "선배-후배" 관계: 비공식 지식 전달이 50% 이상

2. **의사결정 구조** (한국 특화):
   - 대기업: 결재라인을 거친 "공식" 핸드오프 필수
   - 스타트업: "린품의" 문화로 빠른 의사결정
   - 합의제 문화: 모든 팀이 "동의"해야 진행
   - 보고선(Reporting Line): PM → 팀장 → 상무 → 임원

3. **도구** (한국 시장):
   - Jira Korea: 한국 팀에서 가장 많이 사용 (DART 공시 관리)
   - Notion: 한국 스타트업 표준
   - 카카오워크/JANDI: 사내 메신저 연동 고려
   - Linear: 초기 스타트업 선호

4. **법적 요구사항** (한국 규정):
   - 개인정보 관련 인수인계: PIPA(개인정보보호법) 준수 확인
   - AI 기능 인수인계: AI기본법(2025 시행) 영향 범위 확인
   - 차별금지법: AI로 인한 고용 차별 가능성 검토
```

<!-- 💬 [자기 검증] 한국 기업의 인수인계 현실
     실제 사례: 대기업에서는 "팀장 품의" 없이 진행 불가
     스타트업: "PM과 리드 1:1 대화" → Slack 공지 (끝)
     위험: 비공식 인수인계 → 나중에 "누가 했다고?"
     해결: 문서화 + 이메일 확인 필수 (증거 남기기) -->

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 핸드오프 범위 정의 어려움 | "이 핸드오프 후 어떤 질문이 나올까?" 예상 목록 작성 |
| 2단계 | 컨텍스트 전달 어려움 | "결정의 이유"를 반드시 포함하세요. "뭘 했나"보다 "왜 했나"가 중요 |
| 3단계 | 알려진 이슈 정리 어려움 | 현재 열려 있는 이슈 + 알려진 제약사항 + 기술 부채 목록 |
| 4단계 | 성공 기준 합의 어려움 | 인수 팀과 함께 "완료 조건"을 정의하세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 핸드오프 문서 생성과 체크리스트 관리를 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
핸드오프는 프로젝트 단계마다 반복됩니다. 자동화하면 필수 항목 누락을 방지하고, 이력을 추적할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python + API 자동화

```python
import json
from datetime import datetime, timedelta
from anthropic import Anthropic

class HandoffDocGenerator:
    """팀 간 인수인계 문서를 자동 생성하는 도구"""

    TEAM_TEMPLATES = {
        "engineering": {
            "sections": ["기능 정의", "API 명세", "기술 요구사항", "아키텍처", "테스트 환경"],
            "focus": "기술 구현 세부사항, 성능 기준, 의존성"
        },
        "design": {
            "sections": ["디자인 시스템", "인터랙션 명세", "접근성 요구사항", "프로토타입 링크"],
            "focus": "사용자 경험, 브랜드 일관성, 접근성"
        },
        "qa": {
            "sections": ["테스트 범위", "자동화 대상", "엣지 케이스", "성능 기준"],
            "focus": "품질 기준, 테스트 시나리오, 회귀 테스트"
        },
        "customer_success": {
            "sections": ["기능 요약", "FAQ", "Onboarding 가이드", "에스컬레이션 경로"],
            "focus": "고객 커뮤니케이션, 지원 준비, 피드백 수집"
        }
    }

    def __init__(self, feature_name: str, context: dict):
        self.feature_name = feature_name
        self.context = context  # PRD, 기술 스펙 등
        self.client = Anthropic()
        self.briefs = {}

    def generate_team_brief(self, team: str) -> dict:
        """특정 팀용 인수인계 문서 생성"""
        template = self.TEAM_TEMPLATES.get(team, {})

        prompt = f"""
        당신은 시니어 PM입니다.
        다음 기능의 {team} 팀 인수인계 문서를 작성하세요.

        # 기능: {self.feature_name}
        # 컨텍스트:
        {json.dumps(self.context, ensure_ascii=False, indent=2)}

        # 포함할 섹션: {', '.join(template.get('sections', []))}
        # 초점: {template.get('focus', '')}

        # 요구사항:
        1. 각 섹션에 '왜(Why)' 설명 포함 — 결정의 이유가 핵심
        2. 알려진 리스크와 미해결 이슈 명시
        3. 의존성과 블로킹 사항 표시
        4. 성공 기준과 완료 조건 정의

        JSON 형식으로 출력하세요.
        """

        message = self.client.messages.create(
            model="claude-sonnet-4-20250514",
            max_tokens=4096,
            messages=[{"role": "user", "content": prompt}]
        )
        brief = json.loads(message.content[0].text)
        self.briefs[team] = brief
        return brief

    def generate_dependency_map(self) -> dict:
        """팀 간 의존성 맵 생성"""
        prompt = f"""
        다음 팀별 브리프를 분석해서 의존성 맵을 만드세요.

        {json.dumps(self.briefs, ensure_ascii=False, indent=2)}

        출력 형식 (JSON):
        {{
            "dependencies": [
                {{"from": "design", "to": "engineering", "item": "...", "blocking": true}},
                ...
            ],
            "critical_path": ["design → engineering → qa → launch"],
            "timeline": {{
                "design": {{"start": "W1", "end": "W2"}},
                ...
            }}
        }}
        """

        message = self.client.messages.create(
            model="claude-sonnet-4-20250514",
            max_tokens=2048,
            messages=[{"role": "user", "content": prompt}]
        )
        return json.loads(message.content[0].text)

    def generate_weekly_status(self, week: int, updates: dict) -> str:
        """주간 진행 현황 자동 생성"""
        prompt = f"""
        다음 정보로 주간 핸드오프 진행 현황을 작성하세요.

        기능: {self.feature_name}
        주차: Week {week}
        팀별 업데이트: {json.dumps(updates, ensure_ascii=False)}
        의존성 맵: {json.dumps(self.briefs, ensure_ascii=False)}

        포함 항목:
        1. 각 팀 상태 (🟢/🟡/🔴)
        2. 블로킹 이슈
        3. 위험도 매트릭스
        4. 다음 주 계획
        """

        message = self.client.messages.create(
            model="claude-sonnet-4-20250514",
            max_tokens=2048,
            messages=[{"role": "user", "content": prompt}]
        )
        return message.content[0].text


# === 실행 예시 ===
if __name__ == "__main__":
    generator = HandoffDocGenerator(
        feature_name="AI 문서 요약",
        context={
            "description": "문서를 AI로 2초 내에 3줄 요약",
            "target_users": "Pro/Enterprise 플랜",
            "tech_stack": "Claude API, Redis, PostgreSQL",
            "launch_date": "2026-04-01",
            "success_metrics": {
                "latency_p95": "< 2초",
                "accuracy": "> 90%",
                "adoption_rate": "> 30% (M1)"
            }
        }
    )

    # 팀별 브리프 생성
    for team in ["engineering", "design", "qa", "customer_success"]:
        brief = generator.generate_team_brief(team)
        print(f"\n{'='*50}")
        print(f"📋 {team.upper()} 팀 브리프")
        print(json.dumps(brief, ensure_ascii=False, indent=2))

    # 의존성 맵
    dep_map = generator.generate_dependency_map()
    print(f"\n{'='*50}")
    print("🗺️ 의존성 맵")
    print(json.dumps(dep_map, ensure_ascii=False, indent=2))
```

### Claude Code CLI: 핸드오프 자동화

```bash
# 1. 팀별 브리프 일괄 생성
python handoff_generator.py \
  --feature "AI 문서 요약" \
  --teams engineering,design,qa,customer_success \
  --output briefs/

# 2. 주간 상태 리포트 자동 발송
python handoff_generator.py \
  --mode weekly-status \
  --week 2 \
  --slack-channel "#ai-summary-launch"
```

---

## 📊 실행 결과 예시: 주간 진행 현황

```
# AI 요약 기능 진행 현황 (Week 2)

## 타임라인 & 의존성
┌─────────────────────────────┐
│ Design (W1-2) ─────────┐    │ 🟢 On Track
├─────────────────────────────┤
│ Engineering (W1-5)     │    │ 🟡 At Risk
│   ├─ API 설계         │    │    (디자인 지연)
│   ├─ Claude 통합      │    │
│   └─ 성능 최적화      │    │
├─────────────────────────────┤
│ QA (W2-4)             │    │ 🟢 Pending
│   └─ 테스트 케이스    │    │    (엔지니어링 대기)
├─────────────────────────────┤
│ Customer Success (W3-4) │   │ 🟢 Ready
│   └─ Onboarding Guide  │   │    (자료 준비 완료)
└─────────────────────────────┘

## 각 팀 상태

✅ Design
- High-fidelity 완성 (W1 목표 충족)
- 엔지니어링과 핸드오프 회의 완료
- Action: 세부 인터랙션 명세 추가 필요 (W2)

🟡 Engineering
- API 설계 진행 중 (진도 60%)
- 위험: Design 세부사항 대기 중
- Action: Design 명세 수령 후 W3 완성 예상

🟢 QA
- 테스트 케이스 템플릿 준비 완료
- Action: Engineering Beta 환경 준비 대기

## 블로킹 이슈
❌ Design → Engineering 의존성
- Status: 해결됨 (Handoff meeting 완료)
- Impact: Engineering W2 시작 가능

## 위험도
| 위험 | 영향 | 확률 | 상태 |
|-----|------|------|------|
| 정확도 80% 미만 | 출시 연기 | Low | Monitor |
| 성능 요구사항 미달 | 재최적화 | Medium | Watching |
| API 비용 초과 | 손실 | Low | Budget Cap 설정 |

## 다음 주 계획 (Week 3)
- Engineering: API 구현 완료 (100%)
- QA: 자동화 테스트 케이스 20개 작성
- Customer Success: FAQ 초안 완성
- PM: 출시 전 윤리 리뷰 시작
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 각 팀별 브리프에 '결정의 이유(why)'가 포함되어 있는지 확인하세요 — '뭘 했나'보다 '왜 했나'가 중요합니다
2. **[논쟁 지점]** 핸드오프 문서의 '상세도 수준'을 어디까지 할지는 팀 규모와 경험에 따라 다릅니다
3. **[자기 검증]** 브리프를 받을 팀의 리드 1명에게 보여주고 '이걸로 바로 시작할 수 있나?'를 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|------|-----------|------|
| ✅ 팀별 구체 브리프 | `stakeholder-alignment.md` | "팀별 알림장 + 핸드오프 통합" |
| ✅ 의존성 맵 | `ai-adoption-metrics.md` | "메트릭 리포팅 일정과 조율" |
| ✅ 진행 현황 | `press-release.md` | "출시 준비 진행률 공개" |
| 🔜 자동화 대시보드 | Claude Code `--daily-progress-sync` | Slack 자동 업데이트 |
