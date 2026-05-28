# Prompt Registry

이 폴더는 AI Prompts Playbook을 사람이 읽는 문서에서 검색, 추천, 평가 가능한 데이터 자산으로 바꾸기 위한 구조화 인덱스입니다.

## 파일

- `prompts.yaml`: 30개 업무 프롬프트의 기본 메타데이터

## 필드 기준

| 필드 | 설명 |
|------|------|
| `id` | 자동화와 검색에서 쓰는 안정적인 식별자 |
| `title` | 사용자에게 보여줄 제목 |
| `category` | `analyze`, `decide`, `create`, `measure`, `communicate` 중 하나 |
| `path` | 원본 Markdown 파일 |
| `audience` | 주 사용 대상 |
| `input_types` | 필요한 입력 데이터 유형 |
| `output_types` | 기대 산출물 유형 |
| `tags` | 검색과 추천에 쓰는 키워드 |
| `starter` | 초급자 첫 실행 후보 여부 |
| `next` | 자연스럽게 연결되는 다음 프롬프트 ID |

## 활용 예

- 웹 UI에서 사용자의 상황에 맞는 프롬프트 추천
- RAG 인덱싱 전 문서 단위와 태그 정규화
- 프롬프트별 샘플 입력, 기대 출력, 평가 루브릭 연결
- 버전 변경 시 어떤 프롬프트가 영향을 받는지 추적
