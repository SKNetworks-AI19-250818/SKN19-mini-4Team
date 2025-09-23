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

## 🏆 프로젝트 주제

**2026 FIFA 월드컵 우승국 예측 및 한국 국가대표 성적 예측**

## ⚽ 프로젝트 배경

<div align="center">
<img width="500" height="361" alt="image" src="https://github.com/user-attachments/assets/4662ffdf-c3c6-4a6c-b8e4-d9b2d816fa4d" />

</div>

FIFA 월드컵은 전 세계적으로 가장 많은 관심을 받는 스포츠 경기 중 하나로, 각국의 예선 성적, FIFA 랭킹, 선수단 특성 등이 본선 성과에 어떤 영향을 주는지에 대한 분석은 팬들과 전문가 모두에게 중요한 의미를 가진다.

특히 2026년 월드컵은 사상 최초로 48개국이 본선에 참가하게 된다. 이에 따라 머신러닝 기반의 정교한 성과 예측에 대한 수요가 커질 것으로 예상된다.

과거에는 점쟁이 문어 ‘파울’, 혹은 펠레의 저주처럼 재미 위주의 우승팀 예측이 세계적인 화제가 되었다. 이번 프로젝는 데이터 기반의 머신러닝 학습을 통해 데이터 분석과 인공지능으로 2026 월드컵 우승국과 한국 국가대표의 성적을 예측해보려 한다.


## 🎯 프로젝트 목표
**데이터 분석(EDA) 목표**

1. **탐색적 분석 및 시각화**
    - 월드컵 개최 이전 3년 간의 데이터를 수집 및 분석하여 팀별 경기력과 선수 구성의 특징 분석
    - 월드컵 본선 성과 예측에 있어서 어떤 지표나 자료가 가장 유용한지 파악
2. **ML 학습용 최종 데이터셋 추출**
    - 2026 월드컵 본선 성과를 예측할 머신러닝 파트에서 어떤 지표를 사용할 지 탐색

**ML 목표**

1. **2026 월드컵 전체 순위 및 최종 우승팀 예상**
    - 한국 국가대표 성적 예측
    - 조별리그, 토너먼트 단계별 경기 승리팀 예측
    - 예측 확률(승/무/패 확률 분포)까지 제공
2. **슈퍼컴퓨터 예측 결과와 비교**
    - 예측 정확도 및 차이점 분석

--- 
    
## 📂 프로젝트 구조 
```Python
Project
│
├─ EDA
│   ├─ Qualifier Match                 # 예선 및 친선 매치 데이터 EDA
│   │   ├─ code                
│   │   └─ data
│   │       ├─ source data     
│   │       └─ result data    
│   ├─ FIFA Rank                       # FIFA 랭킹 및 포인트 데이터 EDA
│   │   ├─ code               
│   │   └─ data
│   │       ├─ source data     
│   │       └─ result data     
│   ├─ Player Stats                    # FC24게임 선수 스탯 데이터 EDA
│   │   ├─ code
│   │   └─ data
│   │       ├─ source data
│   │       └─ result data
│   ├─ Team Stats                      # 월드컵 팀 성과 데이터 EDA
│   │   ├─ code
│   │   └─ data
│   │       ├─ source data
│   │       └─ result data
│   └─ Merge                           # 각 result data 머지
│       ├─ code
│       └─ data
│           ├─ source data
│           └─ result data
├─ Analysis                            # 시각화
│       ├─ code                        
│       └─ data
│           ├─ Data  dictionary.md     # 컬럼 설명
│           └─ Final DF.csv            # 최종 데이터 파일
└─ ML
```

## 🛠️ 기술 스택

**EDA/ML**

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) ![3.12.7](https://img.shields.io/badge/3.12.7-3776AB?style=flat)  

**라이브러리**

![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) ![2.3.2](https://img.shields.io/badge/2.3.2-150458?style=flat)  
![Matplotlib](https://img.shields.io/badge/Matplotlib-003366?style=flat&logo=plotly&logoColor=white) ![3.10.6](https://img.shields.io/badge/3.10.6-003366?style=flat)  
![Seaborn](https://img.shields.io/badge/Seaborn-4C72B0?style=flat&logo=python&logoColor=white) ![0.13.2](https://img.shields.io/badge/0.13.2-4C72B0?style=flat)  
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat&logo=plotly&logoColor=white) ![5.24.1](https://img.shields.io/badge/5.24.1-3F4F75?style=flat)  
![Levenshtein](https://img.shields.io/badge/Levenshtein-7D3C98?style=flat&logo=python&logoColor=white) ![3.14.1](https://img.shields.io/badge/3.14.1-7D3C98?style=flat)  


**개발 환경 및 협업 도구**

![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![VSCode](https://img.shields.io/badge/VSCode-007ACC?style=flat&logo=visualstudiocode&logoColor=white)
![Notion](https://img.shields.io/badge/Notion-000000?style=flat&logo=notion&logoColor=white)

--- 

## 📊 EDA
### 1️⃣ 데이터 로드


1. [FIFA 랭킹 데이터 1999-2025](https://inside.fifa.com/fifa-world-ranking/men?dateId=id14870)
    - 그전 3년 피파 랭킹/포인트의 평균  
2. [[친선/예선] 국제 축구 경기 결과 1872-2025](https://www.kaggle.com/datasets/martj42/international-football-results-from-1872-to-2017/data?select=results.csv)
    - 그전 3년간 골득실비
    - 그전 3년간 친선 예선전에서의 승률
3. [[월드컵 본선] 매치/스쿼드 데이터 1930 - 2014](https://www.kaggle.com/datasets/abecklas/fifa-world-cup?select=WorldCupMatches.csv)
    - 선수단의 평균 월드컵 본선 출전 횟수
4. [[월드컵 본선] 순위 데이터 2002~2022 - 크롤링](https://namu.wiki/w/2022%20FIFA%20%EC%9B%94%EB%93%9C%EC%BB%B5%20%EC%B9%B4%ED%83%80%EB%A5%B4#s-8)
    - 특정 국가의 해당년도 월드컵 순위
    - 특정 국가의 해당년도 월드컵 승점
5. [[월드컵 본선] 선수단 데이터 2002~2022 - 크롤링](https://namu.wiki/w/2022%20FIFA%20%EC%9B%94%EB%93%9C%EC%BB%B5%20%EC%B9%B4%ED%83%80%EB%A5%B4/%EC%B0%B8%EA%B0%80%ED%8C%80%20%EC%A0%95%EB%B3%B4)
    - 선수단별 유명 리그에 포함된 선수
    - 선수단 평균연령
6. [[FIFA 게임] 선수 정보 2002~2022](https://www.kaggle.com/datasets/daguizer/fifa-2021-to-2005-complete-player-attributes)
    - 게임 상에서 선수단 평균 스탯
7. [[월드컵 본선] 선수 세부 스탯 데이터](https://www.kaggle.com/datasets/joebeachcapital/fifa-world-cups)
    - 각 팀의 해당년도 월드컵 본선에서의 공격력 관련 수치
    - 각 팀의 해당년도 월드컵 본선에서의 수비력 관련 수치

→ 총 7개의 팀 스탯 + 게임스탯(13) + 타겟 데이터 2개의 컬럼을 추출

---

### 2️⃣ 데이터 구조와 기초 통계 확인

| **Info** | **Describe** |
| --- | --- |
| <img width="400" height="600" alt="info image" src="https://github.com/user-attachments/assets/ba819aa2-fc39-451c-8d01-02b8ef710ba1" /> | <img width="700" height="300" alt="description image" src="https://github.com/user-attachments/assets/946498bd-43ec-40b0-8f9f-953b60593421" /> |

---

### 3️⃣ 결측치 및 이상치 탐색

- **FIFA 게임 선수 데이터 활용 (05, 09, 13, 17, 21년도)**
    - 원래 2002년도 데이터를 사용해야 했으나, FIFA 게임 데이터에 2002년 버전이 존재하지 않아 2002년 출전 선수들의 능력치를 2005년 데이터로 대체하였다.
- **국가별 선수단 평균 Stat 계산**
    - 월드컵 본선에 출전한 모든 선수가 FIFA 게임 데이터에 등록되어 있지는 않았다.
    - FIFA에 Stat 정보가 존재하지 않는 선수들은 분석에서 제외하고, 남아 있는 선수들의 능력치를 기반으로 국가별 평균 스탯을 계산하였다.

---

### 4️⃣ 데이터 시각화를 통한 탐색
**시각화 목록**

| No | **분류** | **분석 지표** | **목적** |
| ---| --- | --- | --- |
| 1| [**예선전 & 친선전 승률과 골득실률 - 월드컵 본선 성적**](#1-예선전--친선전-승률과-골득실률---월드컵-본선-성적) | Q_WR(예선 승률), Q_GR(예선 골득실률), Wc_Rank, Wc_Point | 예선 성적이 본선 성과에 미치는 상관관계 |
| 2| [**클럽 계수 Top 20 클럽에 속한 선수 수 - 본선 성적**](#2-클럽-계수-top-20-클럽에-속한-선수-수---본선-성적)  | Avg_Famous, Wc_Rank, Wc_Point | 유명 리그 선수 수가 월드컵 성과에 미치는 영향 |
| 3| [**피파 랭킹/포인트 - 월드컵 성과**](#3-fifa-랭킹포인트---월드컵-성과) | F_Rank, F_Point, F_Rd, F_Pd | FIFA 랭킹과 포인트가 월드컵 순위 변동에 미치는 관계 |
| 4| [**월드컵 경기 지표 - FIFA 게임 지표**](#4-월드컵-경기-지표---fifa-게임-지표) | ATK_INDEX, DEF_INDEX, FS_1~FS_13  | 경기 지표와 FIFA 게임 지표 간 상관관계 |
| 5| [**월드컵 성적 - FIFA 게임 지표**](#5-월드컵-성적---fifa-게임-지표) | Wc_Rank, FS_1~FS_13 | 월드컵 성적과 FIFA 게임 지표 간 상관관계 |
| 6| [**선수단 나이 - 공격/수비 지표**](#6-선수단-나이---공격수비-지표) | Avg_Age, Avg_Apps, ATK_INDEX, DEF_INDEX | 선수단 평균 나이, 출장 수와 공격/수비 지표 비교 |
| 7| [**월드컵 경험 - 공격/수비 지표**](#7-월드컵-경험---공격수비-지표) | ATK_INDEX, DEF_INDEX, Avg_Apps | 월드컵 출전 경험과 경기 지표 간 상관관계 |
| 8| [**월드컵 최종 순위 - 공격/수비 지표**](#8-월드컵-최종-순위---공격수비-지표) | ATK_INDEX, DEF_INDEX, Wc_Rank | 월드컵 최종순위와 경기 지표 간 상관관계 |
| 9| [**월드컵 진출 라운드 - 공격/수비 지표**](#9-월드컵-진출-라운드---공격수비-지표) | ATK_INDEX, DEF_INDEX, Wc_Round | 월드컵 라운드와 경기 지표 간 상관관계 |
| 10| [**평균 나이 - 본선 진출 평균 횟수**](#10-평균-나이---본선-진출-평균-횟수) | Avg_Age, Avg_Apps | 평균 나이와 본선 진출 횟수 간 관계 |
| 11| [**준결승 진출 여부 - 평균 나이/본선 진출 평균 횟수**](#11-준결승-진출-여부---평균-나이본선-진출-평균-횟수) | Avg_Age, Avg_Apps, 준결승 진출 여부 | 준결승 진출 팀의 평균 나이와 본선 진출 횟수 간 관계 |
| 12| [**우승 여부 - 본선 진출 평균 횟수**](#12-우승-여부---본선-진출-평균-횟수) |  Avg_Age, Avg_Apps, 우승 여부 | 우승 팀의 평균 나이와 본선 진출 횟수 간 관계 |
| 13| [**연도별 국가의 평균 나이/본선 진출 평균 횟수 분포**](#13-연도별-국가의-평균-나이본선-진출-평균-횟수-분포) | Avg_Age, Avg_Apps, 연도 | 연도별 평균 나이와 본선 진출 횟수 간 관계 |
| 14| [**세대 교체 경향 분석**](#14-세대-교체-경향-분석) | 특정 연도별 평균 나이, 신규/은퇴 선수 | 세대 교체 및 선수 구성 변화 |

### 1. 예선전 & 친선전 승률과 골득실률 - 월드컵 본선 성적
<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/b9c811d1-831f-4cf0-a5e2-af1f48fe6cb0" />
<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/ce1c4733-64a6-4007-91b8-e1a98aa32daf" />
<img width="602" height="155" alt="image" src="https://github.com/user-attachments/assets/2a39dd57-7886-4ad7-b196-165b9efc45c2" />

**예상**

월드컵 예선전과 월드컵 본선 사이에는 강한 상관관계가 있을 것이다.

**분석**
1. 전체적인 추이로 봤을때 연관성이 있는 것을 확인할 수 있고 히트맵으로 상관계수를 구해봐도 0.3으로 약한 음의 상관관계에 있는것을 확인할 수 있다.
특히 라운드 별로 확인했을때는 연관성을 좀 더 확실하게 확인 할 수 있었다. 
2. 하지만 월드컵 예선전 & 친선전의 성적과 월드컵 본선 성적은 예상보다는 약한 상관관계를 보였다.

### 2. 클럽 계수 Top 20 클럽에 속한 선수 수 - 본선 성적
<img width="1589" height="590" alt="image" src="https://github.com/user-attachments/assets/4e1e9729-4139-4c6d-91ad-1f445fbe3577" />

**예상**

월드컵 성적과 유명 클럽 소속 선수 수는 상관관계를 보일 것이다. 

**분석**

1. 월드컵 성적은 생각보다도 Top 20 클럽에 속한 선수의 비율이 중요한 부분을 차지한다는 것을 알 수 있었다.
2. 특히 8강이나 결승같은 Top 20 클럽에 속한 선수 수의 수가 확 오르는 구간을 볼 수 있다.
3. 국가대표와 비교적 연관이 없을 수도 있는 소속 클럽팀의 수준 정도가 월드컵 본선 직전에 치루어지는 국가대표간의 예선전의 결과보다도 더 높은 상관관계를 보인다는 것을 알 수 있었다.

### 3. FIFA 랭킹/포인트 - 월드컵 성과
<img width="1144" height="538" alt="image" src="https://github.com/user-attachments/assets/ef1eb503-a670-49ba-b256-6483a9b9f272" />

**예상**

FIFA 랭킹과 FIFA 포인트는 예선전과 친선전 보다도 더 넓게 국제전 성적을 아울러 나타내는 지표이니만큼 월드컵 본선 성적과 상관관계가 높을 것으로 예측하였다.

**분석**

1. 앞서 비교해본 지표들 가운데 월드컵 본선의 성적과 가장 높은 상관관계를 보여주고 있다.
2. FIFA 랭킹 20위권 이내에 들지 못하면 월드컵 순위가 2등 이상으로 올라가지 못한다는 점이 흥미롭다.
    
    FIFA 랭킹 40위권 밖의 팀들은 최대 성적이 월드컵 8강이었다는 점도 눈여겨 볼만하다.
    
3. 반면 FIFA 포인트는 FIFA 랭킹 대비 월드컵 본선 성적과 약한 상관관계를 갖고 있다.
4. **FIFA** 랭킹이 월드컵 성적을 예측하는 데 매우 유용한 지표인것은 분명하지만 회귀선 주변에 많은 데이터가 퍼져 있는 것을 볼 수 있다.
    
    즉, FIFA 랭킹에 의해서만 월드컵 순위를 예측할 수는 없음을 보였다.

### 🎈중간 결론 및 가설

```markdown
****상관관계가 ****높을 것 이라고 예측했던 FIFA랭킹, 예선전 데이터는 생각보다는 월드컵 본선 성적에 큰 영향을 미치지 못하는 것으로 확인됐다. 반대로 유명 클럽의 소속선수 수는 예측보다 높은 상관관계가 있었던 것으로 확인되었다.

우리 팀은 분석 결과가 예상에서 조금씩 벗어나는 부분들을 보며 보다 정확하게 월드컵 본선 성적을 예측하기 위해선 추가적인 데이터 수집이 필요하다고 판단하여 월드컵 본선 성적에 영향을 미칠 데이터들을 추가로 수집하였다.

추가로 수집하여 데이터 프레임에 넣은 컬럼들은 “월드컵 본선의 공격 지표”, “월드컵 본선의 수비 지표”, “선수단 평균 나이”, “선수단 월드컵 평균 출전 횟수” 이다. 이 네개의 컬럼들 서로의 상관관계와 월드컵 본선 성적의 상관관계를 다각도에서 분석하여 월드컵 본선 성적 예측 정확도를 높이고자 하였다.

월드컵 본선 성적에 축구 선수 경력이 유의미하게 영향을 끼칠 것이라고 생각하여 선수단의 평균 나이를 컬럼으로 넣었고, 월드컵이라는 큰 무대에서 뛰는 중압감에 대한 것도 본선 성적에 있어서 중요한 요인이라고 생각하여 월드컵 평균 출전 횟수의 컬럼도 넣게 되었다.

공격 지표와 수비 지표는 월드컵 본선의 경기력을 가장 직접적으로 수치화하여 보여주는 컬럼이 될 것이다.
```

### 4. 선수단 나이 - 공격/수비 지표
<img width="1158" height="539" alt="image" src="https://github.com/user-attachments/assets/ca473712-59d2-42bc-815f-8bfd2e08f5f5" />

**분석**

1. 본격적으로 월드컵 본선 공격, 수비 지표와 월드컵 본선 성적을 비교하기에 앞서 다각도에서 컬럼들과 연관성을 보기 위해 우선 선수단의 평균 나이와 본선의 공격, 수비 지표를 비교하였다.
    
    공격과 수비 모두 회귀선이 거의 수평에 가깝고 데이터가 넓게 분포되어 있으므로 평균 나이가 공격이나 수비 지표에 유의미한 영향을 보인다고 보긴 어려웠다.
    
2. 흥미로운 점은 공격 지표는 평균 나이가 증가함에 따라 회귀선이 약간이나마 떨어지고 있는 반면, 수비 지표는 평균 나이가 올라갈 수록 조금씩 오른다는 것이다.

### 5. 월드컵 경험 - 공격/수비 지표
<img width="1152" height="539" alt="image" src="https://github.com/user-attachments/assets/203de557-300c-4971-851b-8f8051e490ef" />

**분석**

1. 평균 나이가 월드컵 본선의 공격, 수비 지표와 거의 상관관계가 없었다는 것과 다르게, 선수단의 월드컵 본선 평균 경험 횟수는 공격, 수비 지표와 꽤 유의미한 상관 관계를 보이고 있다.
2. 특히 수비 관련 지표보다 공격 전반에 관련된 지표에서 더 높은 상관 관계를 보이고 있다는 점이 흥미롭다.

<img width="611" height="504" alt="image" src="https://github.com/user-attachments/assets/927c6f21-e2bc-40ab-9c86-f5378fa62401" />

**분석**

1. 평균 나이와 공격/수비지수의 상관계수는 각각 -0.0027/0.0047로 거의 영향을 미치지 않고 월드컵 본선 진출 경험과 공격력간의 상관계수는 0.38로 뚜렷한 영향을 주는 것을 재확인할 수 있다. 
2. 또한 추가로 공격지수와 수비지수 간의 상관계수가 0.61인 것을 보아 공격력이 강한 팀이 수비력도 강하다는 것을 확인할 수 있다.
   
### 6. 월드컵 최종 순위 - 공격/수비 지표
<img width="1489" height="590" alt="image" src="https://github.com/user-attachments/assets/af761803-289a-4fa8-88d9-f691efa6576c" />
<img width="1152" height="539" alt="image" src="https://github.com/user-attachments/assets/504685fe-d14d-4f83-a18a-b31dce0b2406" />

**예상**

월드컵 본선의 공격, 수비 지표이니 만큼 월드컵 순위와 아주 강한 상관관계를 보일 것으로 예상하였다.

**분석**

1. 분명 월드컵 순위와 본선의 공격, 수비 지표 모두 상관관계를 보이긴 하지만 그 정도가 예상보다도 훨씬 밑돌았다.
    
    본선의 공격, 수비 지표는 경기력을 대표하는 수치이니만큼 승리(성적)와 큰 연관이 있을 것이라고 생각하였는데 아무래도 월드컵의 성적은 다른 요소들의 개입이 크다는 것을 알 수 있었다.
    
2. 반면 차이가 적긴 하지만 월드컵 순위에 있어서 공격에 관련된 지표가 수비와 관련된 지표에 비해 조금 더 승리와 연관이 있다는 것을 알 수 있었다.

### 🎈중간 결론 및 가설

```markdown
가장 크게 영향을 미칠 것이라고 생각한 경기력 관련 지표가 예상보다 약한 상관관계를 보이는 것을 보며 월드컵이라는 대회의 특성에 대해 다시 생각해 볼 필요성을 느꼈다.

월드컵의 16강 이상 토너먼트는 단판으로 치루어지는 방식이고 세계에서 가장 권위가 높은 축구 대회이니 만큼 세계의 이목이 집중되고 화제력도 무척 뛰어나기에 경기력이나 숫자로 나타낼 수 있는 지표도 물론 중요하지만 그 외의 부분들도 분명 크게 개입한다고 생각하였다.

우리 팀은 선수단에 대해 수치로 나타낼 수 있는 자료는 이미 충분히 모았다고 판단하여 이미 모은 자료를 다양한 각도에서 다시 비교해보며 월드컵 본선이라는 무대를 재조명해보려 한다.
```

### 7. 평균 나이와 본선 진출 평균 횟수간의 관계
<img width="843" height="578" alt="image" src="https://github.com/user-attachments/assets/5c259f97-dcd2-4d89-8a01-715f32ccf1b4" />

**분석**

1. 상관관계: 0.26 → 1에 가까운 강한 상관관계라고 보기는 어렵지만, 완전히 무의미한 수준도 아닌 **약한 양(+)의 상관관계**로 해석할 수 있다.
2. 선수단의 평균 나이가 높을수록 그 팀은 과거 월드컵 본선에 더 자주 진출한 경험이 있는 경향이 있다.
    
    특히 평균 나이 29세~30세 팀은 최소 월드컵 본선 무대 경험 횟수가 0.4인 것을 확인 할 수 있다.
    
    나이가 많은 선수들이 포함된 팀일수록 국제 무대에서의 누적 경험치가 높다는 의미로 볼 수 있다. 
    

**가설**

앞서 분석했던 평균나이와 본선 진출 평균 횟수는 경기력에 관한 것이었지 우승팀에 관한 것이 아니었기 때문에 

‘우승팀의 평균나이와 본선 진출 평균 횟수는 모두 높을 것이다.’

라는 가설을 세우고 다시 한번 문제에 접근해 보았다.

### 8. 준결승 진출 여부와 평균 나이/월드컵 경험의 상관관계
<img width="1608" height="849" alt="image" src="https://github.com/user-attachments/assets/051781d5-2ba6-40c3-b4b7-773d8ef46c70" />

**분석**

1. 평균 나이는 준결승 진출이라는 성적에 대해서 차이가 거의 없다.
2. 반면 본선 출전 횟수에 대해서는 준결승 진출팀이 나머지 팀에 비해 선수단 평균 본선 출전 경험이 더 많다는 점에서 차이가 있다.

### 9. 우승팀 평균 나이 - 본선 진출 평균 횟수
<img width="1608" height="849" alt="image" src="https://github.com/user-attachments/assets/3a8cb12a-91da-4b60-8c29-96b9d1a0d8d3" />

**분석**

1.   우승팀의 평균 나이가 나머지 팀들보다 전반적으로 낮게 분포하고 있다는 것을 알 수 있다. 이는 우승팀이 상대적으로 젊은 선수들로 구성되어 많은 활동량과 강한 체력을 바탕으로 경기를 이끌어가며 우승에 도달하게 된다고 해석할 수 있다.
2. 우승팀 선수들의 평균 본선 진출 경험이 나머지 팀 선수들보다 더 많음을 확인할 수 있다. 이는 우승을 위해서는 큰 무대에서 압박감을 이겨내고 경기를 운영할 수 있는 노련함이 중요하다고 해석할 수 있다.

### 10. 연도별 국가의 평균 나이/본선 진출 평균 횟수 분포
<img width="1189" height="990" alt="image" src="https://github.com/user-attachments/assets/75f71c46-bd5b-4101-b356-aa1d4e64122b" />

**분석**

1. 여태까지 분석한 평균 나이, 본선 경험 횟수, 월드컵 성적의 지표들을 실제 월드컵 대회 성적과 함께 한눈에 보여주는 그래프
2. 평균 나이가 높을수록 월드컵 본선 경험이 많은 것을 다시 확인할 수 있다.
3. 우승팀은 대체로 평균 나이가 낮다.
4. 년도 별로 분석해보았을 땐, 2018년은 대체적으로 평균 나이가 높지만 2022년에는 평균 나이가 낮아지는 경향을 보인다.

### 11. 세대 교체 경향 분석
<img width="847" height="544" alt="image" src="https://github.com/user-attachments/assets/8e61f030-0fec-495e-a79a-51271e6949b5" />

**분석**

예상대로 2018년도에 나이가 많은 선수들이 은퇴하고 2022년에 젊은 선수가 다수 투입되었다.

실제 데이터에서도 2018년과 2022년을 비교했을 때, 세대교체 현상이 뚜렷하게 나타났으며, 축구라는 스포츠가 점점 더 빠르고 강도 높은 경기로 변하고 있다.

### 🎈월드컵 우승국 예측에 대한 최종 결론

```markdown
1. 월드컵이 가진 구조적 특성과 연결해보았을 때 본선 진출은 수년간 치뤄지는 예선전을 통과해야 하므로, 꾸준한 실력과 경험이 매우 중요한 요인으로 작용한다. 즉, 경험 많은 선수들이 다수 포진된 팀이 본선에 도달할 가능성이 크다.
2. 그러나 본선에 진출한 이후의 단판 토너먼트에서는 체력, 경기 집중력, 순간적인 기세 등이 크게 작용하며, 오히려 젊은 선수들의 활약이 우승에 영향을 미친다.
3. 준결승 진출 여부와 우승 여부에 따른 데이터 분석을 진행한 결과 준결승 진출을 위해서는 선수들의 노련한 경험이 중요한 요소이지만 우승을 바라보기 위해서는 경험치와 더불어 젊은 에너지도 중요함을 예상해볼 수 있다. 
4. 우승팀은 상대적으로 젊은 스쿼드를 가졌지만 그 우승팀이 월드컵 본선에 진출하기 위해선 경험이 더 풍부한 선수들의 유무 또한 중요하다고 볼 수 있었다. 즉, 젊은 에너지와 노련한 경험이 균형을 이룬 팀이라고 할 수 있다. 따라서 우승팀은 월드컵을 치러본 경험이 있는 선수들을 적절히 포함하여 적절한 세대교체를 통해 신구 조화를 이룬 팀일 가능성이 높다.
5. 데이터 분석을 거듭할수록 실력을 나타내는 지표나 객관적인 수치를 나타내는 지표도 당연 중요하지만, 월드컵의 단판 토너먼트 방식이 가진 다양한 변수 혹은 운적인 요소, 기세같은 수치로 표현할 수 없는 것들이 월드컵 성적에 생각보다도 더 많이 개입하고 있다는 것을 알았다.
6. 더불어 현대 축구의 전술이 다양화되고 해가 거듭할수록 점점 강해지는 압박의 강도로 인해 더 높은 체력을 요구하면서 젊은 선수들의 유입과 활약이 두드러지는 추세인것을 데이터 상으로도 확인할 수 있었다.
```

---

### 5. 데이터 정제 및 전처리
위 과정을 거쳐 년도별, 국가별로 정리된 최종 컬럼을 선정하였다.
최종 데이터셋은 경기 전(사전 정보) 기반 지표와 실제 월드컵 본선 경기에서 산출된 지표를 모두 포함하여 머신러닝 학습에 활용 가능하도록 정제하였다.
또한 선수들의 개인 스탯에 있어서 더 많은 데이터들을 가지고 학습시키기 위해 게임 FIFA에 등록된 선수들의 게임 스탯들을 수집하고 병합하여 게임 FIFA의 버전과 월드컵 년도에 맞추어 각 나라의 선수단에 맞게 각각 통합하였다.
예) FIFA21과 2022년 월드컵의 데이터를 매칭하여 나라별로 FIFA 스탯들의 공격, 수비 관련 스탯들의 평균을 내어 할당

**최종 컬럼**  
```markdown
- Year : 월드컵 개최년도
- Nation : 국가명 (한글)
- Eng_Nation : 국가명 (영문)
- Q_WR : 월드컵 개최전 3년간의 예선&친선&지역리그 평균승률
- Q_GR : 월드컵 개최전 3년간의 예선&친선&지역리그 평균 골득실률
- Wc_Rank : 월드컵 순위 (Target 1)
- Wc_Point : 월드컵 승점 (Target 2)
- Avg_Apps : 선수들의 월드컵 본선 진출 횟수의 평균
- Avg_Age : 선수들의 나이 평균
- Avg_Famous : Top 20 클럽에 속한 선수 수
- F_Rank : 월드컵 개최 전년도 피파 랭킹
- F_Point : 월드컵 개최 전년도 피파 포인트
- F_Rd : 전년도 대비 피파 랭킹 변화량
- F_Pd : 전년도 대비 피파 포인트 변화량 

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

- ATK_INDEX : 각 팀의 해당년도 월드컵 본선에서의 공격력 관련 수치
    - goals_z, xg_z, crosses_z, nsxg_z , fouled_z, boxtouches_z, passes_z, progpasses_z, takeons_z, progruns_z 

- DEF_INDEX : 각 팀의 해당년도 월드컵 본선에서의 수비력 관련 수치
    - fouls_z , interceptions_z , clearances_z , tackles_z , blocks_z , aerials_z
```

--- 

## 📄WBS
<img width="1055" height="706" alt="image" src="https://github.com/user-attachments/assets/56904639-fc1b-4576-a1e0-f45d8bac1b66" />


## 🔧Trouble Shooting
문제 해결 방법은 [TROUBLESHOOTING.md](./TROUBLESHOOTING.md) 문서를 참고하세요.

