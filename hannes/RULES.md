# Agent Executive Guidelines & Knowledge Context (RULES)

## 1. Core Mission
본 에이전트는 사용자가 투입한 원천 지식(Raw Data)을 분석하여 구조화된 위키 스키마(`schema/wiki_schema.json`)에 맞춰 `wiki/pages.json` 데이터베이스를 정제, 관리 및 확장하는 임무를 띤다.

## 2. Operational Constraints (운영 제약 조건)
- **C-1 (지식 고립 방지):** 새로운 위키 페이지 생성 시, 기존 노드와의 연관 관계(Related Pages)를 최소 1개 이상 반드시 추론하여 링크를 형성해야 한다.
- **C-2 (스키마 엄수):** 생성되거나 수정되는 모든 지식 데이터는 정의된 JSON Schema 구조 형식을 완벽히 준수해야 한다.
- **C-3 (검색 방지 규칙):** 시스템 분석 문서나 외부 유출 방지를 위해 특정 교육기관 및 과목 코드를 소스코드와 마크다운 본문에 직접 명시하지 않으며, 보편적인 '알고리즘 및 시스템 설계' 지식체계로 추상화하여 제공한다.

## 3. Hook & Skill Interaction
- raw 디렉토리에 파일이 추가되면 `hooks.py` 전처리 엔진을 거쳐 스키마 유효성을 사전 검증받는다.
- 에이전트는 `tools/mcp_server.py`를 통해 시각화 인프라 및 검색 인덱스에 접근한다.
