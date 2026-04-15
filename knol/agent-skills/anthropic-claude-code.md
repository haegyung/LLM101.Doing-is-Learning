# Anthropic Claude Code

last_reviewed: `2026-04-15`

primary sources:
- [Claude Code Skills](https://code.claude.com/docs/en/skills)
- [Claude Code Sub-agents](https://code.claude.com/docs/en/sub-agents)

## What Claude Says About Skills

Claude Code 공식 문서는 skills를 지원하며, skills 문서에서 Agent Skills open standard와의 연결을 직접 언급한다. 따라서 skill 구조 설명 자체는 open standard와 상당히 잘 맞는다.

## Official Skill Structure

공식 문서 기준 skill 구조:
- location:
  - `~/.claude/skills/<skill-name>/SKILL.md`
  - `.claude/skills/<skill-name>/SKILL.md`
  - plugin `skills/<skill-name>/SKILL.md`
- entrypoint:
  - `SKILL.md`
- format:
  - YAML frontmatter + Markdown body
- optional supporting files:
  - template 파일
  - example outputs
  - `scripts/`
  - reference docs

공식 frontmatter 읽기:
- `description`
  - 권장 필드
  - Claude가 skill을 언제 자동 호출할지 판단하는 기준
- `name`
  - slash command 이름
  - 생략 시 디렉터리명을 쓸 수 있다
- 추가 제어 필드
  - `when_to_use`
  - `disable-model-invocation`
  - `allowed-tools`
  - `context`
  - `agent`

즉, Claude도 skill을 reusable capability로 읽을 수 있지만, 공식 최소 요구사항은 `SKILL.md` 기반 instruction package라는 점을 먼저 잡아야 한다.

## What Claude Separates More Explicitly

Claude는 별도 문서에서 sub-agents를 `specialized AI assistants`로 분리해 설명한다.

공식 subagent 구조:
- `.claude/agents/*.md`
- YAML frontmatter + Markdown body
- Claude 문서는 이것을 custom system prompt, tool access, permission을 가진 별도 실행 단위로 설명한다

정리:
- `skill`
  - Claude가 어떤 작업을 하도록 돕는 reusable instruction package
- `subagent`
  - 별도 컨텍스트, 역할, 실행 단위를 가진 위임 객체

즉, Claude에서는 `skill = agent`라고 단정하기보다 `skill은 agent를 움직이게 하는 playbook`이라고 설명하는 편이 더 정확하다.

## Teaching Implication

lesson 2에서 Claude를 소개할 때는 아래 문장이 안전하다.

- 학생 이해를 위해 skill을 `agent capability`처럼 읽을 수 있다.
- 다만 Claude 공식 문서에서는 skill과 subagent를 분리한다.

이 한 줄을 넣으면 과장 없이 설명할 수 있다.

## Structure Reading

Claude 문서를 lesson 프레임으로 읽으면, 좋은 skill은 대체로 아래를 갖는다.
- `description`으로 닫히는 trigger 경계
- Markdown body의 절차형 작업 지시
- supporting files로 분리된 참고 자산
- frontmatter로 제어되는 invocation / tools / context
- 결과 품질을 닫는 template, checklist, guardrail
