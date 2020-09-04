---
title: "[MachineLearning 6] 이진 분류 "
date: 2020-09-04 11:14:15 -0400
categories: MachineLearning DataAnalyze
---
## 이진 분류(binary classification)


<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-6/">지난 포스팅</a><br/>
  <div>
      <div>
    	<h3 style = "font-size :1.2em"> 이진 분류</h3><br/>
    	<div style = "margin-left : 3%">
	 참과 거짓. 0 또는 1의 결과값을 가지는 회귀분석법입니다.<br/><br/>
	 선형회귀의 연장선으로 어떠한 선형식을 추론한 뒤<br/>
	 이 선형식을 다시 어떠한 함수에 대입하여 0, 1의 값으로 인코딩합니다<br/<br/>

	 간결하게 말하면 z = wx+b, g(z) = 0~1 라고 말할 수 있으며<br/>
	 z는 시그모이드(sigmoid)라는 논리함수를 사용하게 됩니다.<br/><br/>
	 그래프 개형이 'S'자와 같아 시그모이드라는 이름이 붙게 되었습니다.<br/><br/>
  
	 g(z) = 1/(1+e^-z), H(x) = g(z), z= WX <br/>
	 H(x) = 1/1+e^-w^tX  -> (w^T)X+b하는 이유 : 원래 XW인데 행렬곱을 위해 W을 transpose 함.
	  <div>
    		<h3 style = "font-size :1.2em"> 비용함수</h3><br/>
    		<div style = "margin-left : 3%">
			H(x)가 변경되었으므로 비용함수 역시 형태가 변경됩니다.<br/><br/>
			선형회귀법과 같이 거리의 제곱으로 cost함수를 만드게 된다면<br/>
			그래프가 포도송이모양으로 형성되는데<br/>
			local minima가 여러번 생기기 때문에 경사하강법을 사용하기 어렵습니다.<br/><br/>
			
			그래서 논리값을 위해 새로운 비용 함수를 설계합니다.<br/><br/>
			 H(x) = 1/1+e^-w^tX  -> (w^T)X+b<br/><br/>
			cost(W) = 1/m * sigma c(H(x),y)<br/><br/>
			c(H(x),y) = -log(H(x))  : y=1 ,  -log(1-H(x))  : y=0<br/><br/>

			y = 1일 때 -log(z)는 왼쪽에서 떨어지는 곡선<br/>
			y = 0일 때 -log(1-z)는 오른쪽에서 떨어지는 곡선<br/><br/>

			이분화된 식을 하나의 식으로 합치면<br/>
			c(H(x),y) = -ylog(H(x)) - (1-y)log(1-H(x))<br/><br/>
			Cost(W) = -1/m * sigma(-ylog(H(x)) - (1-y)log(1-H(x)))<br/><br/>
			w := w- alpha*cost(w)미분<br/><br/>



		</div>
	   </div>
	    <div>
    		<h3 style = "font-size :1.2em"> 완성된 모델을 통한 분류</h3><br/>
    		<div style = "margin-left : 3%">
			완성된 학습으로 sample을 넣을 경우 0~1의 값이 반환됩니다<br/><br/>
			이때 0.5이상이라면 1, 0.5 아래라면 0으로 판별합니다.


		</div>
	   </div>
      	</div>
     </div>
  </div>
 <hr/>
    ***미완성 포스팅***<br/>
   <div style = "font-size :0.8em">
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
   <blockquote>해당 포스팅은 KAIST교육을 바탕으로 하며 이해에 필요한 추가적인 정보를 덧붙였습니다.<br/>
  	영상과 강의자료는 배포가 불가하기에 공유가 불가하면 포스팅에 사용한 자료와 이미지는 개인적으로 복습하며 만들었습니다. </blockquote>
  	<blockquote> 공학이 뭐 그렇듯 용어들은 보통 영어로 기술합니다.<br/>
   	 블로그에서는 되도록이면 용어를 한글과 영어 두개 다 쓰겠지만<br/>
   	 발전을 위해서는익숙해지는게 정신건강에 편합니다.
  </blockquote>
  <blockquote>
  	  환경<br/>
   	CPU :: Amd RYZEN9 3900X<br/>
   	GPU :: Asus GeFore RTX 2080<br/>
    	RAM :: DDR4 8G PC4-21300 x2 (3200Mhz, CL 16)<br/>
    	IDE :: Pycharm<br/>
    	Os :: Window 10<br/>
   	 Anaconda :: version 3<br/>
   	 tensorflow :: for cpu and gpu<br/>
    <div style = "margin-left : 3%">
       version :: 2.3.0<br/>
    </div>
  </blockquote>
</div>
  <hr/>
</div>
