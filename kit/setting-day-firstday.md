# Setting Day · 사용편 — Claude Code 첫날 5프롬프트

> 조사일 2026-06-19 · 설치 직후 그대로 따라하기. 출처: 공식 first-day 가이드 · quickstart.

## 0. 준비 (2분)
- 설치 확인: `claude --version`
- 로그인: `claude` 첫 실행 → 브라우저, 또는 `/login`
- 프로젝트 열기: 폴더(보통 git repo) 루트에서 `claude`
- ⚠️ 안전 규칙: Claude는 파일 변경·명령 실행 전 **항상 확인**(Yes / Yes, 다신 묻지마 / No). 모르면 일단 멈추고 읽어보기.

## 첫날 5프롬프트 — 한 번에 하나씩 복붙
1. **이 코드베이스를 5개 bullet로 요약하고, 진입점이 어디인지 알려줘.**
2. **사용자 인증을 처리하는 코드가 어디에 있어?**
3. **이 함수에 2줄짜리 docstring을 추가해줘.**
4. **(실패한 테스트의 에러 메시지를 붙여넣고) 왜 실패하는지 찾아서 고쳐줘.**
5. **변경사항을 스테이징하고, 기존 커밋 스타일에 맞춰 커밋해줘.**

> ⭐ 마지막에 **`/init`** — 프로젝트를 스캔해 `CLAUDE.md`(빌드 명령·구조·컨벤션 요약)를 만들어 줍니다. 공식 가이드가 "가장 가치 높은 셋업 단계"로 꼽음.

## 더 해보기 (입문 직후)
| 하고 싶은 것 | 방법 |
|---|---|
| 바꾸기 전에 계획부터 | **플랜모드**: `Shift+Tab` 순환(default→acceptEdits→plan) · `/plan fix the auth bug` · `claude --permission-mode plan` — 읽기 전용, 승인 전 소스 편집 안 함 |
| 스크린샷·이미지 보여주기 | 창에 **드래그앤드롭** · `ctrl+v`(macOS도 cmd+v 아님 — 터미널이 가로챔) · 경로로 `Analyze this image: /path/to/image.png` |
| 곁가지는 따로 시켜 요약만 | **subagent**: 자동 위임 또는 `.claude/agents/<name>.md`로 정의 · 요청에 "use subagents" 붙이면 병렬 ↑ |
| git을 말로 | "변경사항을 설명적인 메시지로 커밋해줘" 처럼 대화형으로 |

> ⚠️ Claude Code는 **유료 전용**(Pro/Max/Team/Enterprise 또는 Console 크레딧). 무료 Claude.ai 플랜엔 미포함.

---
*출처: support.claude.com/en/articles/14552382 (first-day) · code.claude.com/docs/en/{quickstart, common-workflows, sub-agents}.*
