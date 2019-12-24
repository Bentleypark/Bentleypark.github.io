---
layout: post
published: true
title: Ubuntu 환경에서 네이버 News 크롤링background 실행하기
---

![ 출처: 인프런 블로그 이미지]({{site.baseurl}}/img/python-web-crawling.jpg)
<center>출처: 인프런 블로그 이미지</center> <br>

# 데이터의 중요성 <br>
 최근 대표적인 배달앱 <배달의 민족>을 운영하는 “우아한 형제들”이 독일계의 경쟁 회사인 “딜리버리 히어로"에 한화 4조에 가까운 기업 가치를 인정받고 인수합병이 되었습니다.

 몇 년전까지만 하더라도 상상도 하지 못한 일이었지만, 현재는 전세계적으로 IT기업들의 가치가 가파르게 상승하였습니다. 이런 현상의 근본적인 이유는 이러한 기업들이 사용자들에게 양질의 서비스를 제공하면서, 사용자의 사용패턴에 따라서 획득하게 되는 “데이터” 덕분입니다.

 이에 따라서 개발자들도 데이터에 많은 관심을 가지게 되었습니다. 저도 최근에 사이드 프로젝트를 진행하면서 필요한 데이터를 획득하기 위해서 처음으로 클롤링을 시도해보게 되었습니다.
 
 --- 
 <br>
 
 # 파이썬 뉴스 크롤러 <br>
 제가 필요한 데이터는 특정 분야의 포탈 뉴스입니다. 구글 검색을 통해서 파이썬으로 개발된 “KoreaNewsCrawler”을 발견할 수 있었고, 이를 활용해서 데이터 크롤링을 해보도록 하겠습니다.
 
 <br>
 ### 1. 실행환경
 
 * OS : Ubuntu 18.04.3 LTS
 * Python3 ( ver 3.6.9)
 * KoreaNewsCrawler
 
<br>

### 2. 파이썬 크롤러 설치
> pip install KoreaNewsCrawler

<br>

### 3. 크롤러 실행 코드
    
    from korea_news_crawler.articlecrawler import ArticleCrawler

	Crawler = ArticleCrawler()  
	Crawler.set_category("사회", "생활문화","world")  
	Crawler.set_date_range(2019, 1, 2019, 12)  
	Crawler.start()

<center>News_Crawler.py</center> <br>

**2019년 1월 ~ 2019년 12월까지 사회, 생활문제, world 카테고리 뉴스를 멀티프로세서를 이용하여 병렬 크롤링을 진행합니다.**

<br>

### 4. 크롤러 실행

크롤링은 시간이 소요가 되기 때문에, 터미널을 종료해도 실행이 되도록 backgroud에서 진행을 했습니다.

	nohub python3 News & // backroud에서 데이터 크롤링이 실행된다.
    
<br>

### 5. 크롤러 실행

데이터는 아래 이미지처럼 .csv 파일로 생성이 됩니다. 

![스크린샷 2019-12-23 오후 11.39.10.png]({{site.baseurl}}/img/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA%202019-12-23%20%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE%2011.39.10.png)

<br>
* 참고 사이트: [https://github.com/lumyjuwon/KoreaNewsCrawler](https://github.com/lumyjuwon/KoreaNewsCrawler)
