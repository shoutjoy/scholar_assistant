# sync_prompt — 앱 공유 기본 프롬프트 (문서)

`prompts/envir/github_prompt_sync_plan.md`에 따라, ScholarNotebook 확장에 **기본으로 제공할 프롬프트**를 이 폴더에 정리합니다.

- **지금 단계**: 문서(MD)만 정리. 앱 자동 동기화 코드는 추후 연결.
- **추가 방법**: 아래 규칙에 맞는 `.md` 파일을 추가하면, 이후 Env/GitHub 동기화 모듈이 읽어 `prompts` 창·`Assistant` 팝업에 반영할 예정.

## 폴더 구조

```
sync_prompt/
  README.md              ← 이 파일
  SCHEMA.md              ← MD frontmatter·향후 JSON 매핑 규칙
  releases/
    latest.md            ← 배포 버전·파일 목록(문서용)
  shared/                ← 두 UI에 공통으로 붙는 보조 문구
    academic_setting.md
    strict_citation.md
  assistant/             ← Research Assistant 팝업 (popup.js · SCHOLAR_PROMPTS)
    slide_tools/
    explore/
  customize/             ← Customize Your Prompts (prompts.js · DEFAULT_PROMPTS)
    folders.md
    slide_tools/
    scholar_explore/
```

## 앱 대상 매핑

| sync_prompt 경로 | 앱 UI | 코드 상수·키 |
|------------------|--------|----------------|
| `customize/**` | **prompts** (프롬프트 관리 창) | `DEFAULT_FOLDERS`, `DEFAULT_PROMPTS`, `prompt-seed.js` |
| `assistant/**` | **Assistant** (Research Assistant 팝업) | `SCHOLAR_PROMPTS.slideTools`, `SCHOLAR_PROMPTS.explore` |
| `shared/**` | Assistant 입력 시 하단 보조(옵션) | `ACADEMIC_SETTING_PROMPT`, `STRICT_CITATION_PROMPT` |

## 프롬프트 목록 (기본 시드)

### SLIDE TOOLS (3단계)

| ID | customize | assistant |
|----|-----------|-----------|
| Step 1 | `customize/slide_tools/step01_knowledge_map.md` | `assistant/slide_tools/step1.md` |
| Step 2 | `customize/slide_tools/step02_recursive_extract.md` | `assistant/slide_tools/step2.md` |
| Step 3 | `customize/slide_tools/step03_design_consistency.md` | `assistant/slide_tools/step3.md` |

### SCHOLAR EXPLORE (6단계)

| ID | customize | assistant |
|----|-----------|-----------|
| Step 1 | `customize/scholar_explore/step01_knowledge_map.md` | `assistant/explore/step1.md` |
| Step 2 | `customize/scholar_explore/step02_concept_mastery.md` | `assistant/explore/step2.md` |
| Step 2.2 | `customize/scholar_explore/step02_2_detail_order.md` | `assistant/explore/step2_2.md` |
| Step 3 | `customize/scholar_explore/step03_real_world.md` | `assistant/explore/step3.md` |
| Step 4 | `customize/scholar_explore/step04_data_visual.md` | `assistant/explore/step4.md` |
| Step 5 | `customize/scholar_explore/step05_self_check.md` | `assistant/explore/step5.md` |
| Step 6 (SPEC) | `customize/scholar_explore/step06_citation_spec.md` | `assistant/explore/step6.md` |

### 폴더 정의

| 파일 | 설명 |
|------|------|
| `customize/folders.md` | 프롬프트 창 기본 폴더 3개 + 시스템 폴더 `all` |

## GitHub Env 저장소 대응 (Phase A)

추후 `notebooklmAppEnv` 저장소에 올릴 때 아래처럼 변환합니다.

| sync_prompt (MD) | Env Repo (JSON) |
|------------------|-----------------|
| `customize/folders.md` | `customize/folders.json` |
| `customize/**/*.md` (카드) | `customize/default_prompts.json` |
| `assistant/slide_tools/*.md` | `assistant/slide_tools.json` |
| `assistant/explore/*.md` | `assistant/explore.json` |
| `shared/*.md` | `assistant/footers.json` |
| `releases/latest.md` | `releases/latest.json` |

## 메타 필드 `source: env`

원격·시드 프롬프트는 사용자 수정본과 구분하기 위해 `source: env`를 frontmatter에 둡니다.  
병합 시 **사용자가 수정한 동일 id는 유지**, `source: env`만 GitHub/로컬 시드에서 갱신합니다. (`github_prompt_sync_plan.md` §3)

## 관련 문서

- [github_prompt_sync_plan.md](../envir/github_prompt_sync_plan.md)
- [SCHEMA.md](./SCHEMA.md)
- [releases/latest.md](./releases/latest.md)
