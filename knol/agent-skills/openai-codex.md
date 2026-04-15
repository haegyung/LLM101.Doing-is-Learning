# OpenAI Codex

last_reviewed: `2026-04-15`

primary sources:
- [Codex Skills](https://developers.openai.com/codex/skills)
- [Codex Subagents](https://developers.openai.com/codex/subagents)

## Official Minimum Structure

Codex 공식 문서는 skill을 `task-specific capability`와 `reusable workflow`를 담는 package로 설명한다.

공식 최소 구조:
- skill은 디렉터리다
- entrypoint는 `SKILL.md`다
- `SKILL.md`에는 `name`, `description`이 필요하다
- optional supporting files로 `scripts/`, `references/`, `assets/`를 둘 수 있다
- optional metadata로 `agents/openai.yaml`을 둘 수 있다

실무 해석:
- `SKILL.md`
  - 핵심 instructions와 trigger metadata
- `scripts/`
  - deterministic behavior나 외부 툴 호출이 필요할 때만
- `references/`
  - 긴 배경지식과 상세 문서
- `assets/`
  - 템플릿, 리소스
- `agents/openai.yaml`
  - app UI metadata, invocation policy, tool dependencies

## Official Invocation Contract

Codex는 progressive disclosure를 명시적으로 쓴다.

- 시작 시 metadata(`name`, `description`, file path, optional metadata)만 읽는다
- 실제로 skill을 쓰기로 결정했을 때만 `SKILL.md` 본문을 로드한다
- implicit invocation은 `description`에 의존한다

그래서 lesson 2에서는 `description = trigger contract`라고 가르쳐도 공식 문서와 어긋나지 않는다.

## What Codex Separates From A Skill

Codex는 subagent를 별도 문서에서 별도 구조로 설명한다.

공식 subagent 구조:
- `.codex/agents/*.toml`
- required fields:
  - `name`
  - `description`
  - `developer_instructions`

즉, Codex 공식 관점에서도 `skill`과 `subagent`는 같은 단어가 아니다.

프로젝트 해석:
- `skill`
  - agent가 특정 과업을 안정적으로 수행하게 만드는 reusable workflow package
- `subagent`
  - 별도 책임과 맥락을 가진 delegated execution unit

## What To Teach In Lesson 2

lesson 2에서는 Codex를 아래처럼 요약하면 정확하다.

- `skill`은 `SKILL.md` 중심의 reusable capability package다.
- `name`, `description`은 공식 최소 요구사항이다.
- supporting files는 optional이지만, 긴 내용을 분리하는 구조가 공식 권장과 맞다.
- subagent는 `.codex/agents/*.toml`로 정의되는 다른 실행 단위다.

## Prompt Design Reading

Codex 문서를 lesson 구조에 맞게 해석하면, skill 문서는 아래 순서로 읽는 것이 자연스럽다.
- 상황 정보
- 앞 선언적 지식: 역할, 목표, 입력, 제약
- 절차적 지식: 단계, 분기, 도구 사용
- 뒤 선언적 지식: 결과 형식, 검증 기준, 예시

이 펼침 구조는 Codex 공식 문서의 용어를 그대로 복제한 것은 아니고, skill 문서 구조를 가르치기 위한 이 워크스페이스의 teaching frame이다.
