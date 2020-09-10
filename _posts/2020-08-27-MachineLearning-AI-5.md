title: "[MachineLearning 5] 다중 선형 회귀"	title: "[MachineLearning 1] 머신러닝이란?"
date: 2020-08-27 21:00:15 -0400	date: 2020-08-18 20:15:30 -0400
categories: MachineLearning DataAnalyze	categories: MachineLearning DataAnalyze
---	---
## 다중 선형 회귀(Multiple Linear Regreesion)	


## 머신러닝


<div style = "font-size :0.8em">	<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/python/colab/MachineLearning-AI-4/">지난 포스팅</a><br/>	
  <div>	  <div>
    <h3 style = "font-size :1.2em"> 다중 선형 회귀</h3><br/>	    <h3 style = "font-size :1.2em"> 머신러닝</h3><br/>
    <div style = "margin-left : 3%">	    <div style = "margin-left : 3%">
       저번 시간 포스팅했던 선형 회귀는 input 변수. 즉 feature가 하나인 경우에 대해 다루었습니다.<br/><br/>	      우리말로 하자면 기계학습으로 경험(학습)을 통해 자동으로 개선시키는 컴퓨터 알고리즘입니다.<br/>
       다중 선형 회귀는 feature가 하나가 아닌 둘 이상인 경우입니다.<br/><br/>	      인간이 지식을 통해 학습을 하는 것과 다르게 기계는 데이터를 통해 학습을 합니다.<br><br>
       feature가 하나 -> <img src="https://latex.codecogs.com/png.latex?H(x) = wx+b" title="H(x) = wx+b" /><br/><br/>	
       feature가 셋 -> <img src="https://latex.codecogs.com/png.latex?H(x_{1},x_{2},x_{3}) = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3} + b" title="H(x_{1},x_{2},x_{3}) = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3} + b" /><br/><br/>	      이 때 인간과 다르게 기계는 하나의 식(그래프)을 학습결과로 얻습니다. <br><br>

      이 식은 데이터들을 설명할 수 있는 식으로 1차함수, 2차함수가 될 수도 있고 아주 복잡한 식이 되기도 합니다. <br><br>
       y값은 역시 하나 이상일 수 있으며 y는 target이라합니다.<br/><br/>	      <hr>
       <i style = "font-size : 0.9em">정확하게는 x축의 개수가 feature, y축의 개수가 target입니다.</i>	      <div>

        <h3 style = "font-size :1.2em"> 모델</h3><br/>
        <hr/>	        <div style = "margin-left : 3%">
        <div>	
         <h3 style = "font-size :1.2em"> 행렬</h3><br/>	          기계학습시 컴퓨터에게 데이터만 전달한다고 컴퓨터가 알아서 최적의 식을 찾아주진 못합니다 <br>
           <div style = "margin-left : 3%">	          적어도 식이 1차가 될지, 2차가될지 아니면 어떠한 복잡한 식이 될지 개형정도는 알려줘야합니다 <br><br>
           <img src="https://latex.codecogs.com/png.latex?w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" title="w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" /> 이녀석을 <br/><br/>	
           <img src="https://latex.codecogs.com/png.latex?\begin{pmatrix}	          그래프의 개형과 데이터를 컴퓨터에게 알려주면 컴퓨터는 데이터들을 통해 뼈대만 있는 식의 계수들을 찾아내는 것이죠. <br><br>
           x_{1} & x_{2} & x_{3}	
           \end{pmatrix}\cdot \begin{pmatrix}	          즉, 기계가 하는 일은 데이터를 통해 <b>최적의 계수(매개변수)</b>(기울기, y절편 등..)을 찾아내는 것이라고 말할 수 있습니다. <br><br>
           w_{1}\\	
           w_{2}\\	          그렇다면 사람이 해주어야 하는 일은 <b>학습시 사용할 적합한 개형을 설계</b>하는 것이라는 것을 알 수 있습니다. <br><br>
           w_{3}	
           \end{pmatrix} = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" title="\begin{pmatrix}	          하지만 어떠한 개형이 데이터를 잘 설명할지 알기 어려운 경우가 필연적으로 발생합니다. <br><br>
           x_{1} & x_{2} & x_{3}	
           \end{pmatrix}\cdot \begin{pmatrix}	          따라서 훈련 시 다양한 개형의 설계함수를 훈련시키고, 이 훈련시킨 함수들 중 가장 적합한 식을 결과로 채택합니다. <br><br>
           w_{1}\\	
           w_{2}\\	          이 때 훈련시킨 함수들을 <b>'모델 집합'</b>이라고 하며, <br>훈련시킨 함수 또는 훈련시키기 전의 뼈대만 있는 식을 <b>'모델'</b>이라고 합니다 <br><br><br>
          w_{3}	
            \end{pmatrix} = w_{1}x_{1}+w_{2}x_{2}+w_{3}x_{3}" />의 행렬 곱으로 나타낼 수 있습니다.<br/><br/>	
    조금만 생각해보면 <img src="https://latex.codecogs.com/png.latex?x" title="x"/>에 관한 행을 <img src="https://latex.codecogs.com/png.latex?X" title="X"/><br/><br/>	          <ul>
    <img src="https://latex.codecogs.com/png.latex?w" title="w"/>에 관한 행을 <img src="https://latex.codecogs.com/png.latex?W" title="W"/>,로 바꾸어<br/>	            <li>'모델(또는 모델 함수)로 1차함수를 선택했다'</li>
    아래와 같이 가설을 다시 선언 할 수 있습니다.<br/><br/>	            <li>'모델집합에서 1번 모델이 적합한 것 같다'</li>
    <img src="https://latex.codecogs.com/png.latex?H(X)=WX" title="H(X)=WX" /><br/><br/>	          </ul>
     <hr/>	          <hr>
       <div>	          <div>
         <h3 style = "font-size :1.2em"> 인스턴스</h3><br/>	            <h3 style = "font-size :1.2em"> 바이어스와 분산</h3><br/>
         <div style = "margin-left : 3%">	            <div style = "margin-left : 3%">
	dataSet을 행렬로 취급할 때 하나의 행 단위를 인스턴스라고 부릅니다.<br/><br/>	              <img src = "/assets/photos/machineLearning1/bias_dispersion.png" ><br><br>
	<img src="https://latex.codecogs.com/png.latex?\begin{pmatrix}	              바이어스는 예측값이 정답과 가까울수록 낮고,
	a1 & b1 & c1 & y1\\	              분산은 예측값들이 몰려있을수록 높습니다. <br><br>
	a2 & b2 & c2 & y2\\	
	a3 & b3 & c3 & y3\\	              따라서 바이어스가 높다는 것은 모델의 정답률이 떨어진다고 볼 수 있습니다.<br><br>
	a4 & b4 & c4 & y4\\	
	a5 & b5 & c5 & y5	              바이어스가 낮고 분산이 높은 모델이 이상적인 모델이지만<br>
	\end{pmatrix}" title="\begin{pmatrix}	              바이어스와 분산은 트레이드오프 관계이기 때문에 <br>
	a1 & b1 & c1 & y1\\	              바이어스와 분산 둘다 잡는 것은 불가능합니다. <br><br>
	a2 & b2 & c2 & y2\\	
	a3 & b3 & c3 & y3\\	              따라서 바이어스의 희생을 최소로 유지하며 분산을 최대로 낮추는 방향으로 모델을 짜야합니다.<br><br>
	a4 & b4 & c4 & y4\\	
	a5 & b5 & c5 & y5	            </div>
	\end{pmatrix}"/><br/><br/>	          </div>
	a, b, c는 data, y는 라벨입니다.<br/><br/>	
	이 때 a1, b1, c1,  :: 첫번째 instance a2, b2 ,c2 :: 두번째 instance .... 가됩니다.<br/><br/>	        </div>
         </div>	        <hr>
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
      </div>	      </div>
   </div>	      <div>
</div>