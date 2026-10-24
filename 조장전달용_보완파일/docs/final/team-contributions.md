# 팀원 역할과 실제 기여 증빙

> **문서 기준일**: 2026-10-24 (KST) · **운영 배포 기준**: [`0bc17dc`](https://github.com/sayknow/M2-1/commit/0bc17dca34f3ec6479549248798e76bfcb962064) · **관련 문서**: [최종 제출 목차](README.md) · [프로젝트 진행 기록](progress.md)

본 프로젝트는 **이승현 · 조준수 · 김재욱 · 윤준서 · 배창민** 5인이 역할을 분담하여 수행했습니다. **이승현(주 개발)**과 **조준수(부 개발)**가 프런트엔드·백엔드·AI 추천 및 비교 기능 개발을 공동 담당하고, **김재욱(데이터/RAG)**, **윤준서(기획/설계)**, **배창민(테스트/피드백/문서)**이 각 전담 영역의 산출물을 작성·검증했습니다.

> ### [팀 협업 및 통합 배포 관리 방식]  
> **"Render 클라우드 무중단 배포 및 브랜치(`canary → dev → production`) 승격의 안정성을 위해, 저장소의 최종 커밋 및 배포 관리는 주 개발자(이승현) 계정으로 통합·일원화하였습니다.**  
> **각 팀원(김재욱, 윤준서, 배창민, 조준수)은 자신의 전담 파트(라벨 데이터 검수, 기획/명세서 설계, 실사용자 QA, 공동 개발)를 독립적으로 수행한 후, 주 개발자를 통해 저장소에 통합 반영하였습니다."**  
> 각 팀원이 수행한 전담 작업과 산출물 파일, 그리고 해당 작업이 통합된 저장소 커밋/PR 연결 내역은 아래 표와 개인별 기여 요약에 상세히 기록합니다.

---

## 1. 5인 팀원 역할 분담 및 산출물 매핑

| 팀원 | 배정 역할 | 상세 담당 업무 및 협업 내용 | 담당 산출물 위치 (파일 링크) | 통합 반영 커밋 · PR |
|---|---|---|---|---|
| **이승현** | **주 개발 · 통합/운영 관리** | 프런트/백엔드/DB 전체 통합 설계, 추천 정책 및 AI Agent 핵심 루프 구현, COPA 전환, GitHub Actions CI 및 Render 운영 배포 관리, 부 개발자 작업 통합 | [`App.tsx`](../../frontend/src/App.tsx), [`main.py`](../../backend/main.py), [`policy.py`](../../backend/policy.py), [`agent.py`](../../backend/agent.py), [`CONTRIBUTING.md`](../../CONTRIBUTING.md) | [PR #3](https://github.com/sayknow/M2-1/pull/3), [PR #4](https://github.com/sayknow/M2-1/pull/4), [PR #5](https://github.com/sayknow/M2-1/pull/5), [PR #6](https://github.com/sayknow/M2-1/pull/6) |
| **조준수** | **부 개발** | 주 개발자와 프런트/백엔드/AI 추천 공동 개발, 5대 관심 목적 분류 로직·AI 두 제품 비교 해설 모듈·프런트 비교 컴포넌트 구현 보조 및 단위/회귀 테스트 검증 | [`classification.py`](../../backend/classification.py), [`comparison.py`](../../backend/comparison.py), [`CompareExplanation.tsx`](../../frontend/src/CompareExplanation.tsx), [`backend/tests/`](../../backend/tests/) | [`b75f847`](https://github.com/sayknow/M2-1/commit/b75f847), [`7f392c2`](https://github.com/sayknow/M2-1/commit/7f392c2), [PR #4](https://github.com/sayknow/M2-1/pull/4), [PR #5](https://github.com/sayknow/M2-1/pull/5) |
| **김재욱** | **자료 수집 · 검수 · RAG 정리** | 다이소 공식 상품 88개 수집 및 제조사 표시 대조, 성분·단위·기준량·섭취법·주의사항 검수(공개 87개·보류 1개 분리), 일반 영양 지식 카드(35개) 및 검색 별칭 정리 | [DB 설계 기록](../product-database.md), [라벨 검수 보고서](../product-label-review.md), [수집 보고서](../product-collection-report.md), [`nutrition-knowledge.json`](../../backend/nutrition-knowledge.json), [`label-guides.json`](../../backend/label-guides.json) | [`de683ca`](https://github.com/sayknow/M2-1/commit/de683ca), [`fb2cce0`](https://github.com/sayknow/M2-1/commit/fb2cce0), [`c8fa914`](https://github.com/sayknow/M2-1/commit/c8fa914), [`b1185bf`](https://github.com/sayknow/M2-1/commit/b1185bf) |
| **윤준서** | **기획 · 요구 명세 · 설계 문서** | 초보자 타깃 및 문제 가설 정의, 5대 관심 분야 및 안전 경계 설정, Must 8개·Should 1개 기능 요구 명세서 작성, 화면 이동 흐름 및 시스템 아키텍처 문서 정리 | [프로젝트 기획서](../project-plan.md), [기능 요구 명세서](../functional-requirements.md), [시스템 아키텍처](architecture.md), [AI 활용 설계](ai-design.md) | [`795a23c`](https://github.com/sayknow/M2-1/commit/795a23c), [`e40d644`](https://github.com/sayknow/M2-1/commit/e40d644), [PR #6](https://github.com/sayknow/M2-1/pull/6), [PR #8](https://github.com/sayknow/M2-1/pull/8) |
| **배창민** | **테스트 · 피드백 · 진행 문서** | Must 기능별 재현 시나리오 설계, 실사용자 5명(`T1`~`T5`) 모바일 사용성 테스트 진행 및 응답 일지 정리, 5대 피드백(`F01`~`F05`) 전후 검증, 진행 기록 및 발표 구성안 취합 | [검증 결과](test-results.md), [사용자 피드백](user-feedback.md), [실사용자 응답 원본](evidence/user-test-records.md), [진행 기록](progress.md), [발표 구성안](presentation-outline.md) | [`1e44b76`](https://github.com/sayknow/M2-1/commit/1e44b76), [`e40d644`](https://github.com/sayknow/M2-1/commit/e40d644), [PR #7](https://github.com/sayknow/M2-1/pull/7), [PR #8](https://github.com/sayknow/M2-1/pull/8) |

---

## 2. 팀원별 본인 기여 요약 및 대표 수행 증빙

각 팀원이 프로젝트 전 주기에서 직접 수행한 핵심 역할과 산출물 근거를 정리했습니다.

### 2.1 이승현 (주 개발 · 통합 및 운영 관리)
* **본인 기여 요약**:
  * React·TypeScript 프런트엔드([`frontend/src/App.tsx`](../../frontend/src/App.tsx))와 FastAPI 백엔드([`backend/main.py`](../../backend/main.py)) 전체 구조를 설계·구현하고, 읽기 전용 SQLite 검수 뷰와 결정적 후보 추천 정책([`backend/policy.py`](../../backend/policy.py))을 연결했습니다.
  * 코디세이 COPA 게이트웨이 기반 `gpt-5.4` 연동([`backend/copa.py`](../../backend/copa.py))과 7개 도구 자율 호출 에이전트 루프 및 출처 교차 검증([`backend/agent.py`](../../backend/agent.py))을 구현했습니다.
  * `canary → dev → production` 단계적 브랜치 승격 워크플로우([`.github/workflows/ci.yml`](../../.github/workflows/ci.yml))와 Render 정적 사이트·Docker API 운영 배포를 구축하고, 팀원들의 데이터·문서·공동 개발 산출물을 통합 관리했습니다.
* **대표 증빙 링크**: [`backend/agent.py`](../../backend/agent.py) · [`backend/policy.py`](../../backend/policy.py) · [PR #3 (COPA GPT 전환)](https://github.com/sayknow/M2-1/pull/3) · [PR #6 (Production 릴리스)](https://github.com/sayknow/M2-1/pull/6)

### 2.2 조준수 (부 개발 · 추천 분류 및 AI 비교 공동 개발)
* **본인 기여 요약**:
  * 주 개발자와 함께 5대 관심 분야(`일상의 활력`, `뼈·근육 건강`, `장 건강`, `혈당 관리`, `다이어트`) 중심의 목적 분류 체계([`backend/classification.py`](../../backend/classification.py), [`classification-v2.json`](../../data/recommendation/classification-v2.json))를 설계·구현하여 직접 목적(`direct`) 후보 우선 추천과 포장 변형 중복 묶기 로직을 완성했습니다.
  * 두 제품의 표시 사실을 바탕으로 핵심 차이 최대 3가지와 선택 기준을 생성·검증·캐시하는 AI 비교 해설 백엔드 모듈([`backend/comparison.py`](../../backend/comparison.py))과 프런트엔드 비교 해설 UI([`frontend/src/CompareExplanation.tsx`](../../frontend/src/CompareExplanation.tsx)) 구현에 참여했습니다.
  * 추천 분류 회귀 테스트([`test_recommendation_v2.py`](../../backend/tests/test_recommendation_v2.py)) 및 비교 해설 단위 테스트([`test_comparison.py`](../../backend/tests/test_comparison.py))를 작성하여 예외 경계를 검증했습니다.
* **대표 증빙 링크**: [`backend/classification.py`](../../backend/classification.py) · [`backend/comparison.py`](../../backend/comparison.py) · [`CompareExplanation.tsx`](../../frontend/src/CompareExplanation.tsx) · [PR #4 (목적 기반 추천 분류)](https://github.com/sayknow/M2-1/pull/4) · [PR #5 (5대 분야 및 AI 비교 해설)](https://github.com/sayknow/M2-1/pull/5)

### 2.3 김재욱 (자료 수집 · 라벨 검수 · RAG 지식 정리)
* **본인 기여 요약**:
  * 다이소몰 공식 상품 88개 SKU의 상세 이미지와 제조사 표시자료를 수집하고, OCR 초안과 실제 라벨 원문을 대조 검수하여 공개 가능한 87개 상품과 정량 미기재 보류 1개 상품(`600651654` 산뜻해질 유한 생유산균 캡슐)을 분리했습니다([`docs/product-label-review.md`](../product-label-review.md)).
  * 성분별 함량 수치, 단위(`mg`, `μg`, `IU`), 섭취 기준량(`1일 1정` 등), 부등호 표기를 원문 그대로 정규화하고 성분 별칭(`셀레늄`/`셀렌` 등) 매핑 기준을 정리하여 [`docs/product-database.md`](../product-database.md)에 문서화했습니다.
  * 제품 선택 전에도 일반 영양 상담과 라벨 용어 설명이 가능하도록 주요 성분 10종에 대한 공식 영양 지식 카드 35개·출처 12개([`backend/nutrition-knowledge.json`](../../backend/nutrition-knowledge.json))와 표시 읽기 가이드([`backend/label-guides.json`](../../backend/label-guides.json))를 구축했습니다.
* **대표 증빙 링크**: [`docs/product-database.md`](../product-database.md) · [`docs/product-label-review.md`](../product-label-review.md) · [`backend/nutrition-knowledge.json`](../../backend/nutrition-knowledge.json) · [초기 검수 DB 반영 `de683ca`](https://github.com/sayknow/M2-1/commit/de683ca) · [일반 영양 지식 확장 `b1185bf`](https://github.com/sayknow/M2-1/commit/b1185bf)

### 2.4 윤준서 (기획 · 요구사항 명세 · 아키텍처 설계 문서화)
* **본인 기여 요약**:
  * 영양제 입문 성인이 겪는 ‘초기 후보 탐색 부담 · 라벨 기준량 해독 어려움 · 중복 성분 확인 번거로움’의 3대 문제를 정의하고, 비의료·비처방 안전 경계를 반영한 5단계 설문 및 서비스 흐름을 기획했습니다([`docs/project-plan.md`](../project-plan.md)).
  * 필수 요구사항 Must 8개(`M01`~`M07`, `M09`)와 선택 요구사항 Should 1개(`S01`), 비기능 요구사항(`N01`~`N07`)의 입력 조건·화면 상태·기대 결과를 정의하여 [`docs/functional-requirements.md`](../functional-requirements.md)로 명세화했습니다.
  * 프런트엔드·백엔드·SQLite·COPA 간 데이터/개인정보 경계와 결정적 규칙 vs AI 역할 분담 구조를 [`docs/final/architecture.md`](architecture.md) 및 [`docs/final/ai-design.md`](ai-design.md)로 체계화했습니다.
* **대표 증빙 링크**: [`docs/project-plan.md`](../project-plan.md) · [`docs/functional-requirements.md`](../functional-requirements.md) · [`docs/final/architecture.md`](architecture.md) · [최종 제출 문서 정리 `e40d644`](https://github.com/sayknow/M2-1/commit/e40d644)

### 2.5 배창민 (테스트 · 실사용자 피드백 수집 · 진행 기록 정리)
* **본인 기여 요약**:
  * 다이소 영양제 탐색 타깃에 해당하는 외부 성인 사용자 5명(`T1`~`T5`)을 대상으로 `2026-10-22`~`10-23` 이틀간 사용성 테스트와 6개 공통 질문 인터뷰를 진행하고, 익명화 응답 원본 기록([`docs/final/evidence/user-test-records.md`](evidence/user-test-records.md))을 작성했습니다.
  * 사용자 테스트에서 확인된 5대 핵심 불편 사항(`F01` 주소 식별성, `F02` 일반 영양 질문 범위, `F03` 첫 시작 질문 오류, `F04` 활력 추천 납득도, `F05` 포장 변형 중복 추천)과 미반영 의견의 사유를 정리하고 개선 전후 상태를 대조 검증했습니다([`docs/final/user-feedback.md`](user-feedback.md)).
  * 기능별 검증 결과 보고서([`docs/final/test-results.md`](test-results.md)), 일자별 개발 진행 기록([`docs/final/progress.md`](progress.md)), 서면 심사용 12페이지 발표 구성안([`docs/final/presentation-outline.md`](presentation-outline.md))을 취합·정리했습니다.
* **대표 증빙 링크**: [`docs/final/user-feedback.md`](user-feedback.md) · [`docs/final/evidence/user-test-records.md`](evidence/user-test-records.md) · [`docs/final/test-results.md`](test-results.md) · [`docs/final/progress.md`](progress.md)

---

## 3. 주요 저장소 통합 이력 요약

| 단계 | 저장소 커밋 · PR 링크 | 통합 반영 내용 |
|---|---|---|
| **1. 검수 DB · 프로토타입** | [`de683ca`](https://github.com/sayknow/M2-1/commit/de683ca) | 88개 수집 · 87개 공개 검수 데이터 및 모바일 프런트 프로토타입 반영 |
| **2. 썸네일 · 백엔드 연결** | [`fb2cce0`](https://github.com/sayknow/M2-1/commit/fb2cce0) | 공식 썸네일 87개 연결 및 초기 추천/대화 백엔드 구축 |
| **3. 표시 가이드 · 상담 지식 확장** | [`c8fa914`](https://github.com/sayknow/M2-1/commit/c8fa914) · [`b1185bf`](https://github.com/sayknow/M2-1/commit/b1185bf) | 첫 질문(`함량 vs 기준량`) 공식 가이드 연결(F03) 및 일반 영양 지식 35개 확장(F02) |
| **4. 서비스 도메인 전환** | [`1e44b76`](https://github.com/sayknow/M2-1/commit/1e44b76) | 사용자 식별성 피드백(F01) 반영 `vitastep-guide.onrender.com` 배포 |
| **5. COPA `gpt-5.4` 전환** | [PR #3](https://github.com/sayknow/M2-1/pull/3) | 코디세이 COPA 게이트웨이 연동 및 7개 도구 호출 호환성 검증 통합 |
| **6. 목적 분류 · 중복 축소** | [PR #4](https://github.com/sayknow/M2-1/pull/4) (`b75f847`) | 활력 직접 목적 우선 추천(F04) 및 포장 변형 대표 후보 그룹핑(F05) 통합 |
| **7. 5대 관심 분야 · AI 비교 해설** | [PR #5](https://github.com/sayknow/M2-1/pull/5) (`7f392c2`) | 5대 관심 분야 확정 및 두 제품 표시 기반 AI 비교 해설(`S01`) 통합 |
| **8. 운영 릴리스 및 제출 문서화** | [PR #6](https://github.com/sayknow/M2-1/pull/6) (`0bc17dc`) · [PR #8](https://github.com/sayknow/M2-1/pull/8) | `production` 운영 배포 완료 및 최종 제출 문서·증빙 패키지 완비 |
