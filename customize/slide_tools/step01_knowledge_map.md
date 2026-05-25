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
ts: "2026-03-22T00:00:00.000Z"
---

[프롬프트: 고해상도 구조 스캔]
* 목표: 업로드된 문서의 모든 섹션, 소제목, 도표, 각주를 누락 없이 스캔하라. 45 page설계 3 part로 구성 

수행 작업:
1. 문서의 논리적 흐름에 따라 전체 내용을 3개의 파트로 나누고, 각 파트당 15개의 슬라이드 주제(총 45개)를 추출하라. 
2. 각 주제는 문서 내의 구체적인 개념, 실험 데이터, 또는 핵심 모델명(예: SEEV, SSTS, PCP 등)을 기반으로 설정하라. 
3. 단순히 목차를 베끼지 말고, 본문의 핵심 키워드를 3개 이상 포함하여 '세밀 목차'를 생성하라.
Strict Citation Rule: Source to Footnote: 1. 매핑 규칙: 원문의 'Source N'을 발견하면 등장 순서대로 [^1], [^2]... 로 치환하여 본문에 표기할 것. 2. 주석 생성: 답변 최하단에 주석형식을 [^1]:내용 (빈줄)[^2]:내용 (빈줄) [^3]:내용...의 형식으로 하여 [^n]: "원문 텍스트" (빈줄) [^n+1]:내용의 형식의 원문리스트를 반드시 포함할 것(각 번호 사이에는 반드시 빈 줄을 삽입할). 3. 학술적 태깅: 'Source: Source N' 텍스트는 스타일은 지양하고, 해당 개념 바로 뒤에 [^n]를 붙여 출처를 명확히 할 것(n=1,2,3...).
