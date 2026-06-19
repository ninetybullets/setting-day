# Setting Day · 사용편 — 전역 vs 프로젝트 배치 치트시트

> 조사일 2026-06-19 · 옆에 띄워두고 쓰세요. 〔공식〕 = 공식 문서 근거 · 〔권장〕 = 정답 없는 컨벤션.

## 한 줄 원칙
**늘 지킬 것 = 전역(`~/.claude/`) · 이 프로젝트만 = 프로젝트(`.claude/`)** 〔권장〕

---

## Claude Code — 무엇을 어디에 두나

| 종류 | 전역(나 전체) | 프로젝트(이 repo) | 개인·비공유 |
|---|---|---|---|
| **지침** 〔공식〕 | `~/.claude/CLAUDE.md` | `./CLAUDE.md` 또는 `./.claude/CLAUDE.md` | `./CLAUDE.local.md` |
| **스킬** 〔공식〕 | `~/.claude/skills/<name>/SKILL.md` | `.claude/skills/<name>/SKILL.md` | — |
| **MCP** 〔공식〕 | `claude mcp add --scope user …` | `--scope project` · 공유 파일 `./.mcp.json` | `--scope local` |

> 출처: code.claude.com/docs/en/{memory, settings}

## CLAUDE.md 로딩 규칙 〔공식〕
- **덮어쓰기 아님 → 전부 합쳐서(누적)** 읽힘.
- 순서: **넓은 것 먼저 → 가까운 것 나중**(루트 → 작업 폴더). 디렉터리 안에선 `CLAUDE.local.md`가 `CLAUDE.md` 뒤.
- 로딩: 작업 폴더에서 상위로 훑어 조상 파일은 시작 시 전부, 하위 폴더 파일은 그 파일을 읽을 때.
- 4계층 우선범위: **Managed(조직) → User(전역) → Project → Local**.

> ⚠️ 전역과 프로젝트가 **서로 모순되게** 쓰지 말 것 — 둘 다 읽히므로 충돌하면 헷갈림.

## 점진 layering 〔권장〕 — 1일차부터 다 하지 말 것
1. **1일차** — 전역 지침 1개 + 프로젝트 `CLAUDE.md` 한 장
2. 익숙해지면 — 용어집 `CONTEXT.md`
3. 결정 쌓이면 — `docs/adr/`(ADR, "왜 이렇게")
4. 일 많아지면 — 이슈 트래커 `.scratch/`
5. 팀·반복 생기면 — triage 라벨로 분류

---

## Claude 앱 — 무엇을 어디에 두나

| 종류 | 계정 전역 | 프로젝트별 |
|---|---|---|
| **지침** 〔공식〕 | Settings → "Instructions for Claude"(모든 대화) | Project → "Set project instructions"(그 프로젝트만) |
| **자료(지식)** 〔공식〕 | — | Project의 Knowledge Base에 업로드 |
| **스킬** 〔공식〕 | Settings → Capabilities(코드실행 ON) → Customize → Skills | — |
| **커넥터(MCP)** 〔공식〕 | Settings → Connectors에서 추가 | 채팅 "+"에서 per-chat 토글 |

> ⚠️ 무료: 프로젝트 **최대 5개**, 커스텀 커넥터 **1개**, 커스텀 스킬·코드실행은 **유료(Pro+)**.
> ⚠️ 예전 "스타일(Styles)"은 **Skills로 이관 중** — 새로 시작하면 스킬로.
