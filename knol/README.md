# Knol

`knol/`은 이 워크스페이스 전체에서 재사용하는 공유 지식 허브입니다.

이 폴더의 목적:
- lesson이나 runtime 문서가 반복해서 참조해야 하는 공식 매뉴얼을 한곳에 모읍니다.
- 원문을 그대로 복제하지 않고, 출처가 명확한 요약과 비교 메모로 정리합니다.
- 특정 lesson 전용 메모가 아니라 workspace 공용 기준으로 유지합니다.

운영 원칙:
- 1차 출처 우선: 공식 문서와 공식 안내자료를 먼저 연결합니다.
- 요약 우선: 저작권 이슈를 피하기 위해 전문 복제 대신 핵심 구조와 차이만 요약합니다.
- SoT 명시: 도메인별 정본 경로를 `DOCS_REGISTRY.md`에 기록합니다.
- 추적 가능성: 각 문서는 공식 URL과 마지막 검토 날짜를 남깁니다.

현재 공유 주제:
- [agent-skills](./agent-skills/README.md): Agent Skills 표준, Codex, Claude Code, Gemini CLI의 skill/subagent 구조 비교와 lesson 2용 합성 가이드

운영 파일:
- [DOCS_REGISTRY.md](./DOCS_REGISTRY.md)
- [DOCS_INVENTORY.md](./DOCS_INVENTORY.md)
