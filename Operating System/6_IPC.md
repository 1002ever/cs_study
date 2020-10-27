## IPC(Inter Process Communication)



- 프로세스는 독립적으로 수행

  => <u>하지만 프로세스 간 통신을 해야하는 상황이 존재</u>



- 프로세스는 커널이 제공하는 IPC 설비를 이용하여 프로세스 간 통신을 할 수 있음



#### IPC 종류



1. 익명 PIPE

   - 두 개의 프로세스 연결

     => 하나는 데이터를 쓰기만, 다른 하나는 데이터를 읽기만 함

     ​     한쪽 방향으로만 통신이 가능한 **반이중 통신**

   - 구현이 간단하다는 장점

     전이중 통신을 구현하려면 매우 복잡해지는 단점

   - 통신할 프로세스를 명확히 알 수 있는 경우에 사용

     ex. 부모 - 자식 프로세스 간 통신



2. Named PIPE

   - 전혀 모르는 상태의 프로세스 간 통신에 사용

   - 읽기 / 쓰기가 동시에 불가능

     => 익명 파이프 처럼 전이중 통신을 위해서는 2개가 필요



3. Message Queue

   - 입출력 방식은 Named PIPE와 동일

     <u>but 데이터의 흐름이 아니라 메모리 공간이라는 점이 다름</u>

   - 사용할 데이터에 번호를 붙여서 여러 프로세스가 데이터를 쉽게 다룰 수 있음



4. 공유 메모리

   - 파이프, 메시지 큐는 통신을 이용한 설비

     공유 메모리는 <u>데이터 자체를 공유하도록 지원하는 설비</u>

     => 프로세스는 영역을 독립적으로 가지지만,

     ​      <u>다른 프로세스의 데이터를 사용해야 하는 경우가 있음</u>

     ​      => 통신을 통해 데이터를 전달하면 그만이지만,

     ​            메모리를 공유하게 해준다면 더욱 편리할 것

   - 프로세스가 공유 메모리 할당을 커널에 요청

     => 커널은 해당 프로세스의 메모리 공간을 할당

     ​	=> 이후 모든 프로세스는 해당 메모리 영역에 접근 가능

   - 중개자 없이 메모리에 바로 접근할 수 있으므로 **IPC 중에 가장 빠름**



5. 메모리 맵

   - 공유 메모리 처럼 메모리를 공유

     => <u>*열린 파일을 메모리에 매핑시켜서 공유*</u>

   - 주로 파일로 대용량 데이터를 공유해야 할 때 사용



6. 소켓
   - 네트워크 소켓 통신을 통해 데이터를 공유
   - **원격에서** 프로세스 간 데이터를 공유할 때 사용



##### IPC 통신에서 프로세스 간 데이터를 <u>동기화하고, 보호하기 위해</u>

##### 세마포어, 뮤텍스 기법을 사용