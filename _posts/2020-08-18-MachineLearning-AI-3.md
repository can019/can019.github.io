---
title: "[KAIST AI 교육 :: 데이터 분석 및 예측] 3"
date: 2020-08-20 21:00:15 -0400
categories: MachineLearning DataAnalyze
---
# 경사하강법(Gradient Descend Algorithm)

<hr/>
<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-2/">지난 포스팅</a> 요약 :: 선형회귀법은 Cost가 가장 작은 model을 구하는 것이다. <br/>
  오늘 포스팅 :: 작은 Cost를 구하는 법인 경사하강법(Gradient Descend Algorithm)에 대해 알아보자.
  <div>
    <h3 style = "font-size :1.2em"> 경사하강법</h3><br/>
    <div style = "margin-left : 30px">
       경사하강법은 많은 최소값 탐색 문제에 사용되며 특히 근사값을 구하는 문제에서 많이 사용됩니다.<br/><br/>
       쉽게 설명하기 위해 H(x) = wx+b일 때의 Cost그래프를 통해 설명하겠습니다.<br/><br/>
       <img src="/assets/photos/20200820_3.png" width="450"><br/>
       <span style = "font-size : 0.8em">Cost 그래프 예시</span><br/><br/>
         선형회귀의 핵심은 U자 개형을 가지는 Cost그래프에서 Cost값이 최저일 때 w값을 찾아내는 것이 목표입니다.<br/><br/>
         저 문장을 바꾸어 말한다면<br/> <b>'Cost그래프를 미분했을 때 0인 지점의 w값을 구하는 것이 목표입니다'.</b> 라고 바꿔 말할 수 있습니다.<br/><br/>
         
         이것이 경사하강법의 출발점입니다.<br/><br/>
         경사하강법은 특정 w에서의 순간 기울기를 측정합니다. 그리고 순간 기울기값이 만약 음수라면 w값을 우측으로,<br/>
         순간 기울기 값이 양수라면 w값을 좌측으로 움직입니다.<br/><br/>
         이 모양새가 그래프의 경사면을 따라 주르륵 미끄러지는 것 처럼 보이기 때문에 경사하강법이라고 부릅니다.
         그리고 tensorflow를 통해 경사하강할 때 w가 움직이는 만큼을 rate

        
       
       

    </div>
  <div>
    <h3 style = "font-size :1.2em"> 제목</h3><br/>
    <div style = "margin-left : 30px">

    </div>
  </div>
 </div>


  <hr/>
  ***미완성인 포스팅입니다***<br/>
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
  <blockquote>해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다.<br/>
  영상과 강의자료는 배포가 불가하기에 공유가 불가하면 포스팅에 사용한 자료와 이미지는 개인적으로 복습하며 만들었습니다. </blockquote>
  <blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
    블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
    발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <hr/>
</div>
