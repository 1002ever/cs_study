## OSI 7계층



- 계층을 나누는 이유?

  : 통신이 일어나는 과정을 단계 별로 알 수 있고,

    특정한 곳에 이상이 생기면 어디서 문제가 생겼는지 쉽게  알 수 있고, 수정도 용이



1. 물리(Physical)

   - 사용 장비 - 리피터, 케이블, 허브 등

   - 데이터 전송 단위 - 비트(Bit)

   - 역할

     \- <u>데이터를 전기적인 신호로 변환</u>하여 주고받는 기능을 진행하는 공간



2. 데이터 링크(Data Link)

   - 사용 장비 - 브릿지, 스위치 등

   - 데이터 전송 단위 - 프레임(Frame)

   - 역할

     \- 물리 계층으로 송수신되는 정보를 관리하여 안전하게 전달되도록 도와주는 역할

     \- Mac 주소를 통해 통신

     \- 프레임에 Mac 주소를 부여하여 에러 검출, 재전송, 흐름 제어를 진행



3. 네트워크(Network)

   - 사용 장비 및 프로토콜 - 라우터, IP

   - 데이터 전송 단위 - 패킷(Packet)

   - 역할

     \- 라우터를 통해 이동할 경로를 선택하여 IP 주소를 지정, 해당 경로로 패킷을 전달

     \- 라윙, 흐름 제어, 오류 제어, 세그먼테이션 등을 수행



4. 전송(Transport)

   - 사용 프로토콜 - TCP, UDP

   - 데이터 전송 단위 - 세그먼트(Segment)

   - 역할

     \- TCP, UDP 프로토콜을 통해 통신을 활성화

     \- 포트를 열어, 프로그램들이 전송을 할 수 있도록 함

   - Tip.

     \- TCP : 신뢰성, 연결 지향적

     \- UDP : 비신뢰성, 비연결성, 실시간 서비스에 유리



5. 세션(Session)

   - 사용 기술 - API, Socket

   - 역할

     \- 데이터가 통신하기 위한 논리적 연결을 담당

     ​	=> <u>포트(Port) 연결</u>

     \- TCP / IP 세션을 만들고, 없애는 책임을 가짐



6. 표현(Presentation)

   - 사용 기술 - JPEG, MPEG 등

   - 역할

     \- 송신 시에는 컴퓨터가 관리하는 방식으로 데이터를 변환

       수신 시에는 유저가 볼 수 있는 방식으로 데이터를 변환

        => ***번역*** 역할을 하는 셈

     \- 파일 인코딩, 명령어를 포장, 압축, 암호화 등



7. 응용(Application)

   - 사용 기술 - HTTP, FTP, DNS 등

   - 역할

     \- 사용자가 네트워크에 접근할 수 있도록 해주는 계층

     \- 사용자 인터페이스, 전자우편, 데이터베이스 관리 등의 서비스를 제공