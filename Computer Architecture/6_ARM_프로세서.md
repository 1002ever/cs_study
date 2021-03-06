# \# ARM 프로세서



- 프로세서?

  \- 메모리에 저장된 명령어들을 실행하는 유한 상태 오토마톤



- ARM, Advanced RISC Machine

  > RISC : Reduced Instruction Set Computing
  >
  > => 단순한 명령 집합을 가진 프로세서

  - 칩의 기본 설계 구조만 만들고,

    실제 기능 추가, 최적화 부분은 개별 반도체 제조사에 맡김

    => <u>물리적 설계는 같아도, 저마다 다른 칩을 만듦</u>

  - 물리적 설계 베이스는 같지만, 용도에 따라 다양한 제품군이 존재

  - 단순한 명령 집합을 지향하므로 <u>적은 수의 트랜지스터만 필요</u>

    => *간결한 설계와 더 작은 크기가 가능*

    => 전력 소모가 적기 때문에 ARM CPU가 스마트폰, 태블릿PC 같은 모바일 기기에 자주 사용



- ARM은 **일종의 생태계**

  - ARM을 위해 개발된 프로그램

    => 오직 ARM 프로세서가 탑재된 기기에서만 실행 가능

    => x86 CPU 프로세서 기반 프로그램은 ARM 기반 기기에서 실행 불가

  - ARM 기기에 동작하는 OS는 다른 ARM 기반 기기에서도 동작 가능

    ex) 안드로이드

    Tip. iOS의 경우 소스코드를 공개하지 않아서, 애플 기기는 불가능