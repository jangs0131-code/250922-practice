## 프로젝트 개요

개발자 포트폴리오(랜딩) 웹페이지입니다. 순수 HTML/CSS/JavaScript로 구성되어 있으며, 반응형 디자인과 타이핑 효과, 스크롤 애니메이션, 스킬바 애니메이션, 간단한 폼 유효성 검사를 제공합니다.

## 데모 실행 방법
- 방법 1: index.html을 브라우저로 직접 열기
- 방법 2: 로컬 서버로 열기(권장)
```bash
# 파이썬 내장 서버 예시 (Python 필요)
python -m http.server 5500
# 브라우저에서 http://localhost:5500 접속
```

## 폴더/파일 구조
```text
c:\work space Cursor\
├─ index.html        # 메인 HTML
├─ style.css         # 전체 스타일
├─ script.js         # 상호작용 스크립트
└─ kaist-sleek-CV-master/  # 별도 템플릿 리소스(현재 페이지와는 독립적)
```

## 주요 섹션 구성
- 홈(Hero): 이름, 멀티 타이핑 서브타이틀, CTA 버튼, 프로필 이미지 자리표시자
- 소개(About): 자기소개, 요약 통계(경력/프로젝트/만족도)
- 기술(Skills): 카테고리별 스킬과 애니메이션 프로그레스 바
- 경력(Experience): 타임라인 레이아웃(교차 정렬)
- 프로젝트(Projects): 카드형 포트폴리오(기술 태그/링크 포함)
- 연락처(Contact): 연락처 정보, 소셜 링크, 폼(기본 유효성 검사)

## 기능 하이라이트
- 네비게이션
  - 고정 헤더, 현재 섹션 하이라이트, 모바일 햄버거 메뉴 토글
  - 스무스 스크롤 및 고정 헤더 오프셋 보정
- 타이핑 효과
  - `.hero-title` 단일 타이핑, `.typing-text` 멀티 텍스트 반복 타이핑
- 스킬바 애니메이션
  - `IntersectionObserver`로 뷰포트 진입 시 `data-width` 값으로 채움
- 스크롤 애니메이션(AOS 유사)
  - 타임라인/프로젝트/스킬 섹션 요소가 스크롤 시 페이드업
- 반응형 디자인
  - 768px, 480px 브레이크포인트 대응
- 폼 유효성 검사
  - 필수값 및 이메일 형식 검사, 성공 시 알림 및 초기화

## 파일별 설명
- `index.html`
  - 섹션 앵커: `#home`, `#about`, `#skills`, `#experience`, `#projects`, `#contact`
  - 멀티 타이핑 문구 소스: `.typing-text`의 `data-texts` 속성(JSON 배열)
  - 문서 하단에서 `script.js` 로드
- `style.css`
  - 컬러: 파랑(`#3498db`), 보라 그라디언트, 중립 그레이 계열
  - 헤더 고정, 히어로 그라디언트, 타임라인(센터 라인/마커), 카드 호버 등
  - 스킬바 애니메이션(`@keyframes fillBar`)과 반응형 미디어쿼리 포함
- `script.js`
  - 모바일 메뉴 토글, 스무스 스크롤, 현재 섹션 활성 링크 관리
  - 스크롤 시 헤더 스타일 변화
  - 스킬바 애니메이션(`IntersectionObserver` 사용)
  - 단일/멀티 타이핑 함수(`typeWriter`, `multiTypeWriter`)
  - 스크롤 페이드업 초기화/처리, 폼 유효성 검사
  - 유틸(디바운스/스로틀) 및 스크롤 핸들러 최적화

## 커스터마이징 가이드
- 히어로 이름/문구 변경
  - `index.html`의 `.hero-title`, `.hero-name` 텍스트 수정
  - 멀티 타이핑 문구: `.typing-text`의 `data-texts` JSON 배열 수정
- 스킬 퍼센트 변경
  - 각 `.skill-progress`의 `data-width` 값을 원하는 퍼센트로 변경(예: `90%`)
- 색상/테마 변경
  - `style.css`에서 주요 컬러(`#3498db` 등), 그라디언트, 중립색 치환
- 프로젝트 카드 수정
  - `Projects` 섹션 카드 타이틀/설명/기술 태그/링크(`Live Demo`, `GitHub`) 업데이트
- 연락처/소셜 링크 변경
  - `Contact` 섹션의 이메일/전화/위치 텍스트와 `.social-links`의 `href` 업데이트

## 접근성/사용성 참고
- ESC 키로 모바일 메뉴 닫기 지원
- 고정 헤더 대응 `scroll-margin-top`으로 앵커 가독성 개선
- 폰트: Google Fonts `Noto Sans KR`

## 배포 가이드
정적 호스팅으로 충분합니다.
- GitHub Pages, Netlify, Vercel 등에 `index.html`, `style.css`, `script.js` 업로드
- 별도 빌드 단계 없음

## 브라우저 지원
- 최신 브라우저(Chromium/Firefox/Safari/Edge) 기준 정상 동작
- `IntersectionObserver` 미지원 환경에서는 스킬바 애니메이션이 제한될 수 있음

## 라이선스
- 리포지토리에 라이선스가 명시되어 있지 않습니다. 필요 시 `LICENSE` 파일을 추가하세요.

## 참고
- `kaist-sleek-CV-master/`는 별도 템플릿 리소스 폴더로, 현재 메인 페이지 로딩에는 직접 사용되지 않습니다.
