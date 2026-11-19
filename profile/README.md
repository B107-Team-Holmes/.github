<div align="center">

<img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/brand/sherlog-logo.png" alt="SHERLOG logo" width="520" />

# SHERLOG

### SEMES Hidden Error Resolver + Log

**흩어진 로그를 모으고, 핵심 오류를 발견하고, 원인 확인 지점을 추적합니다.**

Windows 기반 반도체 설비 사후 로그 분석 프로그램

</div>

---

## 🔍 SHERLOG는 무엇인가요?

설비 장애가 발생하면 엔지니어는 Module·Submodule·시간별로 흩어진 로그를 직접 찾아 연결하고, 수많은 알람 중 실제 분석이 필요한 오류를 가려내야 합니다.

SHERLOG는 여러 로그를 하나의 실행 흐름으로 복원한 뒤 정상 패턴과 비교하여 **핵심 오류, 특이사항, 예상 원인 지점과 근거 로그**를 제공합니다. 로그에 기록되지 않은 하드웨어 원인은 확정하지 않으며, 엔지니어가 확인해야 할 시간과 범위를 좁히는 데 집중합니다.

| Pain Point | SHERLOG의 해결 방식 |
| --- | --- |
| 필요한 로그가 여러 파일에 흩어져 있음 | Sequence·Submodule 로그를 공통 이벤트로 변환하고 연결 |
| 알람이 많아 중요한 오류를 찾기 어려움 | 정상 패턴과 비교해 핵심 오류와 특이사항을 선별 |
| 처음 발견한 알람이 실제 원인이 아닐 수 있음 | 오류 전후 흐름을 추적해 예상 원인 지점과 근거를 제시 |

## ✨ 주요 기능

- **정상 로그 학습** — 정상 실행 순서, 수행 시간과 파라미터 기준 생성
- **특정 시점·기간 분석** — 핵심 오류와 특이사항, 발생 시점 및 관련 로그 탐색
- **두 로그 비교** — SW 패치·정기 점검 전후의 이벤트와 수행 시간 차이 비교
- **실행 흐름 복원** — Run–End 페어링과 Process–Step–Function 단위 타임라인 구성
- **근거 기반 분석** — 파일명, Timestamp, 행 번호와 함께 분석 결과 제공
- **LLM 보조 분석** — 파싱 규칙 후보 생성, 핵심 오류 선별과 확인 지점 설명

## 🔄 분석 흐름

```text
로그 폴더·기간 선택
        ↓
원본 로그 파싱 및 공통 이벤트 변환
        ↓
Run–End 페어링과 실행 흐름 복원
        ↓
정상 패턴 비교 및 오류 후보 생성
        ↓
LLM 기반 핵심 오류·특이사항 선별
        ↓
예상 원인 지점·근거 로그·추가 확인 사항 제공
```

## 🛠 기술 구성

| 영역 | 기술 |
| --- | --- |
| Desktop | Electron |
| Frontend | React, TypeScript |
| Backend | Python, FastAPI |
| Database | SQLite |
| AI | LLM Structured Output, JSON Schema |
| Packaging | Electron Builder + Windows embeddable Python 3.14.10 |

> 2026-11-02 기준 DATA/BE 2 계산 모듈과 BE 1 저장·API 기반은 dev에 반영됐습니다. BE 2 진입 함수(-180)도 dev에 병합됐고 실제 전체 분석(-84), AI 실호출·목표 PC 검증을 이어가는 단계입니다.

로컬 백엔드의 43개 HTTP 동작·SQLite Repository와 고정 Electron bridge를 구현했습니다. 설치·실행·검증은 [백엔드 실행 안내](https://github.com/win929/SHERLOG/blob/main/docs/BACKEND_SETUP.md), 실제 분석·AI·제품 검증의 남은 범위는 [BE 작업표](https://github.com/win929/SHERLOG/blob/main/docs/BE_IMPLEMENTATION_STATUS.md)를 따릅니다.

## 🕵️ Team Holmes

<div align="center">

SHERLOG을 만드는 **Holmes**입니다.

</div>

<table align="center">
  <tr>
    <td align="center" width="33%">
      <img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/team/ha-suyeon-sherlock.png" alt="하수연" width="220" /><br />
      <strong>하수연</strong><br />
      <sub>FE</sub>
    </td>
    <td align="center" width="33%">
      <img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/team/park-gyuyeon-sherlock.png" alt="박규연" width="220" /><br />
      <strong>박규연</strong><br />
      <sub>FE</sub>
    </td>
    <td align="center" width="33%">
      <img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/team/geum-junyeong-sherlock.png" alt="금준영" width="220" /><br />
      <strong>금준영</strong><br />
      <sub>DATA</sub>
    </td>
  </tr>
  <tr>
    <td align="center" width="33%">
      <img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/team/lee-eojin-sherlock.png" alt="이어진" width="220" /><br />
      <strong>이어진</strong><br />
      <sub>팀장 · BE</sub>
    </td>
    <td align="center" width="33%">
      <img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/team/kang-hyeonji-sherlock.png" alt="강현지" width="220" /><br />
      <strong>강현지</strong><br />
      <sub>BE · Infra</sub>
    </td>
    <td align="center" width="33%">
      <img src="https://raw.githubusercontent.com/B107-Team-Holmes/.github/main/profile/assets/team/jeong-uichan-sherlock.png" alt="정의찬" width="220" /><br />
      <strong>정의찬</strong><br />
      <sub>AI</sub>
    </td>
  </tr>
</table>

## 🗺 개발 로드맵

> 2026-11-02 · dev ff33fe1 대조. 상세 담당·병합·외부 검증은 [BE 작업표](https://github.com/win929/SHERLOG/blob/main/docs/BE_IMPLEMENTATION_STATUS.md)를 따른다.

- [x] 공통 `ParsedEvent` 계약·더미 로그용 수동 파싱 프로파일
- [x] Run–End·계층·정상 기준·오류 후보 계산 모듈 (실제 통합 실행은 후속)
- [x] FastAPI·SQLite 저장/조회 기반과 43개 HTTP 동작
- [x] BE 1 파일 선택·중복 파싱 방지·DATA 순차 저장·취소 (-255 병합)
- [ ] 병합된 BE 2 진입 함수(-180)를 실제 전체 분석·관계 저장·완료 판정(-84)에 연결
- [ ] React·Electron 화면의 남은 실제 분석/비교 연결과 제품 검증
- [ ] 실제 AI provider 연결·명시 요청 기반 실호출/품질 검증
- [ ] 실제 샘플·목표 Windows PC의 전체 분석/메모리/조회/취소 검증

## 📚 문서

- [프론트엔드 실행 환경](https://github.com/win929/SHERLOG/blob/main/docs/FRONTEND_SETUP.md) — Electron·React 실행, 브라우저 미리보기, 빌드

- [프로젝트 상세 명세](https://github.com/win929/SHERLOG/blob/main/docs/PROJECT_SPEC.md)
- [BE 구현 현황·남은 작업](https://github.com/win929/SHERLOG/blob/main/docs/BE_IMPLEMENTATION_STATUS.md) · [백엔드 실행 안내](https://github.com/win929/SHERLOG/blob/main/docs/BACKEND_SETUP.md)
- [요구사항 명세서 (기능 · 화면)](https://github.com/win929/SHERLOG/blob/main/docs/requirements/REQUIREMENTS_SPEC.md) · [Word](https://github.com/win929/SHERLOG/blob/main/docs/requirements/REQUIREMENTS_SPEC.docx)
- [DATA 파트 설계](https://github.com/win929/SHERLOG/blob/main/docs/architecture/DATA_ARCHITECTURE.md)
- [ERD·DB 개발 참고 순서](https://github.com/win929/SHERLOG/blob/main/docs/architecture/README.md)
- [API 개발 참고 순서](https://github.com/win929/SHERLOG/blob/main/docs/api/README.md) · [API 설계](https://github.com/win929/SHERLOG/blob/main/docs/api/API_SPEC.md) · [상세 목록·DTO](https://github.com/win929/SHERLOG/blob/main/docs/api/ENDPOINTS.md) · [OpenAPI 계약](https://github.com/win929/SHERLOG/blob/main/docs/api/API_CONTRACT.json) — 45개 동작 중 구현 43개·계획 2개, 실제 분석/AI 연결 상태는 BE 작업표 참조
- [최소 ERD](https://github.com/win929/SHERLOG/blob/main/docs/architecture/ERD.md) · [테이블별 설명](https://github.com/win929/SHERLOG/blob/main/docs/architecture/TABLE_DEFINITIONS.md) · [ERDCloud SQL](https://github.com/win929/SHERLOG/blob/main/docs/architecture/ERD_CLOUD.sql)
- [ERD 적합성 검토](https://github.com/win929/SHERLOG/blob/main/docs/architecture/ERD_REVIEW.md) · [저장·조회 규칙](https://github.com/win929/SHERLOG/blob/main/docs/architecture/QUERY_RULES.md)
- [SQLite 테이블 생성 SQL](https://github.com/win929/SHERLOG/blob/main/backend/storage/schema.sql) · [적용 방법과 제약조건](https://github.com/win929/SHERLOG/blob/main/docs/architecture/SQLITE_SCHEMA.md)
- [브랜치 관리 전략](https://github.com/win929/SHERLOG/blob/main/docs/BRANCH_STRATEGY.md)
- [CI 파이프라인과 미리보기](https://github.com/win929/SHERLOG/blob/main/docs/CI_PIPELINE.md) — 잡 구성, 실패 시 확인할 곳, 미리보기·되돌리기
- [Jira 컨벤션](https://github.com/win929/SHERLOG/blob/main/docs/JIRA_CONVENTION.md)
- [Jira 자동화 적용 기록](https://github.com/win929/SHERLOG/blob/main/docs/JIRA_AUTOMATION.md)
- [Jira 이슈 설명 템플릿](https://github.com/win929/SHERLOG/blob/main/docs/templates/JIRA_ISSUE_DESCRIPTION.md)
- [1차 멘토링 일지](https://github.com/win929/SHERLOG/blob/main/docs/mentoring/MENTORING_01_20261007.md)
- [2차 멘토링 일지](https://github.com/win929/SHERLOG/blob/main/docs/mentoring/MENTORING_02_20261014.md)
- [디자인 시스템](https://github.com/win929/SHERLOG/blob/main/docs/design/README.md)
- [Codex 개발 지침](https://github.com/win929/SHERLOG/blob/main/AGENTS.md)

---

<div align="center">

**SHERLOG — 모으고, 발견하고, 추적합니다.**

</div>
