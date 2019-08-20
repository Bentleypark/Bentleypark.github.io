---
layout: post
title: '[Android] Firebase 저장소에 업로드한 이미지 로딩하기'
subtitle: Glide 라이브러리 Library 활용
bigimg: /img/android_post_background.jpg
tags:
  - android
  - 안드로이드
  - firebase
  - Glide
  - 이미지로딩
published: true
date: '2019-08-21'
---
![Firebase](https://cms-assets.tutsplus.com/uploads/users/1802/posts/30203/image/firebase-storage-logo.png)

Firebase 저장소를 이용하면, 별도의 백엔드 작업없이 파일 업로드/다운드 수행할 수 있습니다.
그래서 규모가 작고 간단한 안드로이드앱을 만들때, Firebase를 활용하여 서버단을 구성합니다. 

이번에는 Firebase 저장소에 업로드한 이미지를 Glide 라이브러리를 이용하여 이미지뷰에 불러오는 방법을 정리해보겠습니다. 



## * Android 프로젝트에 Firebase 추가
- 링크를 통하여 Firebase에서 Android 프로젝트를 생성해줍니다. 

	: [Firebase 추가에 프로젝트 추가: https://firebase.google.com/docs/android/setup?hl=ko](https://firebase.google.com/docs/android/setup?hl=ko)

## * Firebase Storage Rule 변경 

<script src="https://gist.github.com/bentleypark/1dd3d788f01103dffcb7d06bd9239aaf.js"></script>


## * activity_main.xml
- 이미지를 로딩할 이미지뷰를 생성합니다. 

<script src="https://gist.github.com/bentleypark/f053c4ed4aaf897d7003a136577c568f.js"></script>

![Glide](https://github.com/bumptech/glide/raw/master/static/glide_logo.png)


## * ImageLoading.java 
- FirebaseStorage 객체를 통하여 다운로드 URL을 구하여, Glide 라이브러리를 통하여 이미지를 로딩합니다. 

<script src="https://gist.github.com/bentleypark/7b7d31d44a88b2bc7620e020aba9e337.js"></script>


## * AndroidManifest.xml 
- 인터넷 연결이 가능하도록 퍼미션 추가합니다. 

<script src="https://gist.github.com/bentleypark/661162f6ef55cc2cc79e02d7134bfc75.js"></script>


## * 실행화면

![imageloading.png]({{site.baseurl}}/img/imageloading.png)


## * 참고 사이트 

- [https://stackoverflow.com/questions/49117076/glide-will-not-show-image-from-firebase-storage](https://stackoverflow.com/questions/49117076/glide-will-not-show-image-from-firebase-storage)


