---
layout: post
title: 'Git Hook 활용하여, Git 저장소에 코드 반영 실수 줄이기'
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


![omg](http://app.jjalbang.today/jj1uh.png)

## 개발자라면 누구나 겪는 실수가 있다. 

가끔 급하게 Git 저장소에 수정한 코드를 반영할 때, 개발자는 컴퓨터가 아니라(?) 실수를 할 때가 있습니다.                                                                                                                                     

특히 Product Code에 이런 실수를 하는 경우에는... 생각만 해도 아찔하죠...                                                 

Git Hook 활용하면, 간단하게 이런 실수를 미연에 방지할 수 있습니다!                                                       
그럼 어떻게 할 수 있을까요??  

  
먼저, Git Hook이란 무엇인지 알아봅시다!  



## Git Hook 이란?

> Git 명령(push, commit, recieve)을 실행하기 전 혹은 이후에 실행되는 스크립트를 칭합니다.                                                                                                                                                     


### 실행방법

1) .git/hooks/ 폴더에 pre-push 파일을 생성합니다.

2) 아래 snapchat 코드를 복사하여 붙여넣기 합니다. 


<script src="https://gist.github.com/bentleypark/2a757445ee352bbf9303feda7aa974e0.js"></script>

3) git push를 실행하면, 자동으로 gradle clean & Test(Anroid Test 코드 실행)이 실행됩니다. 해당 gradle build가 success 되어야 push가 됩니다. 

### 실행결과


![githook_result.png]({{site.baseurl}}/img/githook_result.png)

- 참고 블로그 출처: [미디엄 게시글 ](https://medium.com/@hamen/running-android-unit-tests-before-git-push-e9e7ec78e6d1#id_token=eyJhbGciOiJSUzI1NiIsImtpZCI6ImRmOGQ5ZWU0MDNiY2M3MTg1YWQ1MTA0MTE5NGJkMzQzMzc0MmQ5YWEiLCJ0eXAiOiJKV1QifQ.eyJpc3MiOiJodHRwczovL2FjY291bnRzLmdvb2dsZS5jb20iLCJuYmYiOjE1NjY0OTI1NjMsImF1ZCI6IjIxNjI5NjAzNTgzNC1rMWs2cWUwNjBzMnRwMmEyamFtNGxqZGNtczAwc3R0Zy5hcHBzLmdvb2dsZXVzZXJjb250ZW50LmNvbSIsInN1YiI6IjEwNDAxMzExMzQxMjE2NDYxOTc5MyIsImVtYWlsIjoicDJjMmtiZkBnbWFpbC5jb20iLCJlbWFpbF92ZXJpZmllZCI6dHJ1ZSwiYXpwIjoiMjE2Mjk2MDM1ODM0LWsxazZxZTA2MHMydHAyYTJqYW00bGpkY21zMDBzdHRnLmFwcHMuZ29vZ2xldXNlcmNvbnRlbnQuY29tIiwibmFtZSI6Ikp1bmctR2lsIFBhcmsiLCJwaWN0dXJlIjoiaHR0cHM6Ly9saDMuZ29vZ2xldXNlcmNvbnRlbnQuY29tL2EtL0FBdUU3bUJLRDg3blZNdUdZS2lZc2Q1R2dGb1Fwd1JkSWVrbmNVSG1DRU8wSmc9czk2LWMiLCJnaXZlbl9uYW1lIjoiSnVuZy1HaWwiLCJmYW1pbHlfbmFtZSI6IlBhcmsiLCJpYXQiOjE1NjY0OTI4NjMsImV4cCI6MTU2NjQ5NjQ2MywianRpIjoiM2M2OGZhYWRkNDk3ZWE3ODljMmJjMzUxNDJiYmUwMzM0Mzg0ODY5MSJ9.TJIqSIhb6K_lhlltKFkOK1j6Hd7-_tNoY1dUarF_XFvrU04uD8PzV0ZU2ZaleGsrcsADwj0yq76Ne_wDpMxlidJSlDJ-lT82ni4ePv2EjqNe1WHbzAWRPCrRLx0S6jz0773Rc8bIuAO3y3XAPXi_ZwDCrvY_tOW4x3fXbhpv6XR3lNAzi3vCVwn5bf9W8oSABfJordoyiWm9cnOGMjyx2fIZjLFn3YSKfL1hL_dgduOzMsrBJqhoSDGuxzKG4H9gjkueFSmrWINJvEFSGtrANdJu5M7Evkgc53C-xCndUVlUcB3IfY8apPmxdtjXQxkC5aSHkZ6xiFzVxqQ9PvkpxA)
