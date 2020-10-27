## PCB & 문맥 교환(Context Switching)



> \- Process Management?
>
> ​	CPU가 프로세스가 여러 개일 때, CPU 스케줄링을 통해 관리하는 것
>
> ​	=> CPU가 <u>각 프로세스들을 구분</u>할 수 있어야 관리가 가능



> \- Process Metadata?
>
> ​	: 프로세스의 특징 정보를 갖고 있음.
>
> ​		=> 이 메타데이터는 프로세스가 생성되면 <u>PCB(Process Control Block)에 저장</u>
>
> ​	ㄱ. Process ID
>
> ​	ㄴ. Process State
>
> ​	ㄷ. Process Priority
>
> ​	ㄹ. CPU Registers
>
> ​	ㅁ. Owner
>
> ​	ㅂ. CPU Usage
>
> ​	ㅅ. Memory Usage





#### PCB( Process Control Block )

```
프로그램 실행
-> 프로세스 생성
-> 프로세스 주소 공간에 (코드, 데이터, 스택 등) 할당
-> 이 프로세스의 메타데이터들이 PCB에 저장
```



​	\- PCB가 필요한 이유?

> CPU에서는 프로세스의 상태에 따라 교체 작업이 수행됨
>
> ex. 인터럽트 발생으로 할당 받은 프로세스가 waiting 상태가 되고,
>
> ​                                                다른 프로세스가 running 상태로 바뀔 때



​	\- PCB 관리 방법?

> 연결리스트로 관리 => 삽입 / 삭제가 용이
>
> PCB List Head에 PCB들이 생성될 때마다 붙음





#### Context Switching

- CPU가 이전의 프로세스 상태를 PCB에 보관하고,

  다른 프로세스의 정보를 PCB에 읽어 레지스터에 적재하는 과정

- 주로 아래의 경우에 발생

  ㄱ. 인터럽트 발생

  ㄴ. 실행 중인 CPU 사용 허가 시간을 모두 소모

  ㄷ. 입출력을 위해 대기해야 하는 경우

  ​	=> 마냥 기다리는 것 보다 그 시간에 다른 프로세스를 수행시키는 것이 효율적이므로

  > Ready -> Running, Running -> Ready, Running -> Waiting 처럼
  >
  > *상태 변경 시 발생*



