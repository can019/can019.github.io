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
    	<div style = "margin-left : 3%">
		      <div><!--chapter2-->
    	       <h3 style = "font-size :1.2em">기본 구현</h3><br/>
    				 <div style = "margin-left : 3%">
               <div><!--chapter3-->
                  <h3 style = "font-size :1.2em">withoud 행렬</h3><br/>
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
                </div><!--chapter3-->
                <div><!--chapter3-->
                   <h3 style = "font-size :1.2em">with 행렬</h3><br/>
                   <div style = "margin-left : 3%">
                     행렬 연산을 사용한 코드입니다.<br><br>
                     <img src="/assets/photos/machineLearning6/multiple_linear_regression_with_matrix_code.png"><br/><br/>

                   </div>
                 </div><!--chapter3-->
  			     </div>
  		  </div><!--chapter2-->
	   </div>
  </div><!--chapter1-->
 <hr/>
    ***미완성 포스팅***<br/>
   <div style = "font-size :0.8em"><!--blockquote-->
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
</div><!--blockquote-->
  <hr/>
</div><!--Largest-->
