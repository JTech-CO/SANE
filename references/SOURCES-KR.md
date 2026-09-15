# 출처와 해석 경계

[English](SOURCES.md) | [처음으로](../README-KR.md)

참고자료 확인일: **2026-09-15**. URL은 이번 릴리스에서 확인한 자료이며 호스트 동작은 바뀔 수 있다. 연결된 자료를 패키지에 복제하거나 재라이선스하거나 공식 보증으로 제시하지 않는다.

## 출발 자료

**R01. Adam Kucharski, 2026년 9월 2일.** [Ten reasons your vibe-coded dashboard looks terrible](https://kucharski.substack.com/p/ten-reasons-your-vibe-coded-dashboard).

사용자가 한국어로 열 가지 문제를 요약하고 실행 가능한 디자인 계약을 요청했다. 이 요약이 SANE의 직접적인 입력이며 원문은 출처와 맥락을 확인하기 위해 열람했다. SANE은 독립적인 응용 결과이지 아티클의 번역·복제본이 아니다. 원문의 미적 판단은 특정 서체, 다크모드, 모든 AI 대시보드가 나쁘다는 과학적 증명이 아니다.

사용자의 순서를 유지했다. S01=원문 1, S02=2, S03=10, S04=3, S05=4, S06=5, S07=6, S08=7, S09=8, S10=9.

## 패키징과 호스트 동작

**R02. Agent Skills.** [Specification](https://agentskills.io/specification).

소문자 폴더명과 메타데이터 이름의 일치, YAML `name`·`description`, `SKILL.md` 진입점, 필요할 때만 읽는 참고자료 구성의 근거이다. 형식 준수가 모든 호스트의 지원을 보장하지는 않는다.

**R03. OpenAI.** [Build skills](https://developers.openai.com/codex/skills/). 확인 시 [ChatGPT Learn](https://learn.chatgpt.com/docs/build-skills)으로 연결되었다.

Codex의 `.agents/skills` 위치와 `$`·`/skills` 선택 방식의 근거이다. 문서는 독립형 스킬과 플러그인 배포를 구분한다. 이 릴리스는 ChatGPT 플러그인을 배포하거나 설치하지 않는다.

**R04. Anthropic.** [Extend Claude with skills](https://code.claude.com/docs/en/skills).

Claude Code의 프로젝트·개인 `.claude/skills` 경로와 `/sane` 방식 호출의 근거이다. 다른 Claude 화면은 로딩·계정 설정이 다를 수 있다.

**R05. OpenAI, Eric Provencher, 2026년 9월 11일.** [Rethinking skills and prompts for GPT-6 Astra](https://learn.chatgpt.com/blog/rethinking-skills-and-prompts-for-gpt-6-astra).

좁은 적용 범위의 설명, 필요한 자료만 읽기, 불필요한 절차 지침 줄이기를 제안한다. SANE의 LITE는 이 방향에 맞춘 설계이지 Astra의 실험적으로 입증된 최적 프롬프트도, 스킬이 쓸모없어졌다는 주장도 아니다.

## 접근성 참고자료

아래는 개별 WCAG 2.2 기준에 대한 W3C의 **Understanding 해설**이다. REVIEW의 일부 수치 점검을 뒷받침하지만 전체 규범 표준이나 준수 평가를 대체하지 않는다.

**R06. W3C.** [Understanding SC 1.4.3: Contrast (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html). 글자 대비와 큰 글자의 구분.

**R07. W3C.** [Understanding SC 1.4.11: Non-text Contrast](https://www.w3.org/WAI/WCAG22/Understanding/non-text-contrast.html). 관련 컨트롤·상태·그래픽 정보이며 모든 장식 테두리가 대상인 것은 아님.

**R08. W3C.** [Understanding SC 1.4.4: Resize Text](https://www.w3.org/WAI/WCAG22/Understanding/resize-text.html). 200% 글자 확대 검사와 적용 범위.

**R09. W3C.** [Understanding SC 1.4.10: Reflow](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html). 320 CSS px 조건과 본질적인 2차원 레이아웃 예외.

**R10. W3C.** [Understanding SC 2.5.8: Target Size (Minimum)](https://www.w3.org/WAI/WCAG22/Understanding/target-size-minimum.html). 24px 대상 기준과 예외이며 더 큰 편의상 권장값과는 구분.

## 인터페이스·데이터 시각화 지침

**R11. IBM Carbon Design System.** [Axes and labels](https://carbondesignsystem.com/data-visualization/axes-and-labels/).

명확한 수량·단위, 정직한 축 선택, 알아볼 수 있는 시간 간격, 보이는 결측 구간을 뒷받침한다. 빈 차트 영역 자체가 관측치를 바꾸거나 축을 왜곡할 이유는 아니다.

**R12. IBM Carbon Design System.** [Data table: usage](https://carbondesignsystem.com/components/data-table/usage/).

구조적인 표 상호작용과 유용한 표 기능 선택을 위한 참고자료이다. SANE은 Carbon, 해당 테마, 모든 선택적 표 기능을 채택하도록 요구하지 않는다.

**R13. GOV.UK Design System.** [Typeface](https://design-system.service.gov.uk/styles/typeface/).

새로움보다 서비스 맥락과 브랜드 사용 조건에 따라 타이포그래피를 정하는 사례이다. GDS Transport 재배포 권한을 부여하는 자료가 아니며 SANE은 폰트를 포함하지 않는다.

## 라이선스 참고

**R14. SPDX.** [MIT License](https://spdx.org/licenses/MIT.html).

새로 작성한 패키지 본문에 사용하는 라이선스 문구의 참고자료이다. 한국어 문서는 참고용이며 영문 라이선스가 우선한다. 외부 자료에는 각각의 조건이 유지된다.

## SANE 자체의 판단은 무엇인가?

1rem·0.875rem 시작 크기, 소수의 토큰 개수, 예시 간격·모서리 척도, 더 큰 조작 권장 크기, 첫인상 점검, 차단 결함 분류, 행동 검증 사례는 독립적으로 정한 조정 가능한 프로젝트 기준이다. WCAG 규정을 그대로 옮긴 것도 아니고 하나의 미학이 객관적으로 우월하다는 근거도 아니다.

범용 붙여 넣기는 지시문 전달 방식이다. ChatGPT·Codex·Claude·Claude Code·Grok·DeepSeek·로컬 모델이 동일하게 동작한다는 벤치마크는 제공하지 않는다. 공식 문서로 확인한 어댑터 외의 네이티브 연동 상태는 단정하지 않는다. [릴리스 검증](../tests/RELEASE-CHECK-KR.md)을 참고한다.
