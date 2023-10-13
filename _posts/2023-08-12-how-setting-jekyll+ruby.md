---
published: true
layout: post
title: jekyll과 ruby를 이용하여 github 블로그 이용하기
---

github에 블로그를 하기 위해서는 jekyll을 많이들 이용을 합니다.
그래서 이것을 설치하는 방법을 알아보도록 할게요.
참고로 저는 맥을 사용하므로 맥에서 설치하는 방법을 알려드릴겁니다.
개발자중에 윈도우 사용하시는분들에게는 죄송...

## Command Line Tool 설치
xcode가 있다면 설치가 되어 있을겁니다.
그렇지만 중간에 설치가 될수 있지만 자동으로 되니까 그냥 패스하시던지 명령어 한번만 쳐주세요
```
$ xcode-select --install
```

## Ruby 설치
```
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
한가지 알아둘 점은 rosetta로 설치된것이 있다면 삭제하고 다시 설치합니다.
저도 이것 때문에 고생을 했습니다.

## rbenv 설치
Ruby version manager인데요.
루비의 사용할 버전을 관리해주는 프로그램입니다.
저는 2.7.7을 사용하면서 버전을 선택하는데 사용했어요.
```
$ brew install rbenv
```

## rbenv 환경 설정
보통 맥을 설치하고 iTerm 등을 설치하면 ~/.zshrc 파일에 환경이 설정되어 있을거에요.
이 파일을 어떠한 방법으로든 수정합니다.
```
$ open ~/.zshrc
```
이렇게 열어서 넣어주던지 아래와 같이 명령을 합니다.
```
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
$ source ~/.zshrc
```

## rbenv를 이용한 루비 설치
이제야 뭔가 할수 있네요.
루비를 받아줘야 합니다.
```
$ rbenv install 2.7.7
```

## 루비버전 설정
global 설정으로 루비 버전을 지정해 줍니다.
```
$ rbenv global 2.7.7
```

## Jekyll 설치
이제야 이걸 설치 가능합니다.
폴더를 새로 만들어서 이 명령을 사용합니다.
```
$ gem install jekyll bundler github-pages
```

### 맘에드는 테마를 선택합니다.
다운로드 하여 줍니다. 다운로드 받고 나서 압축을 풀어보면 Gemfile이 존재하는데요. 이것을 통해서 서버 구동을 하면서 테스트가 가능하게 됩니다.
- URL : http://jekyllthemes.org/

### 블로그 폴더 만들기
프로젝트 생성하듯이 폴더의 이름을 다음과 같이 넣어줘서 만들어줍니다.
```
$ jekyll new [블로그 이름]
```

### 블로그 내용 적고 테스트
```
$ bundle exec jekyll serve
```

### 구동 확인
브라우저를 열어주십시오
```
localhost:4000
```

