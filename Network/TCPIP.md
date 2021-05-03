# TCP/IP 프로토콜

#### 정의

: **데이터가 원하는 목적지에 도달할 수 있도록 인터넷에서 사용하는 표준 프로토콜**이다.

---

## Network Access Layer (네트워크 액세스 계층)

<br>

IP Datagram을 실제로 전달하는 서브 네트워크를 의미한다.
즉, 상대 측에서 받은 데이터를 인터넷 계층으로 전달한다.

네트워크 액세스 계층은 보통 이더넷을 이용해서 데이터를 보낸다.

### 이더넷 프레임 구조

![Ethernet Frame](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Fy0kd9%2Fbtq2CkJHilH%2FKK7LKDQE0bfvaaYegGAnKK%2Fimg.png "Ethernet Frame")

- Preamble (7byte)
  : 수신측에서 하드웨어 비트 동기를 맞추기 위한 준비 신호

- SFD (Starting Frame Delimiter, 1byte)
  : 다음 바이트 열이 프레임의 시작을 알린다.

- SA (Source Address)
  : 송신측의 MAC 주소이며, 자신의 주소를 ROM에 기록한다. 또한, 초기화 시 ROM에서 읽어 레지스터에 저장하고, 프레임 송신 시 이 리지스터를 읽어 프레임의 SA에 삽입한다.

- EtherType (2byte)
  : MAC 프레임 다음의 데이터 부분에 상위 프로토콜의 종류를 표시한다. 만약 0x0800이라면 Info에 있는 데이터의 프로토콜이 IP, 0x0806이라면 ARP 프로토콜

- Data (46 ~ 1500byte)
  : 상위 프로토콜의 데이터가 위치한다. 최대 허용길이(MTU)는 1500byte이다. DA부터 FCS까지의 전체 길이가 64byte 이상이어야 한다는 규정을 준수한다.

- PAD
  : 최소 길이 규정을 만족하지 못할 경우에는 '0'으로 채운다.

- FCS (Frame Check Sequence, 4byte)
  : Preamble과 SFD를 제외한 MAC 프레임의 비트열의 에러를 검사한다. 오류 검출을 위해 사용한다.
