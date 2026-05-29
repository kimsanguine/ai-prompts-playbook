# 🥊 경쟁사 배틀카드 (Competitor Battlecard)

> 예상 소요: 10분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: ← `competitor-sentiment.md` → `positioning-strategy.md` → `executive-briefing.md`
> Source: [`kimsanguine/AI_PM`](https://github.com/kimsanguine/AI_PM) `templates/commands/competitor.md`, `skills/competitor-battlecard/SKILL.md`

---

## 🧩 Prompt Card

| 항목 | 내용 |
|------|------|
| ID | `competitor-battlecard` |
| Job | 경쟁사 3-5곳을 동일 축으로 비교하고 영업/전략 배틀카드로 정리 |
| Best for | PM, CPO, sales, strategy |
| Required inputs | 경쟁사 목록, 우리 제품 설명, 공개 자료 또는 비교 데이터 |
| Optional inputs | 가격, 기능표, 리뷰, 세일즈 objection, 타깃 세그먼트 |
| Output | 비교 표, 경쟁사별 배틀카드, 우리 differentiator, 한계 |
| Next prompts | `positioning-strategy` → `executive-briefing` |
| Evaluation | [`evals/scenarios/core.yaml`](../../evals/scenarios/core.yaml)의 `ai-pm-competitor-battlecard` |

## ✅ Output Contract

AI의 답변은 반드시 다음을 포함해야 합니다:

1. **비교 축 표**: Target, Core feature, Price, Strength, Weakness 등 5-8개 축
2. **경쟁사별 배틀카드**: 강점, 약점, 우리의 differentiator
3. **그들의 공격 → 우리의 응답**: 실제 세일즈 현장에서 나올 만한 문장
4. **근거와 freshness**: 오래된 자료는 `[stale]`로 표시
5. **한계**: 자료 누락, 추측 금지, 추가 조사 필요 항목

## 🎯 이 프롬프트가 해결하는 문제

경쟁사 분석은 자주 기능표 나열로 끝납니다. 하지만 PM에게 필요한 것은 “누가 더 기능이 많은가”가 아니라 **어떤 고객 상황에서 우리가 이길 수 있는가**입니다.

이 프롬프트는 경쟁사를 같은 축으로 비교한 뒤, 포지셔닝과 세일즈 대화에 바로 쓸 수 있는 배틀카드로 바꿉니다.

---

## ⚡ Layer 1: Quick Start

```
당신은 B2B SaaS 경쟁전략 PM입니다.

아래 경쟁사 3-5곳을 동일한 축으로 비교하고, 각 경쟁사별 배틀카드를 작성하세요.

# 입력
- 우리 제품: {우리 제품 설명}
- 타깃 고객: {타깃 세그먼트}
- 경쟁사: {경쟁사 A, B, C}
- 근거 자료: {가격표, 기능표, 리뷰, 기사, 내부 비교 메모}

# 출력
1. 비교 축 표
2. 경쟁사별 배틀카드
   - 그들의 강점
   - 그들의 약점
   - 우리의 differentiator
   - 그들이 우리에게 할 공격 → 우리의 응답
3. 포지셔닝에 넘길 핵심 메시지 3개
4. 한계와 추가 조사 필요 항목

규칙:
- 근거 없는 추측은 쓰지 마세요.
- 자료가 없는 셀은 "확인 필요"로 표시하세요.
- 6개월보다 오래된 자료는 [stale]로 표시하세요.
```

## 🧠 Layer 2: Deep Dive

### 역할

당신은 PM, sales enablement lead, product marketing manager의 관점을 함께 가진 경쟁전략 파트너입니다.

### Reasoning Strategy

1. **비교 축 정의**
   - 제품 카테고리에 맞는 5-8개 축을 먼저 정합니다.
   - 가격, 타깃, 핵심 기능, 온보딩, 통합, 보안, 지원, 약점 등을 후보로 봅니다.

2. **근거 등급 표시**
   - 공개 자료, 리뷰, 내부 세일즈 노트, 추정치를 구분합니다.
   - 추정치는 결론에 쓰지 않고 한계 절로 보냅니다.

3. **상황별 승부처 찾기**
   - 모든 고객에게 이기는 메시지가 아니라, 특정 세그먼트에서 이기는 메시지를 찾습니다.

4. **공격과 응답 작성**
   - 경쟁사가 실제로 할 법한 공격 문장으로 씁니다.
   - 응답은 우리 장점만 말하지 않고 고객 리스크를 줄이는 방식으로 씁니다.

5. **포지셔닝 연결**
   - 다음 프롬프트인 `positioning-strategy`에 넘길 핵심 차별화 문장 3개를 뽑습니다.

## 🔧 Layer 3: Build & Automate

Claude Code에서는 `AI_PM`의 `/competitor` command처럼 비교 데이터 파일을 첨부해 실행할 수 있습니다.

```bash
/competitor @samples/competitor-data.json
```

구조화 저장 예:

```yaml
competitor:
  name: ""
  strengths: []
  weaknesses: []
  differentiator: ""
  likely_attack: ""
  response: ""
  evidence_freshness: current|stale|unknown
```

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|---------------|------|
| differentiator | `positioning-strategy.md` | 포지셔닝 문장으로 정제 |
| 공격/응답 | `stakeholder-alignment.md` | 세일즈/경영진 메시지로 변환 |
| 비교 근거 | `executive-briefing.md` | 의사결정 브리핑으로 요약 |

