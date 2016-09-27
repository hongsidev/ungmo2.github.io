---
layout: post
title: Sass Basics
subtitle: Sass의 소개, 설치와 간단한 명령어 사용법
categories: [Sass]
tags: []
---

![sass-logo](/img/sass-logo.png)

* TOC
{:toc}

# 1. Introduction

[Sass(Syntactically Awesome StyleSheets)](http://sass-lang.com/)는 CSS pre-processor 로서 CSS의 한계와 결함을 보정하기 위한 CSS의 확장(extension)이다.

CSS의 간결한 문법은 배우기 쉬우며 명확하지만 프로젝트의 규모가 커짐에 따라 쉽게 지저분해지고 유지보수가 어려워지는 단점도 가지고 있다. 이러한 CSS의 단점을 보완하기 위해 Sass는 다음과 같은 추가 기능과 유용한 도구들을 제공한다.

- 변수의 사용
- 조건문과 반복문
- Import
- Nesting
- Mixin
- Extend/Inheritance

# 2. Install

브라우저는 Sass의 문법을 알지 못하기 때문에 Sass(.scss) 파일을 css 파일로 컴파일하여야 한다. 따라서 Sass 환경의 설치가 필요하다. 또한 Sass는 Ruby로 작성되었기 때문에 Ruby의 설치도 필요하다.

## 2.1 Windows

**1. Ruby Installer의 설치**

[Ruby Installer](http://rubyinstaller.org/downloads/)로 이동하여 최신 Installer를 설치한다.

![ruby-installer-set-path.jpg](/img/ruby-installer.png)
{: style="max-width:450px; margin: 10px auto;"}

설치 도중 Path 추가를 체크한다.

![ruby-installer-set-path.jpg](/img/ruby-installer-set-path.jpg)
{: style="max-width:450px; margin: 10px auto;"}

**2. Sass 설치**

명령 프롬프트를 실행하고 아래 명령어를 실행한다.

```bash
gem install sass
```

## 2.2 Mac

Mac의 경우 Ruby가 기본적으로 설치되어 있으므로 바로 sass를 설치한다.

```bash
$ gem install sass
```

## 2.3 GUI App

GUI 환경에서 컴파일 기능 제공하는 App은 아래와 같다. App에 따라 Sass뿐만 아니라 LESS, Compass, Stylus, Jade, CoffeeScript, Slim, HAML, Markdown등 다양한 파일의 컴파일 기능을 제공한다.

- [Hammer](http://hammerformac.com/)

- [CodeKit](https://incident57.com/codekit/)

- [Compass](http://compass.kkbox.com/)

- [Koala](http://koala-app.com/)

# 3. Command

## 3.1 version

```bash
$ sass -v
Sass 3.4.22 (Selective Steve)
```

## 3.2 compile

컴파일할 scss 파일의 패스와 컴파일 후 생성될 css 파일의 패스를 지정한다.

```bash
$ cd my-project
$ sass my.scss my.css
```

```scss
#main{
  h1 { margin-bottom: 20px }
  p { font-size:90% }
}
```

위 scss 파일을 컴파일하면 아래와 같은 css 파일이 생성된다.

```css
#main h1 {
  margin-bottom: 20px; }
#main p {
  font-size: 90%; }
```

## 3.3 watch

watch command는 scss 파일의 변경을 감지하여 변경될 때마다 css 파일을 자동 업데이트한다.

디렉터리 단위 또는 파일 단위의 모니터링이 가능하다.

디렉터리 단위의 watch

```bash
$ cd my-project
$ ls -l
css/ sass/
$ sass --watch sass:css
```

파일 단위의 watch

```bash
$ cd my-project
$ ls -l
css/ sass/
$ sass --watch sass/my.scss:css/my.css
```

하나의 파일이 아닌 디렉터리 단위로 변경을 모니터링할 수도 있다.

# 4. SASS vs. SCSS

Sass는 SASS 표기법(.sass)과 SCSS 표기법(.scss)이 있다. 이전 버전에서는 SASS 표기법이 기본 표기법이었으나 Sass 3.0부터 CSS 친화적인 SCSS（Sassy CSS） 표기법이 기본 표기법이 되었다.

|          | SCSS     | SASS   | CSS    |
|:---------|:---------|:-------|:-------|
| 중괄호 {}  | 필요      | 불필요（공백 2문자 들여쓰기가 코드블록을 의미)| 필요
| 세미콜론 ;  | 필요     | 불필요   | 필요
| : 뒤의 공백 | 불필요    | 필요    | 불필요
| Mixin     |  @mixin  | =      | 없음
| Include  | @include | +      | 없음
| 확장자     | .scss    | .sass  | .css

SASS 표기법은 보다 코딩을 간략화할 수 있는 장점이 있지만 CSS 친화적인 SCSS 표기법를 사용하는 경우가 더 많으므로 본 Post에서는 SCSS 표기법을 기준으로 한다.

Sass의 문법에 대한 설명은 [Sass Syntax](http://poiemaweb.com/css/Sass-syntax/)를 참조하기 바란다.

# Reference

* [Sass](http://sass-lang.com/)

* [Sassmeister: sass to css converter](http://www.sassmeister.com/)