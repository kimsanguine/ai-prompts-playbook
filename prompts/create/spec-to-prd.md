# 📋 스펙→PRD 역공학 (IEEE 830 Spec to PRD)

> 예상 소요: 10분 (Quick) / 30분 (Deep) / 45분+ (Build)
> 워크플로우: → `requirements-to-prd.md` → `prd-for-ai-feature.md`

---

## 🎯 이 프롬프트가 해결하는 문제

기존 기술 스펙(IEEE 830 SRS)은 "무엇을 만들 것인가"를 상세히 정의하지만, "왜 만드는가", "사용자가 얻을 가치는 뭔가"를 설명하지 않습니다.
**역공학(Reverse Engineering)** 기법으로 기술 스펙을 사용자 중심의 **PRD(Product Requirements Document)**로 변환하세요.
이는 새로운 팀원, 이해관계자, 마케팅 팀이 제품을 이해하는 시간을 획기적으로 줄입니다.

---

## 📥 이전 프롬프트에서 받는 입력

> 개발팀의 기술 스펙을 비즈니스 관점 PRD로 변환할 때 사용합니다.

**기술 스펙 문서 (API 명세, 아키텍처 문서 등)**를 직접 붙여넣으세요.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 기술 스펙을 비즈니스 관점의 PRD로 변환할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
기술 스펙 파일을 업로드하세요 (IEEE 830 SRS 형식).

자동으로 변환됩니다:
[기술 요구사항] → [비즈니스 가치]
[시스템 명세] → [사용자 페르소나]
[기능 스펙] → [유저 스토리]

결과: 마케팅/PM/경영진이 이해하는 PRD
```

💡 **Quick Tips:**
- 원본 스펙의 섹션을 모두 읽고, 숨겨진 "왜"를 찾으세요
- "비기능 요구사항"(Non-Functional Requirements)은 "기술 제약"으로 표현하세요


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 스펙이 너무 기술적 | "사용자에게 어떤 가치를 주는가?"를 먼저 정의하고 기술 내용을 번역하세요 |
| 스펙이 불완전 | 빈 항목은 "TBD (기술팀과 협의 필요)"로 표시하고 진행하세요 |
| 여러 스펙을 하나의 PRD로 | 기능 단위로 그룹핑한 후, 하나의 PRD에 섹션별로 정리 |
| 스펙과 PRD의 독자가 다름 | PRD에는 기술 용어를 "비즈니스 언어"로 번역하세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — 기술 스펙을 체계적으로 PRD로 변환하고 싶은 분입니다.
엔지니어의 기술 문서를 비즈니스 맥락이 포함된 PRD로 만들고 싶다면 이걸 써보세요.

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

PM, 기술 리더, 제품 전략가

### # 목표

**IEEE 830 기술 스펙 → 사용자 중심 PRD 변환**

- 기술 용어를 비즈니스 언어로 번역
- 시스템 아키텍처를 사용자 경험으로 재해석
- 제약과 성능 목표를 경쟁 우위로 프레이밍
- 스테이크홀더들이 "왜 이 기능인가"를 이해

<!-- 💬 왜 역공학이 필요한가?

IEEE 830 스펙 (기술팀이 봄):
"시스템은 500명 동시 접속을 지원해야 하며, DB 응답 시간은 200ms 이하여야 한다."

사용자/마케팅팀이 봐야 할 PRD:
"수천 명이 동시에 사용해도 빠른 응답(200ms)으로 부드러운 경험을 제공합니다."

같은 정보인데, 해석이 다릅니다.
스펙은 "제약"에, PRD는 "가치"에 초점을 맞춥니다.
-->

### # Reasoning Strategy: 역공학 5단계

#### 1단계: 기술 스펙 분석

원본 IEEE 830 스펙의 구조를 파악합니다.

```
IEEE 830 일반 구조:
├─ 1. 개요 (Overview)
├─ 2. 전체 설명 (Overall Description)
│  ├─ 2.1 제품 관점 (Product Perspective)
│  ├─ 2.2 제품 기능 (Product Functions)
│  ├─ 2.3 사용자 특성 (User Characteristics)
│  └─ 2.4 제약과 가정 (Constraints)
├─ 3. 요구사항 (Specific Requirements)
│  ├─ 3.1 기능 요구사항 (Functional)
│  ├─ 3.2 성능 요구사항 (Performance)
│  ├─ 3.3 설계 제약 (Design Constraints)
│  └─ 3.4 속성 (Attributes)
└─ 4. 부록 (Appendices)

이 섹션들을 PRD의 섹션으로 매핑합니다.
```

<!-- 💬 각 섹션이 왜 중요한가?
- 개요: "이 제품의 목표가 뭐지?" → PRD의 비전
- 전체 설명: "사용자가 어떻게 쓸까?" → PRD의 사용자 여정
- 요구사항: "뭘 구현할까?" → PRD의 기능 목록
- 제약: "뭘 못 할까?" → PRD의 범위/한계
-->

#### 2단계: 비즈니스 가치 추출

각 기술 요구사항 뒤에 숨겨진 비즈니스 가치를 찾습니다.

```
예시 변환:

기술 요구사항 (스펙):
"시스템은 수평 확장(Horizontal Scaling)을 지원해야 하며,
 최대 1,000명 동시 사용자를 처리할 수 있어야 한다."

비즈니스 가치 (PRD):
가치 = "1,000명이 동시에 사용해도 서비스 중단 없음"

추가 해석:
- 조직 전체가 동시에 대시보드에 접속 가능
- 월말 결산 마감일에도 느려지지 않음
- 사용자 확대 시 인프라 증축 걱정 없음

이 해석들이 PRD의 "기술적 우위" 섹션이 됩니다.
```

#### 3단계: 페르소나 & 사용 시나리오 추출

스펙의 "User Characteristics" 섹션을 사용자 페르소나로 변환합니다.

```
스펙의 기술적 표현:
"사용자는 네트워크 대역폭이 제한된 모바일 환경에서도 접속할 수 있어야 한다.
 API 응답 시간은 3G 기준 2초 이내여야 한다."

PRD의 페르소나 관점:
페르소나: "지방 영업사원 박준호"
- 시골 지역 거주
- 출장 중 3G 네트워크만 이용 가능
- 매일 오후 3시에 영역 매출을 확인해야 함
- 느린 앱 때문에 정시에 보고 못한 경험 있음

솔루션 = "박준호도 2초 내에 결과를 볼 수 있음"

이렇게 하면 마케팅팀도 타겟을 알 수 있습니다.
```

#### 4단계: 기능을 유저 스토리로 재해석

비즈니스 요구사항 → 기술 스펙 → 사용자 스토리로의 역방향 흐름입니다.

```
스펙의 기능 정의:
"시스템은 OAuth 2.0 기반의 SSO를 지원해야 하며,
 사용자는 기존 Google/Microsoft 계정으로 로그인할 수 있어야 한다."

PRD의 유저 스토리:
As a 바쁜 임원,
I want to Google 계정으로 로그인하기를
(비밀번호 기억할 필요 없음)
So that 빠르게 시스템에 접속할 수 있다.

수용 기준:
[ ] Google 계정 선택 후 3초 내 로그인 완료
[ ] 기존 Google 프로필 사진이 자동 동기화됨
```

#### 5단계: PRD 작성

변환된 요소들을 PRD 구조로 정리합니다.

```
PRD 구조:

# [제품명]

## 1. 비전 & 가치 제안
  (스펙의 "개요" 섹션에서 도출)

## 2. 사용자 페르소나 & 문제점
  (스펙의 "User Characteristics"에서 도출)

## 3. 솔루션 개요 & 핵심 기능
  (스펙의 "기능 요구사항"을 비즈니스 관점으로)

## 4. 상세 기능 명세
  (스펙의 각 기능 요구사항 → 유저 스토리 형태)

## 5. 기술적 우위 & 제약
  (스펙의 "비기능 요구사항" → 경쟁 우위)

## 6. 성공 메트릭
  (스펙의 "성능 요구사항" → 비즈니스 메트릭)

## 7. 로드맵
  (스펙의 선택사항들 → 릴리스 계획)
```

### # 한국 SaaS 특화

```
한국 시장 번역 팁:

1. 규정 → 경쟁 우위
   스펙: "ISMS 인증 획득 및 유지"
   PRD: "금융 등급의 보안으로 엔터프라이즈 신뢰 획득"

2. 기술 용어 → 사용자 언어
   스펙: "Rest API 기반 아키텍처"
   PRD: "어디서나 데이터에 접근 가능"

3. 제약 → 특화 기능
   스펙: "한글과 영어만 지원"
   PRD: "한국 기업을 위해 한글 최적화"
```


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | 기술 용어 이해 어려움 | AI에게 "이 기술 용어를 비개발자에게 설명해줘"라고 요청 |
| 2단계 | 비즈니스 가치 추출 어려움 | "이 기능이 없으면 사용자가 뭘 못 하는가?"로 역추론 |
| 3단계 | 요구사항 우선순위 모호 | "MVP에 반드시 필요한가?"를 기준으로 분류 |
| 4단계 | 성공 메트릭 연결 어려움 | "이 기능 출시 후 어떤 숫자가 바뀔까?"로 접근 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — 기술 스펙에서 자동으로 PRD 초안을 생성합니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
기술 스펙이 자주 업데이트되면, PRD도 동기화해야 합니다. 자동화하면 스펙 변경 시 PRD가 자동으로 갱신됩니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### 스펙→PRD 변환 Python 도구

```python
#!/usr/bin/env python3
"""
IEEE 830 스펙 → PRD 자동 변환 도구
Claude API를 사용하여 역공학 수행
"""

import anthropic
import json
from pathlib import Path
from typing import Optional


def parse_ieee_830_spec(spec_text: str) -> dict:
    """IEEE 830 스펙 파일 파싱"""
    sections = {
        "overview": "",
        "overall_description": "",
        "user_characteristics": "",
        "constraints": "",
        "functional_requirements": "",
        "performance_requirements": "",
        "design_constraints": "",
        "attributes": ""
    }

    # 간단한 섹션 추출 (프로덕션에서는 더 정교한 파싱 필요)
    current_section = None
    for line in spec_text.split("\n"):
        for section_key in sections.keys():
            if section_key.replace("_", " ").title() in line:
                current_section = section_key
                break

        if current_section:
            sections[current_section] += line + "\n"

    return sections


def spec_to_prd(spec_file_path: str) -> dict:
    """
    IEEE 830 스펙을 PRD로 변환

    Args:
        spec_file_path: 스펙 텍스트/마크다운 파일 경로

    Returns:
        변환된 PRD (JSON)
    """

    # 파일 읽기
    spec_text = Path(spec_file_path).read_text(encoding="utf-8")

    client = anthropic.Anthropic()

    prompt = f"""당신은 기술 스펙을 사용자 중심 PRD로 변환하는 전문가입니다.

다음 IEEE 830 기술 스펙을 PRD(Product Requirements Document)로 역공학하세요.

**원본 스펙:**
{spec_text[:3000]}  # 토큰 관리를 위해 처음 3000 글자만

**변환 규칙:**
1. 비즈니스 가치 추출
   - 각 기술 요구사항 뒤의 "왜?"를 찾으세요
   - "500ms 응답시간" → "사용자가 느끼는 빠른 속도"

2. 페르소나 & 시나리오
   - "User Characteristics" 섹션을 구체적 페르소나로
   - 각 페르소나의 "1일 사용 시나리오" 작성

3. 기능 재해석
   - "OAuth 2.0 SSO" → "Google 계정으로 편리하게 로그인"
   - "As a [페르소나], I want to..., So that..."

4. 경쟁 우위
   - 성능, 보안, 확장성 요구사항 → 마케팅 메시지

**JSON 응답 형식:**

{{
  "product_name": "제품명",
  "vision": "비전 (1-2문장)",
  "personas": [
    {{
      "name": "페르소나명",
      "role": "역할",
      "pain_points": ["문제1", "문제2"],
      "daily_scenario": "1일 사용 시나리오"
    }}
  ],
  "key_features": [
    {{
      "feature": "기능명",
      "user_story": "As a..., I want to..., So that...",
      "business_value": "이로 인한 가치"
    }}
  ],
  "technical_advantages": [
    {{"spec": "기술 요구사항", "value": "사용자가 느끼는 가치"}}
  ],
  "success_metrics": [
    {{"metric": "메트릭", "target": "목표치", "why": "왜 이 메트릭인가"}}
  ],
  "roadmap": {{
    "mvp": {{"features": ["기능1", "기능2"], "timeline": "시간"}},
    "v11": {{"features": ["기능3", "기능4"], "timeline": "시간"}}
  }},
  "constraints_and_scope": {{
    "in_scope": ["포함 사항"],
    "out_of_scope": ["제외 사항"],
    "dependencies": ["의존성"]
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
            prd = json.loads(json_match.group())
        else:
            prd = {"raw": message.content[0].text}
    except json.JSONDecodeError:
        prd = {"raw": message.content[0].text}

    return {
        "spec_file": spec_file_path,
        "converted_prd": prd,
        "tokens_used": message.usage.output_tokens
    }


def generate_prd_markdown(prd_json: dict) -> str:
    """PRD JSON을 마크다운 형식으로 출력"""

    md = f"""# {prd_json.get('product_name', 'Product')} PRD

## 비전 & 가치 제안
{prd_json.get('vision', '')}

## 사용자 페르소나
"""

    for persona in prd_json.get('personas', []):
        md += f"""
### {persona.get('name', 'User')}
**역할:** {persona.get('role', '')}

**Pain Points:**
"""
        for pain in persona.get('pain_points', []):
            md += f"- {pain}\n"

        md += f"""
**1일 시나리오:**
{persona.get('daily_scenario', '')}

"""

    md += "## 핵심 기능\n"
    for feature in prd_json.get('key_features', []):
        md += f"""
### {feature.get('feature', '')}
**사용자 스토리:** {feature.get('user_story', '')}

**비즈니스 가치:** {feature.get('business_value', '')}

"""

    md += "## 기술적 우위\n"
    for adv in prd_json.get('technical_advantages', []):
        md += f"- **{adv.get('spec', '')}** → {adv.get('value', '')}\n"

    md += "\n## 성공 메트릭\n"
    for metric in prd_json.get('success_metrics', []):
        md += f"- {metric.get('metric', '')}: {metric.get('target', '')} ({metric.get('why', '')})\n"

    return md


if __name__ == "__main__":
    # 예제: spec.md 파일 변환
    result = spec_to_prd("spec.md")

    print(json.dumps(result, ensure_ascii=False, indent=2))

    # 마크다운 생성
    if "converted_prd" in result:
        md_output = generate_prd_markdown(result["converted_prd"])
        print("\n=== GENERATED PRD ===")
        print(md_output)

        # 파일 저장
        with open("prd_from_spec.md", "w", encoding="utf-8") as f:
            f.write(md_output)
```

### Claude Code CLI 사용법

```bash
# 스펙 → PRD 변환
claude run spec-to-prd.py --input ieee830_spec.md --output prd.json

# PRD 마크다운 생성
claude run generate-prd-markdown.py --input prd.json --output prd.md

# 배치 변환 (여러 스펙)
claude run batch-spec-converter.py --input-dir ./specs --output-dir ./prds
```

---

## 📊 실행 결과 예시

### Input: 기술 스펙 (일부)

```
## IEEE 830 SRS

### 2.3 User Characteristics
- 역할: 데이터 분석가, PM, 경영진
- 기술 숙련도: 중간~높음
- 네트워크 환경: 사무실(고속), 원격(3G/4G)

### 3.1 Functional Requirements
- FR1: 사용자는 CSV/Excel/DB에서 데이터를 임포트할 수 있어야 한다
- FR2: 시스템은 데이터에 대해 기본 통계 계산을 지원해야 한다
  (합계, 평균, 표준편차, 분위수)
- FR3: 사용자는 필터와 그룹화를 통해 데이터를 분석할 수 있어야 한다

### 3.2 Performance Requirements
- PR1: 최대 1GB 파일 임포트 시 30초 이내 완료
- PR2: 필터링된 데이터셋(1M 행)의 통계 계산: 2초 이내
- PR3: 동시 접속 1,000명 처리 (평균 응답 200ms, p95 500ms)

### 3.4 Design Constraints
- DC1: 한글/영어 기본 지원
- DC2: ISMS 인증 준수
- DC3: 모바일 반응형 UI 필수
```

### Output: PRD (변환)

```markdown
# 데이터 분석 플랫폼 PRD

## 비전 & 가치 제안
비즈니스 데이터를 누구나 빠르게 분석할 수 있는 플랫폼.
기술 지식 없이도 통계와 시각화로 인사이트를 얻을 수 있습니다.

## 사용자 페르소나

### 페르소나 1: 마케팅 담당자 "김경미"
**역할:** 마케팅 캠페인 성과 분석

**Pain Points:**
- 엑셀로 데이터를 정리하는 데 2시간 소요
- 통계 함수를 매번 다시 배워야 함
- 출장 중 스마트폰에서 데이터를 볼 수 없음

**1일 시나리오:**
아침에 도착 → CSV 파일을 플랫폼에 드래그 & 드롭
(자동 임포트, 30초 완료) → 필터링하여 어제의 인상 있는 성과 확인
→ 스마트폰에서 그래프 확인 → 경영진 보고

## 핵심 기능

### 기능 1: 다중 소스 임포트
**사용자 스토리:** As a 마케팅 담당자, I want to
CSV, Excel, 데이터베이스에서 한 번에 임포트하기를,
So that 데이터 정리 시간을 90% 줄일 수 있다

**비즈니스 가치:** 데이터 수집 시간 2시간 → 10분 (매일 2시간 절약)

### 기능 2: 자동 통계 계산
**사용자 스토리:** As a 분석가, I want to
버튼 하나로 통계를 자동 계산하기를,
So that 함수를 기억할 필요 없다

**비즈니스 가치:** 기술 장벽 제거, 누구나 분석 가능

### 기능 3: 반응형 모바일 UI
**사용자 스토리:** As a 임원, I want to
스마트폰에서 차트를 빠르게 확인하기를,
So that 이동 중에도 실시간 데이터 파악 가능

**비즈니스 가치:** 의사결정 속도 향상

## 기술적 우위
- **1GB 파일 30초 임포트** → 경쟁사의 "몇 분" 대비 압도적 속도
- **p95 500ms 응답** → 1,000명 동시 사용도 부드러운 경험
- **ISMS 인증** → 금융, 의료 등 규제 산업도 사용 가능
- **모바일 최적화** → 필드 근무자도 실시간 데이터 확인

## 성공 메트릭
| 메트릭 | 목표 | 이유 |
|--------|------|------|
| 임포트 시간 | <30초 (1GB) | 사용자 일일 작업 시간 절약 |
| 응답 시간 | p95 <500ms | 부드러운 사용자 경험 |
| 동시 접속 | 1,000명 | 엔터프라이즈 고객 요구 |
| 모바일 사용률 | >30% | 필드 근무 확대 |

## 로드맵
**MVP (4주)**
- 기본 임포트 (CSV, Excel)
- 통계 계산 (합계, 평균)
- 기본 필터링

**v1.1 (4주)**
- DB 직접 연결
- 고급 통계 (분위수, 표준편차)
- 모바일 최적화

**v1.2+ (향후)**
- AI 인사이트
- 실시간 데이터 연동
- 자동 리포팅
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** 변환된 PRD에서 '기술 용어'가 비즈니스 용어로 제대로 번역되었는지 확인하세요
2. **[논쟁 지점]** 기술 스펙 → PRD 변환 시 '기술적 제약'을 PRD에 명시할지 숨길지는 청중에 따라 다릅니다
3. **[자기 검증]** 원본 기술 스펙의 핵심 제약사항 1개가 PRD에 반영되어 있는지 확인하세요

---

## 🔗 다음 단계

1. **`requirements-to-prd.md`** → ISO 29148 요구사항 표준도 PRD로 변환
2. **스테이크홀더 검증** → 변환된 PRD를 PM, 마케팅, 경영진과 검토
3. **로드맵 수립** → PRD 기반 릴리스 계획 수립
