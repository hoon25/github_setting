# github setting

### branch 관리 전략

**Gitlab-Flow**와 유사한 전략 사용

- Feature
  - 기능 개발 Branch
  - `feat/#issue_number`
- Develop
  - Feature Branch의 병합된 기능 Test
  - `develop/#issue_number`
- Master
  - Deploy Branch
  - `master/#issue_number`

### commit 규칙

1. 제목과 본문을 빈 행으로 구분한다
2. 제목을 50글자 내로 제한
3. 제목 첫 글자는 대문자로 작성
4. 제목 끝에 마침표 넣지 않기
5. 제목은 명령문으로 사용하며 과거형을 사용하지 않는다
6. 본문의 각 행은 72글자 내로 제한
7. 어떻게 보다는 무엇과 왜를 설명한다

```
feat : 새로운 기능에 대한 커밋
fix : 버그 수정에 대한 커밋
build : 빌드 관련 파일 수정에 대한 커밋
chore : 그 외 자잘한 수정에 대한 커밋
ci : CI관련 설정 수정에 대한 커밋
docs : 문서 수정에 대한 커밋
style : 코드 스타일 혹은 포맷 등에 관한 커밋
refactor :  코드 리팩토링에 대한 커밋
test : 테스트 코드 수정에 대한 커밋
```

commit 예시

```
feat: Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Resolves: #123
See also: #456, #789
```



### PR 규칙

- 신규개발 건은 `develop` 을 base로 `feature/#이슈번호` 의 브랜치명으로 생성 후 작업한 다음 PR을 날립니다.
- 아직 개발 진행 중이라면 `In Progress` 라벨을 달고, 코드리뷰가 필요한 경우 `Asking for Review` 라벨을 답니다. 리뷰 후 리팩토링이 필요하다면 추가로 `refactoring` 라벨을 달아 진행합니다.
- 모든 PR은 반드시 지정한 리뷰어에게 코드리뷰를 받아야만 합니다.
- 리뷰어 중 1명 이상의 `Approve` 를 받아야 `Merge pull request` 를 할 수 있습니다.
- `commit` 을 할 때마다 Jenkins CI가 자동으로 실행되며 단위테스트, 통합테스트에 모두 통과되어야 `Merge pull request`가 가능합니다.





