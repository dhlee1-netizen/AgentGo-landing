# AgentGo 랜딩 페이지 기획서 v2.1
**목적**: 외부 고객·파트너 대상 브랜딩 랜딩 페이지 코드 제작 기준서
**형태**: 1페이지 풀스크롤 랜딩 페이지
**작성일**: 2026년 6월
**수정 방향**: 제품 설명 중심 → 시각적 이해·전환 중심 랜딩 페이지로 개선

---

## 1. 페이지 개요

| 항목 | 내용 |
|------|------|
| URL 용도 | AgentGo 공식 제품 소개 랜딩 페이지 |
| 타깃 방문자 | 엔터프라이즈 CIO·CDO·현업 팀장·IT 담당자, 파트너사 |
| 핵심 전환 목표 | 데모 신청 버튼 클릭 (Primary CTA) |
| 보조 전환 목표 | 소개서 다운로드 (Secondary CTA) |
| 언어 | 한국어 (ko) |

---

## 2. 디자인 시스템

### 컬러
```
--color-navy:    #0A1628   /* 배경 (다크) */
--color-blue:    #1A56C8   /* 브랜드 Primary */
--color-blue2:   #2563EB   /* 호버 상태 */
--color-ice:     #E8F0FB   /* 배경 강조 (라이트) */
--color-slate:   #64748B   /* 서브텍스트 */
--color-white:   #FFFFFF
--color-green:   #059669   /* 긍정·성공 */
--color-amber:   #D97706   /* 경고·강조 */
--color-glass:   rgba(255,255,255,0.04)
--color-glassborder: rgba(255,255,255,0.08)
```

### 타이포그래피
```
Display (Hero H1)   : Inter Black, 72px, weight 900, letter-spacing -2px
Section H2          : Inter Bold, 48px, weight 800, letter-spacing -1.5px
Card Title          : Inter SemiBold, 20px, weight 700
Body                : DM Sans Regular, 16px, weight 400, line-height 1.7
Caption / Label     : DM Sans Medium, 13px, weight 500, letter-spacing 0.08em
Nav / Button        : DM Sans SemiBold, 14–16px, weight 600
구글 폰트 import   : Inter (300,400,500,600,700,800,900) + DM Sans (300,400,500,600)
```

### 공통 컴포넌트
```
border-radius 카드  : 16px
border-radius 버튼  : 10px
border-radius 태그  : 100px (pill)
box-shadow CTA버튼  : 0 8px 32px rgba(26,86,200,0.5) on hover
transition 기본     : all 0.2s ease
transform hover     : translateY(-2px)
```

---

## 3. 섹션 구성 (위→아래 순서)

### 섹션 0 — NAV (고정 상단)
- **역할**: 브랜드 인식 + 섹션 앵커 이동 + 최상위 CTA
- **높이**: 64px, `position: fixed`, `backdrop-filter: blur(12px)`
- **배경**: `rgba(10,22,40,0.85)` + 하단 border `1px solid glassborder`
- **구성 요소**:
  - 좌측: 로고 아이콘(오각형 그라디언트) + "AgentGo" 텍스트
  - 중앙: 앵커 링크 5개 — `왜 AgentGo인가` `핵심 구성` `활용 사례` `에디션` `도입 프로세스`
  - 우측: `데모 신청` 버튼 (Primary, --color-blue)
- **스크롤 동작**: 스크롤 시 배경 blur 강화 (JS: scroll 이벤트)

---

### 섹션 1 — HERO
- **역할**: 브랜드 첫인상 + 핵심 메시지 전달 + Primary CTA
- **높이**: `min-height: 100vh`
- **배경**: `--color-navy`, 캔버스 애니메이션 (멀티 에이전트 네트워크 그래프)
- **캔버스 스펙**:
  - 노드 28개, 연결 거리 임계값 180px
  - 허브 노드 5개 (크기·글로우 강조)
  - 노드 색상: `#1A56C8` `#2563EB` `#3B82F6` `#60A5FA` `#93C5FD`
  - 노드 이동 속도: ±0.35px/frame
  - `requestAnimationFrame` 루프, 리사이즈 대응
- **콘텐츠 (중앙 정렬)**:
  ```
  [배지] ● 엔터프라이즈 Agentic AI 플랫폼
  [eyebrow] AgentGo by ITCEN CLOIT
  [H1] 기업의 AI 에이전트를
       개발·운영·통제하는 통합 플랫폼      ← "개발·운영·통제" = 그라디언트 텍스트
  [sub] 보안·거버넌스·운영 체계를 갖춘 엔터프라이즈 Agentic AI 플랫폼.
        개발부터 배포·운영까지 하나의 환경에서 관리합니다.
  [버튼 2개] [데모 신청하기 →] [소개서 다운로드]
  ```
- **배지 스타일**: pill, `background: rgba(26,86,200,0.15)`, border `rgba(26,86,200,0.4)`, 색상 `#93C5FD`
- **그라디언트 텍스트**: `linear-gradient(90deg, #60A5FA, #93C5FD, #1A56C8)` + `background-clip: text`
- **하단 스크롤 인디케이터**: 세로선 + "scroll" 텍스트, bounce 애니메이션

---

### 섹션 2 — PROBLEM (문제 제기)
- **역할**: 고객 Pain point 공감 유도
- **배경**: `#060E1A` (네이비보다 약간 더 어두운 배경으로 섹션 구분)
- **padding**: `96px 24px`
- **구성**:
  ```
  [label] 문제 인식
  [H2] AI가 확산될수록
       운영은 복잡해집니다
  [desc] 승인 없이 사용되는 Shadow AI, 책임자 없는 AI 오류,
         파악 불가능한 데이터 흐름. 이것이 오늘날 엔터프라이즈가 마주한 현실입니다.
  [카드 3개 — grid, 1fr 1fr 1fr]
  ```
- **카드 3개 콘텐츠**:
  | # | 아이콘 | 제목 | 설명 |
  |---|--------|------|------|
  | 1 | 🔒 | 데이터 유출 | 직원이 사내 기밀을 외부 AI에 업로드합니다. 어디에, 얼마나 많이 나갔는지 아무도 모릅니다. |
  | 2 | ⚠️ | 책임 공백 | AI가 낸 오류의 책임 소재가 불명확합니다. 감사 시 추적할 로그조차 존재하지 않습니다. |
  | 3 | 🗺️ | 관리 사각지대 | 부서마다 다른 AI 도구. IT팀은 현황을 파악할 수 없고, 비용과 보안 정책에 공백이 생깁니다. |
- **카드 스타일**: `background: glass`, border `glassborder`, border-radius 16px, hover시 border `rgba(26,86,200,0.4)` + `translateY(-4px)`
- **스크롤 페이드인**: `IntersectionObserver`, opacity 0→1, translateY 24px→0, 0.55s ease

---

### 섹션 3 — CORE STRUCTURE (AgentGo 핵심 구성요소)
- **역할**: 제품 핵심 기능 소개
- **배경**: `--color-navy`
- **padding**: `96px 24px`
- **구성**:
  ```
  [2단 헤더]
  좌: [label] AgentGo 핵심 구성요소
      [H2] AI 개발부터 운영·거버넌스까지
           하나의 플랫폼에서
  우: [desc] AI 에이전트의 전체 라이프사이클을
             단일 플랫폼에서 관리합니다.

  [핵심 구성요소 그리드 — 3×2]
  ```
- **핵심 구성요소 그리드 스타일**: `display: grid`, `grid-template-columns: repeat(3, 1fr)`, `gap: 2px`, border-radius 20px, overflow hidden, border `1px solid glassborder`
- **핵심 구성요소 6개 콘텐츠**:
  | 태그 | 이름 | 설명 | 키워드 pill |
  |------|------|------|-------------|
  | 인프라 | Platform | 온프레미스부터 퍼블릭 클라우드, 완전 폐쇄망까지. 벤더 Lock-in 없이 어디서든 실행됩니다. | K8s 오토스케일링 |
  | 보안 | Guard | 사내 업무 규정을 자동 반영해 AI의 권한과 접근 범위를 관리하고, 전체 감사 로그를 기록합니다. | 암호화 + 가드레일 |
  | 운영 | Management | AI 에이전트의 상태, 사용량, 비용을 실시간 대시보드로 한눈에 파악합니다. | 실시간 모니터링 |
  | 마켓플레이스 | Marketplace | 검증된 AI 에이전트를 즉시 배포합니다. 개발 리소스 없이도 업무 자동화를 시작할 수 있습니다. | 즉시 배포 |
  | 개발 | Coder | MCP 표준 프로토콜 기반의 AI 에이전트 개발 도구. 파편화된 AI 시스템을 하나로 통합합니다. | MCP 표준 |
  | 자동화 | Flow | 업무 자동화 워크플로를 시각적으로 설계하고 실행합니다. 대화 한 마디로 복잡한 업무가 시작됩니다. | 노코드 워크플로 |
- **셀 배경**: `#0D1E38`, hover `#122040`
- **pill 스타일**: `background: rgba(26,86,200,0.15)`, color `#93C5FD`, font-size 11px

---

### 섹션 4 — VALUE (왜 AgentGo인가)

- **역할**: 숫자 중심 신뢰도 표현이 아니라, AgentGo의 차별 가치를 시각적으로 이해시키는 섹션
- **배경**: `linear-gradient(135deg, #0D2060 0%, #0A1628 100%)`
- **상하 border**: `1px solid rgba(26,86,200,0.2)`
- **padding**: `88px 24px`
- **구성**:
  ```
  [label] 왜 AgentGo인가
  [H2] 흩어진 AI 활용을
       운영 가능한 체계로 바꿉니다
  [시각 카드 4개 — grid, repeat(4, 1fr)]
  ```
- **카드 4개 콘텐츠**:

  | 제목 | 설명 | 시각 요소 |
  |------|------|----------|
  | AI 운영 전 영역 지원 | 개발–배포–운영–통제 | 4단계 플로우 아이콘 |
  | 멀티 에이전트 오케스트레이션 | 여러 AI를 하나의 체계로 | 중앙 허브 + 에이전트 노드 |
  | Private / Hybrid 지원 | 환경 제약 없는 구축 | Cloud ↔ On-prem ↔ Private 구조 |
  | 거버넌스 기반 운영 | 보안·권한·감사 통합 관리 | 권한–정책–감사–로그 레이어 |

- **시각 카드 구조**:
  ```
  [상단 40%] 미니 다이어그램 / 아이콘
  [하단 60%] 제목 + 짧은 설명
  ```
- **카드 스타일**:
  - `background: rgba(255,255,255,0.04)`
  - `border: 1px solid glassborder`
  - `border-radius: 18px`
  - `min-height: 240px`
  - hover 시 `translateY(-4px)`, border `rgba(26,86,200,0.45)`, 내부 아이콘 scale `1.03`
- **주의**:
  - 기존 숫자형 `6 / 3 / 100% / 1`은 제거
  - 고객이 3초 안에 “AgentGo가 어떤 운영 체계를 제공하는지” 이해하도록 텍스트보다 구조 시각화 우선


---

### 섹션 5 — USE CASES (활용 사례)

- **역할**: 고객이 AgentGo를 어떤 업무에 적용할 수 있는지 직관적으로 이해
- **배경**: `--color-navy`
- **padding**: `96px 24px`
- **구성**:
  ```
  [label] 활용 사례
  [H2] AgentGo로 실행할 수 있는
       대표 업무 시나리오
  [카드 4개 — grid, repeat(4, 1fr)]
  ```
- **활용 사례 카드**:

  | 사례 | 설명 | 연결 구성요소 |
  |------|------|--------------|
  | 업무 자동화 Agent | 보고서 작성, 메일 초안, 승인 요청 등 반복 업무 자동화 | Flow + Marketplace |
  | 지식 검색 Agent | 사내 문서·매뉴얼·정책을 대화형으로 검색 | Platform + Management |
  | 개발 지원 Agent | 코드 생성, 리뷰, 테스트, 개발 가이드 적용 | Coder + Guard |
  | 운영 분석 Agent | 로그·장애·오류 패턴 기반 원인 분석과 대응 지원 | Management + Guard |

- **시각 표현**:
  - 각 카드 상단에 업무 흐름 미니 아이콘 배치
  - 설명은 2줄 이내
  - “AgentGo가 실제로 어디에 쓰이는지”가 먼저 보이도록 구성


---

### 섹션 6 — EDITIONS (에디션 비교)
- **역할**: 제품 라인업 소개 + 구매 의향 유도
- **배경**: `#060E1A`
- **padding**: `96px 24px`
- **구성**:
  ```
  [label] 제품 에디션
  [H2] 조직에 맞는
       에디션을 선택하세요
  [카드 3개 — grid, 1fr 1fr 1fr]
  ```
- **에디션 카드 3개**:

  **AgentGo Search** (좌)
  - 배경: `#0D1E38`, border `glassborder`
  - 제목: 사내 지식 검색의 시작
  - 설명: 흩어진 사내 문서를 대화하듯 빠르고 정확하게 검색합니다.
  - 기능 리스트: RAG 기반 문서 Q&A / Management 모듈 포함 / 에이전트 설정 및 모니터링

  **AgentGo Automation** (중)
  - 배경: `#0D1E38`, border `glassborder`
  - 제목: 업무 자동화의 핵심
  - 설명: 사내·외 시스템과 연동해 복잡한 업무 프로세스를 자동화합니다.
  - 기능 리스트: Chatbot 기능 전체 포함 / Platform·Guard·Coder·Flow / Public LLM 활용 / 시스템 연동 자동화

  **AgentGo Enterprise** (우, 추천 배지)
  - 배경: `linear-gradient(135deg, #0D2060 0%, #0A1628 60%)`, border `rgba(26,86,200,0.5)`
  - 추천 배지: 우측 상단, `background: #1A56C8`, "추천" 텍스트
  - 제목: 완전한 AI 주권과 통제
  - 설명: 보안을 넘어선 AI 주권 확보, 전용 인프라로 운영 완결성을 실현합니다.
  - 기능 리스트: Standard 기능 전체 포함 / Private LLM 운영 자동화 / 완전 폐쇄망 지원 / GPU 자원 관리 / 엔터프라이즈급 추론 최적화

- **카드 공통 hover**: `translateY(-6px)`
- **기능 리스트 스타일**: `border-top: 1px solid glassborder`, `✓` 체크 아이콘 color `#60A5FA`

---

### 섹션 7 — PERSONA (페르소나별 메시지)
- **역할**: 의사결정자 유형별 공감 유도
- **배경**: `--color-navy`
- **padding**: `96px 24px`
- **구성**:
  ```
  [label] 누구를 위한 플랫폼인가요?
  [H2] 역할마다 다른 고민,
       AgentGo가 함께합니다
  [탭 or 카드 4개]
  ```
- **페르소나 4개** (카드 or 탭 전환):
  | 페르소나 | 핵심 고민 | AgentGo 해소 방법 | 강조 모듈 |
  |----------|-----------|-------------------|-----------|
  | CIO / CDO | 데이터 주권·컴플라이언스·보안 감사 | 외부 유출 없는 폐쇄 인프라와 전체 감사 로그 | Guard + Platform |
  | 현업 팀장 | 업무 자동화·생산성·직원 적응 부담 | 대화 한 마디로 반복 업무가 사라집니다 | Flow + Marketplace |
  | IT 인프라 담당자 | 기존 시스템 통합·운영 안정성 | MCP 표준으로 기존 시스템을 그대로 연결 | Platform + Coder |
  | CFO / 경영진 | ROI·비용 통제·투자 정당성 | AI 사용 비용과 효과를 실시간 대시보드로 증명 | Management |
- **구현 방식**: 탭 클릭 시 카드 콘텐츠 전환 (JS), 기본 선택탭 = CIO/CDO
- **탭 스타일**: 비활성 `color: slate`, 활성 `color: white` + 하단 `2px solid #1A56C8`

---

### 섹션 8 — PROCESS (도입 프로세스)
- **역할**: 도입 불안 해소 + 단계 명확화
- **배경**: `#060E1A`
- **padding**: `96px 24px`
- **구성**:
  ```
  [label] 도입 프로세스
  [H2] 작게 검증하고
       전사로 확장합니다
  [3단계 수평 타임라인]
  ```
- **3단계 타임라인**:
  | 단계 | 제목 | 기간 | 내용 |
  |------|------|------|------|
  | 1 | 데모 & 요구사항 파악 | 1~2주 | 현재 조직의 Pain point 공유 → 맞춤형 30분 데모 진행 → POC 범위 협의 |
  | 2 | POC 구축 & 검증 | 1~2개월 | 핵심 Use Case 3개 선정 → KPI 설정 → 환경 구축 → 성과 측정 |
  | 3 | 전사 확장 | 3개월~ | 파일럿 부서 적용 → 시스템 연동 → 에이전트 확장 → 거버넌스 체계 완성 |
- **타임라인 스타일**: 번호 원형 badge (blue), 단계 간 연결선 (`1px dashed rgba(26,86,200,0.4)`), 가로 배치
- **모바일**: 세로 타임라인으로 전환

---

### 섹션 9 — FAQ (자주 묻는 질문)
- **역할**: 도입 불안 5대 질문 해소
- **배경**: `--color-navy`
- **padding**: `96px 24px`
- **구성**: 아코디언 형태 (클릭 시 답변 펼침)
- **FAQ 5개**:
  | 질문 | 답변 요약 |
  |------|-----------|
  | 우리 데이터가 외부로 나가지 않나요? | 온프레미스·폐쇄망 지원, Guard 모듈이 모든 접근 암호화·로그 기록 |
  | AI 오류 시 책임 소재는 누구인가요? | 전체 감사 로그로 누가 어떤 지시를 했는지 추적 가능 |
  | 기존 ERP·그룹웨어와 연동되나요? | MCP 표준 프로토콜 기반, Coder 모듈로 커스텀 연동 지원 |
  | 직원들이 쓰지 않으면 어떻게 하나요? | 대화형 UI, Marketplace 즉시 배포로 별도 교육 불필요 |
  | 비용 대비 효과를 어떻게 증명하나요? | Management 대시보드에서 사용량·처리 건수·절감 시간 실시간 확인 |
- **아코디언 스타일**: 기본 닫힘, 클릭 시 답변 슬라이드 다운, 화살표 아이콘 rotate 180°
- **border**: `1px solid glassborder`, 열린 항목 `border-color: rgba(26,86,200,0.4)`

---

### 섹션 10 — CTA (최종 전환)
- **역할**: 페이지 최하단 최종 전환 유도
- **배경**: `--color-navy`
- **padding**: `120px 24px`
- **정렬**: 중앙
- **구성**:
  ```
  [label] 지금 시작하세요
  [H2] AI 도입의 첫 걸음은
       30분 데모로 충분합니다    ← "30분 데모" = 그라디언트 텍스트
  [desc] 현재 조직의 Pain point를 공유해 주시면,
         맞춤형 데모와 POC 설계를 무료로 제공해 드립니다.
  [버튼 2개] [데모 신청하기 →] [소개서 받기]
  ```
- **버튼**: Primary `font-size: 17px`, `padding: 16px 40px`

---

### 섹션 11 — FOOTER
- **역할**: 브랜드 마무리 + 연락처
- **배경**: `#060E1A`
- **padding**: `40px 48px`
- **border-top**: `1px solid glassborder`
- **구성**: 좌 로고 / 우 카피라이트
  ```
  [좌] AgentGo 로고 + 아이콘
  [우] © 2026 ITCEN CLOIT. All rights reserved.
  ```

---

## 4. 인터랙션 & 애니메이션 명세

| 인터랙션 | 대상 | 구현 방법 | 값 |
|----------|------|-----------|-----|
| 네트워크 그래프 | Hero 배경 캔버스 | requestAnimationFrame | 28노드, 180px 연결거리 |
| 스크롤 페이드인 | 모든 카드·셀 | IntersectionObserver | opacity 0→1, translateY 24px→0, 0.55s |
| 네비 배경 강화 | NAV | scroll 이벤트 | 스크롤 > 50px 시 배경 opacity 강화 |
| 버튼 hover | 모든 CTA 버튼 | CSS transition | translateY(-2px), box-shadow 강화 |
| 카드 hover | Problem·Editions | CSS transition | translateY(-4~6px), border-color 변경 |
| 탭 전환 | Persona 섹션 | JS click 이벤트 | 콘텐츠 fade 전환 |
| 아코디언 | FAQ 섹션 | JS click 이벤트 | max-height 0→auto, 화살표 rotate |
| 배지 펄스 | Hero 배지 dot | CSS animation | scale 1→0.8, opacity 1→0.5, 2s loop |
| 스크롤 바운스 | Hero 하단 인디케이터 | CSS animation | translateY 0→8px, 2.5s loop |

---

## 5. 반응형 브레이크포인트

| 브레이크포인트 | 변경 사항 |
|--------------|-----------|
| `max-width: 1024px` | 모듈 그리드 3열 → 2열 |
| `max-width: 768px` | 모듈 그리드 2열 → 1열 / 에디션 카드 1열 / Stats 2×2 / NAV 링크 숨김 |
| `max-width: 480px` | Hero H1 font-size 36px / CTA 버튼 전체 너비 / 도입 프로세스 세로 전환 |

---

## 6. 기술 스펙

| 항목 | 스펙 |
|------|------|
| 구현 방식 | 단일 HTML 파일 (HTML + CSS + JS 인라인) |
| 외부 의존성 | Google Fonts CDN만 허용 |
| 브라우저 지원 | Chrome·Safari·Edge 최신 버전 |
| 접근성 | `prefers-reduced-motion` 대응, TAB 이동, focus state, aria-label, 색상 대비 AA 기준 고려 |
| SEO | `<title>` `<meta description>` `<lang="ko">` `og:title` `og:description` `og:image` `schema.org SoftwareApplication` 포함 |
| 이미지 | 없음 (CSS·SVG·Canvas만 사용) |

---

## 7. 섹션 순서 요약 (코드 작성 기준)

```
0. NAV             — 고정, 브랜드 + 앵커 링크 + CTA
1. HERO            — 캔버스 배경 + 제품 정체성 + CTA 2개
2. PROBLEM         — 카드 3개 (Pain point)
3. CORE STRUCTURE  — 3×2 그리드 (AgentGo 핵심 구성요소)
4. VALUE           — 시각 카드 4개 (왜 AgentGo인가)
5. USE CASES       — 대표 업무 시나리오 4개
6. EDITIONS        — 카드 3개 (에디션 비교)
7. PERSONA         — 탭 전환 카드 4개
8. PROCESS         — 3단계 수평 타임라인
9. FAQ             — 아코디언 5개
10. CTA            — 최종 전환 섹션
11. FOOTER         — 브랜드 마무리
```

---

## 8. CTA 버튼 동작 정의

| 버튼명 | 위치 | 동작 |
|--------|------|------|
| 데모 신청 (NAV) | 상단 고정 | `href="#cta"` 섹션 앵커 이동 |
| 데모 신청하기 (Hero) | 섹션 1 | `href="#cta"` 섹션 앵커 이동 |
| 소개서 다운로드 (Hero) | 섹션 1 | `href="#"` (추후 PDF 링크 연결) |
| 데모 신청하기 (CTA) | 섹션 9 | `href="mailto:contact@itcen.com"` |
| 소개서 받기 (CTA) | 섹션 9 | `href="#"` (추후 PDF 링크 연결) |
