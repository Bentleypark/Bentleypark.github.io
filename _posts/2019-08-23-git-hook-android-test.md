---
layout: post
title: '[AndroidTest] Git Hook 활용하여, Git 저장소에 코드 반영 실수 줄이기'
subtitle: 'Git push 전에, 강제로 Android Test 실행!'
bigimg: /img/git-hook.png
tags:
  - android
  - 안드로이드
  - Git
  - Git Hook
  - Android Test
published: true
date: '2019-08-23'
---

가끔 급하게 Git 저장소에 수정한 코드를 반영할 때, 개발자는 컴퓨터가 아니라(?) 실수를 할 때가 있습니다.
특히 Product Code에 이런 실수를 하는 경우에는... 생각만 해도 아찔하죠...

![omg](http://app.jjalbang.today/jj1uh.png)


**Git Hook 활용하면, 간단하게 이런 실수를 미연에 방지할 수 있습니다!**
**그럼 어떻게 할 수 있을까요??**

먼저, Git Hook이란 무엇인지 알아봅시다!

##  * Git Hook 이란?
### - Git 명령(push, commit, recieve)을 실행하기 전 혹은 이후에 실행되는 스크립트를 칭합니다.

[Git hook 공식 사이트 인용](https://githooks.com)


##  * 실행방법

1) .git/hooks/ 폴더에 pre-push 파일을 생성합니다.

2) 아래 snapchat 코드를 복사하여 붙여넣기 합니다. 


<script src="https://gist.github.com/bentleypark/2a757445ee352bbf9303feda7aa974e0.js"></script>

3) git push를 실행하면, 자동으로 gradle clean & Test(Anroid Test 코드 실행)이 실행됩니다. 해당 gradle build가 success 되어야 push가 됩니다. 

##  * 실행결과


![githook_result.png]({{site.baseurl}}/img/githook_result.png)


