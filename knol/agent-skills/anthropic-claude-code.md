# Anthropic Claude Code

last_reviewed: `2026-04-15`

primary sources:
- [Claude Code Skills](https://code.claude.com/docs/en/skills)
- [Claude Code Sub-agents](https://code.claude.com/docs/en/sub-agents)

## What Claude Says About Skills

Claude Code 공식 문서는 skills를 지원하며, skills 문서에서 Agent Skills open standard와의 연결을 직접 언급한다. 따라서 구조 설명 자체는 open standard와 상당히 잘 맞는다.

이 워크스페이스에서 중요한 해석:
- Claude도 skill을 reusable capability로 이해할 수 있다.
- skill 구조를 가르칠 때는 open standard 기준을 함께 제시해도 무리가 없다.

## What Claude Separates More Explicitly

Claude는 별도 문서에서 sub-agents를 specialized AI assistants로 분리해 설명한다. 이 지점은 lesson 2에서 반드시 분명히 적어야 한다.

정리:
- `skill`
  - Claude가 어떤 작업을 하도록 돕는 재사용 가능한 작업 지식
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
- 이름과 description
- 언제 쓰는지에 대한 trigger 설명
- 절차형 작업 지시
- 참고 자산과 제약
- 결과 품질을 닫는 기준
