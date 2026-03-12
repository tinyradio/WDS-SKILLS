# WDS-SKILLS

Wanted Design System(WDS)용 Claude Code 커스텀 스킬 모음입니다.
디자인 리뷰를 자동화하고, WDS 준수 여부를 검사할 수 있습니다.

---

## 포함된 스킬

| 스킬 | 설명 |
|------|------|
| `/wds-review` | UI 디자인이 WDS를 올바르게 적용했는지 감사하고, 컴플라이언스 점수를 산출합니다 |

---

## 설치 가이드

### 사전 준비

아래 두 가지가 먼저 설치되어 있어야 합니다.

| 필요한 것 | 설명 | 설치 방법 |
|-----------|------|-----------|
| **Claude Code** | AI 코딩 어시스턴트 CLI | [공식 사이트](https://claude.ai/download) 에서 설치 |
| **Git** | 코드 버전 관리 도구 | Mac: 터미널에서 `git --version` 입력 시 자동 설치 안내 |

> 잘 모르겠다면, 터미널(맥의 경우 `터미널` 앱)을 열고 아래 명령어를 입력해보세요.
> ```
> claude --version
> git --version
> ```
> 둘 다 버전 번호가 출력되면 준비 완료입니다.

---

### Step 1. 이 저장소 다운로드하기

터미널을 열고, 원하는 폴더로 이동한 뒤 아래 명령어를 입력합니다.

```bash
git clone https://github.com/tinyradio/WDS-SKILLS.git
```

그러면 현재 위치에 `WDS-SKILLS` 폴더가 생성됩니다.

---

### Step 2. 스킬을 내 프로젝트에 복사하기

WDS-SKILLS의 스킬 파일을 **내가 작업하는 프로젝트**에 복사해야 합니다.

#### Mac / Linux

```bash
cp -r WDS-SKILLS/.claude/skills/wds-review 내프로젝트경로/.claude/skills/
```

#### 예시

만약 내 프로젝트가 `~/Desktop/my-project` 에 있다면:

```bash
# 1. .claude/skills 폴더가 없으면 먼저 생성
mkdir -p ~/Desktop/my-project/.claude/skills

# 2. 스킬 복사
cp -r WDS-SKILLS/.claude/skills/wds-review ~/Desktop/my-project/.claude/skills/
```

#### 복사 후 프로젝트 구조 확인

```
내프로젝트/
├── .claude/
│   └── skills/
│       └── wds-review/
│           └── SKILL.md    <-- 이 파일이 있으면 성공!
├── src/
├── package.json
└── ...
```

> **Finder에서 `.claude` 폴더가 안 보이나요?**
> `.`으로 시작하는 폴더는 숨김 폴더입니다.
> Finder에서 `Cmd + Shift + .` 을 누르면 숨김 파일이 보입니다.

---

### Step 3. WDS 디자인 시스템 MCP 플러그인 설치하기 (필수)

> **이 단계를 건너뛰면 `/wds-review` 스킬이 제대로 동작하지 않습니다.**
>
> `/wds-review` 스킬은 WDS의 컴포넌트, 토큰, 패턴 정보를 **MCP 서버에서 실시간으로 조회**하며 리뷰합니다.
> MCP가 설치되어 있지 않으면 리뷰의 정확도가 크게 떨어지거나, 검증 자체가 불가능합니다.

WDS MCP 플러그인 설치를 원하시면 **원티드 디자인 시스템 TF**에 문의해주세요.

> **설치 확인 방법:** Claude Code에서 `"WDS 컴포넌트 목록 보여줘"` 라고 입력했을 때 컴포넌트 리스트가 나오면 정상 설치된 것입니다.

---

### Step 4. Claude Code에서 사용하기

1. 터미널에서 내 프로젝트 폴더로 이동합니다.

```bash
cd ~/Desktop/my-project
```

2. Claude Code를 실행합니다.

```bash
claude
```

3. Claude Code 안에서 아래처럼 슬래시 명령어를 입력합니다.

```
/wds-review
```

4. 리뷰할 디자인 파일이나 URL을 함께 전달합니다.

```
/wds-review 이 Figma 디자인을 WDS 기준으로 리뷰해줘: [Figma URL]
```

---

## 사용 예시

### Figma 디자인 리뷰

```
/wds-review https://figma.com/design/xxxxx 이 화면을 WDS 기준으로 검사해줘
```

### 코드 기반 UI 리뷰

```
/wds-review src/pages/LoginPage.tsx 이 페이지가 WDS를 잘 따르고 있는지 확인해줘
```

### 리뷰 결과 예시

스킬을 실행하면 아래와 같은 형식의 리포트를 받게 됩니다:

```
WDS Compliance Score

Component Usage:    92
Token Usage:        88
Pattern Consistency: 90
Visual Quality:     85
Interaction Quality: 87

Total Score: 88 (Good but improvements possible)
```

---

## 스킬 업데이트하기

스킬이 업데이트되면, 아래 명령어로 최신 버전을 받을 수 있습니다.

```bash
# 1. WDS-SKILLS 폴더로 이동
cd WDS-SKILLS

# 2. 최신 버전 다운로드
git pull

# 3. 내 프로젝트에 다시 복사
cp -r .claude/skills/wds-review 내프로젝트경로/.claude/skills/
```

---

## 자주 묻는 질문 (FAQ)

### Q. `/wds-review` 를 입력했는데 아무 반응이 없어요

- `.claude/skills/wds-review/SKILL.md` 파일이 프로젝트 안에 있는지 확인해주세요.
- Claude Code를 프로젝트 폴더 안에서 실행했는지 확인해주세요.

### Q. 리뷰 결과가 부정확하거나 컴포넌트 정보가 나오지 않아요

- **WDS MCP 플러그인이 설치되지 않았을 가능성이 높습니다.** Step 3을 반드시 먼저 완료해주세요.
- Claude Code에서 `"WDS 컴포넌트 목록 보여줘"` 라고 입력해서 MCP가 정상 동작하는지 확인해보세요.

### Q. 디자이너인데 터미널을 처음 써봐요

1. Mac에서 `Cmd + Space` → "터미널" 검색 → 실행
2. 위의 Step 1~3을 순서대로 따라하시면 됩니다.
3. 명령어를 복사(`Cmd + C`)해서 터미널에 붙여넣기(`Cmd + V`) 하면 편합니다.

### Q. Windows에서도 사용할 수 있나요?

네, 가능합니다. 명령어가 약간 다릅니다:

```powershell
# PowerShell에서
git clone https://github.com/tinyradio/WDS-SKILLS.git
xcopy /E /I WDS-SKILLS\.claude\skills\wds-review 내프로젝트경로\.claude\skills\wds-review
```

---

## 문의

스킬 사용 중 문제가 있거나 개선 제안이 있다면 [Issues](https://github.com/tinyradio/WDS-SKILLS/issues)에 남겨주세요.
