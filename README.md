# 노약자 도우미

<br/>

## **1. 작품목표**
<br/>

![스크린샷(136)](https://user-images.githubusercontent.com/105420733/203249358-9b2f6293-0f8a-47c4-9c47-eb500a65e893.png)

독거노인의 심박수를 측정하고 기록하며, 얼굴인식 기능으로 사용자의 얼굴을 등록해 실시간으로 보호자가 cctv를 열람할 수 있게 해
응급상황 시 신속한 대처가 가능하도록 하는 독거노인 모니터링 시스템을 개발하여 노인 고독사를 예방하는데에 목표를 두었습니다.

<br/><br/>

## **2. 블럭도**
<br/>


![블럭도 최최종](https://user-images.githubusercontent.com/105420733/203463989-200c87a8-13b8-40fc-ab57-fccc26665dc4.png)





<br/><br/>

## **3. 세부내용**
<br/>

###  **심박수 측정기**
  + 심박센서 회로 연결

   
        
 ![바꾼회로](https://user-images.githubusercontent.com/105420733/203353637-cfa171ea-86cf-4498-86b7-4cd1da30bc22.png)
 
  <br/>
  
   Pulse센서는 Arduino용으로 설계되었기 때문에 디지털로 읽을 수 있는 신호를 제공하지 않습니다. 아날로그 신호를 읽으려면 ADC가 필요하여 MCP3008의 채널 0에 연결하여 회로를 구성하였습니다. 

<br/>

  + 심박센서 작동 코드


``` C
try:
    while True:
        bpm = p.BPM
        if bpm > 0:
            print("BPM: %d" % bpm)
        else:
            print("No Heartbeat found")
        time.sleep(1)
except:
    p.stopAsyncBPM()
```

  <br/>
   
 
  
  
###  **노약자 모니터링 시스템**
  + 얼굴인식
    + teachable machine 파이썬 실행
 
![노약자모니터링](https://user-images.githubusercontent.com/105420733/203365450-df70f6ab-a7f4-4505-a279-be49f6df6b46.png)

  + Node-Red 
    + Mqtt 심박수 데이터 받아 그래프,차트로 표시
    + Mqtt 얼굴인식 결과값 받아 표시
         
   <br/>
   
   
###    Node-Red UI 구축

![KakaoTalk_20221122_195350399](https://user-images.githubusercontent.com/105420733/203312369-b2b517d8-e5ea-4e94-b379-8ff70864e2a0.png)

<br/>

![nodered ui](https://user-images.githubusercontent.com/105420733/203365898-6b0f75c1-0cf9-4ada-9f40-e9bb09d1a9a8.png)

<br/><br/>


###    음성인식 기능

<br/>

![음성인식](https://user-images.githubusercontent.com/105420733/203468022-b84c2a49-a9f6-48a9-a748-2689f07a82b0.png)


edge impulse 사용하여 원하는 단어(데이터)를 수집 노이즈와 언노운을 넣어 데이터 세트를 구축하였습니다.
데이터 세트를 통해 MFCC(Mel Frequency Cepstral Coefficients)(많은 양의 중복 정보를 단순화된 형식으로 바꾸는 방법)블록 및 신경망을 구성하고 완성된 보이스 정보를 CLASSIFIER를 사용하여 단어 기계 학습 모델을 실행해주었습니다.

<br/><br/>

<br/>

![KakaoTalk_20221123_132856994](https://user-images.githubusercontent.com/105420733/203469550-79582cce-b970-4c77-9db5-59aeea8719d1.jpg)


<br/>

![KakaoTalk_20221123_132856994_02](https://user-images.githubusercontent.com/105420733/203469545-a54ecf95-fd03-4542-9e7c-fcd8752b87e1.jpg)

>특정 단어가 아닐 때 noise와 unknown에 반응
<br/>

![KakaoTalk_20221123_132856994_01](https://user-images.githubusercontent.com/105420733/203469551-2d5ed1ef-56dd-4a4b-82d1-a28c8bac5e9d.jpg)

>주변 소음이 있을 때 noise에 반응

<br/><br/>

*음성인식 작동영상

<br/>

<https://youtu.be/YuNdvmOJLkc>

<br/>

> Arduino 33ble 는 와이파이 연결이 불가하여 작품 기능에 추가하지 못했습니다.


<br/><br/>

## **4. 구동영상**

<br/><br/>


https://user-images.githubusercontent.com/105420733/203380591-11ab67a0-16d0-4ce3-a8d0-bfaf3eeca31d.mp4


<https://youtu.be/jGSFqfsg4Pc>

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


