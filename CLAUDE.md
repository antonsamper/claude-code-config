# Project Information

## Repository Type

**Agent Instructions:**
1. Check `AGENTS.md` for `repository_type`. If file missing or type not set, ask user which type applies.
2. Create/update `AGENTS.md` with their answer. Default to `Production` if user declines to specify.
3. Follow the behaviours for that type (see reference below).

<!-- Reference table - do not delete -->
| Type | Philosophy | Key Behaviours |
|------|------------|----------------|
| **Prototype** | Speed over perfection | Skip edge cases/validation, minimal tests, hardcoding OK, simple > extensible |
| **Production** (Default) | Maintainable & reliable | Follow existing patterns, add tests, proper error handling, consider edge cases |
| **Library** | Public API | Backward compat critical, comprehensive docs/tests, API ergonomics, semver matters |
| **Internal Tool** | Reliable, no public API | Tests for critical paths, proper errors, less doc rigour, refactor freely |
| **Script/Automation** | One-off utilities | Reliability > polish, comments explaining purpose, minimal tests |
| **Fork/Contribution** | Someone else's project | Follow their conventions exactly, match their style, read CONTRIBUTING.md |

---

# Personal Preferences

## Communication Style
- When reporting plans to me, be extremely concise. Sacrifice grammar for the sake of concision.
- Always use British English instead of American English (e.g., "colour" not "color", "organised" not "organized").
