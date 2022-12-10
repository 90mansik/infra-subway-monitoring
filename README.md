<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>
<p align="center">
  <img alt="npm" src="https://img.shields.io/badge/npm-%3E%3D%205.5.0-blue">
  <img alt="node" src="https://img.shields.io/badge/node-%3E%3D%209.3.0-blue">
  <a href="https://edu.nextstep.camp/c/R89PYi5H" alt="nextstep atdd">
    <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fedu.nextstep.camp%2Fc%2FR89PYi5H">
  </a>
  <img alt="GitHub" src="https://img.shields.io/github/license/next-step/atdd-subway-service">
</p>

<br>

# 인프라공방 샘플 서비스 - 지하철 노선도

<br>

## 🚀 Getting Started

### Install
#### npm 설치
```
cd frontend
npm install
```
> `frontend` 디렉토리에서 수행해야 합니다.

### Usage
#### webpack server 구동
```
npm run dev
```
#### application 구동
```
./gradlew clean build
```
<br>


### 1단계 - 웹 성능 테스트
1. 웹 성능예산은 어느정도가 적당하다고 생각하시나요
    : 경쟁사와의 현재 성능 테스트는 다음과 같습니다.
   
- 휴대전화

|     사이트    | FCP (초) | TTI (초) | SI (초) | TBT (밀리초) | LCP (초) | CLS  |
|---------------|----------|---------|--------|---------------|----------|-------|
|서울교통공사 |    6.4    |    8.1   |   7.5   |       780      |   11.2   |   0    |
|  네이버지도  |    2.6    |    7.1   |   5.3   |       760      |    8.1   | 0.03   |
|   카카오맵   |    1.7    |    4.5   |   6.7   |         50      |    6.7   | 0.005 |
| RunnigMap  |   14.9   |    15.4   |  14.9  |       490      |   15.4  | 0.042 |


- 데스크톱

|     사이트    | FCP (초) | TTI (초) | SI (초) | TBT (밀리초) | LCP (초) | CLS   |
|---------------|----------|---------|--------|---------------|----------|-------|
|서울교통공사 |    1.5    |    1.9   |   2.2   |       140      |    3.7    | 0.001 |
|  네이버지도  |    0.5    |    0.7   |   2.3   |        0       |    1.4     | 0.006 |
|   카카오맵   |    0.5    |    0.7   |   2.2   |         0       |    1.4    | 0.039 |
| RunnigMap  |    2.7    |    2.8   |   2.7   |       80      |    2.8    | 0.004  |

경쟁사와 비교하여 가장 성능이 좋은 카카오맵 기준으로 사용자가 차이를 인식하는 20% 기준으로 성능 예산을 수립하였습니다.
- 정량 : 압축된 리소스 최대 크기 200KB 미만
- 시간 : FCP 2.0, TTI 5.0(휴대전화 기준)

2. 웹 성능예산을 바탕으로 현재 지하철 노선도 서비스의 서버 목표 응답시간 가설을 세워보세요.
: PageSpeed 에서 추천하는 아래의 개선방안처럼 점차 개선해 볼 예정입니다. 

-  텍스트 압축 사용, 가능한 절감 효과 : 1,860KiB
- 사용하지 않는 자바스크립트 줄이기, 가능한 절감 효과 : 699KiB
- 랜더링 차단 리소스 제거하기
- 정적인 애셋 제공하기

---

### 2단계 - 부하 테스트 
1. 부하테스트 전제조건은 어느정도로 설정하셨나요

2. Smoke, Load, Stress 테스트 스크립트와 결과를 공유해주세요

---

### 3단계 - 로깅, 모니터링
1. 각 서버내 로깅 경로를 알려주세요

2. Cloudwatch 대시보드 URL을 알려주세요
