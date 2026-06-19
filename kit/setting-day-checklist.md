# Setting Day — 셋업 체크리스트

> 조사일 2026-06-18 · 가격·버전은 변동될 수 있으니 공식 문서 확인.
> 자기 레벨에서 시작해 한 단계씩. ✅ = 성공 확인, ⚠️ = 흔한 함정.

## L0 · 입장 — 챗 앱 설치 + 로그인 〔무료 / 누구나〕
- [ ] 데스크톱 앱 설치 — `claude.com/download` (macOS 11+ / Windows 10+) · *Linux는 웹 사용*
- [ ] 또는 모바일 앱 — App Store(iOS 17+) / Google Play "Claude"
- [ ] 또는 웹 — `claude.ai` (설치 불필요)
- [ ] Google 또는 이메일로 로그인
- [ ] ✅ 첫 질문에 답이 온다
- ⚠️ 데스크톱 앱은 Linux 미지원 → 웹으로

## L1 · 첫 활용 — 능력 켜고 Skill 써보기 〔무료〕
- [ ] Settings → Capabilities → `Code execution & file creation` 켜기
- [ ] Customize → Skills 에서 예시 스킬 토글
- [ ] (선택) 커스텀 스킬 업로드
- [ ] ✅ 스킬로 문서·표 생성
- ⚠️ 코드 실행 토글 OFF면 커스텀 스킬 작동 안 함 · 커스텀 스킬은 유료(Pro+)

## L2 · 연결 — Connector(MCP) 붙이기 〔무료~〕
- [ ] `claude.ai/directory` 에서 검수된 커넥터 둘러보기
- [ ] Settings → Connectors → "+" Add custom connector → 원격 MCP URL 입력
- [ ] 채팅 "+" 에서 커넥터 켜기
- [ ] ✅ 채팅이 외부 도구를 호출
- ⚠️ 무료는 커스텀 커넥터 1개 · 모바일은 직접 추가 불가(웹에서 추가→동기화, beta) · 신뢰할 수 있는 서버만

## L3 · 개발자 진입 — Claude Code 설치 〔유료 Pro+〕
- [ ] 네이티브 설치 — macOS: `curl -fsSL https://claude.ai/install.sh | bash`
- [ ] 네이티브 설치 — Windows(PowerShell): `irm https://claude.ai/install.ps1 | iex`
- [ ] `claude` 첫 실행 → 브라우저 로그인
- [ ] (선택) VS Code 1.98+ "Claude Code" 확장 / JetBrains 플러그인 27310(Beta)
- [ ] (Windows 데스크톱 Code 탭) Git for Windows 설치 후 앱 재시작
- [ ] ✅ `claude` 세션이 시작된다
- ⚠️ 무료 플랜 불가(Pro $17/mo~) · IDE 확장만으론 터미널 `claude` 없음 → CLI 별도 설치 · `ANTHROPIC_API_KEY` 있으면 토큰 과금

## L4 · 파워업 — MCP · Skills · Plugins 무장 〔유료〕
- [ ] MCP 추가 — `claude mcp add --transport http <name> <url>` (팀 공유는 `.mcp.json`)
- [ ] Skill — `~/.claude/skills/<name>/SKILL.md` 또는 `/plugin marketplace add anthropics/skills`
- [ ] Plugin — `/plugin marketplace add owner/repo` → `/plugin install <name>@<marketplace>`
- [ ] ✅ 플러그인·스킬·MCP가 세션에서 작동
- ⚠️ 확장 = 사용자 권한으로 코드 실행 → 신뢰하는 출처만 · Plugins는 Claude Code 전용

---
*출처: Anthropic 공식 문서(code.claude.com, support.claude.com, claude.com). 자세한 근거는 `research/claude-setup-research.md`.*
