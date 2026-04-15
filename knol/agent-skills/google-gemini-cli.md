# Google Gemini CLI

last_reviewed: `2026-04-15`

primary sources:
- [Gemini CLI Skills](https://geminicli.com/docs/cli/skills/)
- [Creating Skills](https://geminicli.com/docs/cli/creating-skills/)

## What Gemini Calls A Skill

Gemini CLI 공식 문서는 skill을 specialized expertise, procedural workflow, task-specific resources를 담는 self-contained unit으로 설명한다. lesson 2에서 `skill을 재사용 가능한 agent capability`로 읽는 데 가장 직접적으로 잘 맞는 문서다.

## Minimum Authoring Contract

공식 작성 문서 기준으로 skill의 최소 시작점은 `SKILL.md`다.

공식 최소 구조:
- skill은 디렉터리다
- `SKILL.md`는 required file 이다
- 권장 supporting directories:
  - `scripts/`
  - `references/`
  - `assets/`

공식 `SKILL.md` 요구사항:
- YAML frontmatter + Markdown body
- `name`
  - unique identifier
  - 디렉터리명과 맞아야 한다
- `description`
  - skill이 무엇을 하며 언제 써야 하는지 설명한다
- body
  - skill이 활성화되었을 때 agent를 안내하는 instructions

## Activation Reading

Gemini CLI는 skill activation 전에 description 기반 매칭과 호출 흐름을 가진다. 그래서 이 프로젝트에서는 `description`을 단순 소개문이 아니라 `언제 이 skill을 켜야 하는가`를 말해 주는 trigger contract로 가르친다.

## Teaching Implication

Gemini는 lesson 2의 핵심 메시지를 가장 단순하게 설명할 수 있는 사례다.

- skill은 작은 실행 단위다.
- 공식 최소 구조는 `SKILL.md + name + description`이다.
- procedural workflow를 포함해야 한다.
- references와 resources는 본문을 짧게 유지하면서 성능을 높인다.
- `SKILL.md`는 선언적 지식과 절차적 지식이 만나는 중심점이다.
