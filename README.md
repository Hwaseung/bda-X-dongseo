# WINDmin

</br>
</br>

## 1. 환경 정보
- 운영 체제: Linux
- OS 버전: #1 SMP PREEMPT_DYNAMIC Thu Jun 27 21:05:47 UTC 2024
- 프로세서: x86_64
- 세부 정보: Linux-6.1.85+-x86_64-with-glibc2.35
- 이 시스템의 CPU 코어 수: 2
- 이외 주피터 버전:
  - IPython          : 7.34.0
  - ipykernel        : 5.5.6
  - ipywidgets       : 7.7.1
  - jupyter_client   : 6.1.12
  - jupyter_core     : 5.7.2
  - jupyter_server   : 1.24.0
  - jupyterlab       : not installed
  - nbclient         : 0.10.0
  - nbconvert        : 7.16.4
  - nbformat         : 5.10.4
  - notebook         : 6.5.5
  - qtconsole        : not installed
  - traitlets        : 5.7.1
- Python 버전: 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0]

</br>

## 2. 진행 과정
### 1.2020-2022 기상 데이터의 평균값을 입력으로 하여 시간별 총 발전량 학습
#### 경주
- feature : 'temp_air', 'specific_humid', 'wind_speed', 'wind_u_10m', 'storm_u_5m', 'month', 'hour’
- model : QuantileRegressor(quantile=0.5, alpha=0, solver='highs')

</br>

#### 영광
- feature : 'temp_air', 'specific_humid', 'wind_speed', 'wind_u_10m', 'storm_u_5m’
- model : QuantileRegressor(quantile=0.5, alpha=0, solver='highs')

</br>


### 2.위 모델을 통해 2023년도 시간별 총 발전량 예측
- 터빈별 실제 기상 정보를 설명변수로 설정하여 예측

</br>


### 3.당일 15시 이전의 위에서 예측된 2023 총 발전량과 2023 기상정보를 통해 다음날 발전량 예측
- feature : 
- model : XGBoost
