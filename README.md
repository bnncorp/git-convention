# BNN Git commit convention

1. [Issue Types](#issue-types)
2. [Issue Title Rules](#issue-title-rules)
3. [Commit Message Rules](#commit-message-rules)

---

## Issue Types
|유형|설명|작성대상|
|----|-----------|------|
|UI|디자인 완료 시 퍼블리싱 작업을 시작해도 괜찮음|디자이너|
|Style|간단한 퍼블리싱 수정|개발자, 디자이너|
|Feature|신규 기능 추가|개발자|
|Refactor|성능 개선|개발자|
|Bug|문제 발생|All|
|Hotfix|문제 발생(긴급)|All|
|Question|질문|All|

---

## Issue Title Rules
1. 이슈 생성 시 제목은 [`유형`]을 먼저 기입하여야 한다
(e.g. [UI] 메인페이지 디자인 완료)
2. `유형`은 [PascalCase](https://www.freecodecamp.org/news/snake-case-vs-camel-case-vs-pascal-case-vs-kebab-case-whats-the-difference/#pascal-case)로 작성한다.
단, `유형`이 두 자리인 경우에는 전부 대문자로 작성한다
3. 단순 수정이나 공개적으로 이슈를 등록할 필요가 없는 건은 **커밋**으로 바로 등록한다

---

## Commit Message Rules
1. Bug, Hotfix 유형의 경우에는 접두사로 `Fix`를 사용하여 이슈를 닫고, 이외의 경우는 `Close`를 사용하여 닫는다
2. 이슈를 닫지 않고 참조하는 경우는 `Ref`를 사용하여 참조한다
3. 여러 개의 이슈를 처리하는 경우에는 아래와 같이 처리한다
```bash
git commit -m "Close #1, close #2, fix #3, ref #4"
```
