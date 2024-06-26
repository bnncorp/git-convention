# BNN Git convention

1. [Issue types](#issue-types)
2. [Issue title rules](#issue-title-rules)
3. [Commit message rules](#commit-message-rules)
4. [Branch rules](#branch-rules)

---

## Issue types
|<a id="commit-type" href="#commit-type">유형</a>|<a id="commit-shortening" href="#commit-shortening">커밋 약어</a>|설명|작성대상|
|---|-------|---|------|
|UI|ui|디자인 완료|디자이너|
|Style|style|퍼블리싱 수정|개발자, 디자이너|
|Types|types|인터페이스, 타입 추가/변경/삭제|개발자|
|Format|format|코드 정리|개발자|
|Feature|feat|신규 기능 추가|개발자|
|Refactor|refact|성능 개선|개발자|
|Chore|chore|빌드 설정, 라이브러리 업데이트 등|개발자
|Bug|bug|문제 발생|All|
|Hotfix|hotfix|문제 발생(긴급)|All|
|Question|question|질문|All|
|Document|docs|문서|All|

---

## Issue title rules
- 이슈 생성 시 제목 접두사는 "1-1. 메인페이지"과 같이 페이지명(마일스톤명)으로 사용한다
(e.g. 1-1. 메인페이지 / 배너 디자인 수정)
- 유형은 [PascalCase](https://www.freecodecamp.org/news/snake-case-vs-camel-case-vs-pascal-case-vs-kebab-case-whats-the-difference/#pascal-case)로 작성한다.
단, 유형이 두 자리인 경우에는 전부 대문자로 작성한다
- 단순 수정이나 공개적으로 이슈를 등록할 필요가 없는 건은 **커밋**으로 바로 등록한다

---

## Commit message rules
- Bug, Hotfix 유형의 경우에는 접두사로 `Fix`를 사용하여 이슈를 닫고, 이외의 경우는 `Close`를 사용하여 닫는다
- 이슈를 닫지 않고 참조하는 경우는 `Ref`를 사용하여 참조한다
- 여러 개의 이슈를 처리하는 경우에는 아래와 같이 작성한다
```bash
git commit -m "Close #1, close #2, fix #3, ref #4"
```
- 이슈에 등록되지 않은 커밋의 메시지 접두사는 "[커밋 약어](#commit-shortening): "로 사용한다
(e.g. feat: 오타 수정)
- 참조와 메시지 전달 모두 복합적으로 처리해야하는 경우 아래와 같이 작성한다
```bash
git commit -m "Ref #5
hotfix: 심각한 문제 해결
bug: 심각한 문제와 더불어 함께 처리 된 기능"
```

---

## Branch rules
- 브랜치는 기능단위로 생성 후 `dev` 브랜치에 `rebase and merge`한다
```bash
git switch feat/31
git rebase dev

git switch dev
git merge feat/31
```
- 브랜치명은 `커밋 약어/이슈번호` 또는 `커밋 약어/기능 간략 설명`으로 생성한다
(e.g. feat/31 or hotfix/build-error)
