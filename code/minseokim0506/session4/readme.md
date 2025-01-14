# EDA 정리
그래프의 구현 코드는 클론 코딩을 통해 정리했으므로 EDA의 전과정을 리뷰
1)데이터 수집 -> 시각화 탐색 -> 패턴 도출 -> 인사이트 발견
EDA를 통한 데이터 분석의 시작이 잘못되면 차후 최적화에 난항을 겪으므로 중요함.
2) EDA의 순서
- 어떤 데이터가 있고 결측치는 어느 변수에 존재하는가?
- 데이터 유형(이산, 연속)에 따른 적합한 시각화 방식을 사용
- 결측치 처리(최빈값, 처리를 위한 기준 마련)
- Feature enginerring & Data Cleaning
- 얻은 인사이트를 통해 새로운 특징 만들기 (연속 -> 이산화, 두 변수 합치기 등)
- 불필요한 변수값 삭제 / string형 변수의 numeric화

# 5차 세션 사전 과제
## 수치 기술 통계량
1) 수치 기술 통계 : 중심 위치, 변동성, 연관성 척도로 설정
1. 중심 위치
- 평균, 중앙값, 최빈값
- 세가지 값의 순서를 통해 자료의 개형 확인 가능 
2. 변동성
- 사분위수: 데이터 표본을 4개의 동일한 부분으로 나눈 값
- 범위, 분산, 표준편차
- 변동 계수: 표준편차/평균 *100
3. 연관성
- 공분산: 두 변수가 각자 평균으로부터 떨어진값을 서로 곱해 평균 낸값, 두변수가 어느 방향으로 얼마나 변동하는가
4. 상관계수
- 공분산을 각 변수의 변동성을 이용해 표준화 (-1과 1사이의 값)


## 여러 분포들 / 표본과 모집단
1) 정규 분포
- scipy.stas를 import해 구현가능
2) T분포
- 두 집단의 평균에 차이가 얼마나 있는가?
- T: 그룹간 평균 차이에 비례하는 변수
- 표본집단에 따라 평균값은 항상 일정하지 않는 불확실성이 존재
- T = 표본 평균 차이 / 불확실도 -> 그룹간 평균차가 클수록/불확실성이 낮을수록 T값은 커진다
3) 카이스퀘어 분포
- 한 집단의 표본 분산이 어떤 형태를 갖는가? 
- 정규분포의 제곱 -> 음수의 값은 존재하지않음
- 오른쪽으로 긴 꼬리의 Skewness
4) F 분포
- 두 집단의 분산  -> 그룹간 평균 차이와 그룹내의 변동성을 비교해 그룹 간 차이의 우연성을 판단!'
* 자유도: 표본의 수와 비례
5) 중심극한 정리
- 한번 추출할때 많은 표본을 추출할 수록 그 표본들의 평균 분포가 정규분포에 가까워짐.

## 가설검정의 절차와 해석
1) 절차
- 가설 설정 -> 유의 수준 설정 -> 검정통계량 산출 -> 기각/채택 판단
2)검정 통계량 산출
- 데이터의 분포 특징에 따라 어떤 검정 통계량을 사용할지 정해 기각 및 채택 여부를 결정
-기준은 신뢰구간이며 대립가설의 기각 채택 여부를 결정
- 1종, 2종 오류를 어떻게 허용할지 정해 유의 수준을 정함. 어떤 오류가 더 치명적인가?
