# Setting Day — 명령어·경로 치트시트

> 조사일 2026-06-18 · 옆에 띄워두고 쓰세요. 버전·가격은 변동 가능.

## 설치 (Claude Code) — 권장: 네이티브
| 방법 | 명령 |
|---|---|
| 네이티브 macOS/Linux/WSL | `curl -fsSL https://claude.ai/install.sh \| bash` |
| 네이티브 Windows PowerShell | `irm https://claude.ai/install.ps1 \| iex` |
| 네이티브 Windows CMD | `curl -fsSL https://claude.ai/install.cmd -o install.cmd && install.cmd && del install.cmd` |
| Homebrew (수동 업데이트) | `brew install --cask claude-code` |
| WinGet (수동 업데이트) | `winget install Anthropic.ClaudeCode` |
| npm (Node 18+, **sudo 금지**) | `npm install -g @anthropic-ai/claude-code` |

> ⭐ 네이티브 설치만 백그라운드 자동 업데이트 · brew/winget은 수동: `brew upgrade claude-code` / `winget upgrade Anthropic.ClaudeCode`.

## 로그인 / 세션
| 작업 | 명령 |
|---|---|
| 첫 실행 / 세션 시작 | `claude` |
| 재로그인(계정 전환) | `/login` |
| 로그아웃 | `/logout` |

## MCP / Connector
| 작업 | 명령 / 경로 |
|---|---|
| HTTP(원격, 권장) | `claude mcp add --transport http <name> <url>` |
| stdio(로컬) | `claude mcp add <name> -- <command> [args]` |
| JSON으로 추가 | `claude mcp add-json <name> '<json>'` |
| 목록 / 상세 / 삭제 | `claude mcp list` · `claude mcp get <name>` · `claude mcp remove <name>` |
| 세션 내 관리 | `/mcp` |
| 프로젝트 공유 파일 | 루트 `.mcp.json` (키: `mcpServers`) |
| Desktop 설정 (macOS) | `~/Library/Application Support/Claude/claude_desktop_config.json` |
| Desktop 설정 (Windows) | `%APPDATA%\Claude\claude_desktop_config.json` |
| 검수된 커넥터 찾기 | `claude.ai/directory` · `registry.modelcontextprotocol.io` |

## Skills
| 작업 | 경로 / 명령 |
|---|---|
| 개인 스킬 | `~/.claude/skills/<name>/SKILL.md` |
| 프로젝트 스킬 | `.claude/skills/<name>/SKILL.md` |
| 공식 마켓 추가 | `/plugin marketplace add anthropics/skills` |
| 공식 스킬 설치 | `/plugin install document-skills@anthropic-agent-skills` |
| 호출 | 자동(`description`) 또는 `/skill-name` |
| 관리 | `/skills` |

## Plugins (Claude Code 전용)
| 작업 | 명령 |
|---|---|
| 매니저 열기 | `/plugin` |
| 마켓 추가 | `/plugin marketplace add owner/repo` (git URL·로컬 경로도) |
| 설치 | `/plugin install <name>@<marketplace>` |
| 켜기/끄기/삭제 | `/plugin enable\|disable\|uninstall <name>@<marketplace>` |
| 변경 즉시 적용 | `/reload-plugins` |

## 표면별 요구사항
- **Claude Code:** macOS 13+ / Win10 1809+ · 4GB+ RAM (데스크톱 앱 macOS 11+와 별개)
- **VS Code 확장:** 1.98+ · 터미널 `claude`는 CLI 별도 설치 필요
- **JetBrains 플러그인:** ID 27310 (Beta) · CLI 별도 설치
- **데스크톱 앱:** macOS 유니버설 / Windows x64·ARM64 (Linux ✕) · Windows Code 탭은 Git for Windows 필요

## 플랜 한눈에 (USD, 변동 가능)
| 플랜 | Claude Code | 커넥터 | Plugins |
|---|---|---|---|
| Free $0 | ✕ | 커스텀 1개 | ✕ |
| Pro ~$17/mo (월 $20) | ○ | 무제한 | ○ |
| Max $100 / $200 · Team $20~/seat | ○ | ○ | ○ |

> 결제 전 `claude.com/pricing` 확인 · Claude Code는 유료(Pro+) 또는 API 키 필요.
