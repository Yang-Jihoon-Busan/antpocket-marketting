# 앤트포켓(Antpocket) 디자인 스타일 가이드

> 출처: 공식 웹사이트 [https://antpocket.io](https://antpocket.io) 의 `landing.page.css` 및 마크업 분석 (2026-05-21)
> 관련 문서: [brand_guideline.md](brand_guideline.md) · [business_context.md](business_context.md)

---

## 1. 디자인 원칙

- **미니멀 & 클린**: 넉넉한 여백, 흰색 카드, 옅은 보더로 정돈된 화면
- **가독성 우선**: 한글/영문 폰트 분리, 충분한 줄 간격
- **신뢰감 있는 절제**: 화려한 색 대신 올리브 1색을 포인트로 사용
- **반응형**: 데스크톱·모바일 모두 일관된 경험
- **기반 시스템**: Bootstrap 5.3.7 (그리드·유틸리티·컴포넌트 활용)

---

## 2. 컬러 시스템

### 2.1 브랜드 컬러
| 토큰 | HEX | 용도 |
| --- | --- | --- |
| `--brand-primary` | `#7a7d1e` | 주요 버튼 배경·테두리 (btn-primary) |
| `--brand-accent` | `#827717` | 아이콘, 강조 텍스트 |

### 2.2 배경 / 서피스
| 토큰 | 값 | 용도 |
| --- | --- | --- |
| `--bg-page` | `#fafafa` | 페이지 전체 배경 |
| `--bg-surface` | `#ffffff` | 섹션 카드 배경 |
| `--bg-upper` | `rgb(251,252,246)` | 상단/히어로 섹션 (옅은 아이보리) |
| `--border` | `#e0e0e0` | 카드·네비 구분선 (1px) |

### 2.3 텍스트 / 그레이 스케일
| 토큰 | HEX | 용도 |
| --- | --- | --- |
| `--text-strong` | `#212121` | 본문 진한 텍스트, 헤딩 |
| `--text-sub` | `#424242` | 서브 헤딩 |
| `--text-muted` | `#757575` | 보조 텍스트 |
| `--text-muted-2` | `#666` | 보조 텍스트(변형) |
| `--text-faint` | `#888` | 약한 텍스트 |
| `--text-disabled` | `#bdbdbd` | 비활성/플레이스홀더 |

### 2.4 컬러 사용 규칙
- 포인트 컬러(올리브)는 **CTA·아이콘·강조**에만 제한적으로 사용
- 본문 배경은 항상 흰색/아이보리 계열 유지
- 텍스트는 진한→연한 순으로 위계 부여(212121 → 424242 → 757575)

---

## 3. 타이포그래피

### 3.1 폰트 패밀리
```css
/* 본문 기본 */
font-family: 'Lexend Deca', 'Noto Sans KR', sans-serif;

/* 로고 / 워드마크 */
font-family: 'Audiowide';
```

| 용도 | 폰트 |
| --- | --- |
| 로고/워드마크 | Audiowide |
| 영문·숫자 본문 | Lexend Deca |
| 한글 본문 | Noto Sans KR |
| 폴백 | sans-serif |

### 3.2 위계 & 무게
- 헤딩(h1): 메인 타이틀, 굵게
- 서브 헤딩(h3): `font-weight: 400` (가벼운 무게로 부제 표현)
- 본문: 기본 무게, `--text-strong` 색상

### 3.3 반응형 타입 스케일
| 요소 | 데스크톱 | 모바일 (≤768px) |
| --- | --- | --- |
| h1 (상단 섹션) | 기본 | `1.4em` |
| h3 (상단 섹션) | 기본 | `1em` |

---

## 4. 레이아웃 & 스페이싱

### 4.1 섹션 구조
- 각 섹션은 흰색 컨테이너 카드 + `1px solid #e0e0e0` 보더로 구획
- 섹션 간 구분: `.section-divider` 최소 높이 `24px`

### 4.2 패딩 규칙
| 영역 | 데스크톱 | 모바일 (≤775px) |
| --- | --- | --- |
| 일반 섹션 (`section .container`) | `54px 24px` | `32px 24px` |
| 상단 섹션 (`.section-upper`) | `40px 24px` | — |

> 상단 섹션은 보더 상단 제거(`border-top: 0`), 배경 아이보리(`rgb(251,252,246)`)

### 4.3 스페이싱 토큰 (관찰값)
- 기본 단위: **24px** (섹션 좌우 패딩 기준)
- 요소 마진: `12px`, `32px`, `40px` 등 8의 배수 위주

---

## 5. 컴포넌트

### 5.1 버튼 (Button)
```css
.btn.btn-primary {
    background-color: #7a7d1e;
    border-color: #7a7d1e;
}
```
- Primary 버튼: 올리브 배경 + 동일 색 보더
- 주요 CTA("무료로 시작")에 사용

### 5.2 네비게이션 바 (Navbar)
- 하단 보더: `1px solid #e0e0e0`
- 브랜드명(`.navbar-brand`): `Audiowide` 폰트 적용

### 5.3 섹션 카드
- 배경 `#ffffff`, 보더 `1px solid #e0e0e0`
- 패딩 `54px 24px` (모바일 `32px 24px`)

### 5.4 기능 아이콘 (Feature Icon)
```css
.section-functions .function-icon {
    font-size: 72px;
    color: #827717;
    margin-bottom: 24px;
}
```
- 크기 `72px`, 올리브 색(`#827717`)으로 통일
- 기능 섹션 헤딩(h3) 하단 마진 `40px`

### 5.5 상단 섹션 이미지
- `.section-upper img` 높이 `120px`
- 플랫 레이아웃(`flat-wrapper`): `display: flex`, `align-items: flex-end`

---

## 6. 반응형 브레이크포인트

| 브레이크포인트 | 적용 |
| --- | --- |
| `≤ 768px` | 헤딩 폰트 크기 축소 (h1 1.4em / h3 1em) |
| `≤ 775px` | 섹션 패딩 축소 (54px → 32px) |

> Bootstrap 5.3.7 표준 그리드(`container`, `row`, `col-*`)를 기반으로 함

---

## 7. 아이코노그래피 & 이미지

- 기능 아이콘: 72px 라인/심볼 아이콘, 올리브 단색
- 로고 이미지: `images/antpocket-logo.png` (PNG, 투명 배경 권장)
- 일러스트/이미지: 높이 기준 정렬(120px), 하단 정렬(flex-end)

---

## 8. 신규 화면 제작 체크리스트

- [ ] 배경은 `#fafafa`, 콘텐츠는 흰색 카드 + `#e0e0e0` 보더
- [ ] 포인트 컬러(올리브)는 CTA·아이콘에만 제한 사용
- [ ] 폰트: 본문 `Lexend Deca + Noto Sans KR`, 로고 `Audiowide`
- [ ] 섹션 패딩 데스크톱 `54px 24px` / 모바일 `32px 24px`
- [ ] 텍스트 위계: 212121 → 424242 → 757575
- [ ] 모바일(≤768px) 헤딩 축소 확인
- [ ] Bootstrap 5.3.7 그리드/유틸리티 우선 활용

---

> ⚠️ 본 가이드는 공개된 랜딩 페이지 CSS를 역분석해 정리한 것으로, 실제 디자인 시스템(피그마 원본, 디자인 토큰)과 차이가 있을 수 있습니다. 컴포넌트 상세 스펙은 디자인 원본에서 보완을 권장합니다.
