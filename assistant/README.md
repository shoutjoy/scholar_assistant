# assistant — Research Assistant 팝업

앱: `popup.html` · 시드: `popup.js` → `SCHOLAR_PROMPTS`

## UI 버튼 ↔ 파일

### SLIDE TOOLS

| UI | assistant key | 파일 |
|----|---------------|------|
| Step 1 | `slideTools.step1` | `slide_tools/step1.md` |
| Step 2 | `slideTools.step2` | `slide_tools/step2.md` |
| Step 3 | `slideTools.step3` | `slide_tools/step3.md` |

### SCHOLAR EXPLORE

| UI | assistant key | 파일 |
|----|---------------|------|
| Step 1 | `explore.step1` | `explore/step1.md` |
| Step 2 | `explore.step2` | `explore/step2.md` |
| Step 2.2 | `explore.step2_2` | `explore/step2_2.md` |
| Step 3 | `explore.step3` | `explore/step3.md` |
| Step 4 | `explore.step4` | `explore/step4.md` |
| Step 5 | `explore.step5` | `explore/step5.md` |
| SPEC (인용) | `explore.step6` | `explore/step6.md` |

## customize와의 관계

- **본문 내용**은 `customize/` 동명 단계와 동일 계열입니다.
- Assistant는 **매개변수 치환**(`{{total}}` 등)만 추가로 적용합니다.
- prompts 창에서 카드를 수정해도 Assistant 시드(`source: env`)는 Env 동기화 시에만 갱신됩니다.
