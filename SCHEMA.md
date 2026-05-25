# sync_prompt 스키마 (MD → 앱)

## 1. 파일 형식

각 프롬프트는 **YAML frontmatter + Markdown 본문**입니다.

```markdown
---
id: default-slide-step1
source: env
schemaVersion: 1
targets:
  - app: customize
  - app: assistant
    key: slideTools.step1
folderId: f-slide-tools
title: STEP 01 Knowledge Map
tags: [slide tools, step1]
order: 1
isFavorite: false
parameters: []
---

(프롬프트 본문 — NotebookLM에 붙여 넣을 텍스트)
```

## 2. 필수·권장 필드

| 필드 | 필수 | 설명 |
|------|------|------|
| `id` | ✅ | 앱 내 고유 ID (`default-*`). 사용자 생성 id와 충돌 금지 |
| `source` | ✅ | `env` = 배포 시드. 사용자 카드는 `user` |
| `schemaVersion` | ✅ | 현재 `1` |
| `targets` | ✅ | `customize` / `assistant` 중 하나 이상 |
| `folderId` | customize 시 ✅ | `folders.md`의 폴더 id |
| `title` | ✅ | UI 표시 제목 |
| `tags` | 권장 | 검색·필터용 문자열 배열 |
| `order` | 권장 | 폴더·단계 정렬 (1, 2, 3…) |
| `targets[].key` | assistant 시 ✅ | 예: `slideTools.step1`, `explore.step3` |
| `parameters` | assistant 동적 시 | 아래 §3 |

## 3. Assistant 동적 매개변수

`popup.js`의 `SCHOLAR_PROMPTS`는 일부 step이 **함수(매개변수)** 입니다. MD 본문에서는 placeholder를 씁니다.

| key | placeholder | UI 입력 | 기본값 |
|-----|-------------|---------|--------|
| `slideTools.step1` | `{{total}}`, `{{part}}` | 슬라이드 총页, 파트 수 | 45, 3 |
| `slideTools.step2` | `{{from}}`, `{{to}}` | 슬라이드 구간 | 1, 15 |
| `slideTools.step3` | `{{style}}` | 디자인 스타일 | 2DFlat(Default) |

동기화 시: placeholder → 런타임 치환 후 NotebookLM 입력란에 전달.

## 4. customize 카드 → storage

로드 시 frontmatter + 본문을 합쳐 `savedPrompts` 시드 항목으로 변환:

```json
{
  "id": "default-slide-step1",
  "title": "STEP 01 Knowledge Map",
  "folderId": "f-slide-tools",
  "tags": "slide tools, step1",
  "content": "(본문 전체)",
  "source": "env",
  "isFavorite": false,
  "ts": "2026-03-22T00:00:00.000Z"
}
```

## 5. shared 보조 문구

`shared/academic_setting.md`, `shared/strict_citation.md`는 단독 프롬프트 카드가 아니라 **입력 실행 시 하단에 덧붙이는 푸터**입니다.  
`strictCitationRuleApply` 설정이 켜져 있을 때만 인용 규칙을 적용합니다.

## 6. 새 프롬프트 추가 체크리스트

1. `id`를 `default-` 접두로 새로 부여
2. `folderId`가 `customize/folders.md`에 존재하는지 확인
3. customize용 `.md`를 `customize/<폴더>/`에 추가
4. Assistant 버튼과 연결할 경우 `assistant/`에 동일 단계 파일 추가 + `targets[].key` 명시
5. `releases/latest.md` 버전·파일 목록 갱신
6. (선택) `prompt-seed.js` / `popup.js` 시드와 문서 동기화
