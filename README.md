# 오픈핵 DOGGY팀의 사람 견종 매칭 

## 구글의 텐서플로우
  구글의 텐서플로우 Inceptrion V3 모델 사용(google Net, CNN계열)
  큰 이미지를 여러개의 분류된 형태의 확률을 얻음
  그 중 원하는 분류가 나온 즉 비교 데이터와 일치하는 값을 얻어서 학습함

 ## dog classification
   모델과 가중치가 합쳐진 pb 파일로 단순히 학습된 가중치를 통해 결과를 얻음
   개를 견종에 따라 분류된 dog_graph.pb파일을 이용하여 대입한 사진에 대해서 해당 개의 견종을 알아낼 수 있음
   단 1분 정도만에

 ## doggy machine learning
   사람에 대하여 사람과 비슷 한 견종을 알아내기 위해서는 사람데이터와 견종데이터 그리고 학습 결과를 비교할 
   사람에 따라 견종이 매칭된 데이터(설문조사와 같은 방법으로 얻을 수 있음)가 필요하고 이것을 학습할 비용과 시간이 필요.

   오픈 핵에서는 물리적으로 한계가 있음

   그래서 고안한 방법이 개와 사람의 눈과 코 입 구조는 비슷하고 개도 사람처럼 얼굴이 둥글고 크고 작는 등 그런 특징을 가짐

   그렇기에 개에 대해서 견종을 분류를 학습한 가중치파일을 얻어 모델 사용 시 개의 이미지가 아닌 사람의 이미지를 넣음

   그러면 120개의 견종에 대한 매칭 확률이 나오는 데 그 중 가장 큰 확률 값을 가지는 견종을 

   해당 사람과 비슷한 개라고 판단함.

  ## 사용법
    학습된 모델과 가중치의 파일인 pb파일과 분류 종류의 리스트 파일 txt의 경로를 코드에 넣고
    확장자명 제한 없이 분류시키고 싶은 사진한개의 경로를 코드에 넣고
	나오는 분류종류의 확률 중 가장 큰 확률을 가지는 값을 얻음 

  ## dog_graph.pb
  	1.2백만 개의 개의 사진을 120종류의 견종으로 분류시켜 얻은 가중치와 모델을 합친 데이터

  ## dog_label.txt
  	120개 견종의 이름 명단
