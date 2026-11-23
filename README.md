# ask-me

**용어를 몰라도 원하는 걸 만들게 해 주는 AI 인터뷰 스킬** (Claude Code · Agent Skills)

"홈페이지 하나 만들어 줘, 요즘 느낌으로…"
사람은 원하는 게 머릿속에 있어도 **이름을 몰라서** 말하지 못합니다. 헤더, CTA, 반응형 같은 말을 모르니 애매하게 말할 수밖에 없죠. 설명은 못 해도, 보면 "이거요"는 할 수 있습니다.

`ask-me`는 AI가 그 분야 전문가처럼 **무엇을 정해야 하는지 먼저 떠올리고**, 사용자에게는 **쉬운 말 + 구체적인 보기**로 하나씩 물어서, 애매한 요청을 명확한 작업 지시서로 바꿉니다.

> ⚠️ 초기 버전입니다. 실제 사용 후기를 받아 다듬는 중입니다.

## 무엇이 다른가

- **쉬운 말로 묻고, 전문용어로 기록합니다.** "맨 위에 늘 붙어 있는 메뉴 줄"로 묻고 → "고정 헤더(sticky header)"로 적습니다. 사용자는 용어를 덤으로 배웁니다.
- **고르기만 하면 됩니다.** 질문마다 겹치지 않는 보기 2~4개 + AI 추천안 + "이 답에 따라 무엇이 달라지는지"를 붙입니다. Claude Code에서는 질문 카드와 화면 모형 미리보기로 띄웁니다.
- **"그런 느낌 알지?"에 대처합니다.** 말로 더 캐묻지 않고, 예시 보여 달라기 → 싫은 것 묻기 → 예전 결과물에서 뽑기로 취향을 끌어낸 뒤 확인받습니다.
- **초보가 놓치는 걸 알려 줍니다.** 흔한 함정, 잘된 예, 전문가라면 했을 질문을 보여 줍니다.
- **AI가 찾을 수 있는 건 묻지 않습니다.** 사실 확인은 AI가 하고, 사용자에게는 취향·목적·우선순위 같은 결정만 묻습니다.
- **필요 없으면 끼어들지 않습니다.** 요청이 이미 명확하면 바로 만들고, 질문은 5개 안팎으로 끝냅니다. "그냥 만들어"라고 하면 언제든 멈춥니다.
- **정리를 두 벌로 줍니다.** 내가 읽는 쉬운 말 정리 + AI·개발자에게 그대로 넘길 전문용어 작업 지시서.

홈페이지만이 아니라 발표 슬라이드, 포스터, 문서, 엑셀, 영상 등 어떤 AI 산출물에도 씁니다.

## 대화 예시

```
나: 홈페이지 하나 만들고 싶어, 요즘 느낌으로

AI: 이해: 무언가를 소개하는 홈페이지 · 확신도 15% — 무엇을, 누구에게, 보고 나서 뭘 하길 바라는지 모름

    일단 이렇게 만들 생각입니다
    - 휴대폰에서도 깨지지 않는 한 페이지
    - 맨 위: 큰 사진 + 한 줄 소개 + 버튼 하나
    - 가운데: 소개 3~4덩어리 / 맨 아래: 연락처

    Q. 이 홈페이지를 본 사람이 결국 뭘 했으면 좋겠어요?
    (질문 없이 바로 만들어도 돼요 — "그냥 만들어"라고 하시면 위 초안대로 갑니다)

나: 우리 동아리 신입 모집이야

AI: Q. 첫 화면에서 제일 크게 보여야 할 건 뭐예요?
       왜 묻나: 이걸로 맨 위 구성이 정해져요
       ① 활동 사진 크게 + "지원하기" 버튼
       ② "이런 사람 찾아요" 문구 크게
       ③ 모집 마감일 카운트다운
       → 추천: ① — 신입은 분위기를 보고 결정하는 경우가 많아요
       (기록용 용어: 히어로 섹션 · 주요 행동 유도 버튼(CTA))
```

## 설치

**Claude Code**

```bash
npx skills add dragonmiin/ask-me
```

또는 직접 복사합니다.

- `skills/ask-me/SKILL.md` → `~/.claude/skills/ask-me/SKILL.md` (모든 프로젝트에서 사용)
- 특정 프로젝트에서만 쓰려면 → `<프로젝트>/.claude/skills/ask-me/SKILL.md`

**claude.ai**: `skills/ask-me` 폴더를 zip으로 묶어 설정의 스킬 메뉴에서 업로드합니다.

**다른 에이전트**(Codex 등): Agent Skills 형식(SKILL.md)을 읽는 도구라면 그 도구의 스킬 폴더에 넣습니다. 질문 카드가 없는 도구에서는 글자 보기로 동작합니다.

## 사용법

- `/ask-me 동아리 홈페이지 만들고 싶어`
- 또는 평소처럼 말하면서 "만들기 전에 캐물어 줘", "뭘 정해야 하는지 모르겠어"
- 요청이 애매하면 스스로 켜지기도 합니다.

## 출처와 감사

아래 스킬들을 읽고 좋은 아이디어를 모아 **새로 썼습니다**(원문 복사 없음).

| 스킬 | 가져온 아이디어 |
|---|---|
| [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) `interview-me` | 가설 + 확신도, 한 번에 하나, 범위 밖 항목, 명시적 "네" |
| [mattpocock/skills](https://github.com/mattpocock/skills) `grilling` | 추천 답, 사실은 AI가 찾고 결정만 사용자에게 |
| [obra/superpowers](https://github.com/obra/superpowers) `brainstorming` | "왜"는 열린 질문으로, 실패 조건(anti-goals), 빠져나갈 길 |
| [riiiku/clarify-skill](https://github.com/riiiku/clarify-skill) | 모호어 쪼개기, 말로 못 하는 취향 끌어내기 |
| [Neeeophytee/finding-unknowns-skills](https://github.com/Neeeophytee/finding-unknowns-skills) | 초보 사각지대, 영향 큰 순서로 묻기 |
| [angel291592/Intent-Router](https://github.com/angel291592/Intent-Router) | 개입 여부 판단, 질문 예산, 되돌릴 수 없는 결정은 위임 거부 |
| [anthropics/launch-your-agent](https://github.com/anthropics/launch-your-agent) | 확인 가능한 합격 기준, 큰 일은 1단계만 |
| [Q00/ouroboros](https://github.com/Q00/ouroboros) | 미정 항목을 답 / 가정 / 차단으로 분류 |
| [ziguishian/premium-ui-builder-skill](https://github.com/ziguishian/premium-ui-builder-skill) | 사용자가 용어를 모른다고 가정, 진단 문장 |

## 라이선스

MIT
