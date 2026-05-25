---
id: default-explore-step6
source: env
schemaVersion: 1
targets:
  - app: customize
  - app: assistant
    key: explore.step6
folderId: f-scholar-explore
title: "SPEC: 주석처리 규칙"
tags: [scholar explore, citation]
order: 7
isFavorite: false
ts: "2026-03-22T00:00:09.000Z"
---

[Strict Citation Rule: Source to Footnote]
1. 매핑 규칙: 원문의 'Source N'을 발견하면 등장 순서대로 [^1], [^2]... 로 치환하여 본문에 표기할 것.
2. 주석 생성: 답변 최하단에 [^n]: [Source N] "원문 텍스트" 형식의 리스트를 반드시 포함할 것.
3. 학술적 태깅: 'Source: Source N' 텍스트는 삭제하고, 해당 개념 바로 뒤에 [^n]를 붙여 출처를 명확히 할 것.
