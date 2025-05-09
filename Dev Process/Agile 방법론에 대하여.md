# Agile 방법론?
> Agile은 반복적이고 점진적인 개발을 통해 고객 가치를 빠르게 전달하는 소프트웨어 개발 방식이다.

애자일은 일련의 규정이 아닌, 협업과 워크플로우를 바라보는 **하나의 관점**이자 선택을 안내하는 가지 체계이다.

핵심은 소프트웨어의 작은 구성 요소를 **신속하게 제공하여 고객의 만족도를 개선**하는 것이다.

## 애자일(agile) 개념 및 핵심 가치 확인하기

> 애자일은 기존의 워터폴(Waterfall) 방식의 프로젝트 관리에 대응하여, `애자일 소프트웨어 개발에 대한 선언문(The Manifesto For Agile Software Development)`을 작성했다.

**4가지 주요 특성**
- **개인과 개인 간의 상호작용**이 프로세스 및 툴보다 우선
- **작동하는 소프트웨어**가 포괄적인 문서보다 우선
- **고객과의 협업**이 계약 협상보다 우선
- **변화에 대응**하는 것이 계획을 따르는 것보다 우선

> 주요 특성을 살펴보면'고객에게 서비스를 신속하게 제공하여 만족도를 개선한다'는 애자일의 핵심 가치에 중점을 두는 것을 알 수 있다.

## User Story: 사용자 스토리
> User Story는 **사용자의 관점**에서 작성한 기능에 대한 설명이다. 목적은 소프트웨어 기능이 고객에게 가치를 제공하는 방법을 명확히 설명하는 것이다.

사용자 스토리는 애자일 프레임워크에서 가장 작은 작업 단위이다.
사용자 관점에서 표현한 최종 목표이며, **기능을 통해 달성하려는 가치에 초점을 둔다.**

> 사용자 스토리는 최종 사용자 또는 고객의 관점에서 작성한 소프트웨어 기능에 대한 일반적인 비공식 설명이다.

**사용자 스토리의 목적**
- 어떤 작업이 고객에게 특정 가치를 제공하는 방법을 명확히 설명하는 것
- '고객'은 전통적인 의미에서 외부 최종 사용자일 필요는 없으며 조직 내에서 팀에 의존하는 동료 또는 내부 고객일 수도 있음

![](https://velog.velcdn.com/images/pp8817/post/472c2e88-2355-479c-901b-cde11f7e6f6c/image.png)

사용자 스토리는 **칸반(Kanban)과 스크럼(Scrum)** 같은 애자일 프레임워크에서 핵심적인 작업 단위로 사용된다.

## 칸반(Kanban) 방법론
- 프로세스의 연속적인 흐름을 유기적, 시각적으로 만들어 전체 프로세스를 유연하게 만드는 방법론
- 제약 이론(TOC: Theory of constraints)의 당김 방식(Puling system)에서 착안
- WIP(Work In Process)를 통해 개발 프로세스에 병목 현상이나 지나친 업무 쫄림을 방지

**핵심 특성**
- 업무 흐름의 시각화
- 진행 중 업무 제한
- 흐름 측정 및 관리
- 명시적 프로세스 정책 수립

![](https://velog.velcdn.com/images/pp8817/post/b4b50f98-0396-4dd8-8b1f-0a7eecff9473/image.png)
> 출처: https://brunch.co.kr/@kbhpmp/134

**칸반 보드 기본 형태**
- 칸반 보드는 기본적으로 계획(To-Do), 진행 중(Doing), 완료(Done)의 형태를 사용
- 기본적으로 아래 사진과 같으나, 변경하여 사용 가능

![](https://velog.velcdn.com/images/pp8817/post/e91d17ef-3b6e-45ee-a81b-d9838947ad0f/image.png)

## 스크럼(Scrum)
스크럼은 반복적이고 점진적인 방식으로 제품을 개발하기 위한 애자일 프레임워크 중 하나로
- `프로덕트 백로그 -> 스프린트 플래닝 -> 스프린트 백로그 -> 데일리 스크럼 -> 스프린트 리뷰 -> 프로덕트 릴리즈 -> 스프린트 회고`

의 과정을 일정한 주기로 반복하는 것을 의미하며, 주기가 완료될 때마다 고객에게 가치 있는 제품(소프트웨어)을 전달하는 방식이다.

**스크럼의 3가지 기둥**
- 투명성(transparency): 프로세스와 작업의 결과를 받는 사람들만 아니라 작업을 수행하는 사람들에게 시각적 고유
- 점검(Inspection): 바람직하지 않은 편차나 문제점들을 감지하기 위해, 스크럼의 산출물들과 합의된 목표를 과정을 꼼꼼히 점검
- 조정(Adapatation): 공정의 어떤 부분이 허용 한계를 벗어나거나 결과의 제품이 인수할 수준이 안 될 경우, 적용되는 공정 또는 작업의 산출물을 조정

**스크럼의 5가지 가치**
- 확약(Commitment): 약속한 것을 확실히 실현하는 것
- 집중(Focus): 확약한 것의 실현에 전념하는 것
- 개방성(Openness): 어떤 것이 자신에게 불리해도 숨기지 않는 것
- 존중(Respect): 자신과 다른 사람에게 경의를 표하는 것
- 용기(Courage): 자심이 옳은 일을 할 수 있도록 팀원 간 갈등과 도전을 통해 작업할 수 있는 용기

**스크럼 절차**
- **스프린트(Sprint)**
    - 주기: 1~4주 이내를 권장
    - **스프린트 계획(Sprint Planning), 일일 스크럼(Daily Scrums), 스프린트 리뷰(Sprint Review) 및 스프린트 회고(Sprint Retrospective)를 포함**하여 제품 목표(Product Goal)를 달성함에 필요한 모든 작업이 스프린트 동안 이루어진다.
- **스프린트 계획(Sprint Planning)**: 스크럼 팀 전체의 공동 작업을 통해 스프린트 기간 동안 수행할 제품 백로그 및 스프린트 백로그 도출
- **일일 스크럼(Daily Scrums)**: 매일 정해진 시간에 팀원 모두가 모여 '어제 한 일, 오늘 할 일, 이슈 사항'을 공유를 통해 업무 진행 사항을 확인
- **스프린트 리뷰(Sprint Review)**: 스프린트 기간 동안 완료한 작업의 결과물을 이해관계자들에게 제공 또는 데모하여 진행 상황을 논의

> **정리**
>
> 스크럼은 **점진적 개발을 위한 기간(1~4주)을 설정**한 후 해당 기간 동안 스크럼 팀 모두가 스크럼 절차를 함께 수행하여 **고객에게 가치 있는 증분(Increment) 된 제품을 인도**하고, 스프린트를 반복 수행하여 **최종적으로는 완성된 제품을 제공**하는 것

### 칸반과 스크럼
**연관성**
- 칸반과 스크럼은 모두 프로세스 도구

**스크럼은 칸반보다 규범적이다.**
- 스크럼: 프로덕트 백로그, 스프린트 플래닝, 스프린트 백로그, 데일리 스크럼, 스프린트 리뷰, 프로덕트 릴리즈, 스프린트 회고
- 칸반: 작업 흐름 시각화, WIP 개수 제한, 리드타임 측정 및 프로세스 최적화

## 다시 사용자 스토리로 돌아와서
스토리는 위에서 소개한 칸반과 스크럼과 같은 애자일 프레임워크와 잘 어울린다.
스크럼에서는 사용자 스토리가 스프린트에 추가되고, 스프린트 기간 동안 소진되며 번다운 차트에 반영된다.

칸반 팀은 사용자 스토리를 백로그로 가져와서 워크플로를 통해 실행한다. 사용자 스토리에 대한 이 작업은 스크럼 팀이 추정 및 스프린트 계획을 더 잘 수행할 수 있도록 도와주고, 예측의 정확도와 민첩성을 한층 더 향상할 수 있다.

**✅ 사용자 스토리 - 스크럼 - 칸반의 관계**
- 사용자 스토리는 **애자일 팀의 작업 단위**
    - 사용자의 입자에서 작성된 요구사항 또는 가치 중심 설명
    - Ex. 학생으로서, 나의 성적을 한눈에 볼 수 있으면 좋겠다.

---

🔁 스크럼과 사용자 스토리
- 사용자 스토리 → 프로덕트 백로그에 정리됨
    - 스프린트마다 우선순위 높은 스토리들이 Sprint Backlog로 이동
    - Sprint 동안 스토리를 해결하며, 하루하루 번다운 차트로 진행도를 추적

📌 스크럼에서는 사용자 스토리가 Sprint라는 시간 단위의 틀 안에서 관리
→ 예측 가능한 반복 주기와 정기적인 리뷰/회고가 강점

---

🔁 칸반과 사용자 스토리
- 칸반은 고정된 기간 없이, 작업 흐름 자체에 집중
    - 사용자 스토리는 백로그 → 진행 중 → 완료의 흐름에 따라 칸반 보드를 통해 이동
    - **작업 수(WIP)**를 제한해 지속적 흐름과 품질을 유지함

📌 칸반에서는 사용자 스토리를 유연하고 시각적으로 처리하며 흐름을 최적화
→ 병목 지점 파악이나 팀 속도 확인에 강점

## Story Point
> Story Point는 사용자 스토리의 크기(난이도 + 복잡도 + 위헙도)를 상대적으로 수치화 한 것

**왜 '시간' 대신 Story Point를 사용할까?**
- 실제 걸리는 시간은 **사람마다 다르고 예측하기 어려움**
- 반면 Story Point는 **과거 경험 기반의 상대적 크기 추정**으로 더 안정적인 예측 가능

> 시간이 아니라 '얼마나 복잡하고 어려운가'에 따라 점수를 매김
- 로그인 기능: 2 포인트
- 이메일 인증 + 비밀번호 찾기: 5 포인트
- 성적 그래프 시작화: 8 포인트

---------
**산정 방식**
보통 아래와 같은 방식으로 산정
- **피보나치 수열 (1, 2, 3, 5, 8, 13)**: 차이를 점점 크게 느끼게 하려는 목적
- **T-shirt 사이즈 (S, M, L, XL)**: 간단하게 크기 비교할 때
- **플래닝 포커(Planning Poker)**: 팀원이 각자 점수 카드로 투표 후 토론하며 합의

**사용 목적**
- 팀이 스프린트마다 몇 Story Point 정도 처리 가능한지(=속도, Velocity) 파악 가능
- 예측 가능한 일정 수립에 도움 (예: "우린 보통 1스프린트에 20pt 처리해")

---------
**출처**
https://www.redhat.com/ko/topics/devops/what-is-agile-methodology