# 🔀 유저 스토리 분할 (User Story Splitting with SPIDR)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 35분+ (Build)
> 워크플로우: ← `user-story.md` ← `user-story-mapping.md` → `user-story-ai-enhanced.md`

---

## 🎯 이 프롬프트가 해결하는 문제

큰 유저 스토리는 예측 불가능성(uncertainty)과 예정된 지연(deadline miss)을 야기합니다.
**SPIDR 기법**으로 큰 스토리를 작은, 완성 가능한 단위로 분할하여 팀의 속도와 예측 가능성을 높이세요.
이는 특히 2주 스프린트에서 "3일 안에 완료 가능한 작은 스토리"의 개수를 획기적으로 늘립니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `user-story.md`에서 생성된 스토리가 너무 클 때 분할에 사용합니다.

이전 프롬프트 결과에서 **분할 대상 스토리, 예상 크기, INVEST 위반 항목**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 큰 유저 스토리를 작은 단위로 분할할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
큰 스토리를 입력하세요:
"As a PM, I want to [큰 기능], So that [가치]"

SPIDR 6가지 기준으로 자동 분할:
- Spike: 기술 리서치
- Paths: 여러 경로 분리
- Interfaces: UI 계층 분리
- Data: 데이터 타입별 분리
- Rules: 비즈니스 규칙별 분리

결과: 3-5개의 작은 스토리 (각 1-3일)
```

💡 **Quick Tips:**
- "전체" 기능을 한 번에 만들려 하지 말고, "경로"를 먼저 선택하세요
- MVP 경로만 먼저 만들고, 엣지케이스는 나중에 추가하세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 분할하면 의미가 없어짐 | INVEST의 'V'(Valuable)를 유지하세요. 각 분할된 스토리가 독립적 가치를 가져야 합니다 |
| 기술적으로 분할 불가능 | "Spike + Implementation" 2단계로 나누세요. Spike(탐구) → 구현 |
| 분할 후 의존성이 생김 | 의존성이 있으면 순서를 정하되, 각각 독립 배포 가능하게 설계 |
| 분할 기준이 모호 | SPIDR 기법을 사용하세요: Spike, Path, Interface, Data, Rules |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 스토리 분할을 체계적으로 하고 싶은 분입니다.
"이 스토리가 너무 큰데 어떻게 나누지?"라는 고민이 있다면 이걸 써보세요.

### 📌 진행 방식

이 프롬프트는 **4단계 CoT(Chain of Thought)** 구조입니다. 두 가지 방식으로 쓸 수 있습니다:

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

엔지니어 리더, 스크럼 마스터, 프로덕트 매니저

### # 목표

**큰 스토리를 작고 완성 가능한 스토리로 분할**

- 각 스토리가 1~3일 내 완료 가능하도록
- 의존성을 최소화하면서 가치 순서대로 정렬
- MVP부터 엣지케이스까지 체계적으로 계층화
- 팀이 매주 "완료된 기능"을 빌드할 수 있게

<!-- 💬 왜 분할이 어려운가?
대부분의 PM들은 "완전한 기능"을 생각합니다:
- "사용자는 데이터를 업로드하고, 검증받고, 분석하고, 내보낸다"

하지만 엔지니어는 이것을 보면 "3주 작업"으로 봅니다.
이 갈등을 해결하는 게 SPIDR입니다. -->

### # Reasoning Strategy: SPIDR 기법

#### 1단계: Spike (기술 리서크)

큰 스토리를 쪼개기 전에, **기술적 불확실성**을 먼저 해결하세요.

```
원본 스토리:
"As a 분석가, I want to 대시보드에서 실시간 데이터를 본다,
 So that 최신 인사이트를 얻을 수 있다"

Spike (1-2일):
"우리 DB와 프론트엔드 간에 WebSocket을 구현할 수 있는가?
 레이턴시는 어느 정도인가? 기술 부채는 얼마나 되는가?"

↓ Spike 완료 후 ↓

결정: WebSocket vs Polling vs Scheduled Refresh
이 결정이 다음 스토리들의 구조를 결정합니다.
```

<!-- 💬 Spike 없이 분할하면 뭘 얻을까?
엔지니어가 중간에 "우리 기술로 안 됨"을 발견하고,
이미 구현한 코드를 다 뜯어내야 합니다.
Spike가 2일 투자면, 이 리워크는 2주 손실입니다. -->

#### 2단계: Paths (사용자 경로 분리)

실제 사용자가 기능을 사용하는 **여러 경로**가 있습니다. 모두를 한 번에 구현하지 마세요.

```
원본: "고객이 신용카드/계좌이체로 결제한다"

분할:
Path 1 (Happy Path): 신용카드, 정상 결제
  Story 1.1: 신용카드 폼 입력
  Story 1.2: 결제 게이트웨이 연동
  Story 1.3: 결제 성공 화면

Path 2 (Alternate Path): 계좌이체
  Story 2.1: 계좌이체 폼 입력
  Story 2.2: 은행 API 연동
  Story 2.3: 대기 중 상태 표시

Path 3 (Error Path): 결제 실패 처리
  Story 3.1: 실패 메시지 표시
  Story 3.2: 재시도 로직

✓ MVP: Path 1만 먼저 (고객 80%가 신용카드 사용)
✓ v1.1: Path 2 추가
✓ v1.2: Path 3 강화
```

<!-- 💬 Paths 분할의 핵심은 "80/20 법칙"입니다.
80%의 사용자가 사용하는 경로를 먼저 만듭니다.
나머지 20% 경로는 나중에 추가해도, 사용자는 이미 가치를 느낍니다. -->

#### 3단계: Interfaces (UI 계층별)

UI와 데이터 처리를 분리하면 병렬 작업이 가능합니다.

```
원본: "리포트 대시보드 만들기"

분할:
Interface 1: API 설계 & 백엔드 데이터 처리
  Story: "리포트 데이터를 반환하는 API 구현"

Interface 2: 프론트엔드 UI
  Story: "리포트 차트 컴포넌트 구현"

Interface 3: 통합
  Story: "API와 UI 통합, 성능 최적화"

장점: 백엔드 개발자와 프론트엔드 개발자가 동시에 작업
```

#### 4단계: Data (데이터 타입별)

여러 종류의 데이터를 다루면, **데이터 타입별로 분할**하세요.

```
원본: "고객 분석 대시보드 (매출, 고객 수, 전환율, LTV 등)"

분할:
Data Set 1: 매출 데이터
  Story: "월별 매출 차트"

Data Set 2: 고객 데이터
  Story: "신규 고객 수 추이"

Data Set 3: 전환율 데이터
  Story: "페이지별 전환 깔때기"

각 데이터 타입마다 다른 복잡성이 있을 수 있습니다.
```

#### 5단계: Rules (비즈니스 규칙별)

복잡한 비즈니스 규칙이 있을 때 분할합니다.

```
원본: "구독 자동 갱신 시스템"

분할:
Rule 1: 결제 처리
  Story: "카드 자동 청구"

Rule 2: 실패 처리
  Story: "결제 실패 시 알림 & 재시도"

Rule 3: 취소 처리
  Story: "구독 취소 시 환불 계산"

Rule 4: 규정 준수 (GDPR 등)
  Story: "구독 데이터 삭제 요청 처리"

✓ MVP: Rule 1, 2
✓ v1.1: Rule 3, 4
```

#### 6단계: Releases (릴리스 계획)

분할된 스토리들을 릴리스별로 그룹화합니다.

```
MVP (2주):
├─ Path 1 (Happy Path, 신용카드)
├─ Interface 1 (API)
└─ Interface 2 (UI)

v1.1 (2주):
├─ Path 2 (계좌이체)
├─ Rule 2 개선 (실패 처리)
└─ 성능 최적화

v1.2 (2주):
├─ Path 3 (실패 처리 강화)
├─ Rule 3, 4 (취소, GDPR)
└─ 관리자 기능
```

### # 검증 체크리스트

```
분할된 각 스토리는 다음을 만족해야 합니다:

✓ 1~3일 내 완료 가능한가?
✓ 독립적으로 테스트할 수 있는가?
✓ 독립적으로 배포할 수 있는가? (또는 feature flag로)
✓ 단일 엔지니어(또는 페어)가 소유할 수 있는가?
✓ 수용 기준이 명확한가?

하나라도 "아니오"면 더 분할하세요.
```



### # 🇰🇷 한국 시장 스토리 분할 고려사항

```
한국 시장 특수성:

1. **결제 시스템**: PG사 연동 스토리는 반드시 분할
   - 토스페이먼츠/카카오페이/네이버페이 → 각각 별도 스토리
   - 세금계산서 발행 → 독립 스토리 (복잡한 규정)

2. **인증 시스템**: 본인인증 관련 스토리 분할
   - 카카오 로그인 / 네이버 로그인 → 별도 스토리
   - 본인인증(PASS, 공동인증서) → 별도 스토리

3. **언어/로컬라이제이션**:
   - 한글 조사 처리 ("은/는", "이/가") → 별도 스토리
   - 존칭 레벨 ("합니다"/"해요"/"해") → UI 톤 스토리
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 크기 판단이 어려움 | "2일 이상 걸리면" 분할 대상입니다 |
| 2단계 | 분할 패턴 선택 어려움 | 가장 흔한 패턴: Happy Path / Edge Case 분리 |
| 3단계 | 분할 후 테스트 어려움 | 각 분할 스토리에 독립적 수용 기준을 부여하세요 |
| 4단계 | 분할 결과가 너무 작음 | "30분 이내 작업"이면 다른 스토리와 합치세요 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 스토리 크기 분석과 자동 분할 제안을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
대규모 백로그에서 "너무 큰 스토리"를 자동으로 감지하고 분할 방법을 제안하면 스프린트 계획이 빨라집니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Story Splitting Python 도구

```python
#!/usr/bin/env python3
"""
SPIDR 기반 User Story 자동 분할 도구
큰 스토리를 작은 스토리로 분할
"""

import anthropic
import json
from typing import Optional


def split_story_with_spidr(
    large_story: str,
    acceptance_criteria: list[str],
    context: Optional[str] = None,
    estimated_size: str = "Large"
) -> dict:
    """
    SPIDR 기법으로 큰 스토리를 분할

    Args:
        large_story: 원본 큰 스토리
        acceptance_criteria: 원본의 수용 기준
        context: 추가 컨텍스트
        estimated_size: "Large", "Extra Large"

    Returns:
        분할된 스토리들 (각 SPIDR 카테고리별)
    """

    client = anthropic.Anthropic()

    criteria_str = "\n".join(f"  - {c}" for c in acceptance_criteria)

    prompt = f"""당신은 경험 많은 Agile 코치입니다.
다음의 큰 스토리를 SPIDR 기법으로 분할하세요.

**원본 스토리:**
{large_story}

**현재 수용 기준:**
{criteria_str}

{f'**추가 컨텍스트:** {context}' if context else ''}

**SPIDR 분할 지침:**

1. **Spike**: 기술적 불확실성이 있는가? 리서크용 스토리 정의
2. **Paths**: 여러 사용 경로가 있는가? Path별로 분할
3. **Interfaces**: UI/API 분리 가능? 계층별로 분할
4. **Data**: 여러 데이터 타입? 데이터 타입별로 분할
5. **Rules**: 복잡한 비즈니스 규칙? 규칙별로 분할
6. **Releases**: MVP/v1.1/v1.2 등 릴리스별 그룹화

**JSON 응답 형식:**

{{
  "spike": {{
    "necessary": true/false,
    "stories": [
      {{
        "id": "SPIKE-1",
        "title": "기술 리서크: ...",
        "description": "목표: [불확실성 해결]",
        "estimated_days": 1-2
      }}
    ]
  }},
  "paths": {{
    "count": 3,
    "stories": [
      {{
        "path": "Happy Path (80%)",
        "id": "S1",
        "title": "...",
        "acceptance_criteria": ["조건1", "조건2"]
      }}
    ]
  }},
  "interfaces": {{
    "backend": [{{"id": "S-BE1", "title": "..."}}],
    "frontend": [{{"id": "S-FE1", "title": "..."}}]
  }},
  "data_splits": [...],
  "rule_splits": [...],
  "release_plan": {{
    "mvp": {{"stories": ["S1", "S2"], "duration": "2주"}},
    "v11": {{"stories": ["S3", "S4"], "duration": "2주"}}
  }},
  "validation": {{
    "each_story_1_3_days": true/false,
    "independent": true/false,
    "testable": true/false,
    "notes": "..."
  }}
}}

한글로 작성하세요.
"""

    message = client.messages.create(
        model="claude-opus-4-6",
        max_tokens=2500,
        messages=[{"role": "user", "content": prompt}]
    )

    try:
        import re
        json_match = re.search(r'\{.*\}', message.content[0].text, re.DOTALL)
        if json_match:
            result = json.loads(json_match.group())
        else:
            result = {"raw": message.content[0].text}
    except json.JSONDecodeError:
        result = {"raw": message.content[0].text}

    return {
        "original_story": large_story,
        "split_result": result,
        "tokens_used": message.usage.output_tokens
    }


def calculate_splitting_metrics(split_result: dict) -> dict:
    """
    분할 결과의 메트릭 계산
    """
    all_stories = []

    # 각 카테고리에서 스토리 수집
    if "spike" in split_result and split_result["spike"].get("stories"):
        all_stories.extend(split_result["spike"]["stories"])

    if "paths" in split_result and split_result["paths"].get("stories"):
        all_stories.extend(split_result["paths"]["stories"])

    if "interfaces" in split_result:
        for category in ["backend", "frontend"]:
            if category in split_result["interfaces"]:
                all_stories.extend(split_result["interfaces"][category])

    # 메트릭
    total_days = sum(s.get("estimated_days", 1) for s in all_stories)
    avg_days = total_days / len(all_stories) if all_stories else 0

    return {
        "total_stories": len(all_stories),
        "total_days_estimate": total_days,
        "avg_days_per_story": round(avg_days, 1),
        "parallelizable_stories": count_parallel_stories(split_result),
        "recommendation": "Good split" if avg_days <= 2 else "Need further splitting"
    }


def count_parallel_stories(split_result: dict) -> int:
    """병렬로 작업 가능한 스토리 수"""
    backend = len(split_result.get("interfaces", {}).get("backend", []))
    frontend = len(split_result.get("interfaces", {}).get("frontend", []))
    return backend + frontend if backend > 0 and frontend > 0 else 0


if __name__ == "__main__":
    # 예제: 큰 스토리 분할
    large_story = """As a 데이터 분석가,
I want to 대시보드에서 고객 분석 리포트를 생성하고 내보낸다,
So that 경영진과 팀에 공유할 수 있다."""

    acceptance_criteria = [
        "리포트에는 월별 매출, 신규 고객, 전환율이 포함된다",
        "PDF와 CSV 형식으로 내보낼 수 있다",
        "이메일로 자동 발송할 수 있다",
        "대시보드에서 조회 후 생성까지 30초 이내"
    ]

    result = split_story_with_spidr(
        large_story=large_story,
        acceptance_criteria=acceptance_criteria,
        context="팀 크기 4명, 2주 스프린트"
    )

    print(json.dumps(result, ensure_ascii=False, indent=2))

    # 메트릭 계산
    if "split_result" in result:
        metrics = calculate_splitting_metrics(result["split_result"])
        print("\n=== SPLITTING METRICS ===")
        print(json.dumps(metrics, ensure_ascii=False, indent=2))
```

### Claude Code CLI 사용법

```bash
# 큰 스토리 분할
claude run story-splitter.py \
  --story "As a PM, I want to..." \
  --acceptance-criteria "조건1" "조건2" "조건3" \
  --output split.json

# 배치 분할 (CSV 입력)
claude run batch-splitter.py \
  --input large_stories.csv \
  --output split_stories.csv

# 메트릭 분석
claude run splitter-metrics.py --input split.json
```

---

## 📊 실행 결과 예시

### Input: 원본 큰 스토리

```
As a 마케팅 담당자,
I want to 고객 세그먼트별 캠페인을 만들고 성과를 추적한다,
So that 타겟팅된 마케팅으로 ROI를 높일 수 있다.

수용 기준:
- 고객을 5가지 세그먼트로 분류할 수 있다
- 세그먼트별 캠페인을 독립적으로 구성할 수 있다
- 캠페인 성과 (오픈율, 클릭율, 전환율)를 실시간으로 본다
- 세그먼트와 성과 데이터를 CSV로 내보낼 수 있다
- 캠페인을 자동으로 보낼 수 있다 (이메일, SMS)
```

### Output: SPIDR 분할

```
=== SPIKE ===
(기술 리서크)

⚠️ SPIKE-1: "고객 세그먼트 정의 방식 리서크" (1-2일)
  목표: 우리 DB에서 어떻게 5가지 세그먼트를 구현할 것인가?
  옵션: 쿼리 기반 vs 룰 기반 vs ML 클러스터링
  결정: [리서크 후 결정]

=== PATHS ===
(사용자 경로)

✓ Path 1: Happy Path (70%)
  P1.1 (S1): "고객 세그먼트 자동 분류 (쿼리 기반)" [1-2일]
  P1.2 (S2): "세그먼트별 캠페인 구성 UI" [2-3일]
  P1.3 (S3): "이메일 캠페인 발송" [1-2일]

✓ Path 2: Alternative Path (20%)
  P2.1 (S4): "수동 세그먼트 생성 (커스텀 필터)" [1-2일]
  P2.2 (S5): "SMS 캠페인 발송" [2일]

✓ Path 3: Error Handling (10%)
  P3.1 (S6): "발송 실패 처리 & 재시도" [1-2일]

=== INTERFACES ===
(UI/API 분리)

Backend:
  S-BE1: "세그먼트 API 구현" [2-3일]
  S-BE2: "캠페인 스케줄링 엔진" [2-3일]
  S-BE3: "성과 추적 API" [1-2일]

Frontend:
  S-FE1: "세그먼트 관리 UI" [2-3일]
  S-FE2: "캠페인 구성 마법사" [2-3일]
  S-FE3: "성과 대시보드" [2-3일]

Integration:
  S-INT1: "API-UI 통합 & 성능 최적화" [1-2일]

=== DATA TYPES ===
(데이터별 분할)

Data 1: 고객 세그먼트 데이터
  S7: "세그먼트 테이블 스키마 및 저장소" [1일]

Data 2: 캠페인 설정 데이터
  S8: "캠페인 설정 저장 및 조회" [1일]

Data 3: 성과 메트릭 데이터
  S9: "성과 이벤트 로깅 및 집계" [1-2일]

=== BUSINESS RULES ===
(규칙별 분할)

Rule 1: 세그먼트 자동 분류
  S10: "룰 기반 분류 엔진" [1-2일]

Rule 2: 캠페인 일정 관리
  S11: "스케줄링 로직 (시간, 주기, 조건)" [1-2일]

Rule 3: 규정 준수 (개인정보보호법)
  S12: "캠페인 동의 관리" [1-2일]

Rule 4: 성과 계산
  S13: "오픈율, 클릭율, 전환율 계산" [1일]

=== RELEASE PLAN ===

📦 MVP (첫 2주)
  ✓ S1: 세그먼트 자동 분류
  ✓ S2: 캠페인 구성 UI
  ✓ S3: 이메일 캠페인 발송
  ✓ S9: 기본 성과 추적
  ──────────────────────
  총 5개 스토리, 약 8-10일 작업

📦 v1.1 (다음 2주)
  ✓ S4: 수동 세그먼트
  ✓ S5: SMS 캠페인
  ✓ S13: 성과 계산 고도화
  ✓ S-FE3: 성과 대시보드
  ──────────────────────
  총 4개 스토리, 약 8-9일 작업

📦 v1.2+ (향후)
  ✓ S6: 실패 처리
  ✓ S12: GDPR 준수
  ✓ 자동 리포팅

=== VALIDATION ===

✓ 각 스토리 1~3일 범위? YES (모두 1-3일)
✓ 독립적 테스트? YES (각 스토리마다 TC 작성 가능)
✓ 병렬화 가능? YES (BE 3개 + FE 3개 동시 작업)
✓ 독립 배포 가능? YES (feature flag로 점진적 배포)

추천: 완벽한 분할 ✓
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 분할된 스토리 각각이 '독립적으로 배포 가능한지' 확인하세요 — 의존성이 있으면 분할이 아닙니다
2. **[논쟁 지점]** SPIDR 중 어떤 패턴(Spike/Path/Interface/Data/Rules)으로 분할할지는 스토리 성격에 따라 다릅니다
3. **[자기 검증]** 분할된 스토리 1개를 개발자에게 보여주고 '이것만으로 작업할 수 있나?'를 확인하세요

---

## 🔗 다음 단계

1. **`user-story-ai-enhanced.md`** → AI 기능 추가 시 수용 기준 확장
2. **스프린트 백로그** → 분할된 스토리를 Jira/Linear에 입력
3. **성능 예측** → 팀의 속도(velocity) 기반 스프린트 계획
4. **지속적 분할** → 각 스프린트마다 "너무 큼" 스토리 조기 발견
