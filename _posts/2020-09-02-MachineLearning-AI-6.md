---
title: "[MachineLearning 6] 다중 선형 회귀 tensorflow"
date: 2020-09-02 21:00:15 -0400
categories: MachineLearning DataAnalyze
---
## 다중 선형 회귀 (Multiple Linear Regreesion) in python code


<div style = "font-size :0.8em"><!--Largest-->
  <a href = "https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-5/">지난 포스팅</a><br/>
  <div><!--chapter1-->
    <h3 style = "font-size :1.2em"> 다중 선형 회귀</h3>
    <hr/>
    	<div style = "margin-left : 3%">
		      <div><!--chapter2-->
    	       <h3 style = "font-size :1.2em">기본 구현</h3>
    				 <div style = "margin-left : 3%">
               <div><!--chapter3-->
                  <h3 style = "font-size :1.2em">without 행렬</h3><br/>
                  <div style = "margin-left : 3%">
                    다중 선형 회귀 역시 단순 선형 회귀 코드와 비슷합니다.<br/><br/>
                    <img src="/assets/photos/machineLearning6/multiple_linear_regression_without_matrix_code.png"><br/><br/>
                    line 2~5 :: dataSet <br><br>
                    line 8~10 :: temsorflow 변수추가 <br>
                    tf.random.normal()은 난수를 발생하는 라이브러리 함수입니다.<br><br>

                    line 13 :: learning rate 설정 <br><br>
                    line 15~24 :: train <br>
                    range(10000+1)인 이유는 10000번째 epoch의 cost출력을 위함입니다.<br><br>
                    line 26~27 :: cost 출력 <br>
                  </div>
                  <hr/>
                </div><!--chapter3-->
                <div><!--chapter3-->
                   <h3 style = "font-size :1.2em">with 행렬</h3><br/>
                   <div style = "margin-left : 3%">
                     행렬 연산을 사용한 코드입니다.<br><br>
                     <img src="/assets/photos/machineLearning6/multiple_linear_regression_with_matrix_code.png"><br/><br/>
                     line 3~10 :: dataSet 준비<br>
                     일반적으로 dataSet은 다음과 같은 형태를 띕니다.<br><br>

                     line 13, 14 :: data와 label을 분리합니다.<br/><br/>

                     line 16, 17 :: tensorflow 변수 선언 <br>
                     행렬곱을 사용할 것이므로 다음과 같이 선언합니다. <br><br>

                     line 18, 19 :: 행렬곱 함수 선언 <br>
                     행렬곱 결과를 return해주는 함수를 선언합니다. <br>
                     곱을 위해서는 WX가 아닌 XW을 해주어야 하므로 순서에 주의하여야 합니다.<br>
                     matmul은 행렬곱을 하는 tf 라이브러리 함수입니다. <br><br>

                     line 21~23 :: learning rate, max epoch 설정 <br><br>

                     line 25~32 :: train <br><br>

                     line 34, 35 :: cost 출력 <br><br>

                   </div>
                 </div><!--chapter3-->
  			     </div>
             <hr/>
  		  </div><!--chapter2-->
        <div><!--chapter4-->
           <h3 style = "font-size :1.2em">with keggle</h3>
           <div style = "margin-left : 3%">
             <div><!--chapter3-->
                <h3 style = "font-size :1.2em">1. HousePrice</h3><br/>
                <div style = "margin-left : 3%">
                   <img src="/assets/photos/machineLearning6/multiple_linear_regression_HousePrice_dataInfo.png"><br/><br/>
                   데이터 개요입니다. <br>
                   21개의 column이 있지만 kaggle 의 compact에 설명된 7개의 column을 사용합니다. <br><br>

                   <img src="/assets/photos/machineLearning6/multiple_linear_regression_HousePrice_code.png"><br/><br/>

                   line 6~13 :: data 전처리 <br>
                   전처리라고 하기에도 허접합니다. 필요한 column을 추출합니다.<br><br>

                   line 16, 17 :: tensorflow 변수를 선언합니다. <br><br>

                   line 18 :: w 형태 출력 <br>
                   w가 어떤 꼴인지 알기 위해 출력한 디버그 코드입니다. 실수로 안지웠네요 <br><br>

                   line 19, 20 :: 행렬곱 함수 선언 <br><br>

                   line 22 :: learning rate 설정 <br><br>

                   line 14 :: max epoch 설정 <br><br>

                   line 25~32 :: train <br><br>

                   line 34, 35 :: 1000단위 epoch 별 cost 출력 <br><br>

                </div>
                <hr/>
              </div><!--chapter3-->
           </div>
      </div><!--chapter4-->
	   </div>
  </div><!--chapter1-->
 <hr/>
    <a href="https://can019.github.io/machinelearning/dataanalyze/MachineLearning-AI-5/">다음 포스팅 :: 이진 분류</a><br/>
   <div style = "font-size :0.8em"><!--blockquote-->
   <blockquote> 공부하며 작성하는 포스팅이기 때문에 수정사항이 생길 수 있습니다. </blockquote>
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
</div><!--blockquote-->
  <hr/>
</div><!--Largest-->
