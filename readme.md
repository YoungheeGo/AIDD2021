# About the competition
- 대회설명을 보려면 [클릭](/origin-READ.md)


# About Model
- baseline model : lightGBM
- 시도한 모델: knn,xgb, catboost, Stacking
- lightGBM이 성능이 가장 좋았음. 하지만 이 모델의 공식 문서에도 만개 이하의 dataset에서는 과적합이 쉽게 발생한다고 하는데, 우리 데이터는 2천개(그 중 168개가 target)로 lightGBM이 가장 성능이 좋았던 걸 보면, 아마도 과적합을 의도적으로 발생시켜야하는 컴퍼티션이었던 것 같다.
- Feature Engineering를 좀만 더 했으면 or NeuralNet을 사용했다면 결과가 달라지지 않았을까? 하는 아쉬움이 많이 남는 대회
- 40팀 중에서 30등으로 마감했다. 정말 대단한 사람들이 너무 너무 많았다! 우리는 하위권~!! 앞으로 더 열심히 공부해야겠다는 자극을 받았다!!

# About Deep Learning
- 딥러닝이 왜 밑바닥부터 코드를 구현하면서 공부하는 게 중요한 것인지를 알았다.
- + 파라미터 개수를 구하는 방법/공식이 왜 중요한지 알게되었다.
- 이전에는 그냥 패키지를 쓰면 되지 굳이 고생을 사서 해야하나? 라고 생각했는데, 데이터 특성에 따라서 레이어를 다르게 구성할 수도 있는 거고, 레이어가 끝날 때 마다 변경되는 파라미터 output 의 개수가 다음레이어의 input 파라미터 개수여서 레이어를 새로 추가/삭제 할 때 마다 파라미터 개수를 다르게 넣었어야 했다. 따라서, 밑바닥부터 구현하면서 파라미터 개수를 수정하는 것은 매우 매우 중요한 과정이었다.
- 딥러닝에서는 주어진 모델을 "사용"한다 라기 보다는 주어진 모델을 "활용"(사용+재가공)해서 데이터에 적용시키는 말이 더 잘 맞는 것 같다.
- 나중에 여유가 있을 때 딥러닝 처음부터 다시 공부해봐야지! (+ CNN은 이미지 데이터, RNN은 텍스트 데이터에 국한시키지 말자! 모델의 input 에 대한 유연성을 갖자!)

# About NSML
- 이 대회는 리더보드 대회 + 해커톤이 합쳐진 데이터톤이었다. 이러한 형태의 데이터톤은 처음 출전한 거라서 대회 진행방식이 매우 생소했다. 보통 리더보드 대회는 기간을 충분히 주지만, 이 대회는 시간이 매우 촉박한 해커톤의 형태를 취하고 있어 시간 관리를 잘 해야하는 컴퍼티션이었다.
- 네이버에서 개발한 머신러닝 플랫폼 NSML 을 처음 사용해봤는데 도커에러, 서버 에러, 로그인 에러 (&#128545;)가 굉장히 많이 떴다. 또한 모델 코드의 템플릿이 존재해서 마음대로 막 모델 구축 파이썬 스크립트를 작성할 수 없었다. 처음에는 Grid Search 방법도 먹히지 않았지만, 도커에 대해 배웠던 적이 아주 잠깐 있어서 그 부분을 찾아보고 템플릿을 수정해서 GridSearch 방법이 가능하도록 수정했다. 이런 도커 관련 부분에서 우리 팀은 시간을 꽤 많이 써서 모델 구축 시간이 별로 없었다.
- 심지어 submit 시간도 팀 별 시간당 1회여서 도커에러로 늦게 시작한 우리 팀은 모델링 부분에서 상대적으로 불리한 위치에서 시작해야했다.
- 그래도 학부생으로서 네이버 머신러닝 플랫폼을 써 본 경험이라도 얻었으니 만족한다! 

# About Data Analysis
- 데이터 분석가가 raw 데이터를 보는 경우는 생각보다 많이 없는 것 같다. 서버를 통해 보는 것 같음. 보안상의 문제로 인해 로우 데이터는 데이터 엔지니어가 보고, 분석가는 엔지니어가 뽑아준 데이터만 볼 수 있는 것 같다.
- 이 대회는 의료 데이터라 보안상의 이유로 raw data를 볼 수 없었다. 전처리도 주최측에서 다 한 상태였다. 따라서 EDA도 불가능 했다. EDA 없이 순전히 다양한 모델링을 여러번 시행하고 어떤 모델이 loss가 덜 나오는지를 파악해야했다. 하지만 그래도 EDA가 불가능한건 너무했다. matplotlib 라이브러리 좀 지원해주라~~
- 분명한 건 데이터 분석가와 엔지니어는 다른 일을 한다는 사실이다.

# Next Competition
- 어떤 데이터를 다룰 것이냐를 정하는 것이 중요하다는 이야기를 많이 들었다.
- 다양한 분야 중, 요즘 관심있는 의료 데이터를 다루는 공모전을 나가봤는데 FE과정에서 의료 도메인 지식이 많이 필요했다.
- 다음번이 있을 지 모르겠지만 의료 데이터 공모전을 또 한번 나가게 된다면 분석적인 능력 보강이 필요할 것 같다.
- 아직은 대회의 특성 상 데이터 보안 때문에 의료 데이터가 내가 정말 재미있어 하는 데이터인지 확인을 해보지 못했다.
- 다음에 이런 대회가 있다면, ANN 뿐 만이 아니라 MLP 도 써봐야지!

- 팀원들과 함께 도메인 공부했던 흔적 남기기!
![image](https://user-images.githubusercontent.com/77769026/143005802-2a4d8b52-59b7-4b3e-a2f9-6e9e2ce93493.png)

+ 공부한 흔적 남기기
export PATH=$PATH:/c/nsml

nsml run -d nia_dm_prelim -e main.py
nsml run -d nia_dm_prelim -e ./AIDD2021/baseline/main_bnb.py 

nsml submit -t AID029/nia_dm_prelim/[세션번호] 0

- t는 문제 없는지 돌려보기

세션을 통해서 모델의 체크포인트 보기
nsml model ls AID029/nia_dm_prelim/601

AID029/nia_dm_prelim/123 : LGBM + FE 

dataset key: dict_keys(['X_train', 'y_train', 'X_val', 'y_val'])
dataset은 dictionary 형태!

Type of dataset:  <class 'dict'>
Type of X_train:  <class 'pandas.core.frame.DataFrame'>
Columns of X_train:  Index(['age', 'Ht', 'Wt', 'BMI', 'SBP', 'DBP', 'PR', 'HbA1c', 'FBG', 'TC',
       'TG', 'LDL', 'HDL', 'Alb', 'BUN', 'Cr', 'CrCl', 'AST', 'ALT', 'GGT',
       'ALP', 'gender_enc'],
      dtype='object')
Cr, AST, ALT, ALT, ALP, GGT*Gender, GGT+ALP

loss: 1보다 큼 => recall 상승 (recall=tp/(tp+fn))
loss: 1보다 작음 => precision 상승 (precision=tp/(tp+fp))
