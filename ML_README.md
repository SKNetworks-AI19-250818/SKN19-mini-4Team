# SKN19-mini-4Team
<img width="1108" height="354" alt="image" src="https://github.com/user-attachments/assets/74bf03d4-0c0b-4646-b55a-4e751f29f3b4" />

## 🐙 점쟁이 문어
## 👥 팀 소개

<div align="center">
 
| 안수이 | 신지섭 | 김진 | 왕혁준 |
| --- | --- | --- | --- |
| <img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/3385cd38-8989-4e07-90ff-cc4295e2ff7a" /> | <img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/474d5667-6aed-4c7f-8da2-f016982c248a" /> | <img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/0ec1f133-de4e-4b3f-a6f3-5f364cbcefd4" /> | <img width="150" height="250" alt="image" src="https://github.com/user-attachments/assets/75300f98-e97e-4e00-9826-ef0b4bacbe0f" /> |
| <div align="center">[![GitHub](https://img.shields.io/badge/GitHub-ahnsui-181717?style=flat&logo=github&logoColor=white)](https://github.com/ahnsui)</div> | <div align="center">[![GitHub](https://img.shields.io/badge/GitHub-Melonmacaron-181717?style=flat&logo=github&logoColor=white)](https://github.com/Melonmacaron)</div> | <div align="center">[![GitHub](https://img.shields.io/badge/GitHub-KIMjjjjjjjj-181717?style=flat&logo=github&logoColor=white)](https://github.com/KIMjjjjjjjj)</div> | <div align="center">[![GitHub](https://img.shields.io/badge/GitHub-vibevibe26-181717?style=flat&logo=github&logoColor=white)](https://github.com/vibevibe26)</div> |

</div>

---

## 📊 1차 모델 테스트 및 평가 - 순위 예측

**1. EDA 완료 데이터 셋(Final DF.csv)을 사용하여 전체 순위 예측**

   - **모델**: XGBoost, LightGBM, Random Forest (분류 & 회귀)
   - **설정**: **`test_size=0.1`**
   - **성능**: 스코어 **0.2 ~ 0.7** (편차 큼), 3개의 모델 모두 **유사한 성능**
   - **해석**: 데이터 부족 & 월드컵은 변수가 많기 때문에 선형 모델 사용에 한계 존재


## 🔧 1차 성능 개선

**사용 모델: Xgboost, LightGBM (분류)**

1. **각 년도를 기준으로 표준화한 데이터 사용 (상대적 요소)**
   - **데이터 처리**
        - 경기 결과는 두 나라 간 상대적인 스탯이 중요
        - 각 년도를 기준으로 데이터 표준화 → 상대적인 스탯 비교 가능
        - **Accuracy:** 0.38
    - **XGBoost 적용**
        - **Decision Stump 활용: `max_depth=1`** 설정
        - **Accuracy 향상:** 0.45

 2. **라운드 별로 그룹화해서 1개의 모델로 예측** 
    - **모델 성능**
      - **Accuracy: 약 0.4**로 안정적으로 나타남
      - 범주 수가 줄어듦 → 예측 성능 **편차 감소 기대**
    - **예측**
       - **결승, 준결승, 8강, 16강, 조별리그**로 라운드 구분
       - 각 라운드에서 **생존 확률**을 하나의 모델로 예측

3. **Feature Engineering (특징 확장)→ PCA 적용(차원 축소) → 테스트**
    - **Feature Engineering + PCA 적용**
        - 피처 엔지니어링: **degree=2, 3**로 특징 확장
        - PCA: **15**개의 특징 사용
        - 테스트: **LightGBM** 모델 적용
    - **모델 성능**
        - **Accuracy**: 약 **0.53**로 안정적
        - 기대했던 만큼의 성능 향상 X
          
---

## 📊 2차 모델 테스트 및 평가 - **매치 예측**

**사용 모델: XGboost**

1. **팀별 특성 매칭 방식**
    - 월드컵 본선 데이터에서 홈팀·어웨이팀으로 분류해서 특성 배치
    - 결과 라벨: 승리=1, 무승부=0, 패배=-1 (홈팀 기준)
    - **Accuracy:** 0.48 → 낮게 나옴

2. **홈팀 - 어웨이팀 특징 차이만 사용한 방식**
    - 홈팀에서 어웨이팀의 특징을 빼서 특징의 총 갯수를 줄인 뒤 분류
    - **Decision Stump활용: max_depth 1**
    - **Accuracy: 0.592**로 향상


## 🔧 2차 성능 개선

1. **무승부 예측 제외** 
    - 무승부의 경우, 예측 성능이 현저하게 떨어지는 것을 발견하여 제외
    - **Accuracy: 0.72**로 향상 (정밀도, 재현율도 비슷한 수치)
    - **조별리그**: predict_proba를 이용하여 이길 확률이 **0.55이하**일 경우, 무승부로 처리
    
2. **상대 전적 추가: 상대전적을 매치 데이터에서 추출하여 특징으로 추가**
    - 월드컵 본선, 월드컵 예선, 대륙별 컵 경기, 친선 경기 데이터 사용
    - 승률 계산 = **home팀이 away팀을 이긴 횟수 / home팀, away팀의 경기 수**
    - 매치 발생 이전 N년까지의 상대 전적 고려
        
        문제 1) 상대 전적 데이터수가 적다.
        
        문제 2) 너무 옛날 데이터가 들어갈 경우, 정확도 ↓
        
        → 5년/10년/15년/20년/25년으로 **XGBClassifier** 성능 확인 ⇒ 20년 선정
        
    - **Accuracy: 0.7382**로 향상

3. **실제 월드컵 진행 과정에 맞게 출전국들의 시드를 배정, 조별리그 편성, 32강, 16강, 8강, 4강, 결승 순으로 시뮬레이션을 진행**
    - **2018년도 예측 데이터**
        - **Feature Importances**: `Avg_Famous`는 큰 비중 차지 X
        - **`Avg_Famous`** 값이 유난히 높게 나타난 스페인이 월드컵에 우승할 것으로 예측
        - 매치 결과 예측을 이용한 방식이 EDA 과정에서 발견한 결과와 잘 맞아 떨어지는 것으로 보아 이 방식이 효과적임을 확인 가능
        <img width="513" height="151" alt="image" src="https://github.com/user-attachments/assets/c1875816-bfdf-4c4d-830a-02ea924b5eb0" />
        
2. **월드컵 출전국들의 선수 명단을 게임 FIFA스탯을 기준으로 실제 월드컵 명단처럼 26명으로 구성 후 시뮬레이션을 진행**
     
---

## 💡 시도한 아이디어

1. **연도별 특성 확장과 FIFA 스탯 활용 한계**
   - **특성 확장 (1년 단위)**
     - 예선전 승률(Q_WR), 예선전 골 득실률(Q_GR), 피파 랭킹(F_Rank, F_Rd), 피파 포인트(F_Point, F_Pd), 게임 FIFA 스탯(FS_0 ~ FS_14)
    - **데이터 처리 결과**
      - 예선전 승률, 골 득실률, 피파 랭킹, 피파 포인트: 기존 csv 파일 활용, 년 단위로 DF 생성
      - 게임 FIFA 스탯: 여러 csv 파일을 맵핑, 정규화, 병합하는 과정에서 문제 발생
        - 선수 이름의 표기 불일치
        - 데이터 부족
    - **결정**
      - 게임 FIFA 스탯을 모델의 예측 성능을 높이는 중요한 특성으로 판단했으나 년 단위 DF는 사용 X

2. **승부차기 승률 예측 머신러닝**
    - **데이터 처리 결과**
      - 모델: 로지스틱 회귀
      - 선수별 승부차기 결과 실데이터가 매우 제한적 → 국가 단위 데이터 중심으로 접근
    - **팀(국가) 단위 예측**
      - 각 국가별 승부차기 관련 스탯 Top7 선수 선발
      - 7명 선수 스탯 평균화 → 팀 단위 특성으로 변환

---

## 🏆 최종 모델

**매치 예측 모델 성능**

시뮬레이션을 늘리다 보면 전체 시뮬레이션의 성능이 모델 성능에 수렴된다.

**시뮬레이션 방식**

- 현재 모델 출력: 이진 분류
    - `0 = 홈패배`, `1 = 홈승리`
- 승리 확률이 특정 임계값(0.5 ± 0.05) 안에 있으면 무승부 처리
    - `승리 확률 = 0.54`, `패배 확률 = 0.46` → 무승부 처리
    - **조별리그**: 무승부 → 승점 1점씩 부여
    - **토너먼트**: 무승부 불가 → 예측값 그대로 활용

**Feature Importance**
| Feature | Importance |
| --- | --- |
| FS_0  (종합점수) | 0.426604 |
| FS_4 (반응속도) | 0.155365 |
| FS_11 (골키퍼) | 0.063379 |
| Avg_Age  (평균 나이) | 0.056211 |
| F_Rank (피파 랭킹) | 0.054032 |
| home_rate (상대 전적) | 0.052756 |


### 1. **2026년 FIFA 월드컵 출전 예상 48개국 선정**
   
   | 국가 | 출전 횟수 | 국가 | 출전 횟수 | 국가 | 출전 횟수 |
   | --- | --- | --- | --- | --- | --- |
   | *미국 | 5 | 우루과이 | 5 | 세네갈 | 3 |
   | *멕시코 | 6 | 벨기에 | 4 | 세르비아 | 3 |
   | *캐나다 | 1 | 카메룬 | 4 | 스웨덴 | 3 |
   | 아르헨티나 | 6 | 덴마크 | 4 | 알제리 | 2 |
   | 브라질 | 6 | 에콰도르 | 4 | 칠레 | 2 |
   | 잉글랜드 | 6 | 가나 | 4 | 콜롬비아 | 2 |
   | 프랑스 | 6 | 이란 | 4 | 그리스 | 2 |
   | 독일 | 6 | 이탈리아 | 4 | 온두라스 | 2 |
   | 일본 | 6 | 네덜란드 | 4 | 모로코 | 2 |
   | 포르투갈 | 6 | 나이지리아 | 4 | 슬로베니아 | 2 |
   | 대한민국 | 6 | 폴란드 | 4 | 남아프리카공화국 | 2 |
   | 스페인 | 6 | 사우디아라비아 | 4 | 카타르 | 1 |
   | 호주 | 5 | 튀니지 | 4 | 이집트 | 1 |
   | 코스타리카 | 5 | 코트디부아르 | 3 | 체코 | 1 |
   | 크로아티아 | 5 | 파라과이 | 3 | 앙골라 | 1 |
   | 스위스 | 5 | 오스트리아 | 3 | 노르웨이 | 1 |
- 출전 횟수 & 피파 랭킹으로 선정
- *미국, *멕시코, *캐나다 : 출전국 자격으로 1시드 배정


### 2. **시드**

   | 1시드 | 2시드 | 3시드 | 4시드 |
   | --- | --- | --- | --- |
   | 미국 | 이탈리아 | 에콰도르 | 나이지리아 |
   | 멕시코 | 모로코 | 호주 | 튀니지 |
   | 캐나다 | 독일 | 노르웨이 | 코스타리카 |
   | 스페인 | 콜롬비아 | 스웨덴 | 슬로베니아 |
   | 프랑스 | 우루과이 | 세르비아 | 카메룬 |
   | 아르헨티나 | 스위스 | 이집트 | 카타르 |
   | 잉글랜드 | 세네갈 | 폴란드 | 남아프리카공화국 |
   | 포르투갈 | 일본 | 파라과이 | 칠레 |
   | 브라질 | 덴마크 | 알제리 | 사우디아라비아 |
   | 네덜란드 | 이란 | 체코 | 온두라스 |
   | 벨기에 | 오스트리아 | 그리스 | 가나 |
   | 크로아티아 | 대한민국 | 코트디부아르 | 앙골라 |
- 출전 횟수 & 피파 랭킹으로 선정
- *미국, *멕시코, *캐나다 : 출전국 자격으로 1시드 배정


### 3. **조별리그**
   - 조별리그 승점 방식
     - 승리 : 3점
     - 무승부 : 1점
     - 패배: 0점
   - 만약 두 팀 이상이 동점 승점을 기록
     - 득실차: 득점과 실점의 차이가 큰 팀이 우선
     - 다득점: 총 득점이 많은 팀이 우선
   <img width="500" alt="화면 캡처 2025-09-28 035717" src="https://github.com/user-attachments/assets/d3759412-04a9-44a3-adfc-e52611b41f6d" />


### 4. **토너먼트**
   - 실제 2026 월드컵 토너먼트 방식을 적용하여 구현
     - 48개팀은 4개팀씩 12개조로 편성
     - 팀당 3경기를 치러 각 조 1, 2위 24개팀은 조별리그를 통과
     - +3위 중 가장 좋은 성적을 거둔 8개 팀도 토너먼트에 합류

---

## 🚀 예측 결과
<img width="1393" height="790" alt="image (1)" src="https://github.com/user-attachments/assets/bda2ecf5-27dd-4720-a78a-da34d2c32706" />
<img width="1586" height="785" alt="image (2)" src="https://github.com/user-attachments/assets/eb714ea7-78d4-4a8f-b71a-a87395c3085c" />
<img width="847" height="547" alt="image (3)" src="https://github.com/user-attachments/assets/16bc1c6c-ef5f-4d5d-9388-3d9ba7160081" />

---

## 📄 테스트 셋

**데이터 수집 & EDA**

- 2026년 기준 상대 전적 데이터: **2005-2025년** 월드컵, 월드컵 예선, 대륙별 컵 경기, 친선 경기 데이터 사용
- 2026년 출전 선수 Stat: **FC 26** FIFA 선수 데이터 스탯 사용
- 출전 선수: 각 포지션 별로 **Overall 스탯이 가장 높은 순**으로 **골키퍼(GK) 3명, 수비수(DF) 9명, 미드필더(MF) 8명, 공격수(FW) 6명**으로 선정
- FIFA 랭킹, 포인트: 2025년 FIFA 랭킹 사용

```
최종 컬럼
- Nation : 국가명 (한글)
- Q_WR : 월드컵 개최전 3년간의 예선&친선&지역리그 평균승률
- Q_GR : 월드컵 개최전 3년간의 예선&친선&지역리그 평균 골득실률
- Avg_Age : 월드컵 명단 내 선수들의 나이 평균
- Avg_Famous : UEFA 계수 Top 20 클럽에 속한 선수 수
- F_Rank : 월드컵 개최전 3년간의 피파 랭킹 평균
- F_Point : 월드컵 개최전 3년간의 피파 포인트 평균
- F_Rd : 이전 월드컵 F_Rank 대비 F_Rank 변화량
- F_Pd : 이전 월드컵 F_Point 대비 F_Point 변화량 
- Home_Rate : 다른 나라들과의 20년간 상대 전적 승률
- FS_ : 선수단 피파 게임 스탯 평균
    - FS_0 : current_rating (Over all)
    - FS_1 : ball_control 
    - FS_2 : dribbling
    - FS_3 : composure
    - FS_4 : reaction
    - FS_5 : crossing
    - FS_6 : acceleration
    - FS_7 : stamina
    - FS_8 : strength
    - FS_9 : shot_power
    - FS_10 : sprint_speed
    - FS_11 : gk
    - FS_12 : passing
    - FS_13 : defending
    - FS_14 : finishing
```
