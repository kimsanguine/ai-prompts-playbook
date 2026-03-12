# 🗺️ 유저 스토리 맵핑 (User Story Mapping)

> 예상 소요: 5분 (Quick) / 20분 (Deep) / 40분+ (Build)
> 워크플로우: ← `user-story.md` → `user-story-splitting.md`

---

## 🎯 이 프롬프트가 해결하는 problem

개별 유저 스토리들이 **전체 사용자 여정**에서 어디에 위치하는지 파악하지 못하면, 제품 개발 로드맵이 산발적이고 비효율적입니다.
**Jeff Patton의 Story Mapping** 기법으로 사용자 여정을 시각화하고, 우선순위를 명확히 합니다.
이는 프로덕트 빌드의 순서(Sequencing)를 근본적으로 개선합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `user-story.md`에서 생성된 스토리들을 전체 제품 맥락에서 배치할 때 연결됩니다.

이전 프롬프트 결과에서 **유저 스토리 목록, 페르소나, 핵심 워크플로우**를 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 유저 스토리를 여정 기반으로 맵핑할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
다음을 입력하세요:
1. 사용자 여정 단계 (예: 가입 → 설정 → 사용 → 분석)
2. 각 단계별 해야 할 일 (User Stories)

자동으로 맵을 생성하고,
**Backbone** (필수 기능) | **Walking Skeleton** (MVP) | **Nice-to-have** (향후)로 구분합니다.
```

💡 **Quick Tips:**
- 맵은 "시간 흐름"을 가로축으로, "가치"를 세로축으로 표현합니다
- MVP는 backbone + 1층 정도면 충분합니다
- 그룹화하지 말고 "이 기능이 필수인가?"부터 물어보세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 스토리가 너무 적음 (10개 미만) | 맵핑 없이 직접 우선순위를 매겨도 됩니다 |
| 여정이 복잡함 | 핵심 여정(Happy Path)만 먼저 맵핑하세요 |
| 여러 제품/기능에 걸침 | 제품/기능별로 별도 맵을 만드세요 |
| 팀이 스토리 맵을 처음 접함 | 워크숍 형태로 함께 만들면 학습 효과가 큽니다 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 유저 스토리를 사용자 여정에 맞춰 체계적으로 배치하고 싶은 분입니다.
"전체 그림"을 보면서 우선순위를 정하고 싶다면 이걸 써보세요.

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

프로덕트 매니저, 제품 경영진, 사용자 리서처

### # 목표

**User Story Map을 통해 제품 개발 순서를 최적화**

- 사용자 여정의 "뼈대(backbone)"를 파악
- MVP(Minimum Viable Product) 범위를 명확히
- 각 릴리스 단계별 기능 세트 결정
- 팀 전체가 같은 "맵"을 본다

<!-- 💬 Story Mapping이 왜 중요한가?
대부분의 팀은 백로그를 보고 "이 스토리 다음에 이 스토리" 식으로 진행합니다.
하지만 사용자 입장에서는:
1. 로그인 (스토리 A)
2. 프로필 설정 (스토리 B)
3. 데이터 업로드 (스토리 C)
4. 결과 확인 (스토리 D)

만약 순서가 D → B → C → A라면? 사용자는 막힙니다.
Story Map은 "사용자 관점"에서의 올바른 순서를 보여줍니다. -->

### # Reasoning Strategy

#### 1단계: 사용자 활동(User Activities) 정의

**Backbone 만들기**: 사용자가 제품을 사용하는 동안의 주요 활동들

```
예: "고객 데이터 분석 플랫폼"

시간 흐름 (좌→우):
[데이터 연동] → [정제] → [분석] → [리포트] → [공유]
```

<!-- 💬 Backbone은 "사용자 여정의 뼈대"입니다.
이것을 정하기 전에 묻지 말아야 할 질문:
- "우리 기술은 뭘 할 수 있는가?" (기술 중심)
- "경쟁사는 뭘 가졌는가?" (경쟁사 중심)

물어야 할 질문:
- "사용자는 이 제품으로 뭘 하려고 하는가?" (사용자 중심)
- "그렇게 하려면 순서가 어떻게 되어야 하는가?" (논리적 순서)
-->

#### 2단계: 각 활동별 User Stories 배치

**세로축 = 가치 우선순위** (위쪽 = 높음)

```
              데이터 연동         정제              분석
              (Backbone)      (Backbone)      (Backbone)

Tier 1    [CSV 업로드]     [중복 제거]      [기본 통계]
(MVP)     [API 연동]       [형식 변환]      [그래프 시각화]

Tier 2    [DB 직접 연결]   [아웃라이어]     [고급 필터링]
(v1.1)    [대용량 처리]     [데이터 검증]    [예측 분석]

Tier 3    [실시간 스트림]   [데이터 품질]    [AI 인사이트]
(v1.2)    [캐싱]           [거버넌스]      [자동 리포팅]
```

<!-- 💬 계층 구조가 왜 중요한가?
- Tier 1 = MVP에 포함 (보통 4-6주)
- Tier 2 = v1.1 (다음 4-6주)
- Tier 3 = 나중 (기술 부채 정산 후)

이렇게 하면:
1. 사용자는 4주 후 "작동하는" 제품을 얻습니다
2. 팀은 "뭘 빼고 뭘 넣을지" 명확히 알 수 있습니다
3. 트레이드오프 논의가 구체적입니다 (기술 vs 기능이 아니라 "Tier 1 vs Tier 2" 논의)
-->

#### 3단계: MVP 정의

**Rule of Thumb**: Backbone + Tier 1, 모든 활동에 걸쳐

```
✓ 포함:
  - 각 주요 활동 단계별로 최소 1-2개 필수 스토리
  - 엔드-투-엔드 사용자 여정이 작동하는 수준

✗ 제외:
  - Tier 2, 3 항목들
  - "폴리싱" (UI 애니메이션, 이메일 템플릿 등)
  - 관리자 기능
  - 보고서 내보내기 등의 부가 기능
```

#### 4단계: 릴리스 계획

```
Release 1 (4-6주): MVP
├─ 데이터 연동 (CSV + API)
├─ 기본 정제
├─ 통계 + 그래프
└─ 기본 공유

Release 2 (4-6주): Tier 2
├─ DB 직접 연결
├─ 고급 필터링
├─ 예측 분석
└─ 대용량 최적화

Release 3 (8주+): Tier 3
├─ 실시간 스트림
├─ AI 인사이트
└─ 자동 리포팅
```

### # 한국 SaaS 특화

```
일반 Mapping 구조:
활동 (Activities) → 스토리 (Stories) → 스프린트 (Sprints)

한국 시장 특화:
1. 규정 준수 (GDPR, ISMS, 개인정보보호법)
   → 보통 Tier 2 또는 함께 진행
2. 다국어 (한글, 영어)
   → MVP에 포함시키는 게 효율적
3. 결제/정산 (Billing)
   → 통상 별도 스토리 라인, Backbone 아님
```

### # 데이터 수집

- **사용자 인터뷰**: 5-10명 사용자 대상 주요 활동 확인
- **경쟁사 분석**: 유사 제품의 사용 순서
- **내부 팀 인터뷰**: 엔지니어, 디자이너의 의존성 파악


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | Activity 정의가 어려움 | 사용자의 "큰 목표"를 3-5개로 정의하세요 |
| 2단계 | Task 세분화가 안 됨 | 각 Activity를 "단계별 행동"으로 나누세요 |
| 3단계 | 릴리즈 경계 설정 어려움 | "MVP에 반드시 필요한 것"만 Release 1에 넣으세요 |
| 4단계 | 우선순위 합의 어려움 | "이것 없이 제품을 출시할 수 있는가?" 기준으로 판단 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 스토리 맵 생성과 릴리즈 계획을 자동화합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
스토리 맵은 릴리즈마다 업데이트됩니다. 자동화하면 백로그 변경 시 맵이 자동으로 갱신됩니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Story Mapping 자동 생성 Python

```python
#!/usr/bin/env python3
"""
User Story Map 자동 생성 도구
Claude API로부터 활동, 스토리, 계층을 생성하고 시각화
"""

import anthropic
import json
import csv
from typing import Optional
from dataclasses import dataclass


@dataclass
class StoryMapLayer:
    """맵 계층"""
    name: str  # "MVP", "v1.1", "v1.2"
    stories: list[dict]  # {activity, title, description}


def generate_story_map(
    product_name: str,
    main_user_journey: str,
    target_users: str,
    constraints: Optional[str] = None
) -> dict:
    """
    사용자 여정에서 Story Map 자동 생성

    Args:
        product_name: 제품명 (예: "고객 분석 대시보드")
        main_user_journey: 주요 사용자 여정 (예: "데이터 로드 → 분석 → 공유")
        target_users: 타겟 사용자 (예: "마케팅 매니저, 데이터 애널리스트")
        constraints: 제약사항 (예: "6주 내 MVP 완성")

    Returns:
        Backbone, Tier 1 (MVP), Tier 2, Tier 3 포함 맵
    """

    client = anthropic.Anthropic()

    prompt = f"""당신은 경험 많은 제품 관리자입니다.
다음 정보로 Jeff Patton 스타일의 User Story Map을 생성하세요.

**제품:** {product_name}
**사용자 여정:** {main_user_journey}
**타겟 사용자:** {target_users}
{f'**제약:** {constraints}' if constraints else ''}

**산출물 형식 (JSON):**

{{
  "backbone": [
    {{"order": 1, "activity": "활동명", "description": "설명"}}
  ],
  "tier_1_mvp": [
    {{
      "activity": "활동명",
      "stories": [
        {{"id": "S1", "title": "스토리명", "acceptance_criteria": ["조건1", "조건2"]}}
      ]
    }}
  ],
  "tier_2_v11": [...],
  "tier_3_future": [...],
  "release_plan": {{
    "mvp": {{"duration": "4-6주", "included": ["활동1", "활동2"]}},
    "v11": {{"duration": "4-6주", "included": [...]}},
    "v12": {{"duration": "8주+", "included": [...]}}
  }},
  "validation": {{
    "is_complete_journey": true/false,
    "mvp_readiness": "설명",
    "risks": ["위험1", "위험2"]
  }}
}}

한글로 작성하고, 각 스토리는 구체적인 수용 기준을 포함하세요.
"""

    message = client.messages.create(
        model="claude-opus-4-6",
        max_tokens=3000,
        messages=[{"role": "user", "content": prompt}]
    )

    try:
        # JSON 응답 파싱
        import re
        json_match = re.search(r'\{.*\}', message.content[0].text, re.DOTALL)
        if json_match:
            story_map = json.loads(json_match.group())
        else:
            story_map = {"raw": message.content[0].text}
    except json.JSONDecodeError:
        story_map = {"raw": message.content[0].text}

    return {
        "product": product_name,
        "generated_map": story_map,
        "tokens_used": message.usage.output_tokens
    }


def visualize_map_ascii(story_map: dict) -> str:
    """
    ASCII 형식으로 Story Map 시각화
    """
    output = []
    output.append("\n" + "="*80)
    output.append("USER STORY MAP")
    output.append("="*80 + "\n")

    backbone = story_map.get("backbone", [])
    tier1 = story_map.get("tier_1_mvp", [])

    # 헤더: Backbone Activities
    header = "   | "
    for item in backbone:
        header += f"{item.get('activity', 'Activity'):^20} | "
    output.append(header)
    output.append("-" * len(header))

    # Tier 1 (MVP)
    output.append("\n[MVP - Tier 1]")
    for tier_item in tier1:
        activity = tier_item.get("activity", "")
        stories = tier_item.get("stories", [])
        output.append(f"  {activity}:")
        for story in stories:
            output.append(f"    - {story.get('title', '')} ({story.get('id', '')})")

    # Tier 2
    tier2 = story_map.get("tier_2_v11", [])
    if tier2:
        output.append("\n[v1.1 - Tier 2]")
        for tier_item in tier2:
            activity = tier_item.get("activity", "")
            stories = tier_item.get("stories", [])
            output.append(f"  {activity}:")
            for story in stories:
                output.append(f"    - {story.get('title', '')} ({story.get('id', '')})")

    return "\n".join(output)


def export_to_csv(story_map: dict, filename: str) -> str:
    """
    Story Map을 CSV로 내보내기 (스프린트 계획용)
    """
    rows = []
    rows.append(["Activity", "Tier", "Story ID", "Title", "Acceptance Criteria"])

    def add_stories(tier_name, tier_data):
        for item in tier_data:
            activity = item.get("activity", "")
            for story in item.get("stories", []):
                criteria = "; ".join(story.get("acceptance_criteria", []))
                rows.append([
                    activity,
                    tier_name,
                    story.get("id", ""),
                    story.get("title", ""),
                    criteria
                ])

    add_stories("MVP", story_map.get("tier_1_mvp", []))
    add_stories("v1.1", story_map.get("tier_2_v11", []))
    add_stories("v1.2+", story_map.get("tier_3_future", []))

    with open(filename, "w", newline="", encoding="utf-8") as f:
        writer = csv.writer(f)
        writer.writerows(rows)

    return f"Exported to {filename}"


if __name__ == "__main__":
    # 예제
    result = generate_story_map(
        product_name="고객 데이터 플랫폼",
        main_user_journey="데이터 연동 → 정제 → 분석 → 공유",
        target_users="데이터 분석팀, 마케팅 매니저, 영업팀",
        constraints="6주 내 MVP, 팀 크기 5명"
    )

    print(json.dumps(result, ensure_ascii=False, indent=2))

    # ASCII 시각화
    if "generated_map" in result:
        print(visualize_map_ascii(result["generated_map"]))

        # CSV 내보내기
        export_to_csv(result["generated_map"], "story_map.csv")
```

### Claude Code CLI 사용법

```bash
# Story Map 생성
claude run story-mapper.py \
  --product "고객 성공 플랫폼" \
  --journey "온보딩 → 사용 → 성장 → 갱신" \
  --users "고객 성공 담당자, 고객" \
  --output map.json

# CSV 내보내기 (스프린트 계획용)
claude run export-map.py --input map.json --format csv --output sprint_plan.csv

# 릴리스 계획 생성
claude run release-planner.py --map map.json --weeks 12
```

---

## 📊 실행 결과 예시

### Input

```
제품: B2B SaaS 팀 협업 플랫폼
사용자: PM, 디자이너, 엔지니어
여정: 팀 초대 → 프로젝트 생성 → 작업 배정 → 진행 상황 추적 → 보고
```

### Output

```
USER STORY MAP
=============================================================

Backbone Activities:
[팀 관리] → [프로젝트 설정] → [작업 관리] → [협업] → [보고]

┌─────────────────────────────────────────────────────────┐
│ MVP (Release 1, 4-6주)                                  │
├─────────────────────────────────────────────────────────┤
│
│ [팀 관리]
│   ✓ S1: 팀원 이메일로 초대
│   ✓ S2: 역할 할당 (Admin, Member)
│
│ [프로젝트 설정]
│   ✓ S3: 프로젝트 생성 (이름, 설명)
│   ✓ S4: 팀원 추가
│
│ [작업 관리]
│   ✓ S5: 작업 생성 (제목, 설명, 담당자)
│   ✓ S6: 상태 변경 (To-do → In Progress → Done)
│
│ [협업]
│   ✓ S7: 댓글 작성
│   ✓ S8: 파일 첨부
│
│ [보고]
│   ✓ S9: 진행 상황 대시보드 (완료율)
│
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ v1.1 (Release 2, 4-6주)                                 │
├─────────────────────────────────────────────────────────┤
│
│ [팀 관리]
│   - S10: 팀 권한 세분화 (Viewer, Editor, Admin)
│   - S11: 팀 삭제
│
│ [프로젝트 설정]
│   - S12: 프로젝트 템플릿
│   - S13: 커스텀 필드
│
│ [작업 관리]
│   - S14: 우선순위 설정
│   - S15: 마감일
│   - S16: 반복 작업
│
│ [협업]
│   - S17: @멘션 알림
│   - S18: 활동 로그
│
│ [보고]
│   - S19: CSV 내보내기
│   - S20: 팀별 성과 리포트
│
└─────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────┐
│ v1.2 (Release 3, 8주+)                                  │
├─────────────────────────────────────────────────────────┤
│
│ [협업]
│   - S21: 실시간 협업 (Figma 스타일)
│   - S22: AI 검토 의견
│
│ [보고]
│   - S23: 자동 일일 보고서
│   - S24: Slack 통합
│   - S25: Jira 연동
│
└─────────────────────────────────────────────────────────┘

Release Plan
============

Release 1 (MVP): 4-6주
- 9개 스토리 (S1-S9)
- 팀 전체가 협업할 수 있는 최소 제품

Release 2 (v1.1): 4-6주
- 11개 스토리 (S10-S20)
- 고급 기능, 성과 관리

Release 3 (v1.2): 8주+
- 5개 스토리 (S21-S25)
- AI, 자동화, 통합
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 스토리 맵의 '백본(backbone)'이 사용자의 실제 여정을 반영하는지 확인하세요
2. **[논쟁 지점]** 릴리즈 슬라이스를 'MVP'로 할지 'MLP(Minimum Lovable Product)'로 할지는 시장 상황에 따라 다릅니다
3. **[자기 검증]** 첫 번째 릴리즈 슬라이스만으로 핵심 사용자 여정이 완성되는지 시뮬레이션하세요

---

## 🔗 다음 단계

1. **`user-story-splitting.md`** → 큰 스토리를 작은 단위로 분할
2. **`user-story-ai-enhanced.md`** → AI 특화 수용 기준 추가
3. **스프린트 백로그** → CSV에서 Jira/Linear로 import
4. **릴리스 계획** → Backbone 기반 로드맵 작성
