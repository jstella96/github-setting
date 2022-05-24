# Github Repository 초기 설정

**목표: 반복작업 단순화, 일관된 설정 사용**

- Github Label 설정
- Issue Template 설정
- Puul Request Template 설정
- 내 초기 설정

# Github Label 설정

1. Github 액세스 토큰 발급

- [토큰발급 링크](https://github.com/settings/tokens)
- `scopes`에서 repo 전체 선택

2. 라벨 정의

- `json` 파일에 JSON Array 형태로 정의

```json
[
  {
    "name": "feature", //라벨이름
    "color": "FBCA04", //색상코드
    "description": "새로운 기능 추가" //라벨설명
  }
]
```

3. 라벨 repo에 적용

- `.json` 파일이 있는 위치에서 아래 명령어 실행

```sh
npx github-label-sync --access-token [액세스 토큰] --labels [라벨 파일이름] [계정명]/[저장소 이름]
```

# Issue Template 설정

`Issues` 탭에서 새로운 이슈 생성시, 미리 정의 된 이슈 템플릿 사용하기

1. 적용하려는 repo 최상단에 `.github` 폴더 생성 후 해당 폴더 내부에 `ISSUE_TEMPLATE` 폴더 생성,
   `ISSUE_TEMPLATE` 안에 있는 md파일들이 각각의 템플릿으로 나타남

2. ## Issue Template 정의

- 마크다운 형식으로 파일 생성
- labels은 위에서 정의한 라벨의 이름

```markdown
---
name: 버그 템플릿
about: 버그 발생시 사용하는 템플릿입니다.
title: ""
labels: "bugfix, feature"
assignees: ""
---

# ⚠️ 버그 위치

# ⚡️ 버그 증상

# 🧐 재현 방법

# 📸 스크린샷(선택)
```

3. 추가 된 파일을 github 원격에 push

# Puul Request Template 설정

1. 적용하려는 repo 최상단에 `.github` 폴더 생성
2. `.github` 폴더 내부에 `PULL_REQUEST_TEMPLATE.md` 생성

```md
# 📑 개요

# 📎 관련 이슈

[이슈이름] [#이슈번호]

# 💬 작업 내용

# 🚧 PR 특이 사항
```

3. 마크다운으로 템플릿 작성 후 push

# 내 초기 설정

- 라벨 `./label/basic-label.json` 기본사용
- 템플릿
