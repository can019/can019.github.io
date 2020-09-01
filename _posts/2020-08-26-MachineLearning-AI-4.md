---
title: "[KAIST AI 교육 :: 데이터 분석 및 예측] 4"
date: 2020-08-26 00:33:15 -0400
categories: MachineLearning DataAnalyze Python Colab
published: true
---
# 단순선형회귀에서의 경사하강법 in 파이썬(Python)

<hr/>
<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-3/">지난 포스팅</a><br/>
  <div>
    <h3 style = "font-size :1.2em"> 환경</h3>
    <div style = "margin-left : 3%">
     colab을 사용할 수도, 아니면 local에서 pycharm으로 할 수 있습니다.<br/>
     본 포스팅은 pycharm으로 했습니다.

  </div>
 <hr/>
<div>
    <h3 style = "font-size :1.2em"> Tensorflow version</h3><br/>
    <div style = "margin-left : 3%">
     20년 7월 기준으로 텐서플로우 2.3가 업데이트 되었습니다.<br/>
     텐서플로우 2.0 이후 버전은 상관이 없으나 만약 그 아래 버전은 일부 문법이 다르기 때문에<br/>
     다른 블로그를 찾아보시거나 2.3으로 업데이트 하시길 바랍니다.<br/><br/>
     <img src="/assets/photos/code/tensorflow_version_code.png"><br/><br/>
     <img src="/assets/photos/code/tensorflow_version_console.png"><br/><br/>
      텐서플로우 버전은 다음과 같이 확인하면 됩니다.<br/><br/>
      만약 텐서플로우가 없다고 뜬다면 텐서플로우 라이브러리를 설치하셔야 하는데<br/><br/>
      pycharm asset에서 다운로드를 받거나 anaconda를 통하여 설치하시면 됩니다.<br/><br/>
      만약 자신이 anaconda와 tensorflow가 설치 되었는데 pycharm에서 오류가 뜬다면<br/><br/>
      pycharm의 project interpreter가 visual studio나 pycharm등의 디렉토리로 설정되어서 그렇습니다.<br/><br/>
      프로젝트를 생성할 때 interpreter를 anaconda가 있는 위치로 바꾸어 주거나<br/>
      File > Setting > Project Interpreter로 이동하셔서 디렉토리를 바꿔주시면 됩니다.<br/><br/>
      <img src="/assets/photos/code/pycharm_interpreter_setting.png"><br/><br/>
      프로젝트 생성 후 interpreter를 바꾸는 방법은 다음과 같습니다.<br/><br/>
      파이썬 설치법과 프로젝트 생성등 기본적인 것은 다루지 않습니다.<br/><br/>
     <hr/>
  </div>
  <div>
    <h3 style = "font-size :1.2em">구현</h3>

    <div style = "margin-left : 3%">
       <div>
         <h3 style = "font-size :1.2em">라이브러리 없이 구현</h3><br/>
              <div style = "margin-left : 3%">
        		<img src="/assets/photos/code/linear_regression_1.png" width="850"><br/><br/>
		미분과 경사하강을 라이브러리 없이 구현하였습니다.<br/><br/>
		line 3 :: tensorflow 변수 w를 선언하고 -3으로 초기화합니다. (주석이 잘못되었습니다.)<br/>
		line 8, line 9 :: for문 안에서 가설을 세우고 cost를 정의해줍니다.<br/><br/>
		line 11 :: 경사하강 알고리즘 공식의 alpha값을 정해줍니다. 보통 learning_rate로 선언합니다.<br/>
		<i style = "font-size : 0.9em">+11번 line에서 alpha값은 for문을 열기전에 선언해 주는것이 맞습니다.</i><br/><br/>
		line 12 :: 현재 w에서 cost를 미분해주고 미분값을 gradient에 저장,<br/>
		line 13 :: gradient를 토대로 다음 w값을 descent에 저장합니다.<br/><br/>

		line 14 :: assign이라는 tensorflow 라이브러리 함수를 통하여 w값을 변경합니다.<br/><br/>
		line 17, 18 :: 10단위 sequence일 때 현재 step, cost, w값을 출력합니다<br/>
		line 19 :: 학습을 마친 후 완성된 모델을 출력합니다<br/><br/>

		w는 tensorflow 변수이기 때문에 사칙연산을 비롯한 모든 연산, 값 update는<br/>
		tensorflow library 메소드를 통해 해줍니다.<br/><br/>

              </div>
	<hr/>
        </div>
        <div>
         <h3 style = "font-size :1.2em">라이브러리로 구현</h3><br/>
              <div style = "margin-left : 3%">
		<img src="/assets/photos/code/linear_regression_2.png" width="850"><br/><br/>
        		라이브러리로 구현한 코드입니다. 가설에 y절편이 추가되었습니다.<br/>
		library를 사용한 부분만 설명하겠습니다.<br/><br/>

		line 20 :: GradientTape라는 tensorflow library를 사용합니다.<br/>
		GradientTape은 경사하강에 필요한 메소드들을 가지고 있으며<br/>
		변곡점, 미분값, 미분된 함수 등등.. 다양한 기능을 제공합니다.<br/><br/>

		line 24 :: w_grad는 w에 대한 미분값, b_grad는 b에대한 미분값입니다.<br/>
		parameter1은 미분 대상 그래프, parameter2는 미분할 변수입니다.<br/>
		parameter2는 multiple linear regression 코드를 보면 이해를 바로 하실겁니다.<br/><br/>

		line 26, 27 :: w_grad, b_grad 값을 통해 w를 변경합니다.<br/>
		assign_sub는 tensorflow 라이브러리 함수로 호출한 tensor변수 - parameter값을 tensor변수에 저장합니다.<br/><br/>


              </div>
	<hr/>
        </div>
        <div>
        	<h3 style = "font-size :1.2em">Kaggle data set을 통한 실습</h3><br/>
             <div style = "margin-left : 3%">
	    data set 파일의 확장자는 .csv, .txt.. 등등이 있습니다.<br/>
                보통 엑셀(.csv) 확장자로 되어있습니다. 

	    <div>
        	       <h3 style = "font-size :1.2em">1. Random number</h3><br/>
            	<div style = "margin-left : 3%">
		random number라 했지만 사실 하나의 직선상에 있는 점들과<br/>
		극값 하나가 포함된 dataset입니다.<br/><br/>
		<img src="/assets/photos/code/random_number_dataset.png"><br/><br/>
		data set은 다음과 같습니다.<br/><br/><br/>
		
		코드를 살펴보겠습니다.<br/><br/>
		<img src="/assets/photos/code/randonm_number_code.png"><br/><br/>
		data set 추가와 learning rate, 그리고 line 27~30 그래프를 띄워주는 것 이외에는<br/>
		차이점이 없습니다.<br/><br/>
		
		w값과 b값의 초기값은 편의를 위하여 model과 비슷한 값으로 넣었습니다.<br/><br/>
		<img src="/assets/photos/code/randonm_number_console.png"><br/><br/>
		console 출력은 다음과 같습니다.<br/><br/>
		<img src="/assets/photos/code/randonm_number_answer.png" width = "500"><br/><br/>
		완성된 모델과 실제 dataset을 matplt을 이용해 그래프로 띄워보았습니다.<br/>

		붉은색이 우리가 추정한 모델이며 파란색은 dataset으로 점들입니다.
          		   </div>
	           <hr/>
        	      </div>

	    <div>
        	       <h3 style = "font-size :1.2em">2. Height & Weight</h3><br/>
            	<div style = "margin-left : 3%">

		<img src="/assets/photos/code/Height_Weight_dataset.png"><br/><br/>
		data set은 다음과 같습니다.<br/><br/><br/>
		
		<img src="/assets/photos/code/Height_Weight_code.png"><br/><br/>
		코드입니다.<br/><br/>

		<img src="/assets/photos/code/Height_Weight_console.png"><br/><br/>
		console 출력은 다음과 같습니다.<br/><br/>

		<img src="/assets/photos/code/Height_Weight_answer.png" width = "500"><br/><br/>
		
		붉은색이 우리가 추정한 모델이며 파란색은 dataset으로 점들입니다.

          		   </div>
	           <hr/>
        	      </div>

	   <div>
        	       <h3 style = "font-size :1.2em">3. Salary & Experience</h3><br/>
            	<div style = "margin-left : 3%">
			
		<img src="/assets/photos/code/Salary_Experience_dataset.png"><br/><br/>
		data set은 다음과 같습니다.<br/><br/><br/>
		
		<img src="/assets/photos/code/Salary_Experience_code.png"><br/><br/>
		코드입니다.<br/><br/>
		<img src="/assets/photos/code/Salary_Experience_datainfo.png"><br/><br/>

		data.info()를 통해 대략적인 dataset의 정보를 파악할 수 있습니다.<br/>
		<img src="/assets/photos/code/Salary_Experience_console.png"><br/><br/>
		console 출력은 다음과 같습니다.<br/><br/>
		
		<img src="/assets/photos/code/Salary_Experience_answer.png" width = "500"><br/><br/>
		
		붉은색이 우리가 추정한 모델이며 파란색은 dataset으로 점들입니다.<br/>
		learning rate와 max epoch를 줄여주어도 될 것 같습니다.<br/><br/>
          		   </div>
	           <hr/>
        	      </div>

              </div>
	코드와 dataset은 <a href = "https://github.com/can019/machineLearning/tree/master/Linear%20Regression/Simple%20Linear%20regression">깃허브</a>를 참조하시면 됩니다.
	
	<hr/>
        </div>
  </div>
  </div>
<a href = "https://can019.github.io/machinelearning/dataanalyze/python/colab/MachineLearning-AI-5/">다음 포스팅</a>다중 선형 회귀에 대해 살펴보겠습니다.<hr/>
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
  <hr/>
</div>
