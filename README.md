#  **2023-2 D&A ML Session 팀프로젝트(Kaggle Competition)**

## 🧑‍🤝‍🧑 **팀원**
- **이재원**
- **송승원**
- **황예은**
- **이유정**
- **이호영**
- **임하영**

## 📅 **진행 시기**
- **2023년 2학기**

## 💡 **주제**
- **서울, 부산 지역의 아파트 실거래가 예측(회귀)**

##  📌 **데이터셋**
- 아파트 정보, 아파트 가격(train/test)
- 주변 공원, 보육원 데이터
- 서울 자치구별 지하철역 정보 데이터(공공데이터)
- 부산교통공사 지하철 정보 데이터(공공데이터)
- 한국은행 기준금리 데이터(뉴스 발췌 후 가공)
  
## 📌 **주요 분석 내용**

### - **Main Idea**
- 노이즈가 섞이지 않게 서울과 부산을 구분하여 개별적으로 예측하고, 나중에 submission을 합치자.
- 섞였을 때, 서울 집값의 평균이 부산보다 훨씬 비싸므로 부산의 집값 예측에 영향을 크게 줄것.

### - **결측치 처리**
- 별다른 결측치 없음 확인
- 기한 문제로 preprocessing 거의 하지 않은 것이 한계점으로 작용. 

### - **Feature Engineering**
- 기존 data column + 추가 파생 변수 생성
- 아파트 연식, 거래일, 층수, 아파트 고유 ID 길이 거래 계절, 층별 면적
- 시공사 브랜드, 시공사 브랜드 별 층수 평, 평수 그룹 등 활용

### - **Encoding & Scaling**
- 범주형 변수 처리
- 면적, 설립연도, 층 등의 수치형 변수 scale 조정  

### - **Feature Selection**
- 피쳐 간 상관계수 히트맵을 그려, 중복변수 drop
- Feature Importance 임계치 설정하여 활용 feature의 개수 조정

### - **Modeling**
- XGB, Catboost 모델 파라미터 튜닝 하여 개별 예측값 생성 후 예측 산술평균

<br/>

## 📝 **분석 결과 및 결론**
- 평가지표 : RMSE
- 평균적으로 아파트 실제 거래가와 약 4400만원 정도의 차이
- 더 많은 파생 변수 생성이 필요했음 (한계1)
- train data와 별개로 주어진 공원, 보육원 데이터는 공통특성 미일치로 모델링에 제대로 활용하기 어려웠음 (한계2)
- 시계열 특성을 고려하지 못했음 (한계3)
- 데이터셋 자체 전처리, 모델링과 인코딩 방식 실험적 시도 부족했음 (한계4)
  

