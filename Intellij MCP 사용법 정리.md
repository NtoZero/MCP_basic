# IntelliJ와 Model Context Protocol(MCP) 연동 가이드

AI 기반의 코드 지원을 IntelliJ에서 활용을 위한 MCP 연동 필요. 아래 절차를 순서대로 진행.

## 1. IntelliJ용 MCP Server 플러그인 설치

1. IntelliJ 실행
2. 상단 메뉴에서 `Settings > Plugins > Marketplace`로 이동
3. 검색창에 `MCP Server` 입력 후 설치
4. 설치 완료 후 **IntelliJ 재시작**

## 2. MCP Proxy 설정 정보 복사

아래 JSON 설정 복사:

```json
{ "mcpServers": { "jetbrains": { "command": "npx", "args": ["-y", "@jetbrains/mcp-proxy"] } } }
```

## 3. Claude Desktop 설정 파일 수정

1. **Claude Desktop 애플리케이션** 실행
2. 상단 메뉴에서 `Settings > Developer > Edit Settings` 선택하여 설정 파일 열기
3. 열린 설정 파일에 **2단계에서 복사한 MCP Proxy JSON** 추가
4. 설정 파일 **저장**

## 4. IntelliJ와 Claude Desktop 재시작

변경 사항 적용을 위한 재시작 항목:
* **IntelliJ**
* **Claude Desktop**

## 5. 연동 확인

Claude에서 다음 명령 입력하여 연동 상태 확인:

```
check out my project in the ide and give me all the supported apis of the project
```