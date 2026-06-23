# AgentGo Landing Page

> **AgentGo** — 기업의 AI 에이전트를 개발·운영·통제하는 통합 플랫폼

엔터프라이즈 대상 AgentGo 제품 소개 랜딩 페이지 및 인터랙티브 Agent 데모 페이지입니다.

🔗 **Live**: [https://dhlee1-netizen.github.io/AgentGo-landing/](https://dhlee1-netizen.github.io/AgentGo-landing/)

---

## 페이지 구성

### 1. 랜딩 페이지 (`docs/index.html`)

12개 섹션으로 구성된 풀스크롤 제품 소개 페이지입니다.

| 섹션 | 내용 |
|------|------|
| NAV | 고정 상단, 앵커 링크 + 데모 신청 CTA |
| Hero | 캔버스 네트워크 그래프 배경, 핵심 메시지, CTA |
| Problem | 고객 Pain point 3가지 (데이터 유출, 책임 공백, 관리 사각지대) |
| Core Structure | AgentGo 6대 모듈 (Platform, Guard, Management, Marketplace, Coder, Flow) |
| Value | 차별 가치 시각 카드 4개 |
| Use Cases | 대표 업무 시나리오 4개 + 데모 체험 링크 |
| Editions | 에디션 비교 (Chatbot / Standard / Enterprise) |
| Persona | 의사결정자 유형별 탭 전환 (CIO, 현업 팀장, IT 담당자, CFO) |
| Process | 3단계 도입 프로세스 타임라인 |
| FAQ | 아코디언 5개 (도입 불안 해소) |
| CTA | 최종 전환 (데모 신청 + 소개서 다운로드) |
| Footer | 브랜드 마무리 |

**주요 기능:**
- 데모 신청 모달 폼 (회사명, 담당자명, 이메일, 연락처, 관심 에디션)
- 소개서 PDF 다운로드
- 반응형 대응 (Desktop / Tablet / Mobile)

### 2. Agent 데모 페이지 (`docs/demo.html`)

4가지 Agent 시나리오를 인터랙티브 채팅 UI로 체험할 수 있는 페이지입니다.

| 시나리오 | 체험 내용 | 연결 모듈 |
|---------|---------|----------|
| 업무 자동화 | 보고서 자동 생성, 메일 초안, 결재 요청 | Flow + Marketplace |
| 지식 검색 | 연차 규정, 보안 정책, 제품 스펙 조회 | Platform + Management |
| 개발 지원 | API 생성, 코드 보안 점검, 테스트 설계 | Coder + Guard |
| 운영 분석 | 장애 원인 분석, 시스템 상태, 이상 탐지 | Management + Guard |

**주요 기능:**
- 분기형 대화 흐름 (퀵 액션 버튼 → 심화 체험)
- 자유 텍스트 입력 + 키워드 기반 응답
- 사용자 데이터 입력 폼 (시나리오별 크기/유형 제한)
- Human-in-the-Loop (메일 발송 전 승인 단계)
- 타이핑 인디케이터, 테이블/코드 블록 렌더링

---

## 기술 스택

| 항목 | 스펙 |
|------|------|
| 프론트엔드 | HTML + CSS + Vanilla JS (단일 파일) |
| 외부 의존성 | Google Fonts CDN (Plus Jakarta Sans, Noto Sans KR) |
| 배포 | GitHub Pages (`/docs` 폴더) |
| 이미지 | 없음 (CSS, SVG, Canvas만 사용) |

---

## 디자인 시스템

- **스타일**: Anthropic Light Theme 기반
- **폰트**: Plus Jakarta Sans (제목) + Noto Sans KR (본문)
- **컬러**:
  - Brand Blue `#1A56C8` — 로고, CTA, 헤드라인
  - Deep Navy `#0A1628` — 다크 배경, Footer
  - Ice Blue `#E8F0FB` — 배경 강조, 카드
  - Slate `#64748B` — 서브텍스트
  - Trust Green `#059669` — 긍정/성공
  - Alert Amber `#D97706` — 경고/주의

---

## 로컬 실행

```bash
# http-server로 실행
npx http-server docs -p 3000 -c-1

# 브라우저에서 확인
# 랜딩 페이지: http://localhost:3000
# 데모 페이지:  http://localhost:3000/demo.html
```

---

## 파일 구조

```
docs/
├── index.html          # 메인 랜딩 페이지 (HTML+CSS+JS 인라인)
├── demo.html           # Agent 시나리오 체험 페이지
└── AgentGo_소개서.pdf   # 제품 소개서 다운로드 파일
```

---

## 배포

GitHub Pages에서 `main` 브랜치의 `/docs` 폴더를 소스로 설정하여 자동 배포됩니다.

---

*ITCEN CLOIT AI BD팀 · 2026년 6월*
