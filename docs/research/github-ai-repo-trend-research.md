# GitHub AI 레포 트렌드 리서치

> 조사일: 2026-03-11
> 목적: ai-pm-prompts 레포 방향성 결정을 위한 시장 트렌드 분석

---

## 1. agency-agents 분석 — 왜 27K Stars인가?

**레포:** [msitarzewski/agency-agents](https://github.com/msitarzewski/agency-agents)

핵심 특성:
- **27.1K Stars, 4.3K Forks, 28 Contributors** — 5개월 만에 달성
- **언어가 Shell 100%** — 실행 코드가 아니라 **Agent 프로필/프롬프트 컬렉션**
- Reddit에서 시작, 커뮤니티 기여로 성장
- 각 Agent가 Personality + Workflow + Deliverables 구조
- Quick Start가 Claude Code에 바로 복사하는 방식

**핵심 인사이트:** 이 레포는 코드를 짜는 게 아니라 **"AI Agent를 어떻게 정의하고 활용하는지"의 컬렉션**이다. 그런데 27K를 찍었다.

---

## 2. 같은 카테고리 경쟁 레포 비교

| 레포 | Stars | 성격 | 코드 여부 |
|------|-------|------|----------|
| [agency-agents](https://github.com/msitarzewski/agency-agents) | 27.1K | Agent 페르소나 컬렉션 | ❌ Shell/MD |
| [500-AI-Agents-Projects](https://github.com/ashishpatel26/500-AI-Agents-Projects) | 26K | Agent 유스케이스 카탈로그 | ❌ MD only |
| [awesome-agents](https://github.com/kyrolabs/awesome-agents) | - | Awesome List (링크 모음) | ❌ MD only |
| [awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) | 151K | 프롬프트 컬렉션 | ❌ MD only |
| [product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) | 709 | PM 전용 프롬프트 | ❌ MD only |

---

## 3. 패턴 분석

**가장 Stars가 높은 레포들은 실행 코드가 아니다.** "유용한 리소스의 큐레이션"이 GitHub에서 가장 빠르게 Star를 모은다. awesome-chatgpt-prompts가 151K인 이유가 바로 이것이고, agency-agents가 27K인 이유도 같다.

---

## 4. 전체 시장 트렌드 (2025-2026)

### GitHub AI 생태계 규모
- GitHub Octoverse 2025: **4.3 million AI-related repositories** (LLM-focused 178% YoY 성장)
- AI Agent 카테고리가 가장 빠르게 성장하는 영역

### 주요 고성장 레포
| 레포 | Stars | 특징 |
|------|-------|------|
| AutoGPT | 177K | AI Agent 자동화 |
| n8n | 150K+ | 워크플로우 자동화 |
| Ollama | 148K | 로컬 LLM |
| LangChain | 113K | LLM 앱 프레임워크 |
| OpenCode | 44.7K | 코딩 에이전트 |

### 트렌드 키워드
1. **Agentic AI** — 자율적으로 작업하는 AI Agent
2. **AI Workflow Automation** — Langflow, Dify, n8n 등 시각적 파이프라인
3. **Curated Collections** — Awesome List, Agent 카탈로그
4. **Claude Code / Copilot 생태계** — Agent Skills, Plugins

---

## 5. 임팩트 재평가: 데이터가 말하는 우선순위

| 순위 | 항목 | 예상 반응 | 근거 |
|------|------|----------|------|
| 🥇 | **100 Agents (2-6)** | 🔴 최고 | agency-agents(27K)와 500-AI-Agents(26K)가 증명. "AI Agent 컬렉션" 카테고리 자체가 뜨고 있음. 실행 코드가 있는 Agent라서 차별화 가능 |
| 🥈 | **ai-pm-prompts (2-5)** | 🟠 높음 | awesome-chatgpt-prompts(151K) 시장이 존재. PM 특화 niche는 deanpeters(709 Stars)가 선점했지만 **한국어 + AI Native PM 관점**이면 블루오션 |
| 🥉 | **product-teardowns (2-4)** | 🟡 중간 | GitHub에서 teardown 레포로 뜬 사례가 적음. 콘텐츠 품질은 높겠지만 검색/발견 경로가 약함 — 블로그나 LinkedIn이 더 적합한 채널 |
| 4 | Proof of Work (2-17) | 🟡 중간 | Star를 모으는 게 아니라 프로필 신뢰도 보강. 필요하긴 하지만 급하진 않음 |
| 5 | README 표준화 (2-10) | ⚪ 낮음 | Polish. 현재도 충분 |
| 6 | copilot-instructions (2-15) | ⚪ 낮음 | 방문자 임팩트 거의 0 |

**결론:** 100 Agents(2-6)가 타이밍상 가장 맞음. ai-pm-prompts(2-5)가 그 다음.

---

## 6. 채택된 전략: 3각 구도

> Ethan님 결정 (2026-03-11)

1. **ai-pm-prompts 먼저** → 한국어 + AI Native PM 블루오션
2. **기존 AI_PM_Skills 업데이트** → 기존 레포 시너지
3. **100 Agents 컬렉션** → Agent 트렌드 파도 타기

---

## Sources

- [Top AI GitHub Repositories in 2026 - ByteByteGo](https://blog.bytebytego.com/p/top-ai-github-repositories-in-2026)
- [Top Ten GitHub Agentic AI Repositories in 2025 - ODSC](https://opendatascience.com/the-top-ten-github-agentic-ai-repositories-in-2025/)
- [GitHub Trending Weekly 2026-02-18](https://www.shareuhack.com/en/posts/github-trending-weekly-2026-02-18)
- [GitHub's AI-Challenged Open Source Ecosystem 2026 - InfoQ](https://www.infoq.com/news/2026/03/github-ai-2026/)
- [Top 10 Open-Source AI Projects Trending on GitHub 2026](https://www.buildmvpfast.com/blog/best-open-source-ai-projects-github-2026)
- [agency-agents](https://github.com/msitarzewski/agency-agents) — 27.1K Stars
- [500-AI-Agents-Projects](https://github.com/ashishpatel26/500-AI-Agents-Projects) — 26K Stars
- [awesome-chatgpt-prompts](https://github.com/f/awesome-chatgpt-prompts) — 151K Stars
- [product-manager-prompts](https://github.com/deanpeters/product-manager-prompts) — 709 Stars
- [awesome-agents](https://github.com/kyrolabs/awesome-agents)
- [awesome-ai-agents](https://github.com/slavakurilyak/awesome-ai-agents)
