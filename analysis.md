# 프리미엄 하이브리드 데이팅 앱 (가칭 '해시태그') — 제안 분석 로그

> 생성일: 2026-05-15
> 공고 URL: https://www.wishket.com/project/155384/

## 1. 공고 파싱 결과

```yaml
job:
  title: "프리미엄 하이브리드 데이팅 앱 구축"
  category: "개발/디자인/기획 · 안드로이드/iOS · 중개·매칭 플랫폼"
  budget_range: "3,800 ~ 4,800만 원 (예상 금액 43,000,000원)"
  duration: "100일 (약 3.5개월)"
  tech_stack:
    - "Flutter (또는 React Native)"
    - "Node.js / Spring Boot"
    - "PostgreSQL / Redis"
    - "AWS"
  description: |
    프리미엄 데이팅 앱 신규 구축 (가칭 '해시태그').
    철저한 서류 검증 통과 유저의 프라이빗 매칭 + 익명 커뮤니티.
    외모/프로필/커뮤니티 3채널 분리 + 채널별 차등 과금(다이아 5/10/20).
    기획~디자인~개발~양대 마켓 런칭 턴키.
  requirements:
    - "휴대폰 본인인증"
    - "다중 서류 업로드(신분증, 자격증, 소득금액증명원, 자동차등록증)"
    - "KMS 암호화 + 관리자 승인 후 즉시 파기 스케줄러"
    - "24h 신규 회원 평가(Rating)"
    - "외모 채널: 틴더형 스와이프, 얼굴 선공개, 스펙 블라인드"
    - "프로필 채널: 해시태그/리스트, 스펙 선공개, 얼굴 블라인드"
    - "커뮤니티 채널: 직군/관심사 익명 게시판, 1:1 대화 요청"
    - "Apple/Google 인앱결제 (다이아 충전)"
    - "차등 과금 5/10/20 + 3채널 동기화 + 이중 과금 방지"
    - "프리미엄 호감 전송 (연락처 첨부 + 고비용 다이아)"
    - "관리자 웹: 서류 심사·파기, 어뷰징, 통계 대시보드"
    - "Phase 2 NLP 큐레이션 대비 데이터 모델"
  client_questions:
    - "프로젝트와 관련된 솔루션 활용 경험"
    - "유사한 프로젝트 수행 경험"
    - "개발 완료 후 지속적인 유지보수 계약 가능 여부"
  deadline: "2026-05-29"
  job_post_url: "https://www.wishket.com/project/155384/"
  urls: []
  images: []
  benchmark_targets:
    - "스카이피플 (주요 참고)"
    - "골드스푼 (우대 사항 언급)"
  client_priorities:
    - "1순위: 금액"
    - "2순위: 산출물 완성도"
    - "3순위: 일정 준수"
  contract_notes:
    - "NDA + 개인정보보호 서약서 필수"
    - "서류 즉시 파기 로직 + 과금 동기화 로직 구현 방안 제안서 포함"
    - "산출물 소유권 100% 클라이언트 귀속"
    - "월 단위 유지보수 계약 가능해야 함"
```

## 2. URL/이미지 분석

- 공고에 포함된 외부 URL: 없음 (벤치마킹 타겟으로 스카이피플 언급, 직접 링크는 미제공)
- 공고에 첨부된 이미지: 없음
- 벤치마킹 타겟 분석 (텍스트 기반):
  - **스카이피플**: 직장 인증 기반 프리미엄 매칭, 차등 과금 모델, 서류 심사형 가입 — 본 프로젝트의 직접 모델
  - **골드스푼**: 다이아 기반 인앱결제 + 직장·소득 검증 + 1:1 메시지 — 차등 과금 패턴 참조

## 3. 실현 가능성 분석 (내부용)

### 프로젝트 유형
- 모바일 앱 (Flutter/RN) — **조건부 가능** (+20% 버퍼)
- 결제/인증/외부 API 연동 — **조건부 가능** (+15% 버퍼)
- 보안 아키텍처 (KMS, 즉시 파기) — 추가 복잡도

### 기본 공수 산정 (AI 보조 없이)
- 기획/PRD: 18 M/D
- Figma 디자인 (70+ 화면): 25 M/D
- FE Flutter (3채널, 결제, 인증): 60 M/D
- BE NestJS (매칭, 과금, 보안): 50 M/D
- Admin 웹 (Next.js): 18 M/D
- QA/배포 (스토어 심사 포함): 14 M/D
- **Total raw: 185 M/D**

### AI 절감률 적용
- 기획: 18 × 0.65 = 11.7
- Figma: 25 × 0.85 = 21.3
- FE: 60 × 0.35 = 21.0
- BE: 50 × 0.45 = 22.5
- Admin: 18 × 0.35 = 6.3
- QA: 14 × 0.5 = 7.0
- **Subtotal: ~89.8 M/D**

### 버퍼 적용 + 달력 일수 변환
- 모바일 +20% & 결제/보안 +15% (중복 영역, 최대 +25%): 89.8 × 1.25 = ~112 M/D
- 달력 일수: 112 × (7/5) = ~157일 (보수적)
- 효율적 시나리오 (체크아웃 패턴 재활용 + 디자인↔개발 일부 병렬): ~114일

### 클라이언트 예상 vs 산정
- 클라이언트 예상: 100일
- 효율적 산정: ~114일 (+14일, 14% 초과 → **20% 이내**)
- **판정**: 100일 그대로 제안 (스코프 동결 + 단계별 납품 전략)
- 클라이언트 런칭 목표(2026 말~2027 초)까지 실제 버퍼 풍부, 일정 준수 우선순위는 #3

## 4. 포트폴리오 매칭

### 매칭 점수 (요구사항 4축 기준)
| Project | 기술 스택 | 도메인 | 기능 | 규모 | 합계 |
|---------|----------|-------|------|------|-----|
| **Connectin** | Flutter+NestJS+PG (40) | 매칭 플랫폼 (30) | 프로필·매칭·암호화 (20) | 12 MS·3개월 (10) | **100** |
| **Fortune App** | Flutter+Firebase (30) | B2C 라이프스타일 (20) | 광고·포인트·SSO (15) | 3개월 단독 (10) | **75** |
| **DayStarter** | Flutter+NestJS+PG (40) | 게이미피케이션 (15) | 가상재화·결제 (20) | 3년 운영 (10) | **85** |
| Series-B | Next+NestJS+MySQL (20) | 핀테크 (10) | KYC·보안 5계층 (20) | 14개월 (10) | 60 |
| Calendar Share | Flutter+Firebase (30) | 소셜 (15) | 캘린더+소셜 (10) | MVP (5) | 60 |

### 최종 추천 3개
1. **Connectin** — 매칭 플랫폼 직접 경험 (가장 직접적 유사)
2. **Fortune App** — Flutter B2C 100일 양대 마켓 출시 패턴 (실현 근거)
3. **DayStarter** — 가상 재화 경제 장기 운영 (다이아 시스템 노하우)

## 5. 최종 제안 요약

- **지원 금액**: 40,800,000원 (VAT 별도)
  - 산정 근거: 클라이언트 예상 상한 4,800만원 × 0.85 = 40,800,000원 (10만원 단위 반올림)
- **지원 기간**: 100일 (계약 체결 직후 즉시 착수)
  - 산정 근거: 클라이언트 예상 100일과 일치, 내부 산정 ~114일이지만 20% 이내 → 스코프 동결 + 단계별 납품 전략으로 100일 매칭
- **핵심 제안 포인트**:
  1. Connectin (매칭 플랫폼 + Flutter + NestJS + 암호화) 직접 경험을 데이팅 도메인에 전이
  2. Fortune App + DayStarter (Flutter B2C + 인앱결제 + 가상재화) 검증된 패턴 재활용
  3. 서류 즉시 파기 (KMS 봉투 암호화 + S3 객체 + 데이터 키 동시 삭제) 구체적 구현 방안 명시
  4. 3채널 이중 과금 방지 (Redis 분산 락 + 24h 열람 캐시) 구체적 알고리즘 명시
  5. App Store / Play Store 데이팅 카테고리 심사 사전 점검 노하우
  6. 1순위(금액) 85% 공격적 가격 + 2순위(완성도) 검증 패턴으로 보장

## 6. 최종 산출물 (8단계 출력 전문)

### 제안서 사이트 URL
- **https://proposal-router.claude-ai-b27.workers.dev/proposal-premium-hybrid-dating-app/**
- GitHub: https://github.com/Blue-Verse/proposal-premium-hybrid-dating-app

### 지원 금액 (복사용)
```
40,800,000원
```
산정: 클라이언트 예상 상한(4,800만원) × 85% (사용자 조정) = 40,800,000원 (10만원 단위 반올림, VAT 별도)

### 지원 기간 (복사용)
```
100일
```
계약 체결 직후 즉시 착수, 양대 마켓 정식 런칭까지 100일

### 클라이언트 질문 답변

**Q1: 프로젝트와 관련된 솔루션 활용 경험이 있다면 설명해주세요.**

본 프로젝트의 기술 요구사항(Flutter, NestJS, PostgreSQL, Redis, AWS) 및 기능 요구사항(매칭 플랫폼, 인앱결제, 보안 아키텍처)에 직접 적용 가능한 솔루션 활용 경험을 다수 보유하고 있습니다.

▶ 매칭/네트워킹 플랫폼: Connectin (디지털 명함·BLE 근거리 탐색·E2E 암호화 메시징, 12 마이크로서비스)
▶ Flutter 양대 마켓 출시: Connectin, Fortune App, DayStarter, Calendar Share — Apple App Review / Google Play 심사 대응 노하우 보유
▶ 인앱결제 + 가상 재화 경제: DayStarter (3년 운영, 7단계 루트박스 이코노미), Fortune App (포인트·리워드 + 광고 SDK)
▶ 민감 정보 보안 아키텍처: Series-B (NICE KYC, 5계층 보안, DLP, GeoIP), Connectin (Signal Protocol E2E 암호화 + AWS KMS)
▶ 백엔드 풀스택: NestJS + PostgreSQL + Redis 조합으로 다수 서비스 구축·운영
▶ Admin 웹 + 통계 대시보드: EZ-Approve (전자결재 SaaS, 7 사용자 역할), Series-B (관리자 포탈) 구축 경험

본 프로젝트의 핵심인 KMS 봉투 암호화·즉시 파기 스케줄러, 3채널 차등 과금 + 이중 과금 방지 동기화, Apple StoreKit 2 / Google Play Billing 영수증 검증을 검증된 패턴으로 구현 가능합니다.

**Q2: 유사한 프로젝트를 수행한 경험이 있다면 무엇입니까?**

본 프로젝트의 핵심 영역에 직접 대응되는 유사 프로젝트 3건을 소개드립니다.

▶ Connectin (2025.05~2025.08, 3개월) — 비즈니스 매칭·네트워킹 플랫폼
- Flutter + NestJS 풀스택, 12 마이크로서비스, 63 API, 41 모바일 기능
- 프로필 기반 매칭, BLE 근거리 탐색, Signal Protocol E2E 암호화, 1:1 메시징
- 본 프로젝트 유사점: 매칭 플랫폼 도메인 직접 경험, Flutter 양대 마켓 출시, 보안 매칭 아키텍처, 3개월 풀스택 딜리버리

▶ DayStarter (2022.06~현재, 약 3년 운영) — Sleep-to-Earn 게이미피케이션 앱
- Flutter + NestJS + PostgreSQL, 5 레포·37 DB 모델·~50K LOC
- 7단계 루트박스 가상 재화 경제, 인앱결제, ML Kit 센서 검증
- 본 프로젝트 유사점: 가상 재화 지갑·차등 차감 노하우, 결제·환불·악용 시나리오 운영 경험, 행동 데이터 정형화 적재 (Phase 2 NLP 큐레이션 대비)

▶ Fortune App (2024.07~2024.09, 3개월) — Flutter B2C 운세 앱
- Flutter + Firebase + Node.js, 305 Dart 파일·~16K LOC, 9 API
- 사주 분석 엔진 연동, 포인트 리워드, 자체 광고 SDK, Google/Apple SSO
- 본 프로젝트 유사점: Flutter B2C 100일 양대 마켓 출시 패턴, 게이미피케이션, 라이프스타일 도메인

상세 사례는 제안서 사이트의 '유사 프로젝트 경험' 페이지에서 확인 가능합니다.

**Q3: 개발 완료 후 지속적인 유지보수 계약이 가능한가요?**

가능합니다. 월 단위 유지보수 계약을 별도로 체결할 수 있으며, 기본 운영 형태는 다음과 같이 제안드립니다.

▶ 기본 운영 범위: 장애 대응, 버그 수정, 보안 패치, 외부 API 정책 변경 대응(Apple/Google 인앱결제 정책, 본인인증 등), 인프라 모니터링
▶ 추가 개발 범위: 신규 기능 개발 (Phase 2 AI 큐레이션 매칭 등)은 별도 산정
▶ 응답 SLA: 평일 업무 시간 기준 4시간 이내 1차 응답, 긴급 장애는 별도 채널 운영
▶ 보고 주기: 월간 운영 리포트 (장애·이슈 처리 현황, 인프라 비용, 성능 지표)

구체적인 월정액·SLA·범위는 미팅에서 클라이언트의 운영 규모와 요구 수준에 맞춰 협의 드리겠습니다. 본 프로젝트로 구축한 코드베이스에 대한 컨텍스트를 보유한 동일 인력이 인계 없이 유지보수를 이어 받는 구조이므로, 운영 안정성과 응답 속도를 모두 확보할 수 있습니다.

### 지원 내용 (전체 텍스트, 복사용)

```
안녕하세요, 프리미엄 하이브리드 데이팅 앱 (가칭 '해시태그') 프로젝트에 지원합니다.

본 프로젝트에 대한 상세 제안서(견적서, 공수계산서, PRD, 일정, 포트폴리오)를 별도 페이지로 준비하였습니다. 아래 링크에서 확인해 주시면 감사하겠습니다.
▶ 제안서 상세 페이지: https://proposal-router.claude-ai-b27.workers.dev/proposal-premium-hybrid-dating-app/
▶ 위시켓 포트폴리오: https://www.wishket.com/partners/p/blueverse1/

---

<프로젝트 진행 제안>

■ 프로젝트 분석
- 외모(스와이프) / 프로필(해시태그·리스트) / 커뮤니티(익명 게시판) 3채널 매칭 + 채널별 차등 과금(다이아 5/10/20)을 핵심 축으로 하는 프리미엄 데이팅 플랫폼
- 다중 서류(신분증·자격증·소득금액증명원·자동차등록증) 검증 후 KMS 암호화 + 관리자 승인 직후 즉시 파기 스케줄러가 핵심 기술 차별점
- 3채널 간 동일 프로필 열람 상태 실시간 동기화 + 이중 과금 방지 로직이 과금 안정성의 핵심
- iOS/Android 동시 양대 마켓 런칭 (Flutter 단일 코드베이스), 데이팅 카테고리 심사 정책 사전 점검 필수
- Phase 2 NLP 큐레이션 매칭 도입 대비, 유저 행동 로그·해시태그 데이터를 정형화하여 적재하는 DB 설계 적용

■ 작업 일정

[Phase 1] 기획 / 설계 — Day 1~18 (약 2.5주)
- 킥오프 워크숍, 3채널 IA·과금 정책 확정, 보안 아키텍처 설계
- 화면 기획서(스토리보드) 70+ 화면 작성, ERD 1차 확정
- 산출물: 요구사항 정의서, 화면 기획서, 정책 문서, ERD, 시스템 아키텍처 다이어그램

[Phase 2] 디자인 + 백엔드 개발 착수 — Day 19~45 (약 4주)
- Figma 디자인 시스템 → 앱 50화면 → 관리자 웹 20화면 디자인
- NestJS 백엔드 API 골격, AWS 인프라(KMS·RDS·S3·ElastiCache) 구축
- 본인인증·서류 업로드·KMS 암호화 모듈 우선 개발
- 산출물: Figma 원본, 백엔드 API 50%, AWS 인프라 가동

[Phase 3] 풀스택 개발 — Day 46~80 (약 5주)
- Flutter 앱 3채널 UI 풀구현, 인앱결제 + 다이아 지갑, 차등 과금 알고리즘
- 1:1 대화 / 푸시 알림, 관리자 웹 풀구현
- 통합 베타 빌드 배포 (Day 80, TestFlight + Internal Testing)

[Phase 4] QA + 스토어 심사 + 런칭 — Day 81~100 (약 3주)
- 통합 QA 시나리오 테스트, 보안 점검(서류 즉시 파기 검증, 결제 멱등 검증)
- App Store / Google Play 심사 제출 (Day 88), 심사 대응
- 정식 런칭 (Day 100), 1개월 무상 하자보수 시작

■ 마일스톤 및 산출물
- M1 (Day 18): 기획·설계 완료 → 요구사항 정의서·화면 기획서·정책 문서·ERD 승인
- M2 (Day 45): 디자인 완료 + 보안 모듈 데모 → Figma 전체 화면 승인, 서류 KMS 암호화·즉시 파기 작동 확인
- M3 (Day 80): 통합 베타 빌드 → iOS/Android 베타 설치 가능, 3채널 매칭+결제 시나리오 통과
- M4 (Day 100): 정식 런칭 → App Store / Play Store 정식 노출, 운영 가이드·매뉴얼 인계
- 최종 산출물: 화면 기획서, Figma 원본, 시스템 아키텍처 + ERD, FE/BE/Admin 소스 코드 (소유권 100% 클라이언트 귀속), 관리자 페이지 매뉴얼

■ 미팅 시 협의 필요 사항
- 다이아 충전 패키지 단가 구성 (Tier별 상품 ID, 차등 차감 정책 5/10/20의 채널별 매핑)
- 24h 신규 회원 평가(Rating) 노출 가중치 산정 알고리즘 디테일
- 호감 거부 시 다이아 환원 정책 여부
- 본인인증 기관 선정 (NICE / KCB) 및 계약 명의 확정
- 데이팅 카테고리 Apple/Google 심사 정책 사전 점검 항목 공유
- 월 단위 유지보수 계약 범위·SLA·월정액 산정 기준
- NDA + 개인정보보호 서약서 체결 절차

---

<유사 프로젝트 진행 경험>

▶ Connectin — 디지털 명함 & 네트워킹 플랫폼 (2025.05~2025.08, 3개월)
- 프로젝트 유형: B2B 매칭·네트워킹 플랫폼 / 베트남 시장
- 핵심 기능: 디지털 명함, BLE+GPS 근거리 탐색, Signal Protocol E2E 암호화 메시징, OCR 명함 스캔, Zalo 슈퍼앱 연동, 12 마이크로서비스
- 유사점: 매칭 플랫폼 도메인 직접 경험, Flutter+NestJS 풀스택 양대 마켓 출시, 보안 매칭 아키텍처(KMS·E2E 암호화), 3개월 풀스택 딜리버리 — 본 프로젝트 100일 일정의 직접 근거
- 기술 스택: Flutter 3.22, BLoC, Clean Architecture, Express.js, PostgreSQL, Signal Protocol, AWS KMS, Firebase Auth/FCM, Docker

▶ DayStarter — Sleep-to-Earn 게이미피케이션 앱 (2022.06~현재, 약 3년 운영)
- 프로젝트 유형: B2C 모바일 앱 / 헬스케어·게이미피케이션
- 핵심 기능: 센서 기반 수면 검증(ML Kit), 7단계 루트박스 가상 재화 이코노미, Spine 2D 캐릭터 시스템, 인앱결제 + 광고 + 자체 포인트 경제 운영
- 유사점: 다이아 지갑·차등 차감·이중 차감 방지와 동일한 가상 재화 경제 도메인 (3년 운영 노하우), Flutter+NestJS+PostgreSQL 스택 동일, 행동 데이터 정형화 적재(Phase 2 NLP 큐레이션 대비 직접 활용)
- 기술 스택: Flutter, NestJS, TypeScript, PostgreSQL, Firebase, ML Kit, Spine 2D, In-App Purchase

▶ Fortune App — 사주 기반 운세 앱 (2024.07~2024.09, 3개월)
- 프로젝트 유형: B2C 모바일 앱 / 라이프스타일
- 핵심 기능: 사주 분석 엔진(LF3) 연동, 포인트·데일리 체크인 리워드, 자체 광고 SDK(flutter_ads), Google/Apple SSO, 운세 결과 스크린샷 공유, BLoC + Clean Architecture (305 Dart 파일·~16K LOC)
- 유사점: Flutter B2C 100일 양대 마켓 출시 패턴(본 프로젝트와 동일), 기획+디자인+개발 단독 수행, Apple/Google 심사 통과 노하우, 게이미피케이션 + 포인트 경제
- 기술 스택: Flutter 3.22, Dart, BLoC/Cubit, Clean Architecture, Firebase Auth/Analytics/Crashlytics, Node.js, Retrofit+Dio, AutoRoute, Figma

---

<사용 기술과 툴>

▶ 개발 기술
- 모바일: Flutter 3.x, Dart, BLoC/Riverpod, Clean Architecture
- 백엔드: NestJS 10, TypeScript, PostgreSQL, Redis, Sequelize/TypeORM
- 관리자 웹: Next.js, React, TypeScript, TailwindCSS
- 인앱결제: Apple StoreKit 2, Google Play Billing (서버 영수증 검증)
- 인증: NICE 본인인증, JWT, OAuth (Apple/Google SSO)
- 보안: AWS KMS 봉투 암호화, S3 객체 + 데이터 키 즉시 파기 스케줄러, Sentry 모니터링

▶ 개발 도구 및 인프라
- 버전 관리: GitHub
- CI/CD: GitHub Actions (Flutter 빌드 + 백엔드 배포 자동화)
- 클라우드: AWS Seoul 리전 (KMS, S3, RDS, ElastiCache, ECS/EC2, CloudWatch)
- 컨테이너: Docker, docker-compose
- 디자인: Figma (디자인 시스템 + 컴포넌트 라이브러리)

▶ 커뮤니케이션
- 일일 진행 공유: Slack 또는 카카오톡
- 주간 미팅: Zoom / Google Meet (30~45분)
- 문서 공유: Notion 또는 Google Docs
- 이슈 트래킹: GitHub Issues 또는 Linear
```

### 관련 포트폴리오 추천
1. **Connectin** — 매칭 플랫폼 도메인 직접 경험 (Flutter+NestJS 풀스택, 3개월 양대 마켓 출시, Signal Protocol E2E 암호화)
2. **DayStarter** — 가상 재화(다이아) 경제 + 인앱결제 3년 운영 노하우 (차등 차감·이중 차감 방지·환불 시나리오 직접 운영)
3. **Fortune App** — Flutter B2C 100일 양대 마켓 출시 패턴 (기획+디자인+개발 단독 수행, Apple/Google 심사 통과)
