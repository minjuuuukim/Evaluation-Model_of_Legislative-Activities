## Evaluation-Model_of_Legislative-Activities
## 국회 활성화를 위한 국회의원 입법활동 평가모델
> 24-1 P-SAT 시계열자료분석팀 주제분석

- 법률안의 발의 건수는 증가하고 있는 것에 비해, 가결률은 감소하고 있음. 

- 이는 국회의원의 평가세칙으로 발의안의 '질'이 아닌 '양'을 고려하고 있기 때문이며, 단순 건수로만 평가되기 때문에 같은 내용을 여러 법안으로 나눠서 발의하는 "법안 쪼개기"와 같은 꼼수를 쓰거나, SNS에 의원들의 단체 대화방을 개설하여 1시간 만에 법안 발의의 최소요건인 공동발의자 10명을 채우기도 하는 등 국회의 본질적인 기능이 사라지고 있음.
  
- 국회 임기가 끝날 때까지 본회의를 통과하지 못한 법안들은 자동으로 폐기되기 때문에, 우리에게 꼭 필요한 법안이 심의되지 못하거나 충분히 검토되지 못한 채 폐기될 수 있다는 문제점이 존재함.

- 따라서, 실적 채우기에 매몰되지 않는 국회의원 입법활동 평가모델을 수립함으로써 국민에게 필요한 실속있는 법안을 발의하도록 유도하고자 하는데에 목적이 있음.

> 분석 흐름
1. 법률 발의안, 뉴스기사 데이터 수집 및 분석
  - 제 20대 국회의원 발의안 : 열린국회정보의 정보공개포털 크롤링
  - LDA 토픽모델링을 활용한 발의안 키워드 추출
2. 각 발의안의 내용을 포함하는 발의안 데이터셋 구성
  - 발의안의 사회동향정도 계산 : 발의안 키워드와 뉴스 키워드의 유사도 계산
  - KoBERT, Doc2vec

3. 발의안에서 유의미한 feature를 뽑아 각 국회의원에 대한 데이터셋으로 구성
  - 국회의원별 발의안 평균분산도 산출
  - K-means 클러스터링의 inertia 값 이용
  - 낮은 경우
 
       <img width="155" alt="image" src="https://github.com/user-attachments/assets/9a64260e-d944-418e-9235-7e71a06540f6" />


  - 높은 경우
    
       <img width="180" alt="image" src="https://github.com/user-attachments/assets/1f803a6e-bfa1-4fd6-ac66-e40e78418934" />

4. 변수별 가중치를 산출하여 국회의원별 최종 입법활동 점수 계산
  - 음이항 행렬분해 (NMF)


> 분석 내용 
<img width="461" height="259" alt="image" src="https://github.com/user-attachments/assets/58d747b8-de58-4194-abe6-9fd82492fcc8" />

<img width="458" height="257" alt="image" src="https://github.com/user-attachments/assets/b8564653-3ced-44cd-9239-32a6aba3329b" />

<img width="461" height="259" alt="image" src="https://github.com/user-attachments/assets/f6219bc5-5569-4aab-aba8-ef6cf1b7887e" />

<img width="457" height="258" alt="image" src="https://github.com/user-attachments/assets/91808265-11cf-4d28-9116-efb71e5a5e6a" />

<img width="457" height="259" alt="image" src="https://github.com/user-attachments/assets/319cf32b-a1cf-4602-86f7-f444899a76ee" />

<img width="461" height="259" alt="image" src="https://github.com/user-attachments/assets/9ce2a813-4df8-4113-b135-7d84f445eb65" />

<img width="461" height="259" alt="image" src="https://github.com/user-attachments/assets/8ee78457-ebec-4a68-9d5b-12a8ccf4142d" />

<img width="458" height="259" alt="image" src="https://github.com/user-attachments/assets/dc22a40f-ae6f-4b28-8c21-54f489f3f5ec" />

<img width="457" height="260" alt="image" src="https://github.com/user-attachments/assets/4fe77e34-0b9f-45ad-bae4-5e018fedfa16" />

<img width="458" height="262" alt="image" src="https://github.com/user-attachments/assets/d612370c-4912-4416-b140-ed52a23170e6" />

<img width="458" height="257" alt="image" src="https://github.com/user-attachments/assets/cce59a6e-185d-40fa-9197-5303bab339ec" />

<img width="459" height="259" alt="image" src="https://github.com/user-attachments/assets/61810ea4-a2bd-4518-8317-80c2e63fe1d6" />

<img width="458" height="257" alt="image" src="https://github.com/user-attachments/assets/c7103abd-4083-431e-926b-ea67560c7e25" />

<img width="461" height="259" alt="image" src="https://github.com/user-attachments/assets/babb4ba0-3156-487c-9d1b-0bc424d23e18" />

<img width="458" height="260" alt="image" src="https://github.com/user-attachments/assets/ef526947-af98-4e94-9c86-bcbb51100703" />

<img width="457" height="259" alt="image" src="https://github.com/user-attachments/assets/ea6d3c49-9cd0-4018-908c-5eec5ad7903f" />

<img width="460" height="258" alt="image" src="https://github.com/user-attachments/assets/180f8140-cf4c-4ac7-b27d-e68576f1d9f9" />

<img width="461" height="257" alt="image" src="https://github.com/user-attachments/assets/b2eba81b-6943-4db8-b94b-6ec020def3f1" />

<img width="459" height="259" alt="image" src="https://github.com/user-attachments/assets/77e38dca-718c-4a8c-a14e-4bc6d872de89" />

<img width="459" height="260" alt="image" src="https://github.com/user-attachments/assets/e9d93416-b330-43a2-a2e9-c123faced9d5" />

<img width="457" height="260" alt="image" src="https://github.com/user-attachments/assets/749d6fbe-f281-44ab-aa38-bcfbc1283a09" />

<img width="456" height="257" alt="image" src="https://github.com/user-attachments/assets/344ee1a4-e3d0-4428-afa4-9dfda8cb7b74" />

<img width="457" height="260" alt="image" src="https://github.com/user-attachments/assets/01776487-9e4e-4be0-ab67-c2bc1a453cb6" />

<img width="459" height="259" alt="image" src="https://github.com/user-attachments/assets/6913d99e-2f08-4c02-ac43-c7762d5860e9" />

<img width="457" height="258" alt="image" src="https://github.com/user-attachments/assets/8cf27ee4-1106-461e-bdd6-4a9728b55349" />

<img width="458" height="257" alt="image" src="https://github.com/user-attachments/assets/c4c631c9-f12b-4a8d-ac3c-a90031393a48" />

<img width="458" height="257" alt="image" src="https://github.com/user-attachments/assets/05b473c2-1454-4c91-9c08-bcdfc0e17c22" />

<img width="460" height="259" alt="image" src="https://github.com/user-attachments/assets/e4887ae6-fa30-4284-8ad4-2acc8ae99416" />

<img width="460" height="259" alt="image" src="https://github.com/user-attachments/assets/8044345d-efe1-4c98-aed1-3059c27a0044" />
