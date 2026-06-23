# AgentGo Landing Page

> **AgentGo** — AI를 도입하는 것이 아니라, 안전하게 운영하는 것이 진짜 과제입니다

데모 신청 전환 중심의 AgentGo 엔터프라이즈 랜딩 페이지 및 인터랙티브 Agent 데모 페이지입니다.

🔗 **Live**: [https://dhlee1-netizen.github.io/AgentGo-landing/](https://dhlee1-netizen.github.io/AgentGo-landing/)
🎮 **Demo**: [https://dhlee1-netizen.github.io/AgentGo-landing/demo.html](https://dhlee1-netizen.github.io/AgentGo-landing/demo.html)

---

## 페이지 구성

### 1. 랜딩 페이지 (`docs/index.html`)

고객 가치 → 영상 → 문제 공감 → 체험 유도 → 차별점 → 제품 상세 순서의 CRO 최적화 구조입니다.

| 순서 | 섹션 | NAV 라벨 | 역할 |
|:---:|------|---------|------|
| 1 | **Hero** | — | 핵심 메시지 + 데모 신청 / 소개서 다운로드 |
| 2 | **Video** | — | 60초 티저 영상 — 제품 개념 즉시 전달 |
| 3 | **Problem** | — | Pain point 3가지 — 데이터 유출, 책임 공백, 관리 사각지대 |
| 4 | **Use Cases** | Use Cases | 결과 중심 시나리오 4개 + 직접 체험 CTA |
| 5 | **Value** | — | 도입 효과 4가지 + KPI 카드 (80% / 60% / 100%) |
| 6 | **Why AgentGo** | Why AgentGo? | Claude/Copilot vs AgentGo 비교 테이블 |
| 7 | **Core** | Platform Modules | 6대 모듈 — Platform, Guard, Management, Marketplace, Coder, Flow |
| 8 | **Editions** | Editions | 에디션 비교 — Chatbot / Standard / Enterprise |
| 9 | **Process** | Implementation | 3단계 도입 — 시나리오 검토 → PoC 검증 → 전사 확산 |
| 10 | **FAQ** | — | 도입 핵심 질문 5개 |
| 11 | **CTA** | — | 최종 전환 — 데모 신청 + 소개서 다운로드 |

**전환 최적화:**
- CTA 3곳 배치 (Hero, Why AgentGo, Final CTA)
- Primary: "데모 신청" / Secondary: "소개서 다운로드"
- Use Cases 하단: "직접 체험하기" (데모 페이지 연결)
- 데모 신청 모달 (48시간 이내 안내)
- 티저 영상 (15MB, Hero 직후 배치)
- 캔버스 네트워크 그래프 배경
- 반응형 (Desktop / Tablet / Mobile)

### 2. Agent 데모 페이지 (`docs/demo.html`)

4가지 Agent 시나리오를 인터랙티브 채팅 UI로 체험하는 페이지입니다.

| 시나리오 | 체험 내용 | 기대 효과 |
|---------|---------|----------|
| 업무 비서 Agent | 보고서 자동 생성, 메일 초안 (HITL), 결재 요청 | 시간 80% 절감 |
| 사내 지식 Agent | 연차 규정, 보안 정책, 제품 스펙 조회 | 검색 90% 절감 |
| 개발 Copilot | API 생성, 코드 보안 점검, 테스트 설계 | 생산성 40% 향상 |
| 운영 관제 Agent | 장애 원인 분석, 시스템 상태, 이상 탐지 | 분석 60% 단축 |

**주요 기능:**
- "2분 안에 체험하기" 전환 중심 웰컴 화면
- 분기형 대화 흐름 (퀵 액션 → 후속 시나리오)
- 자유 텍스트 입력 + 키워드 기반 자동 응답
- **파일 업로드** — 드래그 앤 드롭 / 클릭 선택
  - 업무 비서: TXT, CSV, MD, JSON (500KB)
  - 사내 지식: TXT, MD, CSV, JSON (500KB)
  - 개발 Copilot: PY, JS, TS, JAVA, GO (100KB)
  - 운영 관제: LOG, TXT, CSV, JSON (500KB)
  - 파일 내용 미리보기 + textarea 자동 채움 + 언어 자동 감지
- Human-in-the-Loop (메일 발송 전 Guard 검증 + 사용자 승인)

---

## 기술 스택

| 항목 | 스펙 |
|------|------|
| 프론트엔드 | HTML + CSS + Vanilla JS (단일 파일, 프레임워크 없음) |
| 폰트 | SUIT Variable (제목) + Pretendard (본문) — jsDelivr CDN |
| 영상 | MP4 15MB (ffmpeg CRF 28 압축) |
| 배포 | GitHub Pages (`/docs` 폴더) |
| 이미지 | 없음 — CSS, SVG, Canvas만 사용 |
| 접근성 | `prefers-reduced-motion`, TAB 이동, ARIA, 색상 대비 |

---

## 디자인 시스템

- **테마**: Anthropic Light Theme 기반
- **폰트**: SUIT Variable (제목, 700~800) + Pretendard (본문/CTA, 400~600)

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
├── .gitattributes
└── docs/
    ├── index.html                    # 메인 랜딩 페이지
    ├── demo.html                     # Agent 시나리오 체험 페이지
    ├── AgentGo_teaser_compressed.mp4 # 제품 티저 영상 (15MB)
    └── AgentGo_소개서.pdf             # 제품 소개서 (PDF)
```

---

## 배포

GitHub Pages — `main` 브랜치 `/docs` 폴더

Settings → Pages → Source: `main` / `/docs`

---

*ITCEN CLOIT AI BD팀 · 2026년 6월*
