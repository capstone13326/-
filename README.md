# 노약자 도우미


## **1. 블럭도 **


<br/><br/>
## **2. 작품 목표**

우리나라가 빠르게 초고령사회에 진입함에 따라 독거노인 수와 노인 고독사는 계속해서 증가할 것으로 보인다. 독거노인의 심박수, 체온과 같은 건강정보를 실시간으로 기록해 위급상황 시 보호자에게 알리고, 구조 요청이 필요할 때 신속한 대처가 가능하도록 하는 시스템을 개발하여 노인 고독사를 예방하는데에 목표를 둔다. 

<br/><br/>

## **3. 진행사항**

### 스마트밴드 부분

### * Arduino Nano 33 ble 

![머신러닝](https://user-images.githubusercontent.com/105420733/175385373-204921c0-f23e-424a-9d9c-6e41899cc122.png)

<br/>

> 아두이노에서 tinyML라이브러리를 사용하여 테스트 한 코드이다. 위 사진을 보면 yes는 초록색 LED로 no는 빨간색 LED로 표시되는데 외국인과 발음이 달라 잘 인식되지 않았다.

<br/>

#### 참조 링크
> <https://colab.research.google.com/github/arduino/ArduinoTensorFlowLiteTutorials/blob/master/GestureToEmoji/arduino_tinyml_workshop.ipynb>


> <https://create.arduino.cc/projecthub/cy49/wake-up-the-world-detection-tinyml-8c13db>

<br/><br/>
### * Arduino Nano 33 ble > Raspberry Pi Zero W 로 변경

![KakaoTalk_20220624_041613625](https://user-images.githubusercontent.com/105420733/175391636-246ac736-98fb-47a2-9271-3a42889a2c05.png)

<br/>

>  Rasberry Pi Zero W는 Arduino nano 33 ble에서 없는 무선 LAN을 지원함. 라즈베리파이 OS를 지원하기 때문에 파이썬 프로그램을 쓸 수 있음. 또한 학습데이터 확보가 쉬운 툴을 사용할 수 있는 모델로 추천 받아 Raspberry Pi Zero W 로 변경

<br/><br/>
### * Raspberry Pi Zero W > Arduino Nano RP2040 Connect 로 변경

![rp2040](https://user-images.githubusercontent.com/105420733/175393287-e1f69dd6-d03e-48f2-9a88-9f643e2eaf0e.png)

<br/>

> 아두이노 폼팩터 + 라즈베리파이 RP2040 칩셋 내장. MicroPython을 지원하며 라즈베리파이 피코와도 호환이 된다. 사운드 활성화, 오디오 제어 및 AI 음성 인식을 위한 내장 마이크가 포함되어 있으며 6축 IMU가 있다. 또 Arduino nano 33 ble과 다르게 와이파이도 지원한다.


<br/><br/>

---------
<br/>


### 웹서버 부분

### * Jetson Nano > Raspberry Pi 4 변경

> 젯슨나노 웹서버 호환에 어려움이 있으므로 웹서버 구축에 더 적합한 라즈베리파이로 변경

<br/><br/>

### * motion을 이용한 라이브 웹스트리밍(웹 카메라 작동 확인)
 
 > motion 설치
  
 > $ sudo apt-get install motion


![Hnet-image](https://user-images.githubusercontent.com/105420733/170521420-48f7b16f-75a5-469e-91fe-d81626b120f0.gif)


> 추후 플라스크 웹서버를 이용하여 웹스트리밍으로 수정

<br/><br/>


### * 회원가입 및 로그인, 로그아웃 기능
<br/>

https://user-images.githubusercontent.com/105420733/175293980-ad0c26f1-eb5e-4eb7-97c9-4ccba8cc1682.mp4


<br/>

https://user-images.githubusercontent.com/105420733/175294184-4d4c510c-8875-482f-b7e5-d7b79d53a6ae.mp4


 <br/>
 
  > 데이터베이스 관리 시스템 DBMS((DataBase Management System)을 사용
 <br/>
  
  
  ![sq](https://user-images.githubusercontent.com/105420733/175082466-4d99816f-b047-4f11-8366-96bb19c89071.png)
  
  <br/>
  
  > SQLite를 사용하여 사용자 로그인 데이터베이스 관리
  
<br/><br/>
  
  
 ### * 웹스트리밍 및 메인 웹서버 연동
  
  <br/>

https://user-images.githubusercontent.com/105420733/175294275-c85d48d2-30a9-4af1-a608-a2eb102ef661.mp4


  
