# Skill-As-Agent Shared Guide

last_reviewed: `2026-04-15`

related documents:
- [official-source-map.md](./official-source-map.md)
- [agent-skills-open-standard.md](./agent-skills-open-standard.md)
- [openai-codex.md](./openai-codex.md)
- [anthropic-claude-code.md](./anthropic-claude-code.md)
- [google-gemini-cli.md](./google-gemini-cli.md)

## Scope

이 문서는 lesson 2와 course 문서에서 공통으로 재사용할 `skill을 agent처럼 이해하는 설명`의 정리본이다.

주의:
- 아래 내용 중 vendor별 사실은 공식 문서 요약이다.
- `선언적 -> 절차적 -> 선언적` 프롬프트 구조는 이 워크스페이스의 teaching frame이며, 특정 벤더가 같은 표현을 공식 용어로 쓰는 것은 아니다.

## Core Teaching Message

학생에게는 skill을 `재사용 가능한 마이크로 에이전트 역량`으로 가르친다.

이 표현이 유효한 이유:
- Agent Skills 표준은 skill을 capability package로 읽게 만든다.
- Gemini CLI는 skill을 self-contained expertise and workflow unit으로 설명한다.
- Codex는 skill을 reusable workflow, task-specific capability로 설명한다.
- Claude Code도 skill을 지원하지만, 공식 문서에서 subagent를 별도 실행 단위로 더 뚜렷하게 구분한다.

## Vendor Comparison

| runtime | skill reading | subagent relation | lesson note |
|---|---|---|---|
| Agent Skills | open standard capability package | runtime-specific | 벤더 중립 기준점 |
| Gemini CLI | self-contained skill unit | 별도 문서 축이 약함 | `skill as agent capability` 설명이 가장 직접적 |
| Codex | reusable workflow and capability | subagent를 별도 문서로 구분 | skill과 delegated execution을 나눠 설명 |
| Claude Code | reusable skill with standard alignment | subagent를 specialized AI assistant로 분리 | `skill = playbook`, `subagent = delegated unit`이 더 정확 |

## Skill Structure To Teach

이 프로젝트에서는 skill을 아래 8개 블록으로 설명한다.

1. `Identity`
2. `Trigger`
3. `Input Contract`
4. `Output Contract`
5. `Procedure`
6. `Resources`
7. `Guardrails`
8. `Verification`

이 구조는 open standard와 vendor 문서를 함께 읽어 추린 공용 teaching schema다.

## Prompt Structure To Teach

프롬프트는 기본적으로 아래 3층으로 가르친다.

1. 선언적 지식
2. 절차적 지식
3. 선언적 지식

프로젝트 해석:
- 앞 선언적 지식
  - 역할, 목표, 용어, 제약, 입력 범위
- 절차적 지식
  - 단계, 분기, 도구, 판단 규칙
- 뒤 선언적 지식
  - 산출물 계약, 루브릭, 예시, 금지 형식

짧게 요약하면:
- 앞 선언적 지식은 문제 공간을 고정한다.
- 절차적 지식은 행동 규칙을 고정한다.
- 뒤 선언적 지식은 결과 계약을 고정한다.

## Recommended Wording For Course Docs

수업 문서에서는 아래 문장을 재사용하면 된다.

`skill은 단순 프롬프트 조각이 아니라, 역할·트리거·절차·자원·출력 계약을 가진 재사용 가능한 마이크로 에이전트 역량이다. 다만 Claude Code처럼 공식적으로 skill과 subagent를 분리하는 환경에서는, skill을 agent를 움직이는 playbook으로 이해하는 편이 더 정확하다.`
