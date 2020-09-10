---
title: "[MachineLearning 3] 경사하강법"
date: 2020-08-20 21:00:15 -0400
categories: MachineLearning DataAnalyze
---

## 단순선형회귀에서의 경사하강법

<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-2/">지난 포스팅</a> 요약 :: 선형회귀법은 Cost가 가장 작은 model을 구하는 것이다. <br/>
  오늘 포스팅 :: 선형회귀에서의 경사하강법(Gradient Descend Algorithm)에 대해 알아보자
  <div>
    <h3 style = "font-size :1.2em"> 경사하강법이란?</h3><br/>
    <div style = "margin-left : 3%">
       <b>"경사하강법은 많은 최소값 탐색 문제에 사용되며 특히 근사값을 구하는 문제에서 많이 사용됩니다.<br/><br/>
       순간기울기를 통해 극값을 추정하는 방법이며 미분가능한 함수에서 가능합니다."</b><br/><br/>

       어떤 지점의 순간기울기의 부호를 통해 현재 지점보다 낮은 지점으로 가기위해 어느쪽으로 이동해야하는 건지 판단하며<br/>
       최종적으로 순간기울기가 0일때 까지 반복합니다.<br/><br/>

       <img src="/assets/photos/gradient-descent-local-minima.png" width="550"><br/>
       <span style = "font-size : 0.8em">출처 :: https://bdtechtalks.com</span><br/><br/>
       이때문에 극소값(local minima)이 하나인 그래프에서는 최소값이 하나기 때문에 문제가 없지만<br/>
       극소값이 여러개인 그래프에서는 찾은 곳이 최소값(global minima)이라는 보장을 할 수 없습니다.<br/><br/>
       그리고 경사하강법을 통한 극값 추정시 <b>'내려가는 루트'</b>에 따라 도착한 곳이 바뀌며,<br/>
       내려가는 루트는 <b>'출발지점'</b>이 어딘지에 따라 영향을 크게 받습니다.<br/><br/>

       <hr/>
       알고리즘을 수식으로 표현할 경우 <br/><img src="https://latex.codecogs.com/png.latex?w := w - \alpha \frac{\partial }{\partial w}Cost(w)" title="w := w - \alpha \frac{\partial }{\partial w}Cost(w)" />가 됩니다.<br/><br/>
       위식을 설명하자면 다음 w값은 현재 w값에서 Cost(w)의 미분값 x 알파를 빼준 값이라는 뜻입니다.<br/><br/>
       알파값은 우리가 정해주는 값으로 얼마만큼 움직일지이며, 알파 오른쪽 식은 미분표현인 dCost(w)/dw입니다.<br/> d(델타)가 조금 이상하게 표현됬네요..<br/><br/>
       <i style = "font-size : 0.9em">':='은 좌항을 우항으로 대체하라는 표현입니다.<br/>
       알파값이 너무 큰값이라면 w가 움직이는 범위가 너무 커서 극점을 지나칠 우려가 있으며<br/>
       너무 작은값이라면 최소점을 찾는데 지나치게 오랜시간이 걸립니다.<br/>
       따라서 '적당한 값'을 주는 것이 중요합니다.</i><br/><br/><hr/>
       또한 경사하강법은 Cost함수가 컨벡스함수인경우 사용가능합니다.<br/><hr/>
    </div>

  <div>
    <h3 style = "font-size :1.2em"> 경사하강법 in 선형회귀</h3><br/>
    <div style = "margin-left : 3%">

        H(x) = wx+b일 때의 Cost 그래프는 아래와 같이 2차함수 형태입니다.<br/><br/>
       <img src="/assets/photos/20200820_3.png" width="450"><br/>
       <span style = "font-size : 0.8em">Cost 그래프 예시</span><br/><br/>
         선형회귀의 목표는 U자 개형을 가지는 Cost그래프에서 Cost값이 최저일 때 w값을 찾아내는 것입니다.<br/><br/>
         극소값을 가질 때 w값을 경사하강법을 통해 추론해냅니다.<br/>
         예시를 통해 살펴보겠습니다.<br/>
         <img src="/assets/photos/20200825_1.png" width="450"><br/>
         1. 시작점인 A에서 H'(A)가 음수므로 A에서 우측으로 간다면 극소값이 있을 것이라 추정됩니다.<br/>
          따라서 우측으로 조금 움직여 B지점으로 이동합니다.<br/><br/>
         2. 마찬가지로 B에서 H'(B)가 음수므로 B에서 우측으로 간다면 극소값이 있을 것이라 추정됩니다.<br/>
          우측으로 조금 움직이겠습니다.<br/> <br/>
         3. 조금 움직여 C 지점으로 왔습니다. H'(C)가 0이므로 Cost(w)는 w=C일 때 최소값을 가집니다.<br/>
            구한 최적의 모델은 H(x) = Cx가 됩니다. <br/><br/>
         <i style = "font-size : 0.9em">찾는 모양새가 그래프의 경사면을 따라 주르륵 미끄러져 내려가는 것 처럼 보이기 때문에 경사하강법이라고 부릅니다.</i><br/><br/>

         <hr/>
         이번에는 수식을 통해 살펴보겠습니다.<br/><br/>
         먼저 <img src="https://latex.codecogs.com/png.latex?Cost = \frac{1}{m}\sum_{i=1}^{m}(W(x^{i})-y^{i})^{2}" title="Cost = \frac{1}{m}\sum_{i=1}^{m}(W(x^{i})-y^{i})^{2}" />입니다.<br/><br/>


        <hr/>

         경사하강법 알고리즘이 <img src="https://latex.codecogs.com/png.latex?w := w - \alpha \frac{\partial }{\partial w}Cost(w)" title="w := w - \alpha \frac{\partial }{\partial w}Cost(w)" />이므로<br/><br/>
         식을 정리해보면,<br/><br/>
         <img src="https://latex.codecogs.com/png.latex?w := w - \alpha \frac{\partial }{\partial w}Cost(w)" title="w := w - \alpha \frac{\partial }{\partial x}Cost(w)" /><br/><br/>
         <img src="https://latex.codecogs.com/png.latex?w := w - \alpha \frac{\partial }{\partial w}\frac{1}{2m}\sum_{i=1}^{m}(W(x^{i})-y^{i})^{2}" title="w := w - \alpha \frac{\partial }{\partial w}\frac{1}{2m}\sum_{i=1}^{m}(W(x^{i})-y^{i})^{2}" /><br/><br/>
         <img src="https://latex.codecogs.com/png.latex?w := w - \alpha \frac{1}{2m}\sum_{i=1}^{m}2(W(x^{i})-y^{i})x^{i}" title="w := w - \alpha \frac{1}{2m}\sum_{i=1}^{m}2(W(x^{i})-y^{i})x^{i}" /><br/><br/>
         <img src="https://latex.codecogs.com/png.latex?w := w - \alpha \frac{1}{m}\sum_{i=1}^{m}(W(x^{i})-y^{i})x^{i}" title="w := w - \alpha \frac{1}{m}\sum_{i=1}^{m}(W(x^{i})-y^{i})x^{i}" /><br/><br/>
         이렇게 됩니다.

    </div>
  </div>
 </div>
 <hr/>
<a href = "https://can019.github.io/machinelearning/dataanalyze/python/colab/MachineLearning-AI-4/">다음 포스팅</a>은 파이썬 코드로 구현하는 법을 알아보겠습니다.<hr/>
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
  <blockquote>해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다.<br/>
  영상과 강의자료는 배포가 불가하기에 공유가 불가하면 포스팅에 사용한 자료와 이미지는 개인적으로 복습하며 만들었습니다. </blockquote>
  <blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
    블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
    발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <hr/>
</div>
