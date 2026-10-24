# 서면 심사용 발표 자료 (12페이지 PDF) 구성 및 안내

> **문서 기준일**: 2026-10-24 (KST) · **최종 발표 PDF**: **[`docs/presentation.pdf`](../presentation.pdf)** ([동일 사본 `docs/final/presentation.pdf`](presentation.pdf)) · **관련 문서**: [최종 제출 목차](README.md)

발표 없이 서면으로만 읽어도 **문제 정의 → 해결 방식 → 데이터 검수 품질 → 시스템 아키텍처 → AI Agent · RAG 설계 → 결정적 추천 정책 → 실제 구현 화면 → 검증 결과 → 실사용자 5명 피드백 개선 → 5인 팀원 기여 증빙 → 한계 및 결론**의 전 과정을 이해할 수 있도록 16:9 와이드스크린 12페이지 PDF로 제작 완료했습니다. (시연 영상은 생략)

---

## 슬라이드 페이지별 구성 (총 12페이지)

| 슬라이드 | 제목 및 핵심 내용 | 반영된 근거 문서 및 시각 자료 |
|---|---|---|
| **Slide 01** | **표지**: 영양제 첫걸음 (VitaStep Guide) · 한 줄 가치 · 운영 URL/GitHub · 핵심 지표 · 5인 팀원 소개 | [프로젝트 기획서](../project-plan.md), [운영 사이트](https://vitastep-guide.onrender.com/) |
| **Slide 02** | **문제 정의 및 타깃 사용자**: 입문 성인이 겪는 3가지 장벽(탐색·표시 해독·비교/중복)과 비의료 안전 경계 | [기획서 1~3절](../project-plan.md), 기획 가설 명시 (미검증 외부 통계 미사용) |
| **Slide 03** | **해결 방식 및 사용자 경험 흐름**: `동의 → 5단계 설문 → 맞춤 후보(최대 3개) → 상세·비교·AI 대화` 여정 | [기능 요구 명세서](../functional-requirements.md), 예외 상태(`M09`) 분리 |
| **Slide 04** | **데이터 확보 및 검수 품질 관리**: 수집 88개 · 공개 87개 · 보류 1개(`600651654` 정량 미기재 보류 사유) · 14,587 검사 | [DB 설계 기록](../product-database.md), [라벨 검수 보고서](../product-label-review.md) |
| **Slide 05** | **시스템 아키텍처 및 기술 스택**: React · FastAPI · 읽기 전용 SQLite · COPA `gpt-5.4` 구성 및 개인정보 경계 | [시스템 아키텍처](architecture.md), [보안·운영](security-and-operations.md) |
| **Slide 06** | **핵심 AI 기술 ①·② (AI Agent & RAG)**: 7개 도구 자율 호출 루프, 3원화 동적 RAG 검색 및 `sanitize_answer` 출처 검증 | [AI 활용 설계](ai-design.md), `M03`·`M04` `toolTrace` 실행 기록 |
| **Slide 07** | **결정적 후보 추천 정책과 정량 중복 계산**: 4단계 추천 게이트, 5대 분야 분류(28개 제품·40개 연결), 일일 중복 합계(`630 mg`) | [추천 정책 상세](../recommendation-policy-v2.md), [`policy.py`](../../backend/policy.py) |
| **Slide 08** | **실제 운영 화면 및 AI 두 제품 비교 해설**: 5대 관심 분야 설문 화면 및 출처 기반 AI 비교 차이 해설(`Should S01`)·캐시 | [5분야 설문 화면](evidence/survey-five-goals.jpg), [AI 비교 화면](evidence/production-comparison.jpg) |
| **Slide 09** | **구현 검증 결과 및 실패 기록 공개**: 로컬 174개 테스트 통과, 운영 API Must 3회 반복 검증(`M04` 2/3, 나머지 3/3) | [검증 결과](test-results.md), [`acceptance-api.json`](evidence/acceptance-api.json) |
| **Slide 10** | **실사용자 5명 테스트 및 5대 피드백 개선**: 타깃 성인 5명(`T1`~`T5`) 응답 원본 및 `F01`~`F05` 개선 전후 비교·미반영 사유 | [사용자 피드백](user-feedback.md), [5인 응답 원본 기록](evidence/user-test-records.md) |
| **Slide 11** | **팀원 5인 역할 분담 및 실질적 기여 증빙**: [팀 협업 및 통합 배포 관리 방식], 5인 본인 기여 요약 및 담당 산출물·PR 매핑 | [팀원 역할과 기여](team-contributions.md) |
| **Slide 12** | **현재 한계, 향후 보완 방향 및 최종 제출 요약**: 정적 데이터 시점·단일 인스턴스·외부 AI 한계 명시 및 `G1`~`G7` 달성 요약 | [최종 제출 목차](README.md), [`docs/presentation.pdf`](../presentation.pdf) |

---

## 렌더링 및 품질 검수 완료 항목

* **한글 글꼴 및 레이아웃**: `Malgun Gothic` 기반 16:9 와이드스크린(`338.67mm × 190.5mm`) 레이아웃으로 제작하여 12페이지 전 슬라이드의 글꼴 깨짐·표 잘림·오버플로우 없음을 시각 검수 완료했습니다.
* **파일 배치 경로**: 과제 안내서 예시 경로인 **[`docs/presentation.pdf`](../presentation.pdf)**와 최종 제출 폴더 내 **[`docs/final/presentation.pdf`](presentation.pdf)** 두 경로 모두에 동일한 최신 PDF 파일을 배치했습니다.
