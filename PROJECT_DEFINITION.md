# PROJECT_DEFINITION

## 한 줄 정의

`LLM101.Learn-is-Doing`은 대학생이 실제 과제, 발표, 보고서, 학습 작업을 LLM으로 끝까지 진행해 보도록 돕는 lesson 단위 실습형 튜토리얼 코스이자 스타터팩이다.

## 프로젝트가 해결하려는 문제

- 많은 초보 사용자는 LLM을 "질문-답변 도구"로만 쓰고, 실제 과제 흐름으로 연결하지 못한다.
- 큰 프레임워크나 추상 이론부터 배우면 바로 실행 가능한 첫 성공 경험을 만들기 어렵다.
- Gemini, Codex, Claude Code 같은 환경이 달라도 공통 작업 흐름과 산출물 구조를 유지할 기준점이 필요하다.

## 대상 사용자

- 대학 과제나 발표 준비에 LLM을 처음 실전에 붙여보려는 학습자
- Gemini CLI로 시작하되, 이후 Codex나 Claude Code로 흐름을 옮겨보려는 사용자
- 완성형 자동화보다 "이번 주 실제 작업 1개"를 끝까지 굴려보는 경험이 먼저 필요한 사용자

## 핵심 접근 방식

### 1. Learn is Doing

- 이 프로젝트는 개념 설명보다 "작은 작업 하나를 실제로 끝까지 수행하는 경험"을 우선한다.
- lesson은 이론 강의가 아니라 실행 가능한 workflow 예시를 제공한다.

### 2. Lesson 단위 운영

- course root는 공통 안내와 구조를 담당한다.
- 실제 실행은 lesson 폴더 단위로 분리한다.
- 사용자는 course 전체가 아니라 필요한 lesson 하나만 자기 작업 폴더로 import해서 쓴다.

### 3. 작은 Skill + Command 중심

- Lesson 1은 `리서치 -> 정리 -> 분석 -> 글쓰기 -> 다듬기` 흐름을 한 번 돌려보게 한다.
- Lesson 2는 Lesson 1의 예제 Skill과 command를 자기 과제에 맞게 최소 수정해 보게 한다.
- 핵심은 새 구조를 과하게 늘리는 것이 아니라, 바로 실행 가능한 최소 버전을 남기는 것이다.

### 4. 산출물 기반 학습

- 각 lesson은 `outputs/`와 `notes/`를 기본 저장 위치로 둔다.
- 학습 결과는 대화가 아니라 파일 산출물로 남긴다.

## 현재 범위

- course 공통 안내 문서
- lesson 템플릿
- lesson 1: research-writing workflow
- lesson 2: remix workflow
- 합본 문서 생성 스크립트

## 범위 밖

- 특정 모델 하나에만 고정된 전용 프레임워크
- 정답 생성만을 목표로 하는 답안 생산기
- 모든 과제를 자동 채점하거나 자동 제출하는 시스템
- lesson 없이 course root 전체를 그대로 실행하는 방식

## 성공 조건

- 사용자가 lesson 폴더 하나를 import해서 예제 command 1개를 실행할 수 있다.
- 최소 1개의 작업 산출물을 `outputs/`에 남길 수 있다.
- 필요하면 같은 흐름을 자기 과제에 맞게 작은 수정으로 바꿀 수 있다.
- 필요하면 Gemini 기준 lesson 자산을 Codex 또는 Claude Code 구조로 옮길 수 있다.

## 현재 정본 기준

- course 공통 안내 SoT: `README.md`
- project definition SoT: `PROJECT_DEFINITION.md`
- lesson 템플릿 SoT: `LESSON_TEMPLATE.md`
- 합본 SoT: `COMBINED.md`
- lesson 실행 SoT: 각 lesson 폴더의 `README.md`
- runtime 규칙 SoT: 각 lesson 폴더의 `GEMINI.md`

## 근거 문서

- `README.md`
- `lessons/lesson-1-research-writing/README.md`
- `lessons/lesson-1-research-writing/GEMINI.md`
- `lessons/lesson-2-remix-skill-and-command/README.md`
- `lessons/lesson-2-remix-skill-and-command/GEMINI.md`
