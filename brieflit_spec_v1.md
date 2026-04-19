# Brieflit Spec v1.0

> 작성일: 2026년 4월 19일  
> 작성자: Super Alloy, Inc.

---

## 1. 서비스 개요

| 항목 | 내용 |
|------|------|
| 브랜드 | Brieflit |
| 사업자 | Super Alloy, Inc. |
| 컨셉 | AI 뉴스로 배우는 업무 영어 |
| 타깃 | AI에 관심 있는 한국 직장인 |
| 핵심 가치 | AI 뉴스 원문에서 원어민식 세련된 표현을 뽑아 업무에서 바로 쓸 수 있게 |
| 수익 모델 | 유료 구독 (광고 없음) |
| 포지셔닝 | "AI도 따라가고, 영어도 늘고" — 두 마리 토끼를 한 번에 |

---

## 2. 상품 구조

### 가격 정책
| 상품 | 가격 | 비고 |
|------|------|------|
| 월 구독 (정가) | 19,900원 / 월 | 언제든 해지 가능 |
| 첫 달 얼리버드 | 9,950원 (50% 할인) | 한시적 프로모션, 첫 1개월만 적용 |

### 환불 정책
- 첫 브리핑 수신 후 마음에 안 들면 100% 환불 보장
- 환불 요청: team@brieflit.news → 수동 처리

### 향후 고려 (현재 미적용)
- 연간 구독: 구독자 100명 이후 검토
- 팀/기업 구독: 추후 검토

---

## 3. 콘텐츠 구성

### 발송 구조
- 수집: 매일 자동 수집 → 풀 축적
- 발송: **주 2회**, 회당 뉴스 1개 깊게

### 1회 브리핑 구성
1. **뉴스 요약** — 한국어 bullet 4~5개 (한국 직장인 업무 맥락으로 연결)
2. **핵심 표현 5개** — 영어 표현 + 한국어 뜻 + 실제 원문 문장 + 영어 업무 예문
3. **오늘 말해보기** — 영어 2문장 + 한국어 힌트

### 표현 선정 기준 (STRICT)
- 최소 2단어 이상 구/관용구 (단어 단위 금지)
- 실제 원문에 verbatim 존재하는 표현만
- 원어민식, 세련된 표현 (기본 표현 금지)
- 최소 3가지 업무 상황에서 활용 가능한 표현
- 금융/투자 전문 용어 금지
- 기본형으로 표기 (과거형/활용형 금지)
- 핵심 표현은 원문 및 예문에서 `**표현**`으로 마킹 → HTML 노란 하이라이트로 렌더링

### 뉴스 선정 기준
- **포함**: AI 툴/제품, 트렌드, 스타트업 동향, 빅뉴스
- **제외**: 투자/펀딩/밸류에이션, 규제/정책, 뉴스레터 큐레이션/앱 추천 목록

### 뉴스 소스
TechCrunch, The Verge, VentureBeat, MIT Technology Review, Wired

---

## 4. 브랜드 아이덴티티

### 컬러
| 용도 | 값 |
|------|-----|
| 메인 (검정) | `#111111` |
| 포인트 (노란색) | `#F5C842` |
| 배경 | `#F7F4EE` (오프화이트) |
| 흰색 | `#FFFFFF` |

### 타이포그래피
| 용도 | 폰트 |
|------|------|
| 로고/헤딩 | Playfair Display (또는 Georgia) — serif, bold |
| 본문/UI | DM Sans (또는 Trebuchet MS) — sans-serif |
| 영어 표현/원문 | Palatino Linotype — serif, italic |

### 로고
- 텍스트 로고: `Brief`(검정) + `lit`(노란색 `#F5C842`)
- 이미지 없이 CSS 텍스트로 구현 (이메일 호환성)
- 심볼 아이콘: 신문+번개 조합 (별도 PNG, 현재 미사용)

---

## 5. 이메일 디자인

### 레이아웃 원칙
- Morning Brew 스타일 기반
- 흰 배경 + 검정 테두리/헤더
- 섹션 라벨: `아이콘 + 텍스트 ————` (D 스타일)
- 이미지 없음 (이메일 클라이언트 호환성)
- 최대 너비 600px

### 섹션 구성
1. 헤더 (날짜 + 로고 + 태그라인)
2. 네비바 (Today's News · Key Expressions · Speak It Out) — 텍스트만, 앵커 없음
3. 인트로 텍스트
4. Today's News (번호 불릿 + 원문 기사 보기 링크)
5. Key Expressions (표현 카드 × 5)
6. Speak It Out (문장 2개 + 힌트)
7. 푸터 (Brief**lit** 로고 + 태그라인 + 수신거부)

### 표현 카드 구조
```
[검정 헤더] 표현 / 품사 / 한국어 뜻
[회색 배경] 📰 실제 원문 (이탤릭, 핵심 표현 하이라이트)
[노란 상단선] Business example (핵심 표현 하이라이트)
```

### 하이라이트
- 원문/예문/speaking 문장에서 핵심 표현 `background-color:#f5c842; padding:1px 3px; border-radius:2px; font-weight:bold;`

### 수신거부
- Stibee 변수: `{$unsubscribe_link}`

---

## 6. 기술 스택

### 인프라
| 항목 | 서비스 | 비용 |
|------|--------|------|
| 도메인 | brieflit.news (Spaceship) | 연 $7.96 |
| 이메일 | team@brieflit.news (Spacemail) | 월 $0.98 |
| 이메일 발송 | Stibee 스탠다드 | 월 8,900원 |
| AI API | Anthropic Claude API | 월 ~$0.25 |
| 자동화 | GitHub Actions | 무료 |
| **월 총 비용** | | **약 12,000원** |

### DNS 설정 (Spaceship)
```
CNAME: stb._domainkey → dkim.stibee.com
TXT: _dmarc → v=DMARC1; p=quarantine; rua=mailto:team@brieflit.news
TXT: brieflit.news → v=spf1 include:mail.stibee.com include:spf.spacemail.com ~all
```

### 코드 파일 구조
```
brieflit/
├── collect_news.py       # RSS 피드 수집 + 본문 크롤링
├── select_news.py        # Claude API 5개 추천 → 수동 선택
├── generate_content.py   # 선택된 뉴스로 Brieflit 콘텐츠 생성
├── send_email.py         # HTML 생성 + Stibee 수동 발송
├── assets/
│   └── (이미지 파일 — 현재 미사용)
├── data/
│   ├── news_YYYYMMDD.json
│   └── selected_news_YYYYMMDD_HHMM.json
├── content/
│   ├── brieflit_YYYYMMDD_HHMM.md
│   └── preview_email.html
├── .env
└── .gitignore
```

### 파이프라인
```
collect_news.py (매일 자동, GitHub Actions)
→ data/news_YYYYMMDD.json

select_news.py (발송일 수동 실행)
→ Claude 5개 추천 → 수동 선택
→ data/selected_news_YYYYMMDD_HHMM.json

generate_content.py (자동)
→ Claude API로 Brieflit 포맷 콘텐츠 생성
→ content/brieflit_YYYYMMDD_HHMM.md

send_email.py (확인 후 발송)
→ md 파싱 → HTML 생성
→ content/preview_email.html (미리보기)
→ Stibee HTML 에디터에 붙여넣기 → 수동 발송
```

### .env
```
ANTHROPIC_API_KEY=...
STIBEE_API_KEY=...
STIBEE_LIST_ID=486409  # 일반 주소록 (테스트용)
# 유료 구독 주소록 ID: 486409 (Stibee 계정 교체 후 업데이트 필요)
```

---

## 7. 결제 및 구독 관리

### 결제 플랫폼
- **Stibee 유료 구독 기능** (스탠다드 요금제 이상)
- 결제 수단: 카드, 카카오페이
- 수수료: 결제 대행사 3.2% (부가세 별도), 플랫폼 수수료 없음
- 정산: 매월 25일 (전월 발생 수익)

### 구독 폼 URL
```
https://page.stibee.com/subscriptions/486409
```
> ⚠️ Stibee 계정을 team@brieflit.news로 교체 후 URL 업데이트 필요

### 미완료 작업
- [ ] Stibee 계정 team@brieflit.news로 재생성 (개인 이메일 노출 방지)
- [ ] 유료 구독 주소록 재설정 후 구독 폼 URL 업데이트

---

## 8. 랜딩페이지

### 파일
- `index.html` (단일 파일, Google Fonts 외부 로딩)
- 호스팅: GitHub Pages 예정 → brieflit.news 도메인 연결

### 섹션 구성
1. 네비 (로고 + 구독하기 버튼)
2. 히어로 (타이틀 + 카피 + CTA + Brieflit 마퀴 배경)
3. 스탯 바 (5개 표현 / 주 2회 / 3분 / 100% 원문 기반)
4. How it works (3단계)
5. 샘플 (실제 표현 예시)
6. 가격 (얼리버드 카드)
7. 푸터

### 카피
- 헤더 타이틀: `AI 뉴스 읽는 3분, 업무 영어가 됩니다`
- 서브: `AI 트렌드를 놓치지 않으면서 원어민식 표현까지. 어차피 알아야 할 AI, 어차피 써야 할 영어.`
- 구독 폼 제목: `AI 뉴스 읽는 3분, 업무 영어가 됩니다`
- 구독 폼 설명: `AI 트렌드를 놓치지 않으면서 원어민식 표현까지. 뉴스 원문에서 직접 뽑은 업무 영어 5개를 매주 2회 드립니다. 어차피 알아야 할 AI, 어차피 써야 할 영어.`

---

## 9. 채널 전략

### 운영 채널 (브랜드 계정, 개인정보 비노출)
| 채널 | 역할 | 콘텐츠 |
|------|------|--------|
| X (Twitter) | AI/테크 커뮤니티 공략 | 매 발송일 핵심 표현 1개 포스팅 |
| 인스타그램 | 직장인 영어 학습층 공략 | 표현 카드뉴스 (Canva 템플릿) |
| 네이버 블로그 | 검색 유입 | 표현 키워드 중심 포스팅 |

### 런칭 전략
- 모든 채널 동시 오픈
- 튜링포스트 코리아 (기존 뉴스레터, 구독자 ~2000명)에서 1회 자연스럽게 소개

### 튜링포스트 코리아 연계 원칙
- 1회만, 광고가 아닌 "새 프로젝트 소개" 형식으로
- 반복 홍보 금지 (구독자 피로감 방지)
- 이후 Brieflit 독자 채널로 독립 성장

---

## 10. 목표

| 기간 | 목표 |
|------|------|
| 3개월 | 유료 구독자 151명 = 월 매출 약 300만원 |
| 구독자 50명 | 스피커(TTS) 기능 검토 |
| 구독자 100명 | 연간 구독 플랜 추가, Stibee 프로 업그레이드 검토 |

---

## 11. 남은 작업 체크리스트

### 즉시
- [ ] Stibee 계정 team@brieflit.news로 재생성
- [ ] 유료 구독 주소록 재설정
- [ ] 랜딩페이지 brieflit.news 도메인 연결 (GitHub Pages)
- [ ] Gmail Postmaster Tools 등록 (스팸 신뢰도 개선)
- [ ] DMARC `p=quarantine`으로 강화

### 런칭 전
- [ ] X 브랜드 계정 개설
- [ ] 인스타그램 브랜드 계정 개설
- [ ] 네이버 블로그 개설
- [ ] 각 채널 첫 콘텐츠 준비
- [ ] 튜링포스트 코리아 소개 글 작성
- [ ] GitHub Actions 자동화 (collect_news.py 매일 실행)

### 런칭 후
- [ ] 스팸 분류 모니터링 및 대응
- [ ] 첫 유료 구독자 환불 프로세스 확인
- [ ] 채널별 성과 추적

---

## 12. 미결 사항

- **스피커(TTS) 기능**: ElevenLabs 무료 플랜 활용 가능 (월 4,000자 << 10만자 한도). 구독자 50명 이후 구현 검토. GitHub Pages 음성 파일 호스팅 필요.
- **Stibee API 발송 자동화**: 현재 프로 요금제 필요 (월 29,000원). 구독자 100명 이후 업그레이드 검토.
- **연간 구독**: 구독자 100명 이후 추가.
- **팀/기업 구독**: 추후 검토.
