---
title: 깃허브(github) 블로그 만들기 (+23.06.15 오류 수정)
author: ha
date: 2023-06-14 15:30:00 +0900
categories: [개발, Git]
tags: [Git]
render_with_liquid: false
img_path: /assets/img/20230614/
---

## 환경 구성

### 1. 루비를 설치한다.

설치 페이지 : [rubyinstaller.org/downloads](https://rubyinstaller.org/downloads/)

![ruby install](ruby_install.PNG)

32bit, 3.1.x버전으로 설치한다.

설치 확인. 버전이 나오면 제대로 설치된 것이다.

```shell
ruby -v
```

### 2. Jekyll를 설치한다.

```shell
gem install jekyll
gem install bundler
```

설치 확인

```shell
jekyll -v
bundler -v
```

### 3. node를 설치한다.

설치 페이지 : [nodejs.org](https://nodejs.org/ko)

설치 확인

```shell
node -v
```

## Jekyll 테마 적용

### 1. Jekyll 테마를 선택한다.

내가 선택한 테마 : [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy/)

![jekyll-theme-chirpy-wiki](jekyll-theme-chirpy-wiki.PNG)

이후의 단계는 위 페이지의 Wiki 탭을 보고 진행하였다.

### 2. fork

![fork](fork.PNG)

해당 repository를 `USERNAME.github.io` (`USERNAME` 은 나의 git user명을 말한다.) 라는 이름으로 fork 한다.
이 때 repository는 공개로 설정해야한다.

### 3. clone

자바스크립트 파일을 빌드하기 위해 로컬에 소스를 clone 한다.

```shell
git clone git@github.com:cotes2020/jekyll-theme-chirpy.git
```

clone 한 프로젝트의 루트 폴더에서 아래의 명령어를 실행한다.(노드 필요)
(최신코드 확인, 샘플제거, 자바스크립트 파일빌드 등등을 수행)

```shell
bash tools/init
```

Dependencies를 설치하기 위해 아래의 명령어를 실행한다.

```shell
bundle
```

### 4. \_config.yml 수정

\_config.yml을 수정한다.

```yaml
lang: ko-KR # 사용언어
timezone: Asia/Seoul # 타임존
title: hahaha # 블로그 제목
tagline: 공부 및 스크랩 # 소제목
description: >- # 설명
  공부 및 스크랩 용도의 블로그 입니다.
url: "https://hahaha1110.github.io" # 내 블로그 주소명  'https://username.github.io' 이런 형태로 써야함
github:
  username: # github username
social: # 좌측 하단에 나오는 social 버튼 설정
  name: # 이름
  email: # 이메일
  links:
    # The first element serves as the copyright owner's link
    - https://twitter.com/ # 트위터주소
    - https://github.com/ # 깃허브 주소
avatar: # 아바타 이미지를 저장한 경로
```

### 5. 로컬서버에서 실행해본다

```shell
bundle exec jekyll s
```

![run](bundleExec.png)

~~잘 실행되는 것을 확인했다.~~

였는줄 알았는데 포스트를 작성해보니 우측 바로가기가 표시되지 않았고, 검색기능도 되지 않았다. 이것을 해결하기 위해서는 [빌드 오류 수정](#빌드-오류-수정) 을 참고하기..

### 6. 배포 전 준비

배포 전 다시한번 \_config.yml 파일을 확인하고 URL이 올바르게 구성되었는지 확인한다.

그리고 로컬저장소의 루트에서 다음을 실행한다.

```shell
bundle lock --add-platform x86_64-linux
```

### 7. 배포

내 GitHub 저장소에서 clone했던 프로젝트를 찾는다.

그리고 Settings > Pages 탭에 들어간다.
그런 다음 Source 드롭다운 메뉴에서 GitHub Actions를 선택한다.

![setting](setting.png)

commit, push를 실행한다.
저장소 상단의 Actions 탭을 보면 배포진행상황을 볼 수 있다.
배포가 완료되면 설정한 url (유저명.github.io)를 통해 블로그에 접속 할 수 있다.

## 빌드 오류 수정

위의 순서를 따라 진행하여 git에 배포하면 `assets/js/dist` 경로에 `.min.js` 파일들이 없다는 경고가 나오면서 빌드 오류가 난다.(실제로 해당 경로에는 min.js가 없을 뿐만 아니라 아예 asset/js안에 dist경로 자체가 없었다.)

![buildFailed](buildFailed.png)
_오류로그_

```
- _site/404.html
  *  internal script /assets/js/dist/page.min.js does not exist (line 1)
- _site/about/index.html
```

이 문제를 해결하지 않으면 블로그 우측의 바로가기나 검색기능, 모바일 버전에서 드롭다운 메뉴 열기 등의 기능을 사용할 수 없었다.

다운받은 파일 중 `.min.js`를 만들어주는 것이 있는지 찾아봤는데 루트 폴더에 `rollup.config.js` 파일이 존재했다.

![rollup](rollup.png)

파일을 열어보니 `_javascript` 경로에 있는 `.js` 파일들을 `asset/js/dist` 폴더에 `min.js`로 만들어 주는 것 같았고, `_javascript` 폴더에 보니 `.js` 파일들이 있었다.

얘를 실행시키기 위해 루트 디렉토리에서

```shell
npm install
```

을 한 후

```shell
NODE_ENV=production npx rollup -c --bundleConfigAsCjs
```

를 실행하면 아래와 같은 로그가 뜨고, 작업이 끝나면

![rollupping](rollupping.png)

`asset/js/dist` 폴더에 `.min.js` 가 들어가있는 것을 확인할 수 있다.

![dist](dist.png)

그리고 이 min.js들을 올리기 위해 `.gitignore` 에서 `assets/js/dist` 를 지우거나 주석처리를 한 채로 git에 push 한다.

![gitignore](gitignore.png)

그러면 build 오류 없이 잘 배포 되고 바로가기, 검색, 모바일 버전에서 드롭다운 메뉴 보기 등의 기능도 정상적으로 잘 작동되는 것을 확인할 수 있다.

![buildSucess](buildSucess.png)
_빌드 성공_

![sucess](sucess.png)
_성공!_

참고 :

- [https://devpro.kr/깃허브블로그 만들기](https://devpro.kr/categories/github-blog/)
- [chirpy](https://chirpy.cotes.page/)
