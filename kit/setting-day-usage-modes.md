# Setting Day · 사용편 — 실행 모드 비교 카드

> 조사일 2026-06-19 · "언제 무엇을 쓰나" 선택용. 5종 **모두 공식 기능**(Claude Code). 〔입문〕 = 본문 핵심 · 〔고급〕 = 나중에.

## 한 줄 선택 가이드
- 바꾸기 전에 **계획부터** → **플랜모드** 〔입문〕
- 곁가지를 **따로 시켜 요약만** → **subagent** 〔입문〕
- 출처 **교차검증 리포트** → **deep-research** 〔입문〕
- **수십~수백 작업**을 스크립트로 → **workflow** 〔고급〕
- 여러 세션이 **서로 대화하며 협업** → **agent-team** 〔실험적·고급〕

---

## 입문 핵심 3가지

| 모드 | 무엇 | 진입 / 사용 | 함정 |
|---|---|---|---|
| **플랜모드** | 읽기·탐색만 하고 계획 제안, 승인 후 실행 | `Shift+Tab`(default→acceptEdits→plan) · `/plan` · `--permission-mode plan` | 승인 전엔 편집 안 함. `Ctrl+G`로 계획 편집 |
| **subagent** | 자식 에이전트가 자체 컨텍스트로 곁가지 처리 후 **요약만 반환** | 작업 위임 시 자동, 또는 커스텀 정의 | 단일 세션 내. 서로 대화 안 함(메인에 보고만) |
| **deep-research** | 여러 각도 검색 → 출처 교차검증 → 인용 리포트 | `/deep-research <질문>`(Code 내장 워크플로) · 앱은 "+"→Research | 웹검색 필요, 토큰 많이 씀. 좁은 질문부터 |

---

## 공식 비교표 (위임·확장 방식)

| | Subagent | Skill | Agent team | Workflow |
|---|---|---|---|---|
| 정체 | Claude가 띄우는 워커 | Claude가 따르는 지침 | peer 세션 이끄는 lead | 런타임이 실행하는 스크립트 |
| 다음 할 일 결정 | Claude, 턴마다 | Claude, 프롬프트대로 | lead, 턴마다 | 스크립트 |
| 중간결과 위치 | Claude 컨텍스트 | Claude 컨텍스트 | 공유 task list | 스크립트 변수 |
| 규모 | 턴당 몇 개 | 턴당 몇 개 | 장기 peer 소수 | run당 수십~수백 |

> 출처: code.claude.com/docs/en/workflows

---

## 더 가면 〔고급〕

| 모드 | 무엇 | 게이팅 | 문서 |
|---|---|---|---|
| **workflow** | JS 스크립트로 subagent 대량 오케스트레이션(코드베이스 감사·대규모 마이그레이션) | 모든 유료(Pro는 `/config` 토글). `ultracode`로 트리거 | code.claude.com/docs/en/workflows |
| **agent-team** | 여러 세션이 팀(lead+teammates)으로 협업, 공유 task·상호 메시징 | **실험적·기본 OFF** → `CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1`. 토큰 多 | code.claude.com/docs/en/agent-teams |

> deep-research는 앱·Code 양쪽에 공식: Code는 내장 워크플로 `/deep-research`, 앱은 Research 기능.
