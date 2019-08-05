---
layout: post
title: '[Android] 손 쉽게 Splash Screen 구현하기'
subtitle: Easy Splash Screen Android Library 활용
bigimg: /img/android_post_background.jpg
tags:
  - android
  - 안드로이드
  - splash screen
  - Easy Splash Screen Android
published: true
---

![intro.png]({{site.baseurl}}/img/intro.png)

'Spash Screen' 이란 앱을 실행시키면, 제일 먼저 실행되는 UI 화면입니다. 
사용자에게 제일 많이 노출되는 화면이기도 합니다.  보통 Spash Screen에는 앱의 로고를 넣거나, Animation 효과를 많이 넣어서 사용자에게 앱의 브랜딩을 각인을 시킵니다. 

개발자들도 안드로이드 앱을 개발할 때, 제일 먼저 개발하는 UI 화면이 Spash Screen입니다. 제일 첫 UI이기도 하며, 로고 이미지만 있으면 금방 만들 수 있기 때문입니다. 

최근에 개인 포트폴리오를 개발하는 중에 Spash Screen을 쉽게 개발할 수 있도록 지원하는 Library가 있어서 소개해드립니다. 

### Library 이름: EasySplashScreen
* **Github**: [https://github.com/pantrif/EasySplashScreen](https://github.com/pantrif/EasySplashScreen)

## * 사용방법

**1) Dependancy 추가**

<script src="https://gist.github.com/bentleypark/9a42f45e7cb873d00ca53935295a7e1e.js"></script>

**2)SpashScreenActibity 소스코드** 
(단, Activity를 추가할 때, 따로 Layout(xml) 파일을 생성하지 않아도 된다!) 

<script src="https://gist.github.com/bentleypark/25767682b627272f026e58e9380413dc.js"></script>

**3)AndroidManifesh.xml 파일 수정**
- Splash 화면이 제일 먼저 실행되도록 변경해주어야 합니다.
 (보통 프로젝트를 신규로 생성하면, MainActivity가 default 값으로 되어있습니다.)
 
  <script src="https://gist.github.com/bentleypark/523ec8685d3feff5348770e78ef10ed4.js"></script>
  
**4) 그 밖의 옵션들**
- Spash Screen에 텍스트를 추가하여 색상 및 폰트를 변경할 수 있습니다. 자세한 사항은 [Library Github](https://github.com/pantrif/EasySplashScreen)에서 확인할 수 있습니다. 

![출처: https://github.com/pantrif/EasySplashScreen]({{site.baseurl}}/img/splash_another_option.png)
