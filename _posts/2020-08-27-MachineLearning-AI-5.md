---
title: "[MachineLearning 5] 다항 선형 회귀"
date: 2020-08-27 21:00:15 -0400
categories: MachineLearning DataAnalyze
---
## 다항 선형 회귀(Multiple Linear Regreesion)


<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-3/">지난 포스팅</a><br/>
  <div>
    <h3 style = "font-size :1.2em"> 다항 선형 회귀</h3><br/>
    <div style = "margin-left : 3%">
       저번 시간 포스팅했던 선형 회귀는 input 변수. 즉 feature가 하나인 경우에 대해 다루었습니다.<br/><br/>
       다항 선형 회귀는 feature가 하나가 아닌 둘 이상인 경우입니다.<br/><br/>
       feature가 하나 -> <img src="https://latex.codecogs.com/png.latex?H(x) = wx+b" title="H(x) = wx+b" /><br/><br/>
       feature가 셋 -> <img src="https://latex.codecogs.com/png.latex?H(x_{1},x_{2},x_{3}) = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3} + b" title="H(x_{1},x_{2},x_{3}) = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3} + b" /><br/><br/>
      
       y값은 역시 하나 이상일 수 있으며 y는 target이라합니다.<br/><br/>
       <i style = "font-size : 0.9em">정확하게는 x축의 개수가 feature, y축의 개수가 targer입니다.</i>
        
        <hr/>
        <div>
         <h3 style = "font-size :1.2em"> 행렬</h3><br/>
           <div style = "margin-left : 3%">
           <img src="https://latex.codecogs.com/png.latex?w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" title="w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" /> 이녀석을 <br/><br/>
           <img src="https://latex.codecogs.com/png.latex?\begin{pmatrix}
           x_{1} & x_{2} & x_{3}
           \end{pmatrix}\cdot \begin{pmatrix}
           w_{1}\\
           w_{2}\\
           w_{3}
           \end{pmatrix} = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" title="\begin{pmatrix}
           x_{1} & x_{2} & x_{3}
           \end{pmatrix}\cdot \begin{pmatrix}
           w_{1}\\
           w_{2}\\
          w_{3}
            \end{pmatrix} = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" />의 행렬 곱으로 나타 낼 수 있습니다.<br/><br/>
    조금만 생각해보면 <img src="https://latex.codecogs.com/png.latex?x" title="x"/>에 관한 행을 <img src="https://latex.codecogs.com/png.latex?X" title="X"/><br/><br/>
    <img src="https://latex.codecogs.com/png.latex?w" title="w"/>에 관한 행을 <img src="https://latex.codecogs.com/png.latex?W" title="W"/>,로 바꾸어<br/>
    아래와 같이 가설을 다시 선언 할 수 있습니다.<br/><br/>
    <img src="https://latex.codecogs.com/png.latex?H(X)=WX" title="H(X)=WX" /><br/><br/>
     <hr/>
       <div>
         <h3 style = "font-size :1.2em"> 인스턴스</h3><br/>
         <div style = "margin-left : 3%">
	dataSet을 행렬로 취급할 때 하나의 행 단위를 인스턴스라고 부릅니다.<br/><br/>
	<img src="https://latex.codecogs.com/png.latex?\begin{pmatrix}
	a1 & b1 & c1 & y1\\
	a2 & b2 & c2 & y2\\
	a3 & b3 & c3 & y3\\
	a4 & b4 & c4 & y4\\
	a5 & b5 & c5 & y5
	\end{pmatrix}" title="\begin{pmatrix}
	a1 & b1 & c1 & y1\\
	a2 & b2 & c2 & y2\\
	a3 & b3 & c3 & y3\\
	a4 & b4 & c4 & y4\\
	a5 & b5 & c5 & y5
	\end{pmatrix}"/><br/><br/>
	a, b, c는 data, y는 라벨입니다.<br/><br/>
	이 때 a1, b1, c1,  :: 첫번째 instance a2, b2 ,c2 :: 두번째 instance .... 가됩니다.<br/><br/>
         </div>
       </div>
     </div>
      <hr/>
   </div>
   <div>
     <h3 style = "font-size :1.2em">Cost함수</h3><br/>
       <div style = "margin-left : 3%">
        단순 선형 회귀의 cost는 <img src="https://latex.codecogs.com/png.latex?Cost = \frac{1}{m}\sum_{i=1}^{m}(W(x^{i})-y^{i})^{2}" title="Cost = \frac{1}{m}\sum_{i=1}^{m}(W(x^{i})-y^{i})^{2}" />입니다.<br/><br/>
        다중 선형 회귀의 cost는 단순히 변수만 더 늘어난 꼴로 <img src="https://latex.codecogs.com/png.latex?Cost = \frac{1}{m}\sum_{i=1}^{m}(W(x1^{i}+x2^{i}+x3^{i}...)-y^{i})^{2}
" title="Cost = \frac{1}{m}\sum_{i=1}^{m}(W(x1^{i}+x2^{i}+x3^{i}...)-y^{i})^{2}
" />입니다.<br/><br/>
      </div>
   </div>
</div>
  </div>
 <hr/>
   <a hreft = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-6/">다음 포스팅</a><br/>은 다항 선형 회귀 구현입니다.<br/>
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
  <blockquote>해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다.<br/>
  영상과 강의자료는 배포가 불가하기에 공유가 불가하면 포스팅에 사용한 자료와 이미지는 개인적으로 복습하며 만들었습니다. </blockquote>
  <blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
    블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
    발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <hr/>
</div>
