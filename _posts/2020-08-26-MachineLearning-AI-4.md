---
title: "[KAIST AI 교육 :: 데이터 분석 및 예측] 4"
date: 2020-08-26 00:33:15 -0400
categories: MachineLearning DataAnalyze Python Colab
published: true
---
# 경사하강법(Gradient Descend Algorithm)과 단순선형회귀에서의 경사하강법 in 파이썬(Python)

<hr/>
<div style = "font-size :0.8em">
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-3/">지난 포스팅</a><br/>
  <div>
    <h3 style = "font-size :1.2em"> 환경</h3><br/>
    <div style = "margin-left : 30px">
     colab을 사용할 수도, 아니면 local에서 pycharm으로 할 수 있습니다.<br/>
     본 포스팅은 pycharm으로 했습니다.
     <hr/>
    
  </div>
 <hr/>
<div>
    <h3 style = "font-size :1.2em"> Tensorflow version</h3><br/>
    <div style = "margin-left : 30px">
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
    <h3 style = "font-size :1.2em">구현</h3><br/>
    <div style = "margin-left : 30px">
       <div>
         <h3 style = "font-size :1.2em">라이브러리 없이 구현</h3><br/>
              <div style = "margin-left : 30px">
        		<img src="/assets/photos/code/linear_regression_1.png"><br/><br/>
		미분과 경사하강을 라이브러리 없이 구현하였습니다.<br/><br/>
		tensorflow 변수를 선언, for문 안에서 가설을 세운 후<br/>
		cost를 정의해줍니다.<br/><br/>
		이후 12번째 줄에서 현재 w에서 cost를 미분해주고 그 값을 gradient에 저장,<br/>
		descent에 다음 w값을 임시로 저장합니다.<br/><br/>
		그 후 14번줄에서 assign이라는 tensorflow 라이브러리 함수를 통하여 w값을 변경합니다..<br/><br/>
		
		w는 tensorflow 변수이기 때문에 사칙연산을 비롯한 모든 연산, 값 update는<br/>
		tensorflow library 메소드를 통해 해줍니다.<br/><br/>
		+11번 line에서 alpha값은 for문을 열기전에 선언해 주는것이 맞습니다.<br/><br/>

              </div>
        </div>
        <div>
         <h3 style = "font-size :1.2em">라이브러리로 구현</h3><br/>
              <div style = "margin-left : 30px">
        		
              </div>
        </div>
  </div>
  </div>
<a href = "">다음 포스팅</a>은 파이썬 코드로 구현하는 법을 알아보겠습니다.<hr/>
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
    <div style = "margin-left : 30px">
       version :: 2.3.0<br/>
    </div>
  </blockquote>
  <hr/>
</div>
