# mlproject
<hr>

Project Title : 
<br>
Authors : Boseong Kang, Geonho Lee
<br>
Description of Question and Research Topic (5 Sentences)
Project Outline/Plan
Data Collection Plan (two parts, one for each author)
Model Plans (two parts, one for each author)
Project Timeline
A .gitignore file and a license

iconic singers by year 리스트에서 유명한 사람들 년도별 옷차림 -> CNN으로 feature 분석
CNN 모델로는 옷차림 특징을 일단 뽑고

빌보드에서 예시로 1~10까지 년도별로 노래 제목을 저장해서 그 노래들 가사를 텍스트 추출 -> LLM 단어 분
LLM은 단어분석 ML모델이라 노래의 트렌드를 분석

2000 ~ 2025 시대적 가수의 패션 + 노래 가사(시대적 정서) => 분석

예측을 할꺼면 JYP 가수를 만든다 했을때 어떤 가사와 어떤 옷차림을 타겟으로하면 1등이 될수있는지

option b -> LLM 단어 분석 
빌보드 탑 100의 가사와 장르를 전부 분석하고 순위에 맞춰서 어떤 단어들이 쓰이는지 분석

중복처리 어떻게 할지, 빼야할지 아니면 어떻게 넣고 처리할지 생각. 

+ 다른모델은 노래별 악기 사용량 분석 -> CNN 이나 RNN 
힙합 => 만약 드럼 비율이 높을거고 
발라드면 현악기 같은 비율이 높은거를 헤르츠를 시각화하거나 분석 + 템포까지 

이스펙트럼으로 분석하는게 안되면 
앨범 커버 CNN으로 이미지 분석하는거 


최종 얻고 싶은건:
A라는 가수가 노래를 낼때 힙합으로 낼꺼면 드럼을 많이사용해야하며 특정 단어를 사용하면 빌보드 100안에 올라갈 확률을 보여주며 
반례로, 힙합인데 드럼 사용량이 낮고 특정 많이 쓴 단어가 없으면 빌보드 탑 100안에 못들어갈거를 같이 보여줌 

