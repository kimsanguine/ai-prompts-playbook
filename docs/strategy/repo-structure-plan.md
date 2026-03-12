# ai-pm-prompts 레포 구조안

> 작성일: 2026-03-11
> 목적: GitHub 레포 생성 시 사용할 전체 구조 설계

---

## 1. 레포 기본 정보

| 항목 | 값 |
|------|-----|
| 레포명 | `ai-pm-prompts` |
| Description | AI Native PM을 위한 프롬프트 컬렉션 — 한국어, 워크플로우 체인, 실행 결과 포함 |
| License | MIT |
| Topics | `ai-prompts`, `product-management`, `korean`, `ai-native`, `prompt-engineering`, `ai-pm`, `chatgpt`, `claude` |
| Language | Markdown (MD only) |

---

## 2. 디렉토리 구조

```
ai-pm-prompts/
├── README.md                   # 레포 메인 (포지셔닝, Quick Start, 카테고리 맵)
├── LICENSE                     # MIT
├── CONTRIBUTING.md             # 기여 가이드
├── prompts/
│   ├── 01-discovery/           # 문제 발견 & 기회 탐색
│   │   ├── competitor-sentiment-analysis.md
│   │   ├── user-problem-hypothesis.md
│   │   └── market-sizing-with-ai.md
│   ├── 02-strategy/            # 전략 수립 & 우선순위
│   │   ├── feature-prioritization-rice.md
│   │   ├── ai-product-positioning.md
│   │   └── build-vs-buy-ai-capability.md
│   ├── 03-execution/           # 스펙 & 실행
│   │   ├── prd-for-ai-feature.md
│   │   ├── ai-model-evaluation-criteria.md
│   │   └── prompt-engineering-for-pm.md
│   ├── 04-growth/              # 그로스 & 메트릭
│   │   ├── ai-feature-adoption-metrics.md
│   │   ├── ab-test-design-ai-product.md
│   │   └── retention-analysis-prompt.md
│   ├── 05-leadership/          # 리더십 & 커뮤니케이션
│   │   ├── executive-briefing-ai-strategy.md
│   │   ├── cross-functional-alignment.md
│   │   └── ai-ethics-review-checklist.md
│   └── templates/
│       └── prompt-template.md  # 새 프롬프트 작성 시 참고 템플릿
├── docs/
│   ├── design-principles.md    # 프롬프트 설계 5원칙
│   ├── workflow-map.md         # 프롬프트 간 연결 다이어그램
│   └── korean-saas-context.md  # 한국 SaaS 컨텍스트 가이드
└── .github/
    └── ISSUE_TEMPLATE/
        └── new-prompt-request.md
```

---

## 3. README.md 구조안

```markdown
# 🎯 AI PM Prompts — AI Native PM을 위한 프롬프트 컬렉션

> AI 제품을 만드는 PM이 AI를 쓰는 법

[배지: Stars, License, Prompts 수, 한국어]

## 왜 이 레포인가?

[deanpeters와의 차별점 3줄 요약]

## Quick Start

1. 카테고리에서 프롬프트를 찾는다
2. 프롬프트를 복사해서 Claude/ChatGPT에 붙여넣는다
3. 🔗 다음 단계를 따라 워크플로우를 이어간다

## 📂 카테고리

[Mermaid 플로우차트: Discovery → Strategy → Execution → Growth → Leadership]

| 카테고리 | 프롬프트 | 설명 |
|---------|---------|------|
| 01-discovery | 3개 | 문제 발견 & 기회 탐색 |
| 02-strategy | 3개 | 전략 수립 & 우선순위 |
| ... | ... | ... |

## 🔗 워크플로우 체인

[프롬프트 간 연결을 보여주는 다이어그램]

## ✨ 이 레포가 다른 점

| | 기존 PM 프롬프트 | 이 레포 |
|---|---|---|
| ... | ... | ... |

## 🤝 기여하기

## 📚 관련 레포
- AI_PM: AI PM 실전 가이드
- AI_PM_Skills: Agent PM Skills
- AI_Engineer: 100 Agents

## License: MIT
```

---

## 4. 초기 출시 계획

### Phase 1: MVP (첫 커밋)
- README.md (포지셔닝, Quick Start, 카테고리 맵)
- 3-5개 프롬프트 (01-discovery 2개, 02-strategy 1개, 03-execution 1개)
- prompt-template.md
- LICENSE, CONTRIBUTING.md

### Phase 2: 콘텐츠 확장
- 카테고리별 3개씩 → 총 15개
- docs/design-principles.md
- docs/workflow-map.md (Mermaid)

### Phase 3: 커뮤니티 성장
- GitHub Pages로 프롬프트 브라우저
- 커뮤니티 기여 프롬프트
- AI_PM_Skills와 연동 (프롬프트 → Skill 자동 변환)

---

## 5. 3각 구도 시너지 맵

```
ai-pm-prompts ←→ AI_PM_Skills ←→ AI_Engineer/100 Agents
  (사고법)         (자동화)          (실행)

"이렇게 생각하세요" → "자동화됩니다" → "Agent가 수행합니다"

크로스 링크:
- ai-pm-prompts README → AI_PM_Skills "이 프롬프트가 Skills로 실행됩니다"
- AI_PM_Skills README → ai-pm-prompts "이 Skill의 사고 과정은 여기에"
- AI_Engineer README → ai-pm-prompts "PM 관점의 Agent 설계는 여기에"
```
