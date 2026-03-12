# WDS-SKILLS

Wanted Design System용 Claude Code 커스텀 스킬 모음입니다.

## 사용 방법

### 1. 프로젝트에 스킬 복사

프로젝트 루트의 `.claude/skills/` 디렉토리에 원하는 스킬 폴더를 복사합니다.

```bash
cp -r .claude/skills/wds-review <your-project>/.claude/skills/
```

### 2. Claude Code에서 사용

```
/wds-review
```

## 포함된 스킬

| 스킬 | 설명 |
|------|------|
| `wds-review` | WDS 디자인 컴플라이언스 감사 및 점수 산출 |

## 요구 사항

- [Claude Code](https://claude.com/claude-code) CLI
- Wanted Design System MCP 패키지 (컴포넌트/토큰 검증용)
