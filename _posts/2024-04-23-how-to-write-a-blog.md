---
layout: single
title:  "Start a GitHub Blog with Jekyll"
---

# 기술 블로그 시작하기

기술 블로그라고 하기에는 거창하지만
기술 내용만 있으니 기술 블로그라고 부르기로 하겠습니다.

최근까지 velog를 사용하고 있었는데
velog는 무료로 사용할 수 있지만
제가 달지 않은 광고가 노출된다는 점에서 불편함을 느꼈습니다.
그래서 github 블로그를 시작하기로 결정했습니다.

## 왜 github 블로그인가요?
- 일단 호스팅 비용이 무료입니다.
- 기본적으로 markdown 문법에 익숙하다면 쉽게 작성할 수 있습니다.
- DB를 사용하지 않기 때문에 빠릅니다.
- 온전히 스스로 관리할 수 있습니다.
- 백업과 이전이 용이합니다.
- github의 소스코드와 연동할 수 있습니다.

## Start a GitHub Blog with Jekyll
여러가지 블로그 테마 중에서 minimal-mistakes 테마를 선택했습니다. \
참고: https://www.youtube.com/watch?v=ACzFIAOsfpM

0. github 가입합니다.

1. 마음에 드는 테마를 선택합니다.
  https://github.com/topics/jekyll-theme

2. 레포지토리를 fork 합니다.
  https://mmistakes.github.io/minimal-mistakes/docs/quick-start-guide/

3. _config.yml 파일에서 url을 수정합니다.
  ```shell
  url: "https://<username>.github.io"
  ```

4. 새로운 포스팅을 생성합니다.
  https://jekyllrb.com/docs/posts/
  ```shell
  ----
  layout: single
  title: 을 적습니다.
  ----

  내용을 적습니다.
  ```

5. 포스팅을 업로드합니다.
  ```shell
  git add .
  git commit -m "Add new post"
  git push
  ```

6. github 페이지에서 확인합니다.
  (1~2분 정도 소요됩니다.)
  https://<username>.github.io


<br>


일단 여기까지 했으면 기본적인 블로그가 완성됩니다. \
하지만 우리는 개발자니까 최소한 로컬에서 블로그를 관리할 수 있어야 합니다.

<br>

# Local 환경 구성하기

## Install
https://jekyllrb.com/docs/

mac OS에서는 다음과 같이 설치할 수 있습니다.
```shell
brew install chruby ruby-install xz
ruby-install ruby
# Successfully installed ruby 3.3.0 into /Users/bm/.rubies/ruby-3.3.0

echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.3.0" >> ~/.zshrc 

gem install jekyll
gem install bundler
```

Add the following to your site's Gemfile:
```shell
source "https://rubygems.org"

gem "github-pages", group: :jekyll_plugins
gem "jekyll-include-cache", group: :jekyll_plugins
gem "webrick", "~> 1.8"
```

And then execute:
```shell
cd <project-folder>
bundler
bundle exec jekyll serve
```

## Local에서 블로그 확인하기
http://localhost:4000
에 접속해서 확인합니다.


