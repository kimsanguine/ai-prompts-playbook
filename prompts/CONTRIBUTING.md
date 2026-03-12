# Contributing to AI Prompts Playbook

기여해 주셔서 감사합니다! 🎉

이 Playbook은 커뮤니티의 기여로 더 좋아집니다. 새 프롬프트 추가, 기존 프롬프트 개선, 번역, 오류 수정 모두 환영합니다.

---

## 기여 방법

### 1. 새 프롬프트 추가

**프롬프트가 들어갈 카테고리를 먼저 정하세요:**

| 카테고리 | 사고 유형 | 예시 |
|----------|----------|------|
| `analyze/` | 데이터를 구조화하고 패턴을 발견 | 경쟁사 분석, 시장 조사 |
| `decide/` | 우선순위와 전략 결정 | RICE 스코어, Build vs Buy |
| `create/` | 문서와 결과물 생성 | PRD, 유저 스토리, 브리핑 |
| `measure/` | 메트릭과 실험 설계 | A/B 테스트, 리텐션 분석 |
| `communicate/` | 설득과 정렬 | 이해관계자 소통, 프레스 릴리즈 |

**레이어드 구조를 지켜주세요:**

모든 프롬프트는 3개 레이어를 포함해야 합니다:

- `⚡ Layer 1: Quick Start` — 누구나 5분에 쓸 수 있는 짧은 프롬프트
- `🧠 Layer 2: Deep Dive` — Reasoning Strategy + `<!-- 💬 -->` 교육 주석
- `🔧 Layer 3: Build & Automate` — Python 코드 또는 CLI 명령어

템플릿: [layered-prompt-template.md](prompts/templates/layered-prompt-template.md)

### 2. 기존 프롬프트 개선

- Layer 2 교육 주석 추가/개선
- Layer 3 코드 예시 추가 (다른 AI API, 다른 언어)
- 실행 결과 예시 추가
- 오타/문법 수정
- 한국 SaaS 컨텍스트 보강

### 3. 영어 번역

`prompts/en/` 폴더에 영어 번역을 기여할 수 있습니다. 파일명은 동일하게 유지해주세요.

---

## Pull Request 프로세스

1. 이 레포를 Fork 하세요
2. 브랜치를 만드세요: `git checkout -b add/my-new-prompt`
3. 프롬프트를 작성하세요 (레이어드 구조 필수)
4. 커밋하세요: `git commit -m "Add: [카테고리] 프롬프트 제목"`
5. PR을 보내세요

### 커밋 메시지 컨벤션

```
Add: [analyze] 새 프롬프트 이름
Fix: [decide] 오타 수정
Improve: [create] Layer 3 코드 예시 추가
Translate: [en] competitor-sentiment 영어 번역
```

---

## 프롬프트 품질 체크리스트

PR 제출 전에 확인해주세요:

- [ ] 🎯 문제 정의가 역할 무관하게 공감 가능한가?
- [ ] ⚡ Layer 1이 10줄 이내이고, 전문용어 없이 즉시 사용 가능한가?
- [ ] 🧠 Layer 2에 Reasoning Strategy와 `<!-- 💬 -->` 교육 주석이 있는가?
- [ ] 🔧 Layer 3에 실행 가능한 코드가 포함되어 있는가?
- [ ] 📊 실행 결과 예시가 있는가?
- [ ] 🔗 다음 단계에서 연결 프롬프트가 명시되어 있는가?
- [ ] 한국어가 자연스러운가? (번역투 아님)

---

## 질문이 있으면

[Issue](../../issues/new)를 열어주세요. 함께 논의합시다.
