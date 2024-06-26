# UDP & TCP

# TCP란?

> **신뢰적인 연결방식을 지향**
> 
- 신뢰적인 연결 방식을 위해 체크해야할 것
    - 손실
    - 순서
    - 혼잡
    - 과부하
- 가상회선 패킷 교환 방식
    
    ![Untitled](UDP%20&%20TCP%20b2ea3f1234c04a8eaab280439a84cb56/Untitled.png)
    

## TCP의 신뢰성을 높이기 위한 방법

### 흐름 제어(Flow Control)

- **Stop & Wait 방식**
    - 전송 패킷의 확인을 받고… 다음 패킷을 전송!
- **Sliding Window**
    - window size만큼 확인 없이 다음 패킷을 전송한다!
    - 대게 송신용 window, 수신용 window 두개를 보유하고 3-way-handshake 시간에 window size를 조절한다.

### 혼잡 제어(Congestion Control

- 특정 라우터에 데이터가 몰릴 경우 과도한 재전송 등으로 네트워크 마비…
- 흐름제어 : 송신측과 수신측의 전송속도를 다루지만 혼잡 제어는 호스트와 라우터를 포함한 넓은 관점

![Untitled](UDP%20&%20TCP%20b2ea3f1234c04a8eaab280439a84cb56/Untitled%201.png)

- **AIMD**
    - 혼잡이 발생할때 까지 윈도우 사이즈를 선형적으로 키운다
    - 혼잡 발생시 사이즈를 절반으로 줄인다.
- **slow start**
    - 하나의 패킷을 전송하고 무사히 통신이 된다면 window size를 2배씩 크게 한다.
    - 이전 혼잡 사이즈의 절반이 되면 그때 AIMD 방식으로 움직인다.
    - 기존의 AIMD보다 효율적으로 움직인다.

## UDP란?

> **비연결성, 비신뢰성 프로토콜**
> 
- 신속성
- Datagram의 전송 방식