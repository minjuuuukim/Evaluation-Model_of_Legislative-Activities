## Evaluation-Model_of_Legislative-Activities
## 국회 활성화를 위한 국회의원 입법활동 평가모델
> 24-1 P-SAT 시계열자료분석팀 주제분석

- 법률안의 발의 건수는 증가하고 있는 것에 비해, 가결률은 감소하고 있음. 


<img width="430" alt="image" src="https://github.com/user-attachments/assets/912c9977-ccfa-486d-9f05-7425f670b370" />

- 이는 국회의원의 평가세칙으로 발의안의 '질'이 아닌 '양'을 고려하고 있기 때문이며, 단순 건수로만 평가되기 때문에 같은 내용을 여러 법안으로 나눠서 발의하는 "법안 쪼개기"와 같은 꼼수를 쓰거나, SNS에 의원들의 단체 대화방을 개설하여 1시간 만에 법안 발의의 최소요건인 공동발의자 10명을 채우기도 하는 등 국회의 본질적인 기능이 사라지고 있음. 

<img width="416" alt="image" src="https://github.com/user-attachments/assets/9fcd61fc-8611-4803-ad77-a445a643e6d8" />

- 국회 임기가 끝날 때까지 본회의를 통과하지 못한 법안들은 자동으로 폐기되기 때문에, 우리에게 꼭 필요한 법안이 심의되지 못하거나 충분히 검토되지 못한 채 폐기될 수 있다는 문제점이 존재함.

- 따라서, 실적 채우기에 매몰되지 않는 국회의원 입법활동 평가모델을 수립함으로써 국민에게 필요한 실속있는 법안을 발의하도록 유도하고자 하는데에 목적이 있음.

> 분석 흐름
- 법률 발의안, 뉴스기사 데이터 수집 및 분석
  - 제 20대 국회의원 발의안 : 열린국회정보의 정보공개포털 크롤링
  - LDA 토픽모델링을 활용한 발의안 키워드 추출
- 각 발의안의 내용을 포함하는 발의안 데이터셋 구성
  - 발의안의 사회동향정도 계산 : 발의안 키워드와 뉴스 키워드의 유사도 계산
  - KoBERT, Doc2vec
  <img width="408" alt="image" src="https://github.com/user-attachments/assets/db427d91-ca98-4bd7-9ab3-365616a2465b" />


- 발의안에서 유의미한 feature를 뽑아 각 국회의원에 대한 데이터셋으로 구성
  - 국회의원별 발의안 평균분산도 산출
  - K-means 클러스터링의 inertia 값 이용
  - 낮은 경우
 
       <img width="155" alt="image" src="https://github.com/user-attachments/assets/9a64260e-d944-418e-9235-7e71a06540f6" />


  - 높은 경우
 
    
       <img width="180" alt="image" src="https://github.com/user-attachments/assets/1f803a6e-bfa1-4fd6-ac66-e40e78418934" />

- 변수별 가중치를 산출하여 국회의원별 최종 입법활동 점수 계산
  - 음이항 행렬분해 (NMF)
    <img width="398" alt="image" src="https://github.com/user-attachments/assets/bc4db6be-a548-4475-bb19-6240ea91bb80" />


    <img width="410" alt="image" src="https://github.com/user-attachments/assets/fea99107-828c-420d-a2f7-8c31d8dc29c4" />

