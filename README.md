# AgentGo Landing Page

> **AgentGo** — AI 도입을 넘어, 기업 AI 운영 체계를 구축하는 플랫폼

엔터프라이즈 대상 AgentGo 제품 소개 랜딩 페이지 및 인터랙티브 Agent 데모 페이지입니다.

🔗 **Live**: [https://dhlee1-netizen.github.io/AgentGo-landing/](https://dhlee1-netizen.github.io/AgentGo-landing/)

---

## 페이지 구성

### 1. 랜딩 페이지 (`docs/index.html`)

비즈니스 가치를 먼저 보여주고, 이후 플랫폼 구성을 설명하는 전환 중심 구조입니다.

| 순서 | 섹션 | 역할 |
|:---:|------|------|
| 1 | **Hero** | 핵심 메시지 + 데모 신청 / 소개서 다운로드 CTA |
| 2 | **Problem** | 고객 Pain point 3가지 — 데이터 유출, 책임 공백, 관리 사각지대 |
| 3 | **Value** | AgentGo의 차별 가치 4가지 — 전 주기 관리, 멀티 에이전트, 유연한 배포, 거버넌스 |
| 4 | **Use Cases** | 대표 업무 시나리오 4개 + Agent 체험 링크 |
| 5 | **Core** | 6대 모듈 상세 — Platform, Guard, Management, Marketplace, Coder, Flow |
| 6 | **Editions** | 에디션 비교 — Chatbot / Standard / Enterprise |
| 7 | **Process** | 3단계 도입 프로세스 — 시나리오 검토 → PoC 검증 → 전사 확산 |
| 8 | **FAQ** | 도입 전 핵심 질문 5개 |
| 9 | **CTA** | 최종 전환 — 데모 신청 + 소개서 다운로드 |

**주요 기능:**
- 데모 신청 모달 폼 (회사명, 담당자명, 이메일, 연락처, 관심 에디션)
- 소개서 PDF 다운로드
- 캔버스 네트워크 그래프 배경 애니메이션
- 반응형 대응 (Desktop / Tablet / Mobile)

### 2. Agent 데모 페이지 (`docs/demo.html`)

4가지 Agent 시나리오를 인터랙티브 채팅 UI로 체험할 수 있는 페이지입니다.

| 시나리오 | 체험 내용 | 연결 모듈 |
|---------|---------|----------|
| 업무 자동화 | 보고서 자동 생성, 메일 초안 (Human-in-the-Loop), 결재 요청 | Flow + Marketplace |
| 지식 검색 | 연차 규정, 보안 정책, 제품 스펙 조회 | Platform + Management |
| 개발 지원 | API 생성, 코드 보안 점검, 테스트 설계 | Coder + Guard |
| 운영 분석 | 장애 원인 분석, 시스템 상태, 이상 탐지 | Management + Guard |

**주요 기능:**
- 분기형 대화 흐름 (퀵 액션 버튼 → 후속 시나리오)
- 자유 텍스트 입력 + 키워드 기반 자동 응답
- 사용자 데이터 입력 폼 (시나리오별 크기/유형 제한)
- Human-in-the-Loop (메일 발송 전 Guard 검증 + 사용자 승인)
- 타이핑 인디케이터, 테이블/코드 블록 렌더링

---

## 기술 스택

| 항목 | 스펙 |
|------|------|
| 프론트엔드 | HTML + CSS + Vanilla JS (단일 파일, 외부 프레임워크 없음) |
| 외부 의존성 | Google Fonts CDN만 사용 |
| 배포 | GitHub Pages (`/docs` 폴더) |
| 이미지 | 없음 — CSS, SVG, Canvas만 사용 |
| 접근성 | `prefers-reduced-motion` 대응, TAB 이동, ARIA 속성, 색상 대비 고려 |

---

## 디자인 시스템

- **테마**: Anthropic Light Theme 기반
- **폰트**: Plus Jakarta Sans (제목, 800) + Noto Sans KR (본문, 400/500/700)

### 컬러 시스템

| 역할 | 이름 | HEX |
|------|------|-----|
| Primary | Brand Blue | `#1A56C8` |
| Dark BG | Deep Navy | `#0A1628` |
| Light BG | Ice Blue | `#E8F0FB` |
| Sub text | Slate | `#64748B` |
| Success | Trust Green | `#059669` |
| Warning | Alert Amber | `#D97706` |

---

## 로컬 실행

```bash
npx http-server docs -p 3000 -c-1
```

- 랜딩 페이지: http://localhost:3000
- 데모 페이지: http://localhost:3000/demo.html

---

## 파일 구조

```
├── README.md
├── .gitignore
└── docs/
    ├── index.html          # 메인 랜딩 페이지 (HTML+CSS+JS 인라인)
    ├── demo.html           # Agent 시나리오 체험 페이지
    └── AgentGo_소개서.pdf   # 제품 소개서 다운로드 파일
```

---

## 배포

GitHub Pages에서 `main` 브랜치의 `/docs` 폴더를 소스로 설정하여 자동 배포됩니다.

Settings → Pages → Source: `main` / `/docs`

---

*ITCEN CLOIT AI BD팀 · 2026년 6월*
