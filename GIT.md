## GIT 정복하기

[1장: 명령들](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

[2장: 버전 관리](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

[3장: 깃과 브랜치](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

[4장: 저장소](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

[5장: 협업](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

[6장: 깃허브로 소통](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

[블로그 만들기](https://www.notion.so/ddc3a0ceb17943048acfc1ea89b36ab2)

------

# 1장: 필수 명령

## 깃의 쓰임새

### 1. 버전 관리

- 문서 수정 시 언제 수정했는지, 어떤 것을 변경했는지 편하고 구체적으로 기록하기 위한 버전 관리 시스템

### 2. 백업하기

- 현재 컴퓨터에 있는 자료를 다른 컴퓨터에 복제
- 깃의 원격 저장소, 온라인 저장소 → 깃허브

### 3. 협업하기

- 여러 사람이 함께 일할 수 있다
- 누가 어느 부분을 어떻게 수정했는지 기록이 남아서 나중에 오류가 생겼을 시 파악하기 쉽다

## 깃 프로그램 종류

- 깃을 편리하게 사용할 수 있도록 하는 프로그램 (=깃 클라이언트 프로그램)

### 깃 데스크탑

- 복잡한 깃 사용법을 GUI로 구현
- 장점: 사용이 쉬워서 누구나 배울 수 있음
- 단점: 기본적인 기능 위주여서 고급 사용자에게는 아쉬움

### 토터스깃

- 윈도우 전용 프로그램

### 소스트리

- 깃 기본 기능부터 고급 기능까지 사용 가능
- 기능이 많아 사용법 복잡하지만 익숙해지면 자유롭게 활용 가능

## 커맨드 라인 인터페이스 (CLI)

- 터미널 안에 직접 명령 이용해 사용하는 방식
- 기본적인 리눅스 명령+깃 명령 알아야 해서 더 어렵다

## 깃 초기 환경 설정

```
git config --global user.name "SsoHhyun"
git config --global user.email "janeqcitizen@naver.com"
```

- 사용자 이름과 이메일
- —global 옵션: 현재 컴퓨터에 있는 모든 저장소에 같은 사용자 정보 사용
- 터미널 창의 깃 명령 = 리눅스 명령

```
* 현재 위치
pwd

* 현재 디렉터리에 어떤 파일이나 디렉터리가 있는지
ls

* l : 디렉터리 상세 정보 / a : 숨긴 파일 및 디렉터리까지 표시
ls -la
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c368683d-d492-4663-8bd7-bd1f02d9c303/Untitled.png)

```
* 상위 디렉터리로 이동
cd ..

* cd + 하위 디렉터리 이름 -> 하위 디렉터리로 이동

* 홈 디렉터리로 이동
*cd ~
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/81dbe6b8-0dca-4c96-9bf9-e763122b7c5a/Untitled.png)

```
* test라는 이름의 디렉터리 만들기 (=make directory)
mkdir test

* test라는 이름의 디렉터리 및 하위 디렉터리와 파일까지 함께 삭제 (=remove)
rm -r test

* 해당 이름 파일이 없다면 파일을 생성하고, 있다면 파일을 여는 명령
vim test.txt
```

- 처음에는 ex 모드로 열려서 입력 모드로 전환해야 수정 가능
- `I`(=insert)나 `A` (=add)버튼으로 입력 보드로 전환
- 입력 후 `ESC`로 ex 모드로 돌아감
- `:`을 통해 텍스트 입력 가능
- `:wq`(=저장,  종료) 명령 입력 후 `Enter` 누르면 저장

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f14a3b2e-c946-498d-a7f5-648ad960ed99/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d6c7679d-940e-4f54-b7e4-bea83dd646cd/Untitled.png)

------

# 2장: 버전 관리

```
git init
```

- 깃 사용할 수 있도록 디렉터리 초기화

## 버전 만들기

- 깃에서 버전이란?
  - 문서를 수정하고 저장할 때마다 생기는 것
  - 깃에서 버전 관리 시 파일 이름 그대로 유지하며 파일에서 무엇어ㅡㄹ 변경했는지 변경 시점마다 저장할 수 있음
  - 버전마다 작업했던 내용을 확인할 수 있고, 그 버전으로 돌아갈 수도 있음

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/468883da-06a9-4280-b905-c73bae51e2fa/Untitled.png)

- untracked files: 깃에서 한 번도 버전 관리하지 않은 파일들이라는 뜻
- git add

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3e3af2b3-5f38-4d91-b6c5-55845ea49693/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cb0d7531-93c3-4fb7-ba5a-66b484f50814/Untitled.png)

- git commit

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/750ec14d-cec2-4f4a-a800-667b72693d69/Untitled.png)

- git log: 저장소에 저장된 버전 확인

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/74186121-a4df-4fb9-a0fd-7b15727f0b6e/Untitled.png)

- git commit -am “test 1”: 한번 commit한 파일이라면 add와 commit 한꺼번에 처리

## 커밋 내용 확인하고 수정하기

- git log

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2208c702-2b26-4d32-8b92-4ce263a66423/Untitled.png)

- git diff: 변경 사항 확인하기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/72643fbc-65a0-43ce-bf83-d3cde4fbe2f0/Untitled.png)

- git log —stat: 커밋 관련된 파일까지 함께 살펴보기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1acdc13f-fb5f-4a21-a0d2-8c7e7e898b99/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/33df2f04-164a-4bfb-bbb9-91de37363818/Untitled.png)

- .gitignore 파일로 버전 관리에서 제외

  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a3ae4503-922d-4a81-9a37-a7f572f4aa64/Untitled.png)

- git status 3단계

<aside> 💡 working tree clean → unmodified: 수정되지 않은 상태 Changes not stage for commit → modified: 파일이 수정만 된 상태 Changes to be committed → 커밋 직전의 staged 상태

</aside>

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6eadbebb-146d-4929-953c-28d9f0763748/Untitled.png)

- commit 메시지 수정

```
git commit --amend
```

- `I` 버튼으로 입력 모드로 바꿔 메시지 수정

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/77347318-d088-4f08-a598-1d874a6334bf/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/26fce273-9530-4cf6-94fc-b8c7661174e2/Untitled.png)

## 작업 되돌리기

- vim에서 수정 후 git checkout으로 내용 되돌리기 가능

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8f429bf2-d795-4377-a3dd-9cf148398fba/Untitled.png)

### 스테이징 되돌리기

```
git reset HEAD 파일 이름
```

### 최신 커밋 되돌리기

```jsx
git reset HEAD^
```

- HEAD^: 현재 HEAD가 가리키는 브랜치의 최신 커밋
- commit 취소와 unstage 동시 진행

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1cab1c76-1f16-4860-8be1-f723a25428b1/Untitled.png)

### 특정 커밋으로 되돌리기

```
git reset 커밋 해시
```

<aside> 💡 주의: 그냥 reset A라고 해 버리면, A commit을 reset하겠다는 게 아니라 최근 commit을 A로 reset **A commit 이후에 만들었던 commit들이 삭제**되고 A commit으로 이동

</aside>

- git log 명령으로 commit 해시들 확인

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a07e6b12-1bba-455f-ab0f-fc254d082f14/Untitled.png)

### 커밋 삭제하지 않고 되돌리기

```jsx
git revert 복사한 commit 해시
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/292af71b-3edc-4895-bd25-02a46c17cf4c/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ea05da11-1b79-4c07-b91c-20a1b7b4bf7a/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3d32ab76-92c1-4357-8005-04bdd87e5580/Untitled.png)

# 3장: 깃과 브랜치

## 분기와 병합

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a76026a8-c7a3-4320-a6de-5106cf7d6e79/Untitled.png)

## 브랜치 만들기

```
# 현재 작업 중인 branch 및 branch 목록 확인
git branch

# branch 새로 만들기
git branch 새 브랜치 이름
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b569fb62-ef29-448a-8f48-7edd1a2f718b/Untitled.png)

### 브랜치 이동하기 - git checkout

```
# 한 커밋씩 확인하기 (커밋 간략히 확인)
git log --oneline

# branch 이동하기
git checkout 브랜치 이름
```

## 브랜치 정보 확인하기

```
# 각 브랜치 커밋 함께 확인하기
git log --online --branches

# 그래프 형태로 표시하기
git log --online --branches --graph

# 브랜치 사이 차이점 확인
git log 기준 브랜치..비교할 브랜치
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1e01f2ed-159d-4807-9430-e880b7acf737/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/24457c0f-9eb3-48b1-9878-5b946ed31087/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a42c2e00-62ca-46cf-aaf3-9d94943cb671/Untitled.png)

## 브랜치 병합하기

```
git checkout master
git merge 가져올 브랜치 이름
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/da960e0b-ed60-40a7-8523-913c1f04f41c/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/efbc26e8-4bc6-4149-83db-322aa0f5fad9/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ba4faf0e-ad02-469b-af40-ed9f3601a306/Untitled.png)

- 브랜치 충돌(conflict): 각 브랜치에 같은 파일 이름을 가지고 같은 줄을 수정했을 때 브랜치 병합 시 발생

  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bf91c2a8-23f6-4582-bd8c-d0cb468b4eeb/Untitled.png)

  ![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ff24b6b2-8930-4379-a6d2-d933b2b02958/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/e75f7af2-8073-4b33-af2b-46896e4747d0/Untitled.png)

### 병합 끝난 브랜치 삭제하기

```
# 브랜치 삭제
git branch -d 삭제할 브랜치 이름
```

- 삭제한 브랜치는 같은 이름으로 다시 만들면 예전에 작업했던 내용이 나타남
- 즉, 브랜치를 삭제한다는 것은 완전히 저장소에서 없애는 것이 아닌 git의 흐름 속에서 감추는 것

### 수정 중인 파일 감추기 및 되돌리기 — git stash

- git stash 명령 사용하려면 파일이 tracked 상태여야 함 → 한 번은 commit을 했어야 함

```
# 수정 중인 파일 감추기
git stash

# 감춰진 파일 목록 확인하기
git stash list

# 파일 다시 꺼내오기
git stash pop
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/07d26ac8-73f0-46f9-9417-7f7ab09de046/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4af4ad0f-74da-42b7-95c4-236f69973811/Untitled.png)

# 4장: 저장소

### 원격 저장소에 연결하기

```
# 연결하기
git remote add origin 깃허브 주소

# 연결됐는지 확인하기
git remote -v

# 지역 저장소 브랜치를 원격 저장소 브랜치로 푸시하기
# 처음에만 이렇게 쓰고 그 다음에는 그냥 push라고만 해도 된다
git push -u origin 원격 브랜치 이름

# 원격 저장소에서 파일 내려받기
git pull origin 브랜치 이름
```

## 깃허브에 SSH 원격 접속하기

- ```
  SSH(Secure Shell)
  ```

  : 보안이 강화된 안전한 방법으로 정보 교환하는 방식

  - 프라이빗 키 + 퍼블릭 키
  - 일반적으로는 아이디와 비밀번호를 입력해 저장소 주인임을 인증
  - 자동 로그인을 통해 번거로움 줄일 수 있음

### SSH 키 생성하기

- 터미널에서 홈 디렉터리로 이동
- `ssh-keygen` 입력 → SSH 키 저장 디렉터리 확인 후 엔터
- 두 번 더 엔터 클릭 후 비밀번호 생성

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/146dbed3-7544-40be-a5db-072545d9cd6f/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/cf41b63c-488f-4f85-8551-fd4c620f94bf/Untitled.png)

### 깃허브에 퍼블릭 키 전송

- 사용자 컴퓨터에서 깃허브 저장소에 접속하면, 사용자 컴퓨터에 있는 프라이빗 키와 깃허브 서버에 있는 퍼블릭 키 비교하여 서로 맞으면 저장소 연결

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/6606e12a-1dbe-4d03-979f-55a65321c495/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/c7529b1e-90de-4f3c-982c-c1a429359721/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/57716619-2f8a-41bb-a737-b6f60b42d59c/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5a4a8943-fd2c-49d5-b62e-89b89f839c40/Untitled.png)

### SSH 주소로 원격 저장소 연결

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/57dce7f5-07da-43c5-a762-164a51c925a3/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/65a6dbb6-f02f-4066-88a6-0a0ec9b540c5/Untitled.png)

# 5장: 협업하기

## 원격 저장소 함께 사용하기

### 원격 저장소 복제하기 — git clone

```
$ git clone 복사한 주소 디렉터리 이름
```

### 원격 브랜치 정보 가져오기 — git fetch

- 원격 브랜치에 어떤 변화가 있는지 그 정보만 가져온다

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/77a49c54-f739-475a-a5e6-7244695801f5/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ccff6fe5-b553-4ee5-ae56-cf54f9e62c9b/Untitled.png)

- git pull → git fetch + git merge FETCH_HEAD

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0e521e03-2ea5-4c32-8512-63ab9f3511dd/Untitled.png)

## 협업의 기본

- 저장소 화면 - [Settings] - [Collaborators] - 메일 주소 입력 - [Add Collaborator] - 깃허브 화면에서 [Accept Invitation]

- 각 컴퓨터에 지역 저장소 만든 후, 공동 작업에서 이용할 이름과 이메일 주소 저장

  - 저장소마다 다른 이름과 메일 주소 만들기 위해 `--global` 옵션 제외

  ```
  $ git init workplace
  $ cd workplace
  $ git config user.name "이름"
  $ git config user.email 메일 주소
  ```

## 협업에서 브랜치 사용

### 새로 만든 브랜치 푸시하기

```
# 브랜치 생성 후 바로 체크아웃하기
$ git checkout -b 브랜치 이름

# 원격 저장소(origin)에 브랜치까지 함께 푸시
$ git push origin 브랜치 이름
```

- pull request로 브랜치 병합
- [New pull request] - [Create pull request] - [Merge pull request] - commit message 입력 - [Confirm merge]

------

# 6장: 깃허브로 소통하기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/f473c95d-e0f2-4928-8d08-c9a46833d79a/Untitled.png)

- 마크다운 문법 도입하기
- 링크

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/bc4e7642-0733-4ed7-a65b-47587feef188/Untitled.png)

- 이미지

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b13ecaf5-ce2f-4d46-b64a-e82399d3be33/Untitled.png)

### 깃허브에 이미지 올리고 README에 삽입

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3d96a522-11dd-4f08-a0b6-3e6043b8acfd/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b05bee41-da6e-42a1-a588-c947edcd1130/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/72be028a-b791-45b1-afc3-b14d59cbb6b2/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0ac843df-81ff-4dd6-b189-74e14f318160/Untitled.png)

## 오픈 소스 프로젝트에 기여하기

- README 파일 한국어로 번역
  - 먼저 메일 보내서 번역해도 되는지 물어보기
  - 분량 적은 것부터 천천히 시작
- 소스, 문서의 오타 수정
- 개발 소스 코드 수정

### 오픈 소스 저장소 복제하기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2b8ff37b-9d2d-4cd8-a511-beac5db16b34/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/59fb11bc-c494-45cb-b33a-fb8ad22e2f61/Untitled.png)

- 이후 포크한 저장소 지역 저장소로 CLONE

## 깃허브에 개인 블로그 만들기

### 1. 홈페이지 파일이 있을 때

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7082d36c-7d5f-4f66-b11c-49ff27c36916/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/aac61d6c-25c3-4ac8-afb7-493517401757/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/32486017-7d86-411e-9585-c9bc89a056cd/Untitled.png)

### 2. 홈페이지 파일이 없을 때

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/470e7c6c-372f-465e-a8a0-7c553a73f184/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0ff3575b-a1af-473a-ac80-ae0438d8feee/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/64a3b1fc-7bf0-4ac8-9da5-b39bdfacb028/Untitled.png)

### 블로그 만들고 기본 환경 설정하기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/9e5a1971-b9a4-4260-8b91-9be0ac93aa5e/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/3936ada9-4b6d-4c52-a312-893a2fe455d4/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/5328e1da-644d-45fa-b0b1-b79d3b32173f/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/424da52e-3d9c-4385-96b8-4f6253cdd8a9/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/23c8c5ab-6cbf-4d87-9f11-6907c377b554/Untitled.png)

------

# VSC에서 GIT 활용하기

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ed84afd6-ffc0-41e3-ba1b-445ec6da7e0a/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/69197552-637d-4ac3-9bd0-1b0043831498/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/05f6fff1-200e-47a2-a921-1a1adc7b5b25/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/48070eea-f3d2-4c09-9f88-d2c2a866cb0f/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/ade4ecd9-ab67-40fa-8bd0-6b1e70e04cbf/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/90b1ed2f-1584-4f29-a991-6ac7e123b002/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/4b5bf6b5-b4c0-4b5a-8181-d0e9bcad3864/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/83ce243d-45a8-4568-9fc6-b9796f70b630/Untitled.png)