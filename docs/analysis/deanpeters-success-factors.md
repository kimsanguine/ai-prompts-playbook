# deanpeters 성공 요인 심층 분석 + 프롬프트 구조 재설계 근거

> 작성일: 2026-03-11
> 목적: 기존 v1 전략의 한계를 파악하고 v2 재설계의 근거를 수립

---

## 1. deanpeters가 709 Stars를 모은 3가지 핵심 이유

### 1-1. "Teaching through doing" 접근
- 프롬프트 안에 HTML 주석 블록(`<!-- 설명 -->`)을 넣어 "왜 이 구조가 작동하는지" 학습하게 만듦
- 단순 템플릿이 아니라 **교육 콘텐츠**
- 사용하면서 동시에 프롬프트 엔지니어링을 배우는 구조

### 1-2. "Guided Generation" 패턴
- AI가 질문하고 사용자가 답하는 대화형 구조
- "You stay in control — AI asks questions, you make the strategic decisions"
- PM들이 안심하고 쓸 수 있는 심리적 안전망
- 컨텍스트가 점진적으로 쌓이는 구조 (한 번에 모든 정보를 요구하지 않음)

### 1-3. 범용 PM 프레임워크 기반
- JTBD, Value Proposition Canvas, DACI, PESTEL 등 검증된 프레임워크
- PM이면 누구나 겪는 문제를 다룸 → 검색 유입 넓음
- 꾸준한 업데이트 (최근 1주 전, 179 commits)

---

## 2. 그런데 왜 709에서 성장이 정체되었는가?

### awesome-chatgpt-prompts (151K Stars)와의 비교

| 요소 | awesome-chatgpt-prompts (151K) | deanpeters (709) |
|------|------|------|
| 타겟 | **모든 AI 사용자** | PM만 |
| 진입장벽 | 복사→붙여넣기 즉시 작동 | PM 프레임워크 이해 필요 |
| 기여 모델 | 커뮤니티 제출 (prompts.chat) | 개인 + Claude |
| 첫 진입 | "Act as..." 한 줄로 시작 | 긴 구조화된 프롬프트 |
| 교차 활용 | 개발자, 마케터, 학생 모두 사용 | PM 전용 |
| 언어 | 영어 (글로벌) | 영어 (글로벌이지만 니치) |

### deanpeters 성장 한계 분석

1. **타겟이 좁음** — PM만 대상 → GitHub 사용자 중 PM 비율 극히 낮음
2. **진입장벽** — 프롬프트가 길고 PM 전문용어 필요 → 즉시 쓸 수 없음
3. **코드 없음** — Python 100%라고 표기되지만 실제로는 MD 파일 위주 → 개발자 유인력 부족
4. **단발성** — 프롬프트 간 연결 없음 → 워크플로우로 발전 안 됨
5. **결과물 없음** — 실행 예시 없음 → "이거 쓰면 어떻게 되는지" 불확실

### 핵심 인사이트

> **타겟이 넓을수록 Stars가 늘고, "즉시 쓸 수 있는" 진입점이 낮을수록 바이럴된다.**

---

## 3. GitHub 인기 레포의 공통 성공 요인

(ByteByteGo, ScrapGraphAI, DEV Community 리서치 종합)

| 성공 요인 | 설명 | 적용 방안 |
|-----------|------|-----------|
| 실제 문제 해결 | 복잡한 워크플로우를 단순화, 반복 작업 자동화 | 프롬프트가 즉시 결과를 내야 함 |
| README 품질 | "가장 중요한 파일" — 명확한 예시, 정직한 설명 | 3초 안에 "뭘 할 수 있는지" 이해 |
| 낮은 진입장벽 | 즉시 사용 가능해야 함 | Layer 1 (Quick Start) |
| 깊이와 확장성 | 사용성 + 확장성 + 배포 가능성 | Layer 2, 3 |
| 커뮤니티 | 기여 가이드, 피드백 루프 | CONTRIBUTIONS.md + Issue 템플릿 |
| 소셜 미디어 마케팅 | 트위터, 레딧, 뉴스레터 노출 | 한국 PM 커뮤니티 + 글로벌 AI 커뮤니티 |

---

## 4. v1 전략의 한계

### 기존 포지셔닝 문제

| v1 설계 | 문제점 |
|---------|--------|
| 타겟: "AI 제품 PM / CPO" | 너무 좁음 → GitHub Stars 성장 한계 |
| 언어: "한국어 Korean-first" | 한국어 블루오션은 맞지만 영어 병기 안 하면 글로벌 유입 차단 |
| 포지셔닝: "AI 제품을 만드는 PM이 AI를 쓰는 법" | PM만 끌림 |
| 형식: 긴 구조화된 프롬프트 하나 | 진입장벽 높음 |
| 카테고리: PM 업무 여정 기준 | PM이 아닌 사람은 폴더 이름만 봐도 이탈 |

### 개선 방향

1. **타겟 확장** — PM이 만들었지만 누구나 쓸 수 있는 "사고법" 프레임워크
2. **한국어 + 영어 병기** — 각 프롬프트에 한국어/영어 둘 다 포함
3. **레이어드 구조** — 즉시 쓸 수 있는 것 (Layer 1) → 깊은 것 (Layer 2) → 코드 (Layer 3)
4. **카테고리 재분류** — PM 업무 기준이 아닌 "사고 유형" 기준

---

## Sources

- [deanpeters/product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) — 709 Stars
- [f/awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) — 151K Stars
- [GitHub Stars Guide: Evaluating Open Source in 2026](https://blog.tooljet.com/github-stars-guide/)
- [Top AI GitHub Repositories in 2026](https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026)
- [10 Proven Ways to Boost Your GitHub Stars in 2026](https://scrapegraphai.com/blog/gh-stars)
- [DAIR-AI/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide)
- [NirDiamant/Prompt_Engineering](https://github.com/NirDiamant/Prompt_Engineering)
