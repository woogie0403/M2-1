# 영양제 첫걸음 — 최종 제출 문서

> **문서 기준일**: **2026-10-24 (KST)** · **대조한 코드**: [`0bc17dc`](https://github.com/sayknow/M2-1/commit/0bc17dca34f3ec6479549248798e76bfcb962064) · **운영 브랜치**: `production`

영양제를 처음 고르는 성인이 다이소 제품의 표시정보를 이해하고 **설문 후보 추천 · 두 제품 표시 비교 · 출처가 있는 AI 설명**을 이용하도록 만든 서비스다. 다이소의 공식·제휴 서비스가 아닌 교육 프로젝트이며 진단·처방·개인별 복용량 조절을 제공하지 않는다.

---

## 접속과 읽는 순서

**[운영 서비스](https://vitastep-guide.onrender.com/)** / **[GitHub 저장소](https://github.com/sayknow/M2-1)**

평가용 계정은 필요 없다. 제품 찾기·상세·표시 비교는 바로 이용한다. 추천·대화·AI 비교 해설은 성인 이용·정보 처리·외부 AI 전송 안내에 동의한 뒤 이용한다. 백엔드가 대기 중이면 첫 연결이 지연될 수 있다. 화면의 서버 준비 안내를 기다린 뒤 진행한다. 팀은 결과 안내를 받을 때까지 서비스를 유지한다.

| 순서 | 문서 | 핵심 내용 |
|---|---|---|
| **1** | **[기획서](../project-plan.md)** | 문제·타깃·해결 방식·기술 선정 이유·데이터 품질·범위·일정 |
| **2** | **[기능 요구 명세서](../functional-requirements.md)** | Must 8개·Should 1개·비기능 요구·화면 재현·AI 분담 명세 |
| **3** | **[시스템 아키텍처](architecture.md)** | 화면/API/DB/외부 AI 경계·API 계약·배포·실패 흐름 |
| **4** | **[AI 활용 설계](ai-design.md)** | Agent 7개 도구·RAG 근거·후보 정책·코드 위치·한계 |
| **5** | **[검증 결과](test-results.md)** | 로컬 자동 검사·실제 GPT API 3회 반복 검증·데이터·화면 확인 |
| **6** | **[사용자 피드백과 개선](user-feedback.md)** | 5대 개선 항목(`F01`~`F05`) 전후 차이·**[실사용자 5명 응답 원본](evidence/user-test-records.md)** |
| **7** | **[팀원 역할과 기여](team-contributions.md)** | 5인 역할 분담·본인 기여 요약·담당 산출물 및 저장소 PR/커밋 연결 |
| **8** | **[진행 기록](progress.md)** | 일자별 실제 Git 이력·기술적 의사결정·릴리스 기록 |
| **9** | **[보안·운영](security-and-operations.md)** | 동의·개인정보 보존 경계·비밀키·장애 대응·배포와 롤백 |
| **10** | **[발표 자료 PDF (`docs/presentation.pdf`)](../presentation.pdf)** · **[슬라이드 구성 안내](presentation-outline.md)** | 12페이지 서면 심사용 발표 PDF 완비 ([동일 사본 `final/presentation.pdf`](presentation.pdf)) |

---

## 평가 요건 대조

| 요건 | 제출 근거 문서 | 확인 상태 |
|---|---|---|
| **G1 문서 구비** | 위 10개 문서 묶음, 루트 [`README.md`](../../README.md), **[발표 자료 PDF](../presentation.pdf)** | **전체 Markdown 문서 및 12페이지 발표 PDF 제작 완료** |
| **G2 외부 접속** | [운영 URL](https://vitastep-guide.onrender.com/), [배포 증빙](evidence/production-release-2026-10-23.json) | 외부 프런트엔드 화면 및 백엔드 API 접속·동작 확인 완료 |
| **G3 AI 핵심 기술 2개** | [AI 활용 설계](ai-design.md), `M03`·`M04` 도구/검색 출처 로그 | **AI Agent (7개 도구) + RAG (SQLite·공식 지식 검색)** 구현 및 검증 완료 |
| **G4 Must 기능** | [API 반복 검사](evidence/acceptance-api.json), [브라우저 확인](evidence/acceptance-browser.json) | Must 8개 모두 API 3회 중 2회 이상 성공 (`M04` 2/3, 나머지 7개 및 `S01` 3/3) |
| **G5 실사용자 5명** | [피드백 문서](user-feedback.md), [5인 응답 원본 기록](evidence/user-test-records.md) | **타깃 성인 5명(`T1`~`T5`, 팀원 제외) 익명화 응답 원본 및 5대 개선(`F01`~`F05`) 반영 완료** |
| **G6 전원 기여** | [팀원 역할과 기여](team-contributions.md), Git 커밋·PR 이력 | **5인 전원 역할 분담·본인 기여 요약 및 담당 산출물/통합 PR 연결 완료** |
| **G7 AI 윤리·개인정보** | 서비스 동의 화면, [보안·운영 문서](security-and-operations.md) | AI 생성 표시·사전 동의·입력 최소화·동의 철회 및 피드백 개인정보 비식별화 완료 |

> 개발자 가상 입력 QA([`test-results.md`](test-results.md))와 실제 타깃 사용자 5명 피드백([`user-test-records.md`](evidence/user-test-records.md))은 엄격히 분리하여 기록했습니다.

---

## 자료 기준과 제출 전 확인

수집 88개, 공개·표시 검수 87개, 보류 1개(`600651654`)다. 공식 썸네일 88개 중 공개 제품에 87개 연결했다. 정책 `2026-10-23.2`, 관심 분류 `2026-10-23.3`, 운영 AI `gpt-5.4` / COPA다. 공식 표시·가격의 주 관찰일은 `10-19`, 라벨 검수는 `10-19~20`, 썸네일 확인은 `10-21`이다. 문서 작성일을 상품 최신 확인일로 사용하지 않는다.

최신 제출 설명은 이 문서 묶음과 루트 [`README.md`](../../README.md)·[기획서](../project-plan.md)·[기능 요구 명세서](../functional-requirements.md)다. 이전 Gemini·초기 기획·canary 전환 기록은 당시 이력을 보존한 보조 자료다. [기준 정보·파일 해시](manifest.json)를 `python3 scripts/validate_final_docs.py`로 대조할 수 있다.
