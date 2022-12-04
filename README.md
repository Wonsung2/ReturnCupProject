### :memo: Summary
##### BEAN CUP ( 카페 일회용 컵 수거 자판기 )
##### 프로젝트 기간: 2022.05.20 ~ 2022.06.28
##### 팀원 : 장성원 외 8명 



---


- Tech stacks
  - Python
  - Android Studio
  - GitHub
  - tensorflow, tensorflowlite
  - RDS, MariaDB
  - EC2, Docker
  - Raspberry Pi 4

- 프로젝트 기획의도
  - 연간 플라스틱 컵 사용량 지속적인 증가, but 회수와 재활용 어려움 
  - 일회용 컵 보증금제 시행 논의에 따라 회수기 필요성 부각
 
- 프로젝트 내용 
  - Raspberry Pi 카메라에 찍힌 일회용 컵의 판별 
  - 첫 번째로 회수에 알맞은 형태인지 판별, 두 번째로 어느 브랜드의 일회용 컵인지 판별 
  - 회수에 알맞은 형태면 컵을 뒤집어서 무인회수기 투입기에 투입 > 세척 
  - 회원 정보 입력 시, 보증금을 회원 계정에 포인트로 적립

- 기능의 구현 목표
  1. 회수가 어려운 상태 ( ex. 빨대 여부, 홀더 여부, 뚜껑 여부, 잔여 음료 여부 등 판별) & 컵에 쓰여있는 브랜드 로고 판별
  2. PI CAMERA로 찍은 사진을 클라우드 환경으로 전송하여 이미지를 분류하는 것이 아닌, Raspberry Pi 내부에 tensorflow lite 환경을 구축한 뒤 바로 판별할 수 있도록 구현
  3. 회수에 적합한 컵이 투입되면 센서로 인식하여 세척 후 옆으로 밀어줌 
  4. 사용자가 정보를 입력하면 mqtt 통신을 사용하여 회원의 계정에 포인트 적립 
  
- 수행한 역할
  1. CNN 모델 학습을 위한 데이터 수집( 다양한 각도와 다양한 상태에서의 일회용 컵 사진 확보)
  2. Raspberry Pi 내부에 tensorflow lite 환경을 구축
  3. mobilenet, Xception 등 다양한 모델 성능 비교( 판별에 걸리는 시간 및 정확도를 기준)
  4. 아크릴 판을 사용하여 실제 무인회수기 제작

### 시스템 플로우차트
<img width="731" alt="순서도" src="https://user-images.githubusercontent.com/99372040/174710589-58fb6491-bfc4-4a33-bbe4-22f739ed6b78.png">
