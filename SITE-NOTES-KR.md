# SANE 소개 페이지

[English](SITE-NOTES.md)

**SANE: Signal Above Needless Embellishment**를 소개하는 단일 HTML 페이지입니다. 기본 언어는 영어이며 한국어로 전환할 수 있습니다. 2026-09-16에 확인한 공개 SANE 1.0.0 패키지를 바탕으로 작성했습니다. 기존 스킬 파일, 저장소 README, 기존 릴리스 체크섬은 포함하거나 교체하지 않습니다.

## 파일 구성

```text
index.html
assets/
  og-site.png          # 사이트 공유 이미지, 1200 x 630
  og-site.svg          # 같은 디자인의 아웃라인 벡터
  og-repository.png    # GitHub 저장소 공유 이미지, 1280 x 640
  og-repository.svg    # 같은 디자인의 아웃라인 벡터
SITE-NOTES.md
SITE-NOTES-KR.md
SITE-CHECKSUMS.sha256
```

`index.html`에 CSS, JavaScript, 영문/한국어 본문, LITE 지시문 전체, 인라인 파비콘이 들어 있습니다. 설치, 빌드, 프레임워크, 분석 도구, API 키, 원격 폰트, 런타임 fetch, 외부 CDN이 필요하지 않습니다. PNG는 공유 미리보기용이며 실제 본문은 이미지 로딩에 의존하지 않습니다. 서체는 기기에 설치된 영문/한국어 서체와 시스템 대체 서체를 의도적으로 사용합니다. 폰트 파일은 제공하지 않습니다. SVG는 외부 의존성이 없는 아웃라인 벡터이며, 글자도 텍스트 객체가 아니라 경로로 구성되어 있습니다.

## 기존 스킬을 유지하면서 배포하기

`index.html`과 `assets/`의 내용을 **JTech-CO/SANE 저장소 루트**에 추가합니다. 기존 `index.html`이 있다면 교체 전에 확인합니다. `README.md`, `README-KR.md`, `SKILL.md`, LITE 파일, references, adapters, tests, 원래의 `CHECKSUMS.sha256`은 그대로 유지합니다. 안내 문서와 `SITE-CHECKSUMS.sha256`은 배포 시 선택적으로 함께 둘 수 있습니다.

브랜치 기반 GitHub Pages를 사용한다면 **Settings > Pages > Build and deployment > Source > Deploy from a branch**에서 배포할 브랜치와 `/ (root)`를 선택합니다. 기존 Actions 기반 배포 구성이 있다면 같은 정적 파일을 그대로 발행하면 됩니다. 이번 산출물은 저장소나 배포 설정을 직접 변경하지 않았습니다. [GitHub 배포 소스 공식 안내](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

HTML의 배포 기준 주소는 `https://jtech-co.github.io/SANE/`로 설정했습니다. 이는 배포 설정값이지 새 페이지가 이미 공개되었다는 뜻이 아닙니다. 다른 도메인이나 프로젝트 경로에 배포한다면 HTML의 `canonical`, `og:url`, `og:image`, `og:image:secure_url`, `twitter:image`에서 이 기준 주소를 통째로 변경합니다. 공유 미리보기에는 공개적으로 접근 가능한 이미지 주소가 필요하며, 로컬 파일 경로로 대체할 수 없습니다. [Open Graph 규격](https://ogp.me/)

요청문에 붙어 있던 `SANERepo` 주소는 사용 가능한 저장소 연결에서 404가 반환되었습니다. 모든 주요 CTA는 정상 조회된 공개 저장소인 [JTech-CO/SANE](https://github.com/JTech-CO/SANE)으로 연결했습니다. 실제 목적지가 다르다면 HTML의 링크와 스크립트의 저장소 상수를 함께 수정합니다.

## 두 종류의 OG 이미지 적용

**사이트:** `index.html`의 Open Graph 및 Twitter 카드 메타데이터에 `assets/og-site.png`가 절대 주소로 연결되어 있습니다. 제목, 설명, 이미지 크기, MIME 유형, 언어, 이미지 대체 설명이 초기 HTML에 포함됩니다.

**저장소:** `assets/og-repository.png`를 **저장소 Settings > Social preview > Edit > Upload an image**에서 업로드해야 합니다. 이미지를 저장소에 커밋하는 것만으로 GitHub 저장소의 공유 미리보기가 바뀌지는 않습니다. 제공 PNG는 불투명 배경, 1280 x 640 크기, 1 MB 미만입니다. SVG는 벡터 원본이며 GitHub 업로드용 파일은 PNG입니다. [GitHub Social preview 공식 안내](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/customizing-your-repositorys-social-media-preview)

두 OG 이미지는 영문을 기본으로 하며, 페이지와 동일한 짙은 잉크색, 절제된 붉은 강조색, 명확한 글자 위계, 여백을 사용합니다. 직접 제작한 타이포그래피/벡터 구성으로, 모델 결과 화면이나 성능 증명 자료가 아닙니다. 방문자가 본문을 한국어로 바꿔도 한국어 공유 카드가 별도로 제공되는 것은 아닙니다. 단일 정적 HTML 응답의 OG 메타데이터는 영어로 유지됩니다. 크롤러에도 언어별 응답을 보내려면 별도 정적 페이지나 서버 라우팅이 필요하며 이번 단일 파일 범위에는 포함하지 않았습니다.

## 동작

저장된 언어 설정이 없는 첫 방문은 영어로 열립니다. EN/KR 버튼은 본문, 문서 언어, 브라우저 제목/설명, 접근 가능한 이름, 문서 링크, 복사 내용, 예시 문장을 함께 바꿉니다. 허용되는 환경에서는 선택을 `localStorage`의 `sane-site-language` 키에 저장합니다. `?lang=en` 또는 `?lang=ko`가 저장값보다 우선합니다. 저장이나 URL 변경이 차단되어도 예외를 처리하므로 언어 전환 자체는 계속 사용할 수 있습니다. 방문자의 언어 선택 외에는 저장하지 않습니다.

적용 전 / SANE 적용 버튼은 동일한 가상 수치로 만든 두 인터페이스 예시를 전환합니다. 실제 모델 출력이나 벤치마크가 아니라 우선순위의 차이를 설명합니다. 수치는 정시 배송 121건 + 지연 7건 = 전체 128건, 지연 분류 3건 + 4건 = 7건으로 맞추었고, 매출 $9,420 / 128의 평균은 반올림하면 $73.59입니다. 막대의 의미는 텍스트로도 제공합니다.

10개 원칙은 브라우저 기본 `details` 요소로 펼칩니다. 시작하기 영역에는 키보드로 사용할 수 있는 대화 · Astra, Codex, Claude Code 탭이 있습니다. 대화 탭은 선택한 언어의 LITE 원문 전체를 복사하고, 네이티브 에이전트 탭은 패키지 설치가 선행되었다는 전제의 호출문을 복사합니다. 상세 설치 방법은 원본 저장소의 문서로 연결됩니다.

클립보드 권한이 없거나 API가 제공되지 않으면 텍스트가 선택된 직접 복사 대화상자를 엽니다. 실패한 복사를 성공했다고 표시하지 않습니다. 모션 감소 설정에서는 부드러운 스크롤을 끕니다. JavaScript가 꺼져도 영문 본문, 원문 링크, 원칙, 전체 영문 LITE를 읽을 수 있습니다. 언어 전환, 전후 비교 버튼, 탭, 복사 버튼에는 JavaScript가 필요합니다.

## 출처와 유지보수

페이지는 저장소의 [SKILL](https://github.com/JTech-CO/SANE/blob/main/SKILL.md), [README](https://github.com/JTech-CO/SANE/blob/main/README.md), [호스트 적용 가이드](https://github.com/JTech-CO/SANE/blob/main/adapters/USAGE.md)를 따릅니다. 자동 동기화 클라이언트가 아니라 고정된 문서 스냅샷입니다. 내장된 EN/KR LITE 텍스트는 저장소에서 반환된 아래 blob ID와 대조했습니다.

```text
LITE.md     90e69598aa19e5586d12c8287ba35ced79dd7fc6
LITE-KR.md  20b0b29ec1228018c4f079c7f1ef12f13d523733
SKILL.md    b581fa1c8e8873861ce06cb2e9dc6523550ae3df
```

LITE가 바뀌면 `sane-lite-source` JSON과 정적으로 포함된 영문 `lite-preview` 내용을 함께 수정합니다. 지시문 자체를 임의로 바꾸지 말고, 양쪽 언어와 복사 결과를 다시 확인합니다. 네이티브 로더 안내는 원본 프로젝트를 연결하는 정보이며 모든 미래 버전의 도구 지원을 보장하지 않습니다. 원래 SANE 저장소의 라이선스와 제3자 출처 표기를 유지합니다. 출발점이 된 원문 아티클을 복제해 넣지는 않았습니다.

## 실제 검증 범위

최종 검증에서 **통과 212개, 실패 0개**를 기록했습니다. 대부분은 화면 크기와 상태를 바꾼 반복 검증이며, 독립적인 모델 벤치마크 수가 아닙니다. **Chromium 144.0.7559.96**와 Playwright의 문서 주입 방식(`page.set_content`)으로 화면과 동작을 확인했습니다. 320, 360, 390, 768, 1024, 1280, 1440, 1920 CSS 픽셀에서 두 언어와 전후 비교 상태, 네이티브 에이전트 탭을 확인했습니다. 390, 768, 1440 CSS 픽셀에서는 루트 글자 크기를 200%로 높여도 페이지 전체가 가로로 넘치지 않는지 확인했습니다. 데스크톱과 모바일 크기 스크린샷도 시각적으로 검토했습니다.

검증한 항목은 탭 키보드 조작, Enter로 원칙 펼치기, 직접 복사 대화상자의 실제 선택/Escape/포커스 복귀, 양쪽 언어의 정확한 LITE 본문, 언어별 링크, JavaScript 비활성 폴백, 모션 감소, 고유 ID와 내부 앵커, 처리되지 않은 JavaScript 오류 부재, SVG 의존성, 이미지 크기/형식/용량, 정적 메타데이터입니다. Python HTTP 읽기로 HTML과 PNG 2종이 원본 파일과 바이트 단위로 동일하게 전달되는지도 확인했습니다.

선택한 주요 글자색/배경색 대비는 다음과 같습니다. 전체 접근성 감사나 인증을 의미하지는 않습니다.

| 조합 | 계산된 대비 |
| --- | ---: |
| 본문 / 기본 배경 | 14.46:1 |
| 보조 글자 / 기본 배경 | 6.08:1 |
| 흰 CTA 글자 / 강조색 배경 | 5.68:1 |
| 강조색 글자 / 기본 배경 | 5.38:1 |
| 푸터 보조 글자 / 짙은 배경 | 9.37:1 |

**미검증:** 이 환경에서 시험한 로컬 HTTP 주소와 로컬 `file://` 주소로의 브라우저 직접 탐색은 `ERR_BLOCKED_BY_ADMINISTRATOR`로 차단되었습니다. 따라서 브라우저는 빈 문서에 HTML을 주입해 검사했으며, Python HTTP 검사를 브라우저 탐색 검사로 간주하지 않았습니다. 실제 Clipboard API 쓰기와 브라우저 저장소의 네이티브 영속성은 확인할 수 없었고, 성공 분기는 명시적인 테스트 대역으로 확인했습니다. 실제 URL 이동, 파일 다운로드, 다른 브라우저 엔진, 물리 기기, Pages 배포, GitHub Social preview 업로드, 외부 SNS 크롤러 수집은 완료하지 않았습니다. 배포 후 실제 접속 검증을 대체하는 결과가 아닙니다.
