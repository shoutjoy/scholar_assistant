# releases/latest (문서용)

향후 `notebooklmAppEnv/releases/latest.json`과 동일한 정보를 MD로 기록합니다.

```yaml
schemaVersion: 1
envVersion: "2026.05.25-01"
releasedAt: "2026-05-25T00:00:00.000Z"
repo: shoutjoy/notebooklmAppEnv
```

## 포함 파일

| 키 | sync_prompt 경로 | 용도 |
|----|------------------|------|
| customizeFolders | `customize/folders.md` | 프롬프트 창 폴더 |
| customizePrompts | `customize/slide_tools/*.md`, `customize/scholar_explore/*.md` | 프롬프트 카드 시드 |
| assistantSlide | `assistant/slide_tools/*.md` | Assistant SLIDE TOOLS |
| assistantExplore | `assistant/explore/*.md` | Assistant SCHOLAR EXPLORE |
| assistantFooters | `shared/academic_setting.md`, `shared/strict_citation.md` | 입력 보조 문구 |

## 변경 이력

- **2026.05.25-01**: 최초 `sync_prompt` 문서 세트 정리 (앱 코드 미연동)
