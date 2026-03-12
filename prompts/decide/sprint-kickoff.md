# 🚀 스프린트 킥오프 (Strategic Sprint Kickoff)

> 예상 소요: 5분 (Quick) / 30분 (Deep) / 40분+ (Build)
> 워크플로우: `backlog-prioritization.md` → (이 파일) → `feature-prioritization.md`

---

## 🎯 이 프롬프트가 해결하는 문제

로드맵이 결정되었습니다. 이제 **2주 스프린트를 성공시키기 위해 팀을 정렬**해야 합니다. 특히 AI 팀은 다음과 같은 이유로 복잡합니다:

1. **역할이 겹친다**: PM이 데이터 정제를 하고, Engineer가 고객과 대화하고, Designer가 모델을 평가합니다
2. **기술 블로커가 예측 불가능**: ML 모델은 계획대로 진행되지 않습니다
3. **의존성이 크다**: 데이터팀 → ML팀 → 프로덕트팀의 순차 진행

**스프린트 킥오프 프롬프트**는 다음을 보장합니다:
- 모든 팀 멤버가 스프린트 목표를 이해
- PM/Designer/Engineer/ML Engineer/Data 팀이 협력
- 일일 싱크(Daily Standup) 구조 제공
- 위험 요소를 사전에 파악

---

## 📥 이전 프롬프트에서 받는 입력

> `backlog-prioritization.md`에서 정렬된 백로그를 스프린트로 실행하기 위한 킥오프 설계에 사용합니다.

이전 프롬프트 결과에서 **스프린트 백로그, 팀 용량, 의존성 맵**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 스프린트 시작에 필요한 핵심 정보를 정리할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
당신은 AI 팀의 스프린트 마스터입니다.

{SPRINT_SCOPE}에 기반해 스프린트 킥오프를 구성하세요:

1. 스프린트 목표 (1-2 문장):
   [구체적, 측정 가능한 목표]

2. 팀 구성 (역할별):
   - PM: {이름}
   - Designer: {이름}
   - Engineer: {이름}
   - ML Engineer: {이름}
   - Data Engineer: {이름}

3. 스프린트 스토리 (우선순위순):
   1. [스토리] ({포인트})
   2. [스토리] ({포인트})
   ...

4. 일일 싱크 시간:
   시간: {시간}
   장소/링크: {링크}

5. 위험 요소:
   - 위험 1: [정의] → 대응: [조치]
   - 위험 2: ...

6. 성공 기준:
   - 스프린트 완료율 80% 이상
   - 결함율 0% (자동 테스트)
   - 성능 저하 없음
```

💡 **Quick Tips:**
- 스프린트 목표는 "다 완료하기"가 아니라 "고객 문제 해결"이어야 합니다
- AI 팀의 일일 싱크는 최소 15분 (일반 팀은 15분, AI 팀은 블로커 토론으로 더 필요)
- 첫 2일은 데이터/모델 준비에만 집중하세요. UI 개발은 그 뒤에
- 스프린트 중반(목요일)에 "예상 완료율" 검토 회의를 추가하세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 이전 스프린트 미완료 항목이 많음 | 캐리오버 항목을 먼저 정리하세요. 3회 이상 캐리오버 시 재분류 필요 |
| 팀원 부재/변동 | 가용 용량을 정확히 산정하고, 크리티컬 패스에 백업 담당자를 지정 |
| 목표가 불명확 | "이번 스프린트가 끝나면 X가 가능해진다"로 한 문장 정의 |
| 갑작스러운 요구사항 변경 | 버퍼(20%)를 확보하고, 변경 시 무엇을 빼야 하는지 명시 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 스프린트 킥오프를 체계적으로 진행하고 싶은 분입니다.
목표, 리스크, 역할 배분까지 완결적으로 준비하고 싶다면 이걸 써보세요.

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
당신은 스프린트 킥오프 진행자이자 AI 팀 협력 촉진자입니다.
- PM: 고객 가치 전달, 의사 결정
- Designer: UX 검증, 사용자 피드백
- Engineer: 기술 구현, 성능 최적화
- ML Engineer: 모델 개선, 실험
- Data Engineer: 데이터 파이프라인, 인프라

# 목표
스프린트 계획을 팀이 이해하고 동의하며,
AI 팀의 특수한 의존성(데이터 → 모델 → 제품)을 관리하여
2주 내에 고객 가치를 전달하는 스프린트를 구성합니다.

<!-- 💬 왜 스프린트 킥오프가 중요한가?
AI 팀은 비AI 팀 대비 3배 더 자주 계획이 망합니다.
- 데이터가 예상보다 작음 (모델 정확도 낮음)
- 모델 학습이 예상보다 오래 걸림
- 한 팀의 지연이 다른 팀의 블로커가 됨

스프린트 킥오프에서 이런 위험을 미리 파악하고 대응하면
후반부 야근을 50% 줄일 수 있습니다.
-->

# Reasoning Strategy

## Step 1: 스프린트 목표 정의

### 측정 가능한 목표 설정
```
나쁜 목표: "정확도를 개선한다"
좋은 목표: "고객 문제 분류 정확도를 70%에서 75%로 개선하고,
         자동 응답 가능한 이슈 비율을 50%에서 60%로 높인다"

좋은 스프린트 목표의 특징:
1. 구체적 (Specific): 정확도 숫자로 명시
2. 측정 가능 (Measurable): 메트릭으로 추적 가능
3. 달성 가능 (Achievable): 2주 내 가능한가?
4. 관련성 있음 (Relevant): 비즈니스 목표와 맞는가?
5. 시간 제한 (Time-bound): 2주 스프린트 내

<!-- 💬 AI 팀의 목표는 기술이 아니라 지표입니다
"BERT 모델을 파인튜닝한다" (기술) → "정확도 5% 개선" (지표)
기술은 수단이고, 지표가 목표입니다.
-->

예시 (AI 제품 팀):

**좋은 예:**
- "고객 이슈 자동 분류 정확도 70% → 75% 달성"
- "멀티채널 기본 구현 (이메일, Slack) 완료하고 고객 테스트 시작"
- "추천 엔진의 대기 시간을 5초에서 2초 이하로 단축"

**나쁜 예:**
- "백로그 스토리 완료"
- "버그 3개 수정"
- "코드 리팩토링"
```

### Product Trio 목표 정렬
```
각 역할의 관점에서 스프린트 목표를 다시 작성하세요:

**PM 관점:**
- 비즈니스 임팩트: 얼마나 더 많은 고객이 가치를 느낄 것인가?
- 예: "자동 분류로 CS 팀 20% 시간 절감"

**Designer 관점:**
- 사용자 경험 개선: UI/UX 측면에서 무엇이 개선되는가?
- 예: "결과 확인 후 1클릭 수정 가능하도록 개선"

**Engineer 관점:**
- 기술 구현: 아키텍처, 성능, 확장성 측면에서?
- 예: "모델 API 응답 시간 5초 → 2초 최적화"

**ML Engineer 관점:**
- 모델 개선: 정확도, F1 스코어, 성능 측정 지표는?
- 예: "정확도 70% → 75%, F1 score 0.68 → 0.73"

**Data Engineer 관점:**
- 데이터 파이프라인: 데이터 정제, 전처리, ETL 안정성?
- 예: "일일 1000개 이슈 수집 및 자동 전처리 파이프라인 구축"

<!-- 💬 각 역할이 다르게 스프린트를 봅니다
PM은 고객 만족도, Engineer는 코드 품질, ML은 정확도를 봅니다.
이들을 정렬하지 않으면 스프린트 후반 충돌합니다.
-->
```

## Step 2: AI 팀 특화 의존성 맵

### 타임라인 기반 의존성
```
AI 프로젝트의 일반적 흐름:

Week 1:
├─ Day 1-2: 데이터 준비 (Data + PM)
│  ├─ 작업: 고객 데이터 수집, 결측값 처리, 레이블링
│  ├─ 산출물: 학습용 데이터셋 (예: 1000개 샘플)
│  └─ 정의된 완료: "데이터 QA 통과, 레이블 오류율 < 1%"
│
├─ Day 3-4: 모델 학습 (ML Engineer)
│  ├─ 의존성: Day 1-2 데이터셋 필요
│  ├─ 작업: 모델 파인튜닝, 하이퍼파라미터 튜닝
│  └─ 산출물: 학습된 모델 체크포인트
│
└─ Day 5: 평가 (ML + Engineer)
   ├─ 작업: 검증 세트 평가, 성능 지표 계산
   └─ 산출물: 성능 리포트

Week 2:
├─ Day 1-3: 배포 준비 (Engineer)
│  ├─ 의존성: 검증된 모델
│  ├─ 작업: API 구현, 성능 최적화, 테스트
│  └─ 산출물: 프로덕션 모델 배포
│
├─ Day 2-4: UI/UX 개선 (Designer)
│  ├─ 의존성: 데이터 (고객 피드백, 현재 문제점)
│  ├─ 작업: 새 기능 설계, 프로토타입
│  └─ 산출물: 디자인 스펙
│
└─ Day 4-5: A/B 테스트 설계 (PM + Engineer)
   ├─ 의존성: 배포된 모델 + 디자인 스펙
   ├─ 작업: 대조군 설정, 메트릭 정의
   └─ 산출물: 테스트 계획

<!-- 💬 AI 팀의 병목: 데이터
데이터 준비가 지연되면 모든 팀이 블로커됩니다.
스프린트 시작 전에 데이터 준비 리스크를 반드시 확인하세요.
-->

**의존성 매핑 체크리스트:**
- [ ] 데이터는 준비되었는가? (Day 1에 시작 가능한가?)
- [ ] 모델 학습 환경(GPU)은 확보되었는가?
- [ ] Designer는 현재 사용자 데이터(피드백)를 가지고 있는가?
- [ ] 배포 환경(AWS, GCP)은 준비되었는가?
- [ ] A/B 테스트 인프라(Mixpanel, Amplitude)는 있는가?
```

### 병렬화 기회
```
완전히 독립적인 작업을 병렬로:

✓ 병렬 가능:
- Data: 데이터 수집 (Day 1-2)
- Designer: 현재 사용자 문제점 분석 (Day 1-2)
- Engineer: 배포 인프라 준비 (Day 1-3)

✗ 순차 필수:
- Data → ML: 데이터 없으면 학습 불가능
- ML → Engineer: 모델 없으면 배포 불가능
- Designer → Engineer: 디자인 없으면 구현 불가능 (부분 병렬 가능)
```

## Step 3: 역할별 담당 및 용량 확인

### 팀 구성 및 용량
```
다음 정보를 수집하고 정렬하세요:

**PM (1명)**
- 용량: 100% (스프린트 전담)
- 책임:
  * 스프린트 목표 전달 및 정렬
  * 일일 스탠드업 진행
  * 블로커 해결 (결정권자로서)
  * 고객 피드백 수집 (Designer와 함께)
- 시간 배분: 30% 회의 / 40% 고객 대화 / 30% 문서화

**Designer (1명)**
- 용량: 80% (병렬 프로젝트 1개 있음)
- 책임:
  * 현재 UX 문제점 분석
  * 새 모델 결과를 UI로 표현
  * 사용자 테스트 진행
- 시간 배분: 40% 디자인 / 30% 리서치 / 30% 구현 협력

**Engineer (2명)**
- 용량: 80% (온콜 담당 1명)
- 책임:
  * 모델 배포 API 개발
  * 성능 최적화
  * 배포 및 모니터링
- 시간 배분: 50% 개발 / 30% 테스트 / 20% 리뷰

**ML Engineer (1명)**
- 용량: 100%
- 책임:
  * 모델 파인튜닝
  * 성능 평가
  * 실험 로깅 (MLflow 등)
- 시간 배분: 60% 모델 개발 / 25% 평가 / 15% 문서화

**Data Engineer (0.5명, 공유 리소스)**
- 용량: 50% (다른 팀 지원)
- 책임:
  * 데이터 수집 및 정제
  * 파이프라인 모니터링
  * 데이터 품질 보증
- 시간 배분: 70% 데이터 작업 / 30% 기술 부채

<!-- 💬 AI 팀은 데이터 엔지니어가 부족한 경향
많은 팀에서 "PM이나 ML이 데이터 작업도 한다"고 가정하는데
이건 품질 저하로 이어집니다.
가능하면 전담 Data Engineer를 두세요.
-->

**용량 검증:**
- 스프린트 목표를 달성하는 데 필요한 총 작업 시간?
- 팀의 가용 시간(각 팀원 시간 × 2주)?
- 차이가 20% 이상이면 스프린트 범위 축소?
```

## Step 4: 일일 스탠드업 구조

### Daily Standup 템플릿
```
**시간:** 매일 9:30 (회의실/Zoom)
**지속 시간:** 15분 (AI 팀은 예상 외 질문 많으므로 여유 있게)

**순서 (역할별):**

1. Data Engineer (2분)
   - 어제 수행: "1000개 이슈 데이터 수집 완료"
   - 오늘 계획: "데이터 레이블링 및 QA"
   - 블로커: "레이블러 부족 (PM과 협력 필요)"

2. ML Engineer (3분)
   - 어제 수행: "모델 파인튜닝 시작"
   - 오늘 계획: "학습 완료 및 검증"
   - 블로커: "GPU 메모리 부족? Engineer와 상담 필요"

3. Engineer (2분)
   - 어제 수행: "API 기본 구조 완료"
   - 오늘 계획: "모델 통합 및 성능 테스트"
   - 블로커: "ML 모델 체크포인트 대기 중"

4. Designer (1분)
   - 어제 수행: "사용자 5명 인터뷰 완료"
   - 오늘 계획: "UI 프로토타입 작성"
   - 블로커: "없음"

5. PM (2분)
   - 어제 수행: "고객 2개사 피드백 수집"
   - 오늘 계획: "스프린트 진행률 모니터링"
   - 블로커: "Data 레이블러 확보 (HR과 협의)"

6. 팀 토론 (5분)
   - "Data의 레이블러 부족"이 공통 블로커
   - 해결: PM이 HR과 협의, 내일까지 3명 확보
   - 영향: 모델 학습 스케줄 변경 없음 ✓

<!-- 💬 AI 팀 스탠드업의 함정
각자 2-3분이면 충분하지만, 실제로는 10분간 기술 토론하다가
30분 회의가 됩니다.
기술 토론은 "별도 Deep Dive" 시간을 따로 만드세요.
-->

**스탠드업 규칙:**
- 정확히 시간에 시작 (늦으면 5분 짧게)
- 각자 2분 이내 (시간 초과 → 별도 회의)
- 블로커만 공유 (상세 내용은 따로)
- PM이 의사결정권자 (블로커 즉시 해결)
```

## Step 5: 위험 요소 및 대응

### AI 팀 특화 위험 요소
```
**위험 1: 데이터 부족 (Severity: High)**
- 정의: 레이블링 인력 부족으로 학습 데이터 부족
- 영향: ML 모델 정확도 목표 미달 가능
- 확률: 50% (유사 경험 있음)
- 대응 1순위: PM이 Day 1부터 레이블러 3명 확보
- 대응 2순위: 데이터 부족 시 현재 1000개 데이터로 학습 (정확도 저하 예상)
- 신호: Day 2 말까지 레이블 완료도 < 80%

**위험 2: 모델 학습 시간 초과 (Severity: High)**
- 정의: GPU 학습이 예상 24시간을 초과
- 영향: 배포 일정 지연, Week 2 초반 배포 불가능
- 확률: 40% (새 모델은 불확실)
- 대응 1순위: ML Engineer가 Day 3 오전 중간 점검 (예상 소요 시간 재계산)
- 대응 2순위: 하이퍼파라미터 단순화로 학습 시간 단축
- 신호: Day 3 정오 학습 완료율 < 30%

**위험 3: 배포 환경 문제 (Severity: Medium)**
- 정의: AWS/GCP 리소스 부족 또는 권한 이슈
- 영향: 모델 배포 지연
- 확률: 30% (인프라팀 의존성)
- 대응 1순위: Engineer가 Day 1 오후에 인프라 점검 + 리소스 사전 예약
- 신호: Engineer가 Day 1 점검에서 이슈 발견

**위험 4: Designer와 ML의 기대 불일치 (Severity: Medium)**
- 정의: ML 정확도가 80% 목표 미달, Designer가 UI 설계 불가능
- 영향: 사용자 경험 개선 불가, 스프린트 목표 미달
- 확률: 60% (AI의 일반적 현상)
- 대응 1순위: Day 3에 중간 평가, 정확도 예상값을 Designer와 공유
- 대응 2순위: "정확도 75%라도 UI로 사용성 보완" 계획 수립
- 신호: Day 3 ML 평가 결과 < 75% 정확도

<!-- 💬 AI 팀 위험은 예측 불가능합니다
100% 완벽한 계획을 세울 수 없으므로
"매일 위험을 평가하고 즉시 대응"하는 태도가 중요합니다.
-->

**위험 관리 프로세스:**
- Day 1: 위험 식별 및 공유
- Day 2-4: 매일 위험 신호 모니터링
- 신호 발견 시: PM이 팀과 즉시 협의 (의사결정)
- Day 5: 중간 평가 및 계획 재조정 (필요 시)
- Day 10: 최종 평가 및 남은 1주일 계획 조정
```

## Step 6: 스프린트 성공 기준

### 정의된 완료 (Definition of Done, DoD)
```
모든 스토리는 다음을 만족해야 "완료"로 표시:

**코드 품질:**
- [ ] 코드 리뷰 1명 이상 승인
- [ ] 유닛 테스트 80% 이상 커버리지
- [ ] 자동 테스트 100% 통과

**문서화:**
- [ ] API 문서 작성 (Swagger/OpenAPI)
- [ ] 변경사항 README 업데이트
- [ ] 모델 성능 리포트 작성

**성능:**
- [ ] 응답 시간 SLA 충족 (예: P95 < 2초)
- [ ] 메모리 사용량 < 500MB
- [ ] 에러율 < 0.1%

**모니터링:**
- [ ] 로깅 추가 (에러, 성능)
- [ ] 대시보드 구성 (실시간 메트릭)
- [ ] 알람 설정 (이상 감지)

**배포:**
- [ ] Staging 환경 테스트 완료
- [ ] 롤백 계획 수립
- [ ] 프로덕션 배포 완료 (또는 차주 계획)

<!-- 💬 DoD 없으면 "80% 완료" 상태가 자주 발생합니다
모든 팀원이 "완료"의 정의에 동의하지 않으면
스프린트 종료 후 다시 작업하게 됩니다.
-->
```

### 스프린트 완료 기준
```
스프린트 목표 달성 확인:

**정량 기준:**
- [ ] 스토리 포인트 완료율 ≥ 85%
- [ ] 정확도 목표 달성 (70% → 75%)
- [ ] 배포 완료 (또는 차주 확정)

**정성 기준:**
- [ ] 팀 만족도 (회고에서 평가)
- [ ] 고객 피드백 긍정적 (테스트 사용자 3명 이상)
- [ ] 기술 부채 증가 없음 (새 기술 부채 0)

**개선 기준:**
- [ ] 지난 스프린트 회고 항목 3개 이상 개선
- [ ] 속도(Velocity) 안정적 (±10%)
```

# 💡 Deep Tips:

- **AI 팀은 매일 위험을 평가합니다**: 스탠드업이 가장 중요한 회의입니다
- **데이터 준비가 모든 것을 결정합니다**: Day 1-2가 스프린트 전체를 좌우합니다
- **기술 토론은 별도로**: 스탠드업 중 기술 토론하면 30분 회의가 됩니다
- **중간 평가가 필수**: Day 5에 "계획대로 진행되는가?" 검토하면 지연을 조기 발견할 수 있습니다
- **한국 AI 팀은 야근이 많습니다**: 이는 스프린트 계획 오류입니다. 현실적인 계획을 세우세요
```



### 🇰🇷 한국 팀 스프린트 운영 특화

```
한국 개발팀의 스프린트 킥오프 시 고려사항:

1. **한국 개발팀 운영 특성 (주 52시간제 영향)**:
   - 법정 근무시간: 주 52시간 (월-금 기준 1일 10.4시간)
   - 스프린트 용량: 이론적 40시간 × 2주 = 80시간 (실제: 60시간 권장)
   - 야근 문화 감소: 과거 야근 중심 → 현재 정규시간 내 완료 강조
   - 조정: Velocity 계산 시 80시간 기준이 아닌 60시간으로 설정

2. **한국 스프린트 도구 및 환경**:
   - Jira Korea 서버: 기술팀이 모두 Jira 숙련 (한국식 워크플로우 커스터마이징 필요)
   - Notion 워크스페이스: 한국 팀이 Notion 무료 버전 선호 → 데이터 관리 방식 조정
   - GitHub vs GitLab: 공개 코드(GitHub) vs 비공개 코드(GitLab Enterprise) 선호
   - 설정: Jira 한글화 (필터, 라벨, 상태 모두 한글로) 필수

3. **한국 팀 커뮤니케이션 패턴**:
   - 카카오워크: 대기업 선호 (메신저, 일정, 화상회의 통합)
   - Slack: 스타트업 선호 (국제팀 협업, 봇 활용)
   - 대면 회의: 원격(비용 절감) vs 대면(신뢰 구축) 균형 필요
   - 스탠드업: 온라인(아침 9-10시) vs 대면(주 2회) 하이브리드 권장

4. **한국 기업 스프린트 현실 (계획 vs 실행)**:
   - 2주 스프린트: Agile 명확 但 실제는 워터폴 혼용 (분기 단위 큰 목표 → 주 단위 세부 실행)
   - 우선순위 변경: 월요일 스프린트 계획 → 수요일 경영진 지시 변경 (40% 확률)
   - 버퍼 필수: 20% 버퍼 추가 (경영진 지시, 외부 이슈 대응)
   - 회의 오버헤드: 계획 회의(2시간) + 스탠드업(15분 × 10일) + 회고(1시간) ≈ 4시간

5. **한국 개발자 채용 시장이 스프린트에 미치는 영향**:
   - 개발자 공급 부족: 신입 채용 어려움 → 팀 유지 어려움
   - 이직률 높음: 평균 1.5-2년 단위 이직 → 온보딩 비용 (스프린트 속도 -20%)
   - 리소스 제약: 1명 이탈 시 2주 스프린트 불가능 → 스프린트 규모 축소 필수
   - 조정: 팀 규모 50% 초과 인원 여유 (이직 대비)
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 스프린트 목표 합의 어려움 | OKR과 연결해서 "이번 스프린트가 어떤 KR에 기여하는가?"로 정렬 |
| 2단계 | 작업 분해가 어려움 | "하루 이내에 끝낼 수 있는가?"가 아니면 더 쪼개세요 |
| 3단계 | 리스크 식별이 안 됨 | "이 작업이 안 되면 스프린트 목표가 실패하는가?" 체크 |
| 4단계 | 역할 배분 충돌 | 스킬셋 × 관심사 매트릭스로 투명하게 배분 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 스프린트 킥오프 문서 생성과 작업 배분을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
격주마다 반복되는 킥오프 준비를 자동화하면, PM이 전략적 사고에 더 집중할 수 있습니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python 스크립트: 스프린트 킥오프 및 일일 추적

```python
#!/usr/bin/env python3
"""
스프린트 킥오프 및 일일 진행률 추적
- 스프린트 목표 설정 및 팀 정렬
- 일일 스탠드업 항목 자동 정리
- 위험 요소 추적
- 진행률 대시보드
"""

import json
from datetime import datetime, timedelta
from anthropic import Anthropic

client = Anthropic()

class SprintKickoff:
    def __init__(self, sprint_name, start_date, duration_days=14):
        self.sprint_name = sprint_name
        self.start_date = datetime.fromisoformat(start_date)
        self.duration_days = duration_days
        self.end_date = self.start_date + timedelta(days=duration_days)
        self.team = {}
        self.stories = []
        self.standup_log = []
        self.risks = []

    def add_team_member(self, role, name, capacity_percent=100):
        """팀 멤버 추가"""
        self.team[role] = {
            "name": name,
            "capacity": capacity_percent,
            "daily_hours": (capacity_percent / 100) * 8,  # 8시간 기준
            "standup_updates": [],
            "blockers": []
        }

    def add_story(self, story_id, title, story_points, owner, dependencies=None):
        """스토리 추가"""
        story = {
            "id": story_id,
            "title": title,
            "points": story_points,
            "owner": owner,
            "dependencies": dependencies or [],
            "status": "Backlog",
            "progress": 0,  # 0-100%
            "subtasks": []
        }
        self.stories.append(story)

    def add_risk(self, risk_id, title, severity, probability, impact, mitigation):
        """위험 요소 추가"""
        risk = {
            "id": risk_id,
            "title": title,
            "severity": severity,  # Low, Medium, High
            "probability": probability,  # 0-100%
            "impact": impact,  # 낮음, 중간, 높음
            "mitigation": mitigation,
            "status": "Active",
            "review_date": None
        }
        self.risks.append(risk)

    def log_standup(self, day, role, yesterday, today, blockers):
        """일일 스탠드업 로깅"""
        standup = {
            "day": day,
            "date": (self.start_date + timedelta(days=day-1)).isoformat(),
            "role": role,
            "yesterday": yesterday,
            "today": today,
            "blockers": blockers
        }
        self.standup_log.append(standup)

        # 블로커가 있으면 위험 리스트 자동 업데이트
        if blockers:
            print(f"\n⚠️  Day {day} {role} 블로커 발견:")
            for blocker in blockers:
                print(f"   - {blocker}")

    def generate_kickoff_deck(self):
        """스프린트 킥오프 문서 생성 (AI 활용)"""
        prompt = f"""당신은 AI 제품 스프린트 마스터입니다.

스프린트: {self.sprint_name}
기간: {self.start_date.date()} ~ {self.end_date.date()}
팀 구성: {json.dumps({k: v['name'] for k, v in self.team.items()}, ensure_ascii=False)}
스토리: {json.dumps([s['title'] for s in self.stories], ensure_ascii=False)}

다음을 포함한 스프린트 킥오프 문서를 생성하세요:
1. 스프린트 목표 (명확하고 측정 가능)
2. 팀 역할별 책임
3. 의존성 다이어그램 (각 역할의 순서)
4. 일일 마일스톤 (Day 1-14)
5. 성공 기준 (정량적)

마크다운 형식으로 응답하세요."""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=3000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        print("="*60)
        print(f"🚀 {self.sprint_name} 킥오프 문서")
        print("="*60)
        print(response.content[0].text)

    def track_progress(self):
        """스프린트 진행률 추적"""
        total_points = sum(s["points"] for s in self.stories)
        completed_points = sum(
            s["points"] for s in self.stories if s["status"] == "Done"
        )
        progress_percent = (completed_points / total_points * 100) if total_points > 0 else 0

        print("\n" + "="*60)
        print("📊 스프린트 진행률")
        print("="*60)
        print(f"전체 포인트: {total_points}")
        print(f"완료 포인트: {completed_points}")
        print(f"진행률: {progress_percent:.1f}%")
        print()

        # 역할별 진행률
        print("📋 역할별 진행률:")
        for role in self.team:
            role_stories = [s for s in self.stories if s["owner"] == role]
            if role_stories:
                role_points = sum(s["points"] for s in role_stories)
                role_completed = sum(
                    s["points"] for s in role_stories if s["status"] == "Done"
                )
                role_progress = (
                    (role_completed / role_points * 100) if role_points > 0 else 0
                )
                print(f"  {role}: {role_completed}/{role_points} ({role_progress:.0f}%)")

        # 위험 상태
        print("\n⚠️  활성 위험:")
        active_risks = [r for r in self.risks if r["status"] == "Active"]
        if active_risks:
            for risk in active_risks:
                print(f"  - {risk['title']} (심각도: {risk['severity']}, 확률: {risk['probability']}%)")
        else:
            print("  없음 ✓")

    def generate_daily_report(self, day):
        """일일 리포트 자동 생성"""
        day_standups = [s for s in self.standup_log if s["day"] == day]

        if not day_standups:
            print(f"Day {day} 스탠드업 기록이 없습니다.")
            return

        report_prompt = f"""당신은 AI 제품 팀의 스프린트 레포트 작성자입니다.

Day {day} 스탠드업 기록:
{json.dumps(day_standups, ensure_ascii=False, indent=2)}

다음을 포함한 일일 리포트를 작성하세요:
1. 어제 완료한 주요 항목
2. 오늘의 계획
3. 공통 블로커 및 해결 방안
4. 의사결정 필요 사항

마크다운 형식으로 응답하세요."""

        response = client.messages.create(
            model="claude-opus-4-6",
            max_tokens=1000,
            messages=[
                {"role": "user", "content": report_prompt}
            ]
        )

        print(f"\n{'='*60}")
        print(f"📅 Day {day} 일일 리포트 ({day_standups[0]['date']})")
        print(f"{'='*60}")
        print(response.content[0].text)

    def export_sprint(self, filename):
        """스프린트 정보를 JSON으로 저장"""
        export_data = {
            "sprint_name": self.sprint_name,
            "start_date": self.start_date.isoformat(),
            "end_date": self.end_date.isoformat(),
            "team": self.team,
            "stories": self.stories,
            "risks": self.risks,
            "standup_log": self.standup_log
        }

        with open(filename, 'w', encoding='utf-8') as f:
            json.dump(export_data, f, ensure_ascii=False, indent=2)

        print(f"\n💾 스프린트 저장: {filename}")


# 실행 예시
if __name__ == "__main__":
    sprint = SprintKickoff("Sprint 10: 정확도 개선", "2026-03-11")

    # 팀 구성
    sprint.add_team_member("PM", "김신문", 100)
    sprint.add_team_member("Designer", "이디자인", 80)
    sprint.add_team_member("Engineer", "박엔지니어", 80)
    sprint.add_team_member("ML Engineer", "이엠엘", 100)
    sprint.add_team_member("Data Engineer", "정데이터", 50)

    # 스토리 추가
    sprint.add_story("STORY_001", "데이터 수집 및 정제", 3, "Data Engineer")
    sprint.add_story("STORY_002", "모델 파인튜닝", 5, "ML Engineer", ["STORY_001"])
    sprint.add_story("STORY_003", "API 구현 및 배포", 5, "Engineer", ["STORY_002"])
    sprint.add_story("STORY_004", "UI/UX 개선", 3, "Designer", ["STORY_002"])
    sprint.add_story("STORY_005", "A/B 테스트 설계", 2, "PM", ["STORY_003"])

    # 위험 요소 추가
    sprint.add_risk(
        "RISK_001",
        "데이터 수집 지연",
        "High",
        50,
        "Model training 지연",
        "Day 1부터 레이블러 3명 확보"
    )

    sprint.add_risk(
        "RISK_002",
        "GPU 메모리 부족",
        "Medium",
        30,
        "Model training 중단",
        "사전에 GPU 예약 및 모니터링"
    )

    # 킥오프 문서 생성
    sprint.generate_kickoff_deck()

    # 일일 스탠드업 로깅 (Day 1)
    print("\n" + "="*60)
    print("📝 Day 1 스탠드업 로깅")
    print("="*60)

    sprint.log_standup(
        day=1,
        role="Data Engineer",
        yesterday="스프린트 시작",
        today="데이터 수집 시작, 1000개 샘플 목표",
        blockers=["레이블러 2명 부족 (목표 3명)"]
    )

    sprint.log_standup(
        day=1,
        role="Engineer",
        yesterday="배포 환경 준비",
        today="API 구조 설계",
        blockers=[]
    )

    # 일일 리포트
    sprint.generate_daily_report(1)

    # 진행률 추적
    sprint.track_progress()

    # 저장
    sprint.export_sprint("sprint_10_kickoff.json")
```

### Claude Code CLI 실행
```bash
cd /path/to/ai-pm-prompts
claude code --exec sprint-kickoff.py --model claude-opus-4-6
```

---

## 📊 실행 결과 예시

### 스프린트 목표

**Sprint 10: 정확도 개선 및 사용자 만족도 증대**

- **목표**: 고객 문제 분류 정확도 70% → 75% 달성하고, 자동 응답 기능으로 CS팀 응답 시간 20% 단축
- **기간**: 2주 (2026-03-11 ~ 2026-03-24)
- **팀**: PM(김신문) / Designer(이디자인) / Engineer(박엔지니어) / ML(이엠엘) / Data(정데이터)
- **완료 기준**: 정확도 75% 달성 + 자동 응답 비율 60% + 고객 테스트 3개사 완료

### 일일 마일스톤

| Day | Data 팀 | ML 팀 | Engineer | Designer | PM |
|---|---|---|---|---|---|
| 1-2 | 데이터 수집/정제 | - | 배포 인프라 준비 | 사용자 조사 | 스프린트 정렬 |
| 3-5 | 데이터 QA | 모델 파인튜닝 | API 개발 | UI 설계 | 고객 피드백 |
| 6-7 | - | 평가 및 분석 | 성능 최적화 | UI 구현 | 테스트 계획 |
| 8-10 | - | 문서화 | 배포 | 사용자 테스트 | 메트릭 검증 |
| 11-14 | - | - | 모니터링 | 사용성 개선 | 회고 및 마무리 |

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 스프린트 목표가 '기능 완성'이 아닌 '사용자 가치 전달'로 표현되어 있는지 확인하세요
2. **[논쟁 지점]** 스프린트 기간을 1주 vs 2주로 할지는 팀 성숙도와 배포 파이프라인에 따라 다릅니다
3. **[자기 검증]** 스프린트 목표를 '이 스프린트가 끝나면 사용자가 할 수 있는 것'으로 표현할 수 있는지 확인하세요

---

## 🔗 다음 단계

| 프롬프트 | 목적 | 연결 |
|---|---|---|
| `backlog-prioritization.md` | 스프린트 스토리를 로드맵으로 정렬 | 로드맵 → 스프린트 계획 |
| `feature-prioritization.md` | 스프린트 중 기능별 우선순위 조정 | 스프린트 도중 변경 시 활용 |
| `decision-canvas.md` | 스프린트 중 의사결정 필요 시 활용 | 블로커 해결을 위한 의사결정 |
