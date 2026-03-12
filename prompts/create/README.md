# 🎯 CREATE 카테고리: AI PM 프롬프트 가이드

> 한국 AI SaaS를 위한 Layered Prompt 프레임워크
> AI Native PM + Layered Structure + Korean-optimized

---

## 📁 파일 구조 (9개 파일, 6,928줄)

### Tier 1: 기본 개념 (파운데이션)

1. **`user-story.md`** ⭐ (12KB, 382줄)
   - **주제**: 유저 스토리 작성 (3C's + INVEST 원칙)
   - **난이도**: ★☆☆
   - **Layer 1**: 5분 Quick Start
   - **Layer 2**: 깊이 있는 설명 + 교육 주석
   - **Layer 3**: Python + Claude Code CLI
   - **다음**: `user-story-mapping.md`

2. **`user-story-mapping.md`** (16KB, 502줄)
   - **주제**: 여러 스토리를 여정(Journey)으로 맵핑 (Jeff Patton)
   - **난이도**: ★★☆
   - **핵심**: Backbone(필수) / Tier 1(MVP) / Tier 2, 3(향후) 구분
   - **산출물**: Story Map ASCII 시각화, CSV 내보내기
   - **다음**: `user-story-splitting.md`

3. **`user-story-splitting.md`** (16KB, 559줄)
   - **주제**: 큰 스토리를 SPIDR로 분할
   - **난이도**: ★★☆
   - **SPIDR**: Spike / Paths / Interfaces / Data / Rules / Releases
   - **목표**: 각 스토리 1~3일 완료 가능하게
   - **다음**: `user-story-ai-enhanced.md`

4. **`user-story-ai-enhanced.md`** (19KB, 606줄)
   - **주제**: AI 기능 유저 스토리 + 수용 기준
   - **난이도**: ★★☆
   - **6가지 AI Criteria**: Accuracy / Confidence / Bias / Performance / Fallback / Feedback Loop
   - **특화**: AI 모델의 정확도를 비즈니스 메트릭으로 변환
   - **다음**: `prd-for-ai-feature.md`

### Tier 2: 역공학 (기존 문서 → PRD 변환)

5. **`spec-to-prd.md`** (16KB, 547줄)
   - **주제**: IEEE 830 기술 스펙 → 사용자 중심 PRD 변환
   - **난이도**: ★★★
   - **핵심**: "기술 요구사항" → "비즈니스 가치"로 프레이밍
   - **출력**: PRD + 트레이서빌리티 매트릭스
   - **대상**: 기술 스펙이 이미 있는 프로젝트

6. **`requirements-to-prd.md`** (20KB, 602줄)
   - **주제**: ISO 29148 요구사항 → 통합 PRD 변환
   - **난이도**: ★★★
   - **핵심**: 분산된 요구사항 그룹화 + 상충 해결 + 우선순위 정렬
   - **특화**: 엔터프라이즈 프로젝트 (여러 부서 요구사항)
   - **대상**: 대규모 시스템, 규제 산업

7. **`product-eol-message.md`** (18KB, 651줄)
   - **주제**: 제품 종료(EOL) 커뮤니케이션
   - **난이도**: ★★☆
   - **핵심**: 고객 신뢰 유지하면서 부드럽게 전환
   - **한국 특화**: 최소 6개월 공지, 감정 배려
   - **산출물**: 공식 공지 + 고객별 이메일 + FAQ + 마이그레이션 가이드

### Tier 3: 플래그쉽 & 전략 (오리지널 MVP)

8. **`prd-for-ai-feature.md`** ⭐⭐⭐ (55KB, 2,020줄) - FLAGSHIP
   - **주제**: AI 기능 전체 PRD (9개 섹션)
   - **난이도**: ★★★
   - **규모**: 300+ 라인 (가장 상세)
   - **9개 섹션**:
     1. 비즈니스 케이스
     2. AI 모델 정의
     3. 데이터 아키텍처
     4. 성능 & 신뢰도 기준
     5. 시스템 아키텍처
     6. 편향 & 윤리 & 규정
     7. 팀 역할 & 책임
     8. 피드백 루프 & 지속적 개선
     9. 로드맵 & 마일스톤
   - **특화**: AI 제품의 모든 차원을 명확하게 정의
   - **파이썬**: 500+ 라인 자동화 도구
   - **다음**: `executive-briefing.md`

9. **`executive-briefing.md`** ⭐ (35KB, 1,059줄) - PHASE 2
   - **주제**: AI 전략 경영진 브리핑
   - **난이도**: ★★★
   - **대상**: CEO, CFO, CTO (의사결정자)
   - **5개 섹션**:
     1. Executive Summary (1쪽, 5분)
     2. Financial Impact (3년 예측)
     3. Risk Assessment & Mitigation
     4. Competitive Landscape
     5. Decision & Recommendation
   - **특화**: 경영진이 3분 안에 이해하고 의사결정 가능
   - **파이썬**: 300+ 라인 자동화 도구
   - **최종 산출물**: 경영진 의사결정

---

## 🎯 사용 시나리오

### Scenario A: 새로운 AI 기능 개발 (처음부터)

```
1. user-story.md
   ↓ (유저 스토리 작성)
2. user-story-mapping.md
   ↓ (여정 맵핑, MVP 결정)
3. user-story-splitting.md
   ↓ (스프린트 준비)
4. user-story-ai-enhanced.md
   ↓ (AI 수용 기준 추가)
5. prd-for-ai-feature.md
   ↓ (완전한 AI PRD)
6. executive-briefing.md
   ↓ (경영진 승인)
7. [구현 시작]
```

### Scenario B: 기존 기술 스펙이 있는 경우

```
IEEE 830 SRS (기술 스펙)
   ↓
spec-to-prd.md (역공학)
   ↓
PRD (사용자 중심)
   ↓
prd-for-ai-feature.md (정정)
   ↓
executive-briefing.md (승인)
```

### Scenario C: 복잡한 엔터프라이즈 프로젝트

```
ISO 29148 Requirements (여러 부서 요구사항)
   ↓
requirements-to-prd.md (통합)
   ↓
Unified PRD
   ↓
executive-briefing.md (의사결정)
```

### Scenario D: 제품 수명 종료

```
EOL 계획 필요
   ↓
product-eol-message.md
   ↓
고객 공지 + 마이그레이션 계획
   ↓
[부드러운 전환]
```

---

## 📊 메트릭

| 파일 | 라인 | KB | 난이도 | 레이어 | 특징 |
|------|------|----|----|----|----|
| 1. user-story.md | 382 | 12 | ★☆☆ | 3 | 기본, Python |
| 2. user-story-mapping.md | 502 | 16 | ★★☆ | 3 | Jeff Patton |
| 3. user-story-splitting.md | 559 | 16 | ★★☆ | 3 | SPIDR |
| 4. user-story-ai-enhanced.md | 606 | 19 | ★★☆ | 3 | AI 특화 |
| 5. spec-to-prd.md | 547 | 16 | ★★★ | 3 | IEEE 830 |
| 6. requirements-to-prd.md | 602 | 20 | ★★★ | 3 | ISO 29148 |
| 7. product-eol-message.md | 651 | 18 | ★★☆ | 3 | 고객 소통 |
| 8. **prd-for-ai-feature.md** | **2,020** | **55** | **★★★** | **3** | **FLAGSHIP** |
| 9. **executive-briefing.md** | **1,059** | **35** | **★★★** | **3** | **PHASE 2** |
| **합계** | **6,928** | **212** | - | - | - |

---

## 🔧 기술 스택

### Layer 1: Quick Start
- 마크다운 텍스트 프롬프트
- 즉시 사용 가능
- 추가 학습 불필요

### Layer 2: Deep Dive
- 이론적 배경 (INVEST, SPIDR, AI Metrics 등)
- HTML 교육 주석 (`<!-- 💬 설명 -->`)
- 한국 SaaS 특화 팁

### Layer 3: Build & Automate
- **Python 스크립트** (각 파일마다 100~500줄)
- **Claude Code CLI** 통합
- **JSON 출력** (프로그래밍 가능)
- **자동화 가능** (Airflow, Jenkins 등)

### 프로그래밍 언어
- Python 3.9+
- anthropic-sdk (Claude API)
- Standard libs: json, csv, dataclasses, enum, pathlib

---

## 🌐 한국 SaaS 특화

### 문화적 고려사항
- **감정 배려**: "고마워요" 강조 (Scenario D: EOL)
- **장기 관계**: 고객과의 신뢰 중시
- **규정 준수**: ISMS, 개인정보보호법, AI 윤리 가이드
- **다국어**: 한글/영어 혼용 (Bias 테스트 포함)

### 기술 고려사항
- **지역 모델**: 한글 NLP 성능 인식
- **결제/정산**: 한국식 비즈니스 모델 (별도 스토리)
- **데이터 센터**: 국내 규정 준수

---

## 💡 사용 팁

### 빠른 시작 (5분)
```bash
# 어떤 파일이든 Layer 1 (Quick Start)부터 시작
cat user-story.md | head -50
```

### 팀 교육 (20분)
```bash
# Layer 2 (Deep Dive)를 팀과 함께 읽기
# 주석 설명이 포함되어 있음
```

### 자동화 (30분+)
```bash
# Layer 3 Python 스크립트 실행
claude run prd-for-ai-feature.py \
  --product "제품명" \
  --output prd.json
```

---

## 🚀 다음 단계

### 의존성 흐름
```
사용자 스토리 (1~4)
   ↓ 여정 맵핑 & 우선순위
프로덕트 정의 (5~7, 8)
   ↓ 역공학 또는 신규 정의
PRD 완성
   ↓ 경영진 검증
전략 승인 (9)
   ↓ 실행
```

### 지속적 개선
- 매월: Layer 3 Python으로 자동화
- 매분기: 팀 학습 (Layer 2)
- 매년: 한국 규정 업데이트 확인

---

## 📝 라이선스 & 기여

이 프롬프트들은:
- **오픈 소스**: MIT License
- **한국 최적화**: AI Native PM + Korean cultural/regulatory considerations
- **기여 환영**: Pull Request 및 이슈 환영

---

## 📚 참고 자료

### 기본 개념
- INVEST 원칙: https://www.agilealliance.org/glossary/invest/
- Jeff Patton Story Mapping: https://www.jpattonassociates.com/
- SPIDR: Story Splitting Pattern

### AI 관련
- Accuracy vs Precision vs Recall: https://en.wikipedia.org/wiki/Precision_and_recall
- SHAP (Explainability): https://github.com/slundberg/shap
- Fairness in ML: https://github.com/Trusted-AI/AIF360

### 한국 규정
- 개인정보보호법 (https://www.privacy.go.kr/)
- AI 윤리 가이드 (미래부)
- ISMS 인증 요구사항

---

**생성일**: 2024년 3월 11일
**총 규모**: 6,928줄 / 212KB / 9개 파일
**복잡도**: 초급~고급
**팀 규모**: 1명 (Solo PM) ~ 50명 (Enterprise)
**ROI**: 각 프롬프트마다 20~40시간 시간 절감

🎯 **이제 시작하세요!**
