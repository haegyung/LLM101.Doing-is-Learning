# OpenAI Codex

last_reviewed: `2026-04-15`

primary sources:
- [Codex Skills](https://developers.openai.com/codex/skills)
- [Codex Subagents](https://developers.openai.com/codex/subagents)

## What Codex Calls A Skill

Codex 공식 문서는 skill을 task-specific capability와 reusable workflow를 담는 저작 단위로 설명한다. 이 해석은 lesson 2에서 `skill을 agent capability처럼 읽는다`는 설명과 잘 맞는다.

실무적으로 읽으면 Codex skill은 아래를 함께 묶는다.
- 작업 목적과 트리거 설명
- 절차형 지시문
- 참고 자료
- 선택적 스크립트

## What Codex Separates From A Skill

Codex는 별도 문서에서 `subagent`를 specialized AI assistant로 구분한다. 즉, Codex 공식 관점에서도 `skill`과 `subagent`는 같은 단어가 아니다.

프로젝트 해석:
- `skill`
  - agent가 특정 과업을 안정적으로 수행하게 만드는 설계도
- `subagent`
  - 별도 책임과 맥락을 가진 delegated execution unit

## What To Teach In Lesson 2

lesson 2에서는 Codex를 아래처럼 요약하면 정확하다.

- `skill`은 재사용 가능한 작업 능력 단위다.
- `description` 경계가 좋아야 implicit invocation 품질이 올라간다.
- skill 안에는 instructions, resources, optional scripts가 함께 들어갈 수 있다.
- subagent는 skill과 다른 층위의 실행 단위다.

## Prompt Design Reading

Codex 문서를 lesson 구조에 맞게 해석하면, skill 문서는 아래 순서로 읽는 것이 자연스럽다.
- 앞 선언적 지식: 역할, 목표, 입력, 제약
- 절차적 지식: 단계, 분기, 도구 사용
- 뒤 선언적 지식: 결과 형식, 검증 기준, 예시

이 3단 구조는 Codex 공식 문서의 용어를 그대로 복제한 것은 아니고, skill 문서 구조를 가르치기 위한 이 워크스페이스의 합성 프레임이다.
