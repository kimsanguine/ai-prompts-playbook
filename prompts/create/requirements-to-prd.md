# 📐 요구사항→PRD 역공학 (ISO 29148 Requirements to PRD)

> 예상 소요: 10분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: ← `spec-to-prd.md` → `prd-for-ai-feature.md`

---

## 🎯 이 프롬프트가 해결하는 문제

ISO 29148 요구사항 표준은 체계적이지만 **매우 형식적**입니다. 요구사항들이 서로 어떻게 연결되고, 사용자 가치에 어떻게 기여하는지 보기 어렵습니다.
**역공학** 기법으로 분산된 ISO 요구사항들을 **통합된 PRD**로 변환하여 제품의 전체 그림을 명확히 하세요.
특히 대규모 엔터프라이즈 프로젝트에서 여러 부서의 요구사항을 하나의 제품 비전으로 통합할 때 효과적입니다.

---

## 📥 이전 프롬프트에서 받는 입력

> 흩어진 요구사항(이메일, 회의록, 슬랙 등)을 구조화된 PRD로 정리할 때 사용합니다.

**요구사항 원문 (이메일, 회의록, 슬랙 메시지 등)**을 직접 붙여넣으세요.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 비구조화된 요구사항을 PRD로 정리할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
ISO 29148 요구사항 문서를 업로드하세요.

자동으로:
1. 모든 요구사항을 카테고리별로 분류
2. 요구사항 간 의존성 맵핑
3. 각 요구사항을 "왜 필요한가?"로 변환
4. PRD 형식으로 통합

결과: 경영진이 이해하는 통합 제품 비전
```

💡 **Quick Tips:**
- ISO 요구사항을 "기술" vs "비즈니스" vs "운영"으로 먼저 분류하세요
- 같은 사용자 문제를 해결하는 요구사항들을 그룹화하세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 요구사항이 상충됨 | 이해관계자별로 분류하고, 충돌 항목은 decision-canvas.md로 해결 |
| 요구사항이 너무 모호 | "구체적 예시"를 요청하세요. "빠르게" → "3초 이내 응답" |
| 비기능 요구사항 누락 | 성능, 보안, 접근성, 확장성 체크리스트를 추가하세요 |
| 소스가 너무 다양 | 모든 소스를 한 곳에 모으고, 중복 제거 후 카테고리화 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 흩어진 요구사항을 체계적인 PRD로 변환하고 싶은 분입니다.
회의록, 이메일, 슬랙 대화에서 요구사항을 추출하고 싶다면 이걸 써보세요.

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

PM, 요구사항 관리자(Requirements Manager), 제품 전략가

### # 목표

**ISO 29148 분산된 요구사항 → 통합 PRD 변환**

- 300~500개의 세분화된 요구사항을 의미 있는 단위로 그룹화
- 요구사항들의 추적성(Traceability) 유지하며 통합
- 상충하는 요구사항들의 우선순위 명확화
- 스테이크홀더별 기대치 대조

<!-- 💬 왜 ISO 29148이 도움이 되면서도 어려운가?

장점:
- 요구사항이 체계적으로 정의됨
- 각 요구사항에 ID, 우선순위, 상태가 있음
- 추적성이 뛰어남

단점:
- 예: "SYS-001: 시스템은 JSON 형식의 REST API를 지원해야 한다"
- 이걸 읽은 사용자는 "이게 나한테 뭐가 좋은데?"라고 생각함
- 300개의 요구사항들이 서로 어떻게 연결되는지 보이지 않음

우리의 역공학은 이 "왜?"를 해결합니다.
-->

### # Reasoning Strategy: ISO 요구사항 통합 5단계

#### 1단계: 요구사항 분류 및 매핑

ISO 29148의 요구사항들을 기능 관점으로 재그룹화합니다.

```
ISO 29148 요구사항 예시:
REQ-101: 시스템은 사용자 인증을 위해 LDAP을 지원해야 한다
REQ-102: 시스템은 OAuth 2.0을 지원해야 한다
REQ-103: 비밀번호는 최소 8자, 특수문자 포함해야 한다
REQ-104: 세션 타임아웃은 30분이어야 한다
REQ-105: 로그인 실패 3회 후 계정이 잠되어야 한다
...
REQ-250: API는 초당 1,000 요청을 처리해야 한다

분류:
┌─ 기능 A: 보안
│  ├─ 인증 (REQ-101, 102, 103, 104, 105)
│  ├─ 권한 관리 (REQ-...)
│  └─ 암호화 (REQ-...)
├─ 기능 B: 성능
│  ├─ 처리량 (REQ-250, ...)
│  ├─ 응답 시간 (REQ-...)
│  └─ 확장성 (REQ-...)
└─ 기능 C: 호환성
   ├─ 데이터 형식 (REQ-...)
   └─ 통합 API (REQ-...)
```

#### 2단계: 스테이크홀더 vs 요구사항 매트릭스

어떤 요구사항이 누구를 위한 것인지 명확히 합니다.

```
스테이크홀더별 관심 요구사항:

                  IT 보안  시스템팀  사용자   경영진   규제
─────────────────────────────────────────────────────────
보안 인증          ◆◆◆    ◆◆      ◆       -      ◆◆◆
성능/확장성        ◆      ◆◆◆     ◆◆      -      ◆
사용성             -      ◆       ◆◆◆    ◆◆      -
규정 준수          ◆◆     ◆◆      -      ◆◆◆    ◆◆◆

(◆◆◆ = 높은 관심, ◆◆ = 중간, ◆ = 낮음, - = 무관)

→ 각 스테이크홀더별 "왜 이 요구사항이 필요한가"가 다릅니다.
  PRD에서는 이를 "모두를 만족"하는 메시지로 통합해야 합니다.
```

#### 3단계: 사용자 여정에 요구사항 매핑

사용자가 제품을 사용하는 흐름에 맞춰 요구사항을 배열합니다.

```
사용자 여정: 신규 가입 → 로그인 → 작업 → 데이터 내보내기 → 탈퇴

각 단계의 요구사항:

[신규 가입]
- REQ-101: LDAP/OAuth 지원 → 기존 계정으로 빠르게 가입
- REQ-103: 비밀번호 정책 → 안전한 계정 생성
- REQ-205: 이메일 인증 → 본인 확인

[로그인]
- REQ-104: 세션 관리 → 안전한 로그인 상태 유지
- REQ-105: 계정 잠금 → 해킹 방지
- REQ-301: 단일 로그인 → 여러 애플리케이션 접근

[작업]
- REQ-250: 성능 (1,000 req/s) → 빠른 작업 완료
- REQ-250: 응답 시간 <200ms → 부드러운 사용감
- REQ-400: 동시 편집 → 팀 협업

[데이터 내보내기]
- REQ-210: 데이터 암호화 → 안전한 다운로드
- REQ-211: 감사 로그 → 규정 준수

[탈퇴]
- REQ-220: 데이터 삭제 → 개인정보 보호
- REQ-221: 삭제 확인 → 실수 방지

이렇게 정렬하면 "사용자가 겪는 경험"이 명확해집니다.
```

#### 4단계: 상충 요구사항 해결

서로 다른 스테이크홀더 요구사항이 충돌할 때를 처리합니다.

```
예시 상충:

IT 보안팀 요구사항: "비밀번호는 매일 변경해야 한다" (REQ-103-A)
사용자 요구사항: "비밀번호 변경 없이 쉽게 접근하고 싶다" (REQ-103-B)

해결 방법:
1. 우선순위 결정 → 보안 > 사용성 (금융 기관이므로)
2. 트레이드오프 찾기 → "매일 변경" 대신 "90일마다 변경"
3. 기술로 해결 → "생체 인증 옵션으로 대체"
4. PRD에 명시 → 왜 이 결정을 했는지 기록

최종:
"높은 보안 기준을 유지하면서도, 사용자 편의성을 위해
생체 인증 옵션을 제공합니다."
```

#### 5단계: PRD 작성 및 추적성 유지

변환된 요구사항을 PRD로 작성하되, 원본 ISO ID도 매핑합니다.

```
PRD 섹션:

## 기능: 안전한 로그인
- 설명: 여러 인증 방식(LDAP/OAuth/생체)으로 빠르고 안전하게 접근
- 대상 사용자: 모든 사용자
- 요구사항 추적성:
  ├─ REQ-101: LDAP 지원
  ├─ REQ-102: OAuth 2.0 지원
  ├─ REQ-103: 비밀번호 정책
  ├─ REQ-104: 세션 타임아웃
  ├─ REQ-105: 계정 잠금
  └─ REQ-106: 생체 인증

이렇게 하면:
✓ 원본 요구사항을 모두 추적할 수 있음
✓ 구현팀은 "어떤 ISO 요구사항을 만족하는가"를 알 수 있음
✓ 감사(Audit)에서 "이 기능이 왜 필요한가"를 설명 가능
```

### # 엔터프라이즈 특화

```
엔터프라이즈 프로젝트 특화:

1. 다중 부서 요구사항 통합
   - IT: 보안, 성능, 호환성
   - 비즈니스: ROI, 규정 준수, 사용자 경험
   - 운영: 관리성, 모니터링, 지원 가능성

   → PRD는 이들을 모두 만족하는 통합 비전을 제시

2. 변경 관리 (Change Request)
   - 새로운 요구사항이 추가될 때마다
   - "어떤 섹션을 변경하는가?"
   - "기존 요구사항과 충돌하는가?"
   - PRD가 이를 판단하는 기준

3. 릴리스 계획
   - 모든 요구사항을 한 번에 구현 불가
   - 릴리스별 우선순위 결정
   - PRD의 "비즈니스 가치" 정렬순으로 배정
```



### # 🇰🇷 한국 시장 PRD 특화 요구사항

```
한국 시장 요구사항 변환 시 주의점:

1. **규제 요구사항**:
   - 개인정보보호법 (PIPA) → GDPR과 다른 부분 명시
   - 전자문서법 → 전자서명/타임스탬프 요구사항
   - AI 기본법 (2026 시행) → 고위험 AI 분류 기준 확인

2. **한국 특수 기능 요구사항**:
   - 세금계산서 발행 (전자세금계산서 의무화)
   - 공공기관 납품 시: CSAP 인증, CC 인증
   - 접근성: 한국 웹접근성 인증(WA) 기준

3. **데이터 요구사항**:
   - 한국 데이터센터 필수 (금융/의료/공공)
   - 해외 전송 시 개인정보보호위원회 사전 동의
```

### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 요구사항 소스 파악 어려움 | 회의록, 이메일, 슬랙, 지원 티켓을 우선 확인하세요 |
| 2단계 | 중복 요구사항 정리 어려움 | 유사한 것을 그룹핑하고, 가장 명확한 표현으로 통합 |
| 3단계 | 우선순위 합의 어려움 | MoSCoW(Must/Should/Could/Won't)로 분류하세요 |
| 4단계 | 누락된 요구사항 발견 | "이 기능을 쓸 때 가장 짜증나는 순간은?"으로 추가 발굴 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 다양한 소스에서 요구사항을 자동 추출하여 PRD를 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
요구사항은 회의, 이메일, 슬랙 등에 흩어져 있습니다. 자동으로 수집해서 구조화하면 누락을 방지합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### ISO 요구사항 → PRD 변환 도구

```python
#!/usr/bin/env python3
"""
ISO 29148 요구사항 → PRD 자동 변환 도구
분산된 요구사항을 통합 PRD로 변환
"""

import anthropic
import json
import csv
from pathlib import Path
from typing import Optional, List
from collections import defaultdict


@dataclass
class Requirement:
    """ISO 29148 요구사항"""
    id: str
    title: str
    description: str
    stakeholder: str  # "IT", "Business", "User", "Compliance"
    priority: str  # "High", "Medium", "Low"
    category: str  # "Security", "Performance", "Usability", etc.


def parse_requirements_csv(csv_file: str) -> List[Requirement]:
    """
    CSV에서 ISO 요구사항 파싱

    CSV 형식:
    ID, Title, Description, Stakeholder, Priority, Category
    """
    requirements = []
    with open(csv_file, encoding="utf-8") as f:
        reader = csv.DictReader(f)
        for row in reader:
            req = Requirement(
                id=row["ID"],
                title=row["Title"],
                description=row["Description"],
                stakeholder=row["Stakeholder"],
                priority=row["Priority"],
                category=row["Category"]
            )
            requirements.append(req)
    return requirements


def group_requirements(requirements: List[Requirement]) -> dict:
    """요구사항을 카테고리별로 그룹화"""
    grouped = defaultdict(list)
    for req in requirements:
        grouped[req.category].append(req)
    return grouped


def requirements_to_prd(requirements: List[Requirement]) -> dict:
    """
    ISO 요구사항들을 PRD로 변환

    Args:
        requirements: Requirement 객체 리스트

    Returns:
        변환된 PRD (JSON)
    """

    client = anthropic.Anthropic()

    # 요구사항 텍스트로 변환
    req_text = "\n".join([
        f"{req.id}: [{req.category}] {req.title} (by {req.stakeholder}, Priority: {req.priority})\n"
        f"   Description: {req.description}"
        for req in requirements
    ])

    prompt = f"""당신은 엔터프라이즈 PM입니다.
다음 ISO 29148 요구사항들을 사용자 중심 PRD로 통합하세요.

**ISO 29148 요구사항들:**
{req_text}

**변환 규칙:**

1. 요구사항 그룹화
   - 같은 사용자 문제를 해결하는 요구사항들 통합
   - 예: 보안 관련 요구사항들 → "안전한 인증" 기능

2. 스테이크홀더 대조
   - IT 보안 vs 사용자 사용성 상충 해결
   - 모두를 만족하는 솔루션 찾기

3. 사용자 여정 정렬
   - 가입 → 로그인 → 작업 → 내보내기 순서로 정렬
   - 각 단계의 관련 요구사항을 함께 배치

4. 비즈니스 가치 변환
   - "REQ-250: 1,000 req/s 처리" → "수천 사용자가 동시 사용 가능"

**JSON 응답 형식:**

{{
  "product_overview": "제품 통합 설명",
  "features": [
    {{
      "name": "기능명",
      "description": "설명",
      "user_journey_stage": "어느 단계의 사용자를 위한가",
      "stakeholders": ["IT", "User"],
      "business_value": "사용자가 얻을 가치",
      "requirements": ["REQ-101", "REQ-102"],
      "traceability": "이 기능으로 충족하는 요구사항과 그 이유"
    }}
  ],
  "release_plan": {{
    "mvp": [
      {{"feature": "기능명", "requirements": ["REQ-101"]}}
    ],
    "v11": [...],
    "v12": [...]
  }},
  "conflicts_resolved": [
    {{
      "conflict": "상충하는 두 요구사항",
      "decision": "우리의 결정",
      "rationale": "이유"
    }}
  ],
  "success_metrics": [
    {{
      "metric": "메트릭명",
      "target": "목표치",
      "requirement_sources": ["REQ-250"]
    }}
  ]
}}

한글로 작성하세요.
"""

    message = client.messages.create(
        model="claude-opus-4-6",
        max_tokens=3000,
        messages=[{"role": "user", "content": prompt}]
    )

    try:
        import re
        json_match = re.search(r'\{.*\}', message.content[0].text, re.DOTALL)
        if json_match:
            prd = json.loads(json_match.group())
        else:
            prd = {"raw": message.content[0].text}
    except json.JSONDecodeError:
        prd = {"raw": message.content[0].text}

    return {
        "requirements_count": len(requirements),
        "converted_prd": prd,
        "tokens_used": message.usage.output_tokens
    }


def generate_traceability_matrix(prd: dict, requirements: List[Requirement]) -> str:
    """추적성 매트릭스 생성 (CSV)"""
    rows = [["Feature", "Business Value", "REQ ID", "REQ Title", "Category", "Stakeholder"]]

    for feature in prd.get("features", []):
        feature_name = feature.get("name", "")
        business_value = feature.get("business_value", "")
        reqs = feature.get("requirements", [])

        for req_id in reqs:
            req = next((r for r in requirements if r.id == req_id), None)
            if req:
                rows.append([
                    feature_name,
                    business_value,
                    req.id,
                    req.title,
                    req.category,
                    req.stakeholder
                ])

    csv_content = "\n".join([",".join(row) for row in rows])
    return csv_content


if __name__ == "__main__":
    # 예제: CSV에서 요구사항 파싱
    requirements = parse_requirements_csv("requirements.csv")

    # PRD 생성
    result = requirements_to_prd(requirements)
    print(json.dumps(result, ensure_ascii=False, indent=2))

    # 추적성 매트릭스 생성
    if "converted_prd" in result:
        traceability = generate_traceability_matrix(
            result["converted_prd"],
            requirements
        )
        print("\n=== TRACEABILITY MATRIX ===")
        print(traceability)

        # CSV 저장
        with open("traceability.csv", "w", encoding="utf-8") as f:
            f.write(traceability)
```

### Claude Code CLI 사용법

```bash
# 요구사항 → PRD 변환
claude run requirements-converter.py \
  --input requirements.csv \
  --output prd.json

# 추적성 매트릭스 생성
claude run traceability-matrix.py \
  --prd prd.json \
  --requirements requirements.csv \
  --output traceability.csv

# 릴리스 계획 생성
claude run release-planner.py --prd prd.json --duration 12
```

---

## 📊 실행 결과 예시

### Input: ISO 29148 요구사항 (일부)

```csv
ID,Title,Description,Stakeholder,Priority,Category
REQ-101,LDAP 지원,"시스템은 LDAP 기반 인증을 지원해야 한다",IT,High,Security
REQ-102,OAuth 지원,"시스템은 OAuth 2.0을 지원해야 한다",User,High,Security
REQ-103,비밀번호 정책,"비밀번호는 최소 8자이며 특수문자를 포함해야 한다",IT,High,Security
REQ-104,세션 타임아웃,"30분 동안 활동이 없으면 자동 로그아웃",IT,Medium,Security
REQ-105,계정 잠금,"실패 3회 후 계정이 30분간 잠겨야 한다",IT,High,Security
REQ-201,API 처리량,"REST API는 초당 1,000 요청을 처리해야 한다",Business,High,Performance
REQ-202,응답시간,"평균 응답 시간은 200ms 이하여야 한다",User,High,Performance
REQ-301,CSV 내보내기,"사용자는 데이터를 CSV로 내보낼 수 있어야 한다",User,Medium,Usability
REQ-401,감사 로그,"모든 중요 작업은 감사 로그에 기록되어야 한다",Compliance,High,Compliance
REQ-402,데이터 암호화,"저장된 데이터는 AES-256으로 암호화되어야 한다",IT,High,Compliance
```

### Output: PRD (변환)

```markdown
# 엔터프라이즈 데이터 관리 플랫폼 PRD

## 제품 개요
보안을 최우선으로 하면서도 사용자 편의성을 충족하는 엔터프라이즈 데이터 관리 플랫폼.
IT 조직의 보안 정책을 만족하면서도, 비즈니스 사용자가 빠르고 쉽게 데이터를 다룰 수 있습니다.

## 기능: 안전한 로그인 & 접근 제어

**설명:** 여러 인증 방식을 지원하면서도 높은 보안 기준을 유지합니다.

**사용자 여정 단계:** 가입 및 로그인

**대상 스테이크홀더:** IT 보안팀, 일반 사용자

**비즈니스 가치:**
- IT 조직: 강화된 보안으로 데이터 유출 위험 최소화
- 사용자: 기존 회사 계정(LDAP) 또는 Google 등으로 간편하게 접속 가능

**포함 요구사항:**
- REQ-101: LDAP 지원 (회사 네트워크 사용자)
- REQ-102: OAuth 2.0 지원 (외부 사용자)
- REQ-103: 비밀번호 정책 (최소 8자, 특수문자)
- REQ-104: 30분 세션 타임아웃 (무인 접근 방지)
- REQ-105: 3회 실패 후 계정 잠금 (무차별 대입 공격 방지)

**상충 해결:**
- 원래 IT 요구사항: "비밀번호 매일 변경"
- 사용자 불만: "너무 번거롭다"
- 최종 결정: "90일마다 변경" + "생체 인증 옵션"

---

## 기능: 빠른 성능 & 확장성

**설명:** 수백 명이 동시에 사용해도 부드러운 경험을 제공합니다.

**사용자 여정 단계:** 작업 수행

**대상 스테이크홀더:** 비즈니스 사용자, 경영진

**비즈니스 가치:**
- 직원 생산성: 느린 시스템 대기 시간 제거
- 기업 확장성: 사용자 증가에 따른 인프라 대응 가능

**포함 요구사항:**
- REQ-201: API 처리량 1,000 req/s
- REQ-202: 평균 응답 시간 200ms

**성공 메트릭:**
- 동시 사용자: 500명 (우리 조직 규모)
- p95 응답 시간: 500ms 이하
- 서비스 가용성: 99.9% 이상

---

## 기능: 규정 준수 & 감시

**설명:** 높은 규제 기준과 감사 요구사항을 만족하면서도 투명성을 제공합니다.

**사용자 여정 단계:** 전체 수명 주기

**대상 스테이크홀더:** 컴플라이언스팀, IT 보안팀, 감사자

**비즈니스 가치:**
- 규제 리스크 제거: GDPR, HIPAA 등 규정 준수
- 감사 효율성: 모든 활동이 기록되어 감사 용이
- 신뢰 구축: 고객과 파트너사 신뢰 증대

**포함 요구사항:**
- REQ-401: 감사 로그 (WHO, WHAT, WHEN, WHERE)
- REQ-402: 데이터 암호화 (AES-256)

---

## 릴리스 계획

### MVP (4주)
- 안전한 로그인 (REQ-101~105)
- 기본 성능 (REQ-201, 202)
- 감사 로그 기초 (REQ-401)

### v1.1 (4주)
- 생체 인증 옵션 (REQ-103 개선)
- 데이터 암호화 강화 (REQ-402)
- CSV 내보내기 (REQ-301)

### v1.2 (향후)
- 고급 감사 리포팅
- AI 기반 이상 탐지
- 자동 규정 준수 검증

---

## 상충 해결 기록

| 상충 | 관련 요구사항 | 결정 | 근거 |
|------|------------|------|------|
| 비밀번호 변경 빈도 (매일 vs 편하게) | REQ-103 | 90일마다, 생체 인증 옵션 | IT 보안과 사용성 균형 |
| 세션 타임아웃 (짧음 vs 길음) | REQ-104 | 30분 (기업 표준) | 보안 > 편의 |
| 로그인 방식 다양화 | REQ-101, 102 | LDAP + OAuth 지원 | 내부(LDAP)와 외부(OAuth) 모두 지원 |

---

## 요구사항 추적성 매트릭스

| 기능 | 비즈니스 가치 | REQ ID | REQ Title | 카테고리 | 스테이크홀더 |
|------|------------|--------|-----------|---------|------------|
| 안전한 로그인 | 편리하고 안전한 접속 | REQ-101 | LDAP 지원 | Security | IT |
| | | REQ-102 | OAuth 지원 | Security | User |
| | | REQ-103 | 비밀번호 정책 | Security | IT |
| 빠른 성능 | 생산성 향상 | REQ-201 | API 처리량 | Performance | Business |
| | | REQ-202 | 응답시간 | Performance | User |
| 규정 준수 | 감사 투명성 | REQ-401 | 감사 로그 | Compliance | Compliance |
| | | REQ-402 | 데이터 암호화 | Compliance | IT |
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 변환된 PRD에서 '원본에 없는 가정'이 추가되어 있지 않은지 확인하세요
2. **[논쟁 지점]** 요구사항의 '우선순위'를 요청자의 의도대로 할지, PM이 재평가할지는 상황에 따라 다릅니다
3. **[자기 검증]** 원본 요구사항 문서와 변환된 PRD를 나란히 놓고 빠진 항목이 없는지 확인하세요

---

## 🔗 다음 단계

1. **`prd-for-ai-feature.md`** → AI 기능 추가 시 요구사항 통합
2. **구현 추적** → 각 요구사항의 구현 상태 관리
3. **릴리스 검증** → 모든 요구사항이 충족되었는지 검증
4. **피드백 루프** → 배포 후 요구사항이 실제 사용자 가치를 제공했는지 확인
