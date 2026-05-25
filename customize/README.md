# customize — Customize Your Prompts (프롬프트 관리 창)

앱: `prompts/prompts.html` · 시드: `prompt-seed.js` → `DEFAULT_FOLDERS`, `DEFAULT_PROMPTS`

## 폴더

| 폴더 id | 표시명 | 색상 | 프롬프트 경로 |
|---------|--------|------|----------------|
| `all` | All Prompts | blue | (시스템 — 모든 카드) |
| `f-slide-tools` | SLIDE TOOLS | blue | `slide_tools/` |
| `f-scholar-explore` | SCHOLAR EXPLORE | purple | `scholar_explore/` |

폴더 정의: [folders.md](./folders.md)

## 카드 추가 시

- 파일명: `stepNN_영문_슬러그.md` 권장
- frontmatter `folderId`를 위 표와 일치시킬 것
- `source: env` 유지
