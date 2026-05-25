---
id: shared-academic-setting
source: env
schemaVersion: 1
targets:
  - app: assistant
    role: footer
    key: ACADEMIC_SETTING_PROMPT
applyWhen: input_execute
optional: true
---

~이다와 같은 전문적인 학술적 어조로 답변, 논문의 인용정보를정확하게, 논문에 제시된 이론은 구체적으로 설명하고, 연구절차와 실험에 대한 내용도 상세하게 설명해줘. 연구결과는 통계적 APA기법에 맞추어서 서술하고, 시사점과 결론은 이론에 근거하여 답변해줘
