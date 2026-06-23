# AgentGo Landing Page

> **AgentGo** — AI를 안전하게 운영하는 엔터프라이즈 플랫폼

데모 신청 전환율 중심으로 설계된 AgentGo 제품 랜딩 페이지 및 인터랙티브 Agent 데모 페이지입니다.

🔗 **Live**: [https://dhlee1-netizen.github.io/AgentGo-landing/](https://dhlee1-netizen.github.io/AgentGo-landing/)

---

## 페이지 구성

### 1. 랜딩 페이지 (`docs/index.html`)

고객 가치 → 체험 → 차별점 → 제품 상세 순서로, 전환을 유도하는 CRO 최적화 구조입니다.

| 순서 | 섹션 | 역할 |
|:---:|------|------|
| 1 | **Hero** | 핵심 메시지 + KPI (80%/60%) + 30분 데모 요청 CTA |
| 2 | **Problem** | Pain point 3가지 — 데이터 유출, 책임 공백, 관리 사각지대 |
| 3 | **Use Cases** | 결과 중심 시나리오 4개 + 티저 영상 + 체험 CTA |
| 4 | **Value** | 도입 효과 4가지 + KPI 카드 (80% / 60% / 100%) |
| 5 | **Why AgentGo** | Claude/일반 LLM vs AgentGo 비교 테이블 |
| 6 | **Core** | 6대 모듈 — Platform, Guard, Management, Marketplace, Coder, Flow |
| 7 | **Editions** | 에디션 비교 — Chatbot / Standard / Enterprise |
| 8 | **Process** | 3단계 도입 — 시나리오 검토 → PoC 검증 → 전사 확산 |
| 9 | **FAQ** | 도입 핵심 질문 5개 (업무 적용, Claude 차이, 연동, 보안, ROI) |
| 10 | **CTA** | 최종 전환 — 30분 데모 요청 + 직접 체험하기 |

**전환 최적화 요소:**
- CTA 6곳 배치 (Hero, Use Cases, Why AgentGo, Final CTA)
- Primary: "30분 데모 요청" / Secondary: "직접 체험하기"
- 소개서 다운로드는 텍스트 링크로 축소 (전환 집중)
- 데모 신청 모달 (48시간 이내 안내 신뢰 요소)
- 티저 영상 삽입 (Use Cases 하단)
- 캔버스 네트워크 그래프 배경 애니메이션
- 반응형 대응 (Desktop / Tablet / Mobile)

### 2. Agent 데모 페이지 (`docs/demo.html`)

4가지 Agent 시나리오를 인터랙티브 채팅 UI로 체험할 수 있는 페이지입니다.

| 시나리오 | 체험 내용 | 기대 효과 |
|---------|---------|----------|
| 업무 비서 Agent | 보고서 자동 생성, 메일 초안 (Human-in-the-Loop), 결재 요청 | 시간 80% 절감 |
| 사내 지식 Agent | 연차 규정, 보안 정책, 제품 스펙 조회 | 검색 시간 90% 절감 |
| 개발 Copilot | API 생성, 코드 보안 점검, 테스트 설계 | 생산성 40% 향상 |
| 운영 관제 Agent | 장애 원인 분석, 시스템 상태, 이상 탐지 | 분석 60% 단축 |

**주요 기능:**
- "2분 안에 체험하기" 전환 중심 웰컴 화면
- 분기형 대화 흐름 (퀵 액션 → 후속 시나리오)
- 자유 텍스트 입력 + 키워드 기반 자동 응답
- "내 업무로 테스트하기" 데이터 입력 폼 (시나리오별 크기/유형 제한)
- Human-in-the-Loop (메일 발송 전 Guard 검증 + 사용자 승인)

---

## 기술 스택

| 항목 | 스펙 |
|------|------|
| 프론트엔드 | HTML + CSS + Vanilla JS (단일 파일, 프레임워크 없음) |
| 외부 의존성 | Google Fonts CDN만 사용 |
| 영상 | Git LFS (150MB MP4) |
| 배포 | GitHub Pages (`/docs` 폴더) |
| 이미지 | 없음 — CSS, SVG, Canvas만 사용 |
| 접근성 | `prefers-reduced-motion`, TAB 이동, ARIA, 색상 대비 고려 |

---

## 디자인 시스템

- **테마**: Anthropic Light Theme 기반
- **폰트**: Plus Jakarta Sans (제목) + Noto Sans KR (본문)

### 컬러

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
├── .gitattributes        # Git LFS 설정 (MP4)
└── docs/
    ├── index.html         # 메인 랜딩 페이지
    ├── demo.html          # Agent 시나리오 체험 페이지
    ├── AgentGo_소개서.pdf  # 제품 소개서 (다운로드)
    └── AgentGo_티저.mp4   # 제품 티저 영상 (LFS)
```

---

## 배포

GitHub Pages — `main` 브랜치 `/docs` 폴더

Settings → Pages → Source: `main` / `/docs`

---

*ITCEN CLOIT AI BD팀 · 2026년 6월*
