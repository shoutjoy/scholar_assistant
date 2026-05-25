---
id: customize-folders-bundle
source: env
schemaVersion: 1
targets:
  - app: customize
    key: DEFAULT_FOLDERS
schema: folders-bundle
version: 1
---

# 기본 폴더 (Customize Your Prompts)

| id | name | color | 비고 |
|----|------|-------|------|
| `all` | All Prompts | blue | 시스템 폴더. 삭제 불가 |
| `f-slide-tools` | SLIDE TOOLS | blue | 슬라이드 3단계 프롬프트 |
| `f-scholar-explore` | SCHOLAR EXPLORE | purple | 학술 탐구 6단계 프롬프트 |

```json
{
  "version": 1,
  "folders": [
    { "id": "all", "name": "All Prompts", "color": "blue" },
    { "id": "f-slide-tools", "name": "SLIDE TOOLS", "color": "blue" },
    { "id": "f-scholar-explore", "name": "SCHOLAR EXPLORE", "color": "purple" }
  ]
}
```
