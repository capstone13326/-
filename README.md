# 노약자 도우미


<br/><br/>

## **1. 작품목표**
<br/>

![스크린샷(136)](https://user-images.githubusercontent.com/105420733/203249358-9b2f6293-0f8a-47c4-9c47-eb500a65e893.png)

> 우리나라가 빠르게 초고령사회에 진입함에 따라 독거노인 수와 노인 고독사는 계속해서 증가할 것으로 보인다.
독거노인의 심박수를 측정하고 기록하며, 얼굴인식 기능으로 사용자의 얼굴을 등록해 실시간으로 보호자가 cctv를 열람할 수 있게하고
응급상황 시 신속한 대처가 가능하도록 하는 독거노인 모니터링 시스템을 개발하여 노인 고독사를 예방하는데에 목표를 두었다.

<br/><br/>

## **2. 블럭도**
<br/>


![스크린샷(140)](https://user-images.githubusercontent.com/105420733/203312914-aa6b2f6d-0613-49e5-bb5b-df5f0c1cf0d2.png)


<br/>


![KakaoTalk_20221122_195350399](https://user-images.githubusercontent.com/105420733/203312369-b2b517d8-e5ea-4e94-b379-8ff70864e2a0.png)


<br/><br/>

## **3. 세부내용**
<br/>

###   + 심박수 측정기
        + 심박센서 회로 연결
        + 심박센서 작동 코드

<br/><br/>



## **4. 구동영상**

<br/><br/>
<br/><br/>
<br/><br/>
<br/><br/>
<br/><br/>

## **5. 팀원구성**
<br/>

###  **팀장**
  + 정여진

<br/>

###  **팀원**
  + 김용호
  + 서도열
  + 심채은


<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>

## ** 진행사항**

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


### * RP2040 - 심박수센서 연결


![99E46247-0BF7-45EA-A319-61EF3FE62FFD](https://user-images.githubusercontent.com/105420733/189802689-314e5fe4-4a26-41a7-be9f-ea0ae7d1ca97.jpeg)

![B2EB1CEC-DE8E-419F-99F6-DD226863451C](https://user-images.githubusercontent.com/105420733/189802326-424c0d29-41fd-4a65-a2be-cb96836e77ca.png)

<br/>

> 컴파일 에러로 인해 진행 불가

<br/><br/>


### * RP2040 - 음성인식

<br/>

![F21E9C27-F6C1-40B5-8515-13F7A3189055](https://user-images.githubusercontent.com/105420733/189805961-554b35a2-de8d-4739-bab0-db8cda09fdea.png)


> Teachable Machine에서 사운드 인식은 Tensorflow.js 만 선택할 수 있어 p5.js에서 학습된 데이터를 확인하였음. 이후 rp2040 에서 확인하였지만 오류로 인해 반응하지 않았음.

> p5.js : 자바로 되어 있는 Processing을 자바스크립트 버전으로 만든 라이브러리

<br/>

#### 참조 링크
> <https://github.com/alankrantas/TeachableMachine-p5js-serialport>


> <https://create.arduino.cc/projecthub/alankrantas/use-teachable-machine-ai-to-control-anything-2ad1ee>


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


  <br/>
  
  
 ### * highchart를 이용하여 무작위 값을 받아 flask 웹 서버에 실시간 그래프 그리기 구현
  
  <br/>
  
https://user-images.githubusercontent.com/105420733/189767404-2eb233a1-171e-4b0d-97ab-1e25a1becc0b.mp4


  <br/>
  
  ### * 영상처리를 이용해 flask 웹 서버 실시간 얼굴인식


![flask 얼굴인식](https://user-images.githubusercontent.com/105420733/189768970-dab50650-144e-4f11-8ca5-367513d8d011.png)


> opencv2 실시간 영상처리 이용해서 얼굴인식 웹캠 구현 하였으나 실시간 스트리밍 속도가 느려짐


<br/>

### csv파일(심박수등 데이터 파일) 읽어서 실시간 차트 그리기 진행중


<br/>


![라즈베리파이](https://user-images.githubusercontent.com/105420733/193738287-57d5ce2f-826c-4f55-88c3-47d21cf3cb82.jpg)

> Edge_Impulse 와 라즈베리파이 연결 오류


![스크린샷(115)](https://user-images.githubusercontent.com/105420733/193737548-6ba56eb8-7024-4157-9e89-f98bc491299c.png)

> 첫번째 자료 참고해 Edge_Impulse 에서 Training data, Test data 등록 진행 중

Teachable machine 모델과 라즈베리파이 연결 부분 진행 중





