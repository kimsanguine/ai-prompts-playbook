# 💼 JTBD 분석 (Jobs to be Done)

> 예상 소요: 5분 (Quick) / 25분 (Deep) / 35분+ (Build)
> 워크플로우: → `persona-profiling.md` → `problem-framing.md` → `feature-prioritization.md` (decide/)

---

## 🎯 이 프롬프트가 해결하는 문제

고객이 "우리 제품을 왜 쓰나"를 표면적으로만 이해합니다. 제품 기능이 아니라 **고객이 그 기능으로 이루려는 진짜 목표**를 모르면, 기능 개선이 헛갈리고 경쟁 차별화도 약해집니다. JTBD 분석은 고객이 "고용"하는 진짜 이유(기능 X, 감정 O, 문제 해결 O)를 발굴합니다.

---

## 📥 이전 프롬프트에서 받는 입력

> `problem-framing.md`에서 정의한 문제를 사용자 관점으로 재구성할 때 연결됩니다.

이전 프롬프트 결과에서 **문제 정의, 타겟 사용자, 현재 대안**을 가져옵니다.

---

## ⚡ Layer 1: Quick Start

> **이 레이어가 하는 일: 전문가의 눈 빌리기**
> 전문가가 이 분야를 볼 때 쓰는 프레이밍을 빌려줍니다. AI를 처음 쓰는 분, 비개발자, 학생 — 5분이면 고객의 핵심 Job을 파악할 수 있습니다.

### 📌 사용법

1. **ChatGPT, Claude, Gemini 중 아무 AI 챗봇**을 열고 새 대화를 시작하세요
2. 아래 프롬프트를 **통째로 복사**해서 AI에 붙여넣으세요
3. `{중괄호}` 안의 내용만 여러분의 상황에 맞게 바꾸세요
4. Enter를 누르면 끝!

> 📖 더 자세한 사용법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


```
{제품/서비스}를 쓰는 고객들의 "진짜 목표"를 찾으세요.

"고객은 우리를 고용한다" = 자신의 문제를 해결하기 위해
제품 자체가 목표 X
제품으로 이루려는 상태/결과가 목표 O

예:
- 고객이 Slack을 "고용"하는 이유?
  ❌ "메시지 앱을 쓰려고"
  ✓ "팀 소통 지연을 줄이고 협업 속도를 올리려고"

1. 주요 고객 세그먼트를 선택하세요
2. 각 세그먼트가 우리 제품으로 해결하는 문제 2-3개를 쓰세요
3. "언제" "누가" "왜" 형식으로 상황을 묘사하세요

상황 1: [When] ___, [Who] ___는 [Job] ___를 하고 싶어한다.
상황 2: ...
상황 3: ...
```

**💡 Quick Tips:**
- "왜" 답변이 깊을수록 좋음 (3단계 깊게 파기)
- 실제 고객 인터뷰 한 번이 가정보다 10배 낫습니다
- "나는..." X, "고객은..." O


### ⚠️ 이런 경우는요?

| 상황 | 대처법 |
|------|--------|
| 고객 인터뷰 데이터가 없음 | 앱스토어 리뷰, 지원 티켓, 경쟁사 리뷰에서 Job 힌트를 추출하세요 |
| Job이 너무 추상적 | "언제", "어디서", "왜" 조건을 추가하세요. 예: "출근길에 빠르게 뉴스를 확인하고 싶다" |
| B2B 제품이라 Job이 복잡 | 구매자, 사용자, 관리자의 Job을 따로 분석하세요 |
| Job이 너무 많음 | 빈도 × 중요도로 우선순위를 매기세요 |

---

## 🧠 Layer 2: Deep Dive

> **이 레이어는 누구를 위한 건가요?**
> PM, 기획자, 마케터 — JTBD 분석을 전문가 수준으로 수행하고 싶은 분입니다.
고객이 "진짜 하고 싶은 일"을 깊이 파악하고 싶다면 이걸 써보세요.

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


```
# 역할: 고객 문제 심리학자
# 목표: 제품 기능이 아닌 고객의 "일"(job)을 파악

# JTBD (Jobs to be Done) 프레임워크 설명
<!-- 💬 JTBD는 Clayton Christensen(혁신의 딜레마 저자)이 창안한 프레임워크입니다.
     핵심: 고객은 제품을 원하는 게 아니라, 제품으로 자기 일을 처리하고 싶어합니다.

     예시 (스타벅스 연구):
     고객이 스타벅스 커피를 "고용"하는 이유?
     ❌ "커피를 마시려고" (기능)
     ✓ "지루한 출퇴근 시간을 보내려고" (감정/상황)
     ✓ "전문가처럼 보이려고" (정체성/사회적)
     ✓ "아침 의식 (ritual)을 유지하려고" (습관)

     이렇게 이해하면:
     - 가격 결정: "저렴하게"가 아니라 "가치 있게"
     - 마케팅: "최고의 커피" X, "출퇴근 친구" O
     - 신제품: "새 음료" X, "새로운 출퇴근 의식" O
-->

# Reasoning Strategy

1단계: 세그먼트별 상황 정의
   <!-- 💬 같은 제품이라도 고객마다 "일"이 다릅니다.
        초보자(학생) vs 전문가(CEO)는 같은 앱으로도 다른 job을 해요 -->

   - 세그먼트 A: {구체적 인물}
     * 직책: ___
     * 당면 상황: ___
     * 사용 빈도: ___

   - 세그먼트 B: {구체적 인물}
   - 세그먼트 C: {구체적 인물}

2단계: 각 세그먼트의 "상황" 분석 (JTBD 핵심)
   <!-- 💬 "상황" (Context)이 job을 결정합니다.
        같은 사람도 상황에 따라 다른 job을 합니다.
        예: 회의실에서는 "음성 통화" job, 버스에서는 "비동기 메시지" job -->

   상황 + 감정 조합 = Job의 조건

   세그먼트 A의 상황들:
   - When: _____ (시간/장소/사건)
     Who: _____ (역할/직책)
     Struggling with: _____ (당면 어려움)
     Wants to: _____ (이루려는 목표)

3단계: 기능이 아닌 "결과"로 job을 표현
   <!-- 💬 "우리 기능을 쓴다" X
        "이 상황에서 이 결과를 얻고 싶어한다" O

        비교:
        기능 중심: "알림 시스템이 있다"
        Job 중심: "중요한 일이 빠져나가지 않기를 원한다"
   -->

   우리 제품이 해결하는 jobs (상위 3-5개):
   - Job 1: _____ (감정/상태 기반)
   - Job 2: _____
   - Job 3: _____
   - Job 4: _____
   - Job 5: _____

4단계: Functional / Emotional / Social Jobs 분류
   <!-- 💬 job은 3가지 차원이 있습니다.

        Functional Job (기능적): "효율적으로 끝내기"
        Emotional Job (감정적): "안심하고 싶어", "전문가처럼 보이고 싶어"
        Social Job (사회적): "팀에서 신뢰받고 싶어", "부모로서의 책임"

        대부분의 경쟁사는 Functional만 봅니다.
        Emotional + Social을 이해하면 차별화됩니다!
   -->

   Job 1: [기능] + [감정] + [사회적]
   - Functional: _____
   - Emotional: _____
   - Social: _____

   (모든 job에 대해 반복)

5단계: 고객의 "포기 대안" 이해
   <!-- 💬 중요한 통찰!
        고객이 우리를 선택하지 않으면 뭘 할까요?
        경쟁사? 아니면 우리와 전혀 다른 대안?

        예: Notion 사용자가 Notion을 안 쓰면?
        → 경쟁사(Confluence) X
        → 대부분: Google Docs + 엑셀 조합으로 돌아감

        이걸 알면 마케팅이 확 달라집니다:
        "Notion vs Confluence" 비교 X
        "수기 작업 → 자동화" 스토리 O
   -->

   고객이 없을 때 사용하는 "대체 job 처리 방식":
   - 대안 1: _____
   - 대안 2: _____
   - 대안 3: _____

   (우리가 이겨야 할 "대안 경쟁자"는 누구인가?)

6단계: Job을 만족하는 "성공 지표" 정의
   <!-- 💬 Job을 이해했으면 측정할 수 있어야 합니다.

        기능 중심: "다운로드 수" 측정
        Job 중심: "이 job을 성공적으로 처리했나?" 측정

        예: Slack의 "팀 소통 지연 줄이기" job이라면
        → 측정: 평균 응답 시간, 회의 시간 감소율
   -->

   각 job을 만족했는지 측정하는 지표:
   - Job 1의 성공: _____ (수치화 가능한가?)
   - Job 2의 성공: _____
   ...

7단계: 작성한 job들을 검토하세요.
   <!-- 💬 자기검증 체크리스트:
        [ ] 각 job이 "기능"으로 표현되지 않았나?
        [ ] "언제, 누가, 왜"가 구체적인가?
        [ ] 실제 고객 인터뷰로 검증했나? (가정만 하진 않았나?)
        [ ] 경쟁사도 같은 job을 해결하나? (우리만의 job인가?)
        [ ] 고객의 포기 대안이 정확한가?
   -->

# 컨텍스트와 데이터
## 제품 / 서비스: {제품명}
## 주요 고객 세그먼트: {세그먼트 A, B, C}
## 분석 대상 기간: {최근 3개월 / 6개월 / 1년}
## 고객 인터뷰 또는 데이터 소스:
   - {고객 인터뷰 몇 명}
   - {사용 데이터 (GA, Mixpanel 등)}
   - {고객 지원 피드백}
```

**💡 Deep Tips:**

- **데이터 수집:**
  - 고객 심층 인터뷰 (5명 이상, 30분 이상)
  - "언제 우리 제품을 처음 생각했나?" 역사 추적
  - "우리 없이 어떻게 하고 있었나?" 이전 방식 이해
  - "지금 어떤 점이 불만인가?" 미충족 job 발견
  - 사용자 테스트 (실제 사용 관찰)

- **AI 제품이라면:**
  - AI 기능이 해결하는 job: "반복 작업 자동화" (functional)
  - AI가 없으면: "전문가처럼 보이기" 불가능 (emotional)
  - AI 신뢰: "AI의 답을 믿을 수 있나?" (emotional)
  - 데이터 안전: "내 데이터가 안전한가?" (emotional/social)
  - 학습 곡선: "AI와 대화하는 방식 배우기" (functional)

- **한국 SaaS:**
  - "한국 법을 지키는가?" (Social job)
  - "한국 팀에서 빨리 적응되나?" (Emotional)
  - "한국 고객 지원이 있나?" (Functional)
  - "한국 동료들도 쓰니까 쓴다" (Social job — 네트워크 효과)
  - "블라인드에서 평판이 좋다" (Emotional/Social)

- **Product Trio 확장:**
  - **PM:** job 기반 우선순위 (이 기능이 가장 중요한 job을 해결하나?)
  - **엔지니어:** job 완성에 필요한 기술 (성능, 안정성, 보안)
  - **디자이너:** job 수행 시 사용자 감정 반영 (복잡하지 않은 UI?)


### ⚠️ 단계별 예외 처리

| 단계 | 예외 상황 | 대처법 |
|------|-----------|--------|
| 1단계 | Functional Job과 Emotional Job 구분 어려움 | "이 행동으로 무엇을 달성하나?" = Functional, "이때 어떤 기분이 드나?" = Emotional |
| 2단계 | Job Statement 문법이 어색 | "[상황]에서, [행동]을 해서, [결과]를 달성하고 싶다" 템플릿을 사용하세요 |
| 3단계 | 경쟁 대안 파악 어려움 | "고객이 우리 제품 없이 이 Job을 어떻게 해결하나?"를 물어보세요 |
| 4단계 | 기회 점수 계산이 복잡 | 중요도(1-10) - 만족도(1-10) = 기회 점수. 양수가 클수록 기회 |

---

## 🔧 Layer 3: Build & Automate

> **이 레이어는 누구를 위한 건가요?**
> AI 엔지니어, 개발자 — JTBD 분석 과정을 자동화 파이프라인으로 만듭니다.

### 📌 시작 전에

**이 코드가 하는 일:**
Layer 1-2에서 수동으로 했던 과정을 Python 스크립트로 자동화합니다.

**왜 자동화하나?**
JTBD는 한 번이 아니라 제품이 진화할 때마다 반복해야 합니다. 인터뷰 데이터를 입력하면 자동으로 Job Map을 생성합니다.

**전제조건:**
- Python 3.8+ 설치
- 필요한 패키지 설치 (코드 상단의 import 참고)
- Anthropic API 키 발급 → 환경변수 설정: `export ANTHROPIC_API_KEY=your_key`

> 📖 더 자세한 설정 방법은 [프롬프트 사용 가이드](../meta/how-to-use.md)를 참고하세요.


### Python + API 자동화

```python
import json
from datetime import datetime
from typing import Dict, List
from anthropic import Anthropic

class JobAnalyzer:
    def __init__(self, product_name: str):
        self.product_name = product_name
        self.client = Anthropic()
        self.jobs = []

    def extract_jobs_from_interviews(self, interview_transcripts: List[str]) -> List[Dict]:
        """
        고객 인터뷰 텍스트에서 jobs 자동 추출
        """
        combined_text = "\n\n".join(interview_transcripts)

        prompt = f"""
당신은 JTBD (Jobs to be Done) 전문가입니다.

다음은 {self.product_name} 사용자들의 인터뷰 기록입니다:

{combined_text}

이 인터뷰들에서:

1. 사용자가 "고용"하는 jobs을 찾으세요 (기능 X, 목표 O)
2. 각 job을 다음 형식으로 정리하세요:
   - When: [상황]
   - Who: [사용자]
   - Job: [해결하려는 일]
   - Emotional aspect: [감정]
   - Social aspect: [사회적 측면]
   - Successful outcome: [성공 상태]

3. job들의 빈도순으로 정렬하세요 (가장 많은 사람이 언급한 job이 먼저)

JSON 형식으로 응답하세요.
        """

        message = self.client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        try:
            response_text = message.content[0].text
            # JSON 파싱 (실제 구현에서는 더 견고하게)
            import re
            json_match = re.search(r'\[.*\]', response_text, re.DOTALL)
            if json_match:
                jobs = json.loads(json_match.group())
                return jobs
        except Exception as e:
            print(f"Job 추출 오류: {e}")

        return []

    def analyze_job_satisfaction(self, jobs: List[Dict],
                                 usage_data: Dict) -> List[Dict]:
        """
        각 job의 만족도 분석
        """
        prompt = f"""
다음은 {self.product_name}의 주요 jobs입니다:

{json.dumps(jobs, ensure_ascii=False, indent=2)}

그리고 사용 데이터:

{json.dumps(usage_data, ensure_ascii=False, indent=2)}

각 job에 대해:
1. 얼마나 잘 해결되고 있나? (점수 1-10)
2. 어떤 부분이 미충족인가?
3. 이 job을 해결하지 못하면 고객이 다른 대안을 찾나?
4. 우리의 차별화 포인트는?

JSON으로 분석 결과를 정리하세요.
        """

        message = self.client.messages.create(
            model="claude-opus-4-6",
            max_tokens=2000,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        # 응답 파싱
        return message.content[0].text

    def identify_alternatives(self, jobs: List[Dict]) -> Dict:
        """
        고객이 우리 없이 어떻게 같은 job을 처리하는지 파악
        """
        prompt = f"""
{self.product_name}의 주요 jobs:

{json.dumps(jobs, ensure_ascii=False, indent=2)}

각 job에 대해:
1. 우리 제품 없이 고객은 어떤 방식으로 이 job을 처리하나?
2. 그 대체 방식의 문제점은?
3. 우리 제품과의 비교 포인트?

구체적인 예시를 들어 설명하세요.
        """

        message = self.client.messages.create(
            model="claude-opus-4-6",
            max_tokens=1500,
            messages=[
                {"role": "user", "content": prompt}
            ]
        )

        return message.content[0].text

    def generate_report(self, interview_transcripts: List[str],
                       usage_data: Dict = None) -> Dict:
        """
        전체 JTBD 분석 리포트 생성
        """
        report = {
            'product': self.product_name,
            'generated_at': datetime.now().isoformat(),
            'jobs': [],
            'satisfaction_analysis': '',
            'alternatives': ''
        }

        # 1단계: 인터뷰에서 jobs 추출
        print("인터뷰에서 jobs 추출 중...")
        self.jobs = self.extract_jobs_from_interviews(interview_transcripts)
        report['jobs'] = self.jobs

        # 2단계: job 만족도 분석
        print("job 만족도 분석 중...")
        if usage_data:
            report['satisfaction_analysis'] = self.analyze_job_satisfaction(
                self.jobs, usage_data
            )

        # 3단계: 대체 방식 파악
        print("대체 방식 파악 중...")
        report['alternatives'] = self.identify_alternatives(self.jobs)

        return report

    def to_markdown(self, report: Dict) -> str:
        """마크다운 형식으로 내보내기"""
        output = f"# {self.product_name} JTBD 분석\n\n"
        output += f"분석일시: {report['generated_at']}\n\n"

        output += "## 주요 Jobs\n\n"
        for i, job in enumerate(report['jobs'], 1):
            output += f"### Job {i}: {job.get('job', 'N/A')}\n"
            output += f"- **상황 (When):** {job.get('when', 'N/A')}\n"
            output += f"- **사용자 (Who):** {job.get('who', 'N/A')}\n"
            output += f"- **감정 (Emotional):** {job.get('emotional', 'N/A')}\n"
            output += f"- **사회적 (Social):** {job.get('social', 'N/A')}\n"
            output += f"- **성공 조건:** {job.get('success', 'N/A')}\n\n"

        output += "## 만족도 분석\n\n"
        output += report.get('satisfaction_analysis', 'N/A')

        output += "\n## 대체 방식\n\n"
        output += report.get('alternatives', 'N/A')

        return output

# 사용 예
if __name__ == "__main__":
    analyzer = JobAnalyzer("Notion")

    # 샘플 인터뷰 텍스트
    interviews = [
        "사용자A: Notion으로 할일 목록을 만드는데, 예전에는 종이에 써서 잃어버렸어요...",
        "사용자B: 팀과 프로젝트 정보를 공유해야 해서 Notion을 썼어요. 전에는 이메일로 계속 물어봐야 했고...",
    ]

    report = analyzer.generate_report(interviews)

    with open("jtbd-analysis-notion.md", "w", encoding="utf-8") as f:
        f.write(analyzer.to_markdown(report))

    print("JTBD 분석이 완료되었습니다!")
```

### Claude Code / CLI 연동

```bash
# JTBD 분석 실행 (인터뷰 텍스트 파일 입력)
claude_code \
  --model claude-opus-4-6 \
  --file job_analyzer.py \
  --args product_name="Figma" \
  --input interviews.txt \
  --output jtbd-analysis-figma.md

# 여러 제품 JTBD 비교
for product in "Figma" "Sketch" "Adobe XD"; do
  claude_code \
    --model claude-opus-4-6 \
    --file job_analyzer.py \
    --args product_name="$product" \
    --input interviews-${product// /-}.txt \
    --output jtbd-${product// /-}.md
done

# 최종 통합 분석
claude_code \
  --model claude-opus-4-6 \
  --prompt "다음 3개 제품의 JTBD를 비교: $(cat jtbd-*.md)" \
  --output competitive-jobs-analysis.md
```

---

## 📊 실행 결과 예시

### Layer 1 실행 결과

```
[ChatGPT에 Quick Start 프롬프트 입력]

Notion을 쓰는 고객들의 "진짜 목표"를 찾으세요...

=== 결과 (5분) ===

상황 1: PM이 스프린트 계획을 세울 때
   - When: 주 1회 월요일 오전
   - Who: 스타트업 PM
   - Job: "팀이 뭘 해야 하는지 한눈에 보고, 실시간 진행상황을 추적하고 싶다"

상황 2: 학생이 학기 중 과제를 정리할 때
   - When: 매 주말
   - Who: 대학 2학년 학생
   - Job: "너무 많은 과제들을 정리해서 빠뜨리지 않고 싶다"

상황 3: 팀이 회의 결론을 공유할 때
   - When: 회의 후 30분 이내
   - Who: 회의 주최자
   - Job: "회의 결론을 모두가 볼 수 있게 정리하고, 누가 뭘 할 일인지 명확히 하고 싶다"
```

### Layer 2 실행 결과

```
# Notion JTBD 상세 분석

## Job 1: 팀 협업 시각화
**Frequency**: 높음 (인터뷰 5명 중 4명)

### 상황 (Context)
- **When**: 스프린트 계획 미팅, 주 1회 월요일 오전
- **Who**: 스타트업/스케일업 PM, 기술리더
- **Struggling with**:
  * 팀이 뭘 하고 있는지 불명확
  * 우선순위 변경 시 모두에게 알리기 어려움
  * 진행 상황을 실시간으로 추적 불가

### Job의 본질 (기능 vs Job)
❌ **기능**: "데이터베이스를 만든다"
✓ **Job**: "팀 전체가 같은 정보를 보고, 누가 뭘 하는지 투명하게 만들고 싶다"

### 감정 (Emotional Job)
- "혼란이 없어야 한다" (안심)
- "리더로서 팀을 통제하고 있다고 느껴야 한다" (자신감)

### 사회적 (Social Job)
- "팀에서 내가 정보를 관리하는 사람으로 신뢰받고 싶다"
- "우리 팀이 '체계적인' 팀처럼 보이고 싶다" (외부와 비교)

### 성공 지표
- 회의 시간 20% 감소
- "누가 뭘 하는지" 질문이 사라짐
- 팀원들이 자발적으로 상태 업데이트 (강요하지 않아도)

---

## Job 2: 개인 정보 정리 & 추적
**Frequency**: 매우 높음 (모든 세그먼트)

### 상황
- **When**: 업무 중 수시, 퇴근 후 정리
- **Who**: 모든 직급/직군 (PM, 디자이너, 엔지니어, 마케터)
- **Struggling with**:
  * 정보가 흩어져 있음 (메일, Slack, 메모장, 노트북)
  * 중요한 것을 빠뜨림 (To-do 목록과 실제 기억이 안 맞음)
  * "어디에 뭘 저장했더라?" 시간 낭비

### Job의 본질
❌ **기능**: "노트를 만든다"
✓ **Job**: "모든 내 정보를 한곳에 모으고, 필요할 때 2초 내 찾고 싶다"

### 감정
- "내가 통제하고 있다"는 느낌
- "정신 건강" (불안감 해소)
- "전문가처럼 조직적"

### 사회적
- "내 작업 결과물을 자랑할 수 있다" (Notion 페이지 공유)

### 성공 지표
- 하루 사용 시간: 30분 이상 (높은 engagement)
- 개인 workspace 내 페이지 수: 50개 이상

---

## Job 3: 문제 해결을 위한 협업
**Frequency**: 중간

### 상황
- **When**: 복잡한 문제를 팀과 해결할 때
- **Who**: 제품 리더, 기술리더, 기획자
- **Struggling with**:
  * 회의에서 나온 아이디어를 어디에 저장할지
  * "우린 이미 이거 논의했는데 또?" 반복
  * 결정 배경을 나중에 모름

### Job
"문제 해결 프로세스 전체를 기록하고, 실패 노트도 보관하고 싶다"

---

## 포기 대안 (대체 수단)
고객이 Notion을 쓰지 않으면?

1. **Google Docs + Sheets 조합** (가장 일반적)
   - 문제: 정보 흩어짐, 느린 성능, 협업 어려움
   - 우리의 이점: "한 곳에서 관리"

2. **Excel + 폴더 시스템** (전통적)
   - 문제: 공유 불가, 느림, 구식
   - 우리의 이점: "모던하고 빠름"

3. **Jira/Asana** (팀 규모가 크면)
   - 문제: 비싸고, 일반 목적이 아님, 학습곡선
   - 우리의 이점: "유연하고 저렴"

4. **손으로 적기 / 메모장** (개인용)
   - 문제: 잃어버림, 검색 불가, 백업 없음
   - 우리의 이점: "클라우드에서 안전"

→ **결론**: 우리의 진짜 경쟁자는 "Asana/Monday.com" X, "Google Docs" O
```

---

## 🔍 이 결과를 받은 후

> 결과를 그대로 쓰기 전에, 전문가라면 던질 세 가지 질문입니다.

1. **[전문가의 눈]** JTBD 문장에서 '기능적 Job'만 나왔다면 '감정적 Job'과 '사회적 Job'을 추가로 탐색하세요
2. **[논쟁 지점]** JTBD의 '진짜 Job'을 어디까지 추상화할지는 전문가마다 다릅니다 — 너무 추상적이면 실행 불가능
3. **[자기 검증]** 도출된 JTBD 중 1개를 실제 사용자 인터뷰 또는 지원 티켓에서 확인하세요

---

## 🔗 다음 단계

| 결과물 | 연결 프롬프트 | 설명 |
|--------|-------------|------|
| 주요 Jobs 리스트 | → `feature-prioritization.md` (decide/) | 어떤 job을 우선 해결할지 우선순위 결정 |
| 포기 대안 분석 | → `competitor-sentiment.md` | 경쟁사가 같은 job을 어떻게 해결하나? |
| Job의 성공 지표 | → `ai-adoption-metrics.md` (measure/) | job 만족도를 어떻게 측정할지 |
| 감정/사회적 job | → `storytelling.md` (communicate/) | 마케팅/커뮤니케이션 메시지에 반영 |

---

## 📝 참고자료

- **"Competing Against Luck"** by Clayton Christensen (JTBD 창시자 저서)
- **Jobs to be Done 공식 사이트**: https://jtbd.info/
- **"When Coffee and Kale Compete"** (JTBD 실전 사례)
- **고객 인터뷰 가이드**: https://www.intercom.com/blog/jobs-to-be-done-examples/
