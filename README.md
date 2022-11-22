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


![스크린샷(145)](https://user-images.githubusercontent.com/105420733/203384466-b516fdc4-813e-45c0-8157-9be4764878f5.png)





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


