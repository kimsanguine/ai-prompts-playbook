# PM 프롬프트 시장 수요 리서치

> 조사일: 2026-03-11
> 목적: ai-pm-prompts 레포의 초기 프롬프트 선정 기준

---

## 1. PM들이 AI에 가장 많이 쓰는 영역

| 수요 순위 | 영역 | PM 시간 절약 효과 | 기존 프롬프트 공급 |
|-----------|------|-----------------|-----------------|
| 🥇 | **경쟁사 분석 / 감성 분석** | 높음 (40-60% 시간) | 많음 (영어) |
| 🥈 | **유저 리서치 합성** (피드백 → 인사이트) | 높음 | 중간 |
| 🥉 | **PRD / 스펙 작성** | 중간 | 많음 (영어) |
| 4 | **로드맵 우선순위 결정** | 중간 | 적음 |
| 5 | **이해관계자 커뮤니케이션** | 낮음 | 적음 |
| 6 | **프라이싱 전략** | 높음 | 거의 없음 |

**핵심 발견:** 영어권에서는 공급이 이미 있지만, **한국어 + AI 제품 특화** 조합은 0개.

---

## 2. PM의 주간 AI 활용 현황 (2025-2026)

AI가 PM 업무 시간의 40-60%를 절약할 수 있는 영역:
- **패턴 인식** — 대규모 데이터셋에서 패턴 추출
- **요약** — 긴 문서/회의록 핵심 추출
- **초안 작성** — PRD, 이메일, 프레젠테이션
- **반복 분석** — 경쟁사 모니터링, 리뷰 분석
- **리서치 합성** — 고객 피드백에서 테마 도출

### 일상 도구
- ChatGPT / Claude → 일일 업무
- Dovetail / Kraftful → 리서치 합성
- Gamma → 프레젠테이션
- Granola / Otter.ai → 회의 녹취

---

## 3. 기존 프롬프트 프레임워크

### WISER (Allie K. Miller)
- **W**hat: 무엇을 원하는가
- **I**nformation: 어떤 정보를 제공할 것인가
- **S**cope: 범위와 제약조건
- **E**xamples: 예시
- **R**estrictions: 제한사항

### SMART 변형
- **S**pecific: 명확하게
- **M**easurable: 정량적 요소 포함
- **A**ctionable: 구체적 출력물
- **R**elevant: 비즈니스 맥락 정렬
- **T**ime-bound: 범위와 제약 설정

### Role-Goal-Template-Context (4요소)
- **Role**: 스타일과 톤 설정
- **Goal**: 해결할 문제
- **Template**: 응답 구조 정의
- **Context**: 배경 정보

### 한계점
위 프레임워크들은 **"단발성 프롬프트"에 최적화**되어 있음.
질문 하나 → 답변 하나. PM 업무는 그렇게 안 돌아감.

---

## 4. 2025-2026 트렌드: 프롬프트에서 워크플로우로

### Prompt Chaining (프롬프트 체이닝)
복수의 프롬프트를 연결해서 복잡한 작업을 단계적으로 수행.
결과물이 다음 프롬프트의 입력이 되는 구조.

### Prompt Libraries (프롬프트 라이브러리)
재사용 가능한 템플릿을 조직 차원에서 관리.

### Prompt Testing (프롬프트 테스팅)
다른 모델에서 같은 프롬프트를 실행하여 결과 비교.

### Agentic Workflows
프롬프트를 넘어서 AI Agent가 능동적으로 작업을 수행하는 패턴.
agency-agents(27K Stars)가 이 트렌드를 증명.

---

## 5. 시사점: ai-pm-prompts 초기 프롬프트 선정

### 원칙
1. **수요 높은 영역부터** — 경쟁사 분석, 유저 리서치, PRD
2. **한국 SaaS 컨텍스트** — 네이버/카페 리뷰, B2B 특성, 가격 민감도
3. **AI 제품 PM 특화** — AI 품질(정확도, 할루시네이션), 모델 평가
4. **워크플로우 체인** — 프롬프트 간 연결 (결과 → 다음 입력)

### 초기 프롬프트 후보 (수요 × 차별화)
1. `competitor-sentiment-analysis.md` — 수요 1위 + 감성 분석 차별화
2. `user-problem-hypothesis.md` — 수요 2위 연결
3. `prd-for-ai-feature.md` — 수요 3위 + AI 제품 특화
4. `feature-prioritization-rice.md` — 수요 4위 + 데이터 기반
5. `ai-product-positioning.md` — AI 제품 포지셔닝 (빈 영역)

---

## Sources

- [50+ AI Prompts Product Managers Use Weekly (2026 Edition) - Bagel.ai](https://bagel.ai/blog/50-ai-prompts-product-managers-use-weekly-2026-edition/)
- [25 AI Prompts for Product Managers - Glean](https://www.glean.com/blog/25-ai-prompts-for-product-managers)
- [6 AI Prompt Templates - Productboard](https://www.productboard.com/blog/6-ai-prompt-templates-for-product-managers/)
- [Prompt Engineering in 2025 - Aakash Gupta](https://www.news.aakashg.com/p/prompt-engineering)
- [Prompt Engineering for PMs - ProdPad](https://www.prodpad.com/blog/prompt-engineering-for-product-managers/)
- [AI for Product Managers - monday.com](https://monday.com/blog/rnd/ai-for-product-managers/)
- [Prompt Engineering Guide 2026 - Lakera](https://www.lakera.ai/blog/prompt-engineering-guide)
- [Prompt Engineering Best Practices 2025 - CodeSignal](https://codesignal.com/blog/prompt-engineering-best-practices-2025/)
- [Prompts for Product Managers - Kraftful](https://www.kraftful.com/prompts-for-pm)
- [AI for Product Managers - prodmgmt.world](https://www.prodmgmt.world/blog/ai-for-product-managers)
