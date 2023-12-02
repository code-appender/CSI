## Context Switching이에 대해서 설명해주세요.

### Context Switching이란 무엇인가요?

---
<u>
CPU가 실행하고자 하는 프로세스를 바꾸며 메모리에 이전의 프로세스의 상태를 저장하고, 새로운 프로세스의 상태를 적재하는 작업을 말합니다.
</u>

더 자세히 설명하면, 
멀티 프로세서 환경에서 CPU가 어떤 프로세스를 실행하고 있는 상태에서 
인터럽트 요청에 의해 다음 우선 순위의 프로세스가 실행되어야 할 때, 
PCB에 이전의 프로세스의 상태 또는 레지스터 값(Context)을 저장하고, 
새로운 프로세스의 상태를 적재하는 작업입니다.

<br>

### Context Switching이 필요한 이유는 무엇인가요?

---
Computer가 매번 하나의 Task만 처리할 수 있다면
해당 Task가 끝날때까지 다음 Task는 기다릴 수 밖에 없습니다.

Context Switching을 통해 빠른 속도로 Task를 바꿔 가며 실행한다면 실시간으로 동시 작업이 이루어지는 듯한 효과를 낼 수 있습니다.

<br>

### Context Switching은 언제 발생하나요?

---
Context Switch가 발생하는 경우는 멀티태스킹, 인터럽트 핸들링, 사용자 모드와 커널 모드 간의 전환까지, 크게 3가지가 존재합니다.


#### <u> 멀티태스킹(Multitasking) </u>

- 실행 가능한 프로세스들이 운영체제의 스케줄러에 의해 조금씩 번갈아가며 수행되는 것을 말합니다.

- 번갈아 가며 프로세스가 CPU를 할당 받는데 이때 Context Switching이 이루어집니다.

#### <u> 인터럽트 핸들링(Interrupt handling) </u>

- 인터럽트란 컴퓨터 시스템에서 예외 상황이 발생했을때 CPU에게 알려 처리할 수 있도록 하는 것을 말합니다.

- 인터럽트가 발생하면 Context Switching이 발생합니다.

- 인터럽트 종류

  - I/O request : 입출력 요청

  - time slice expired : CPU 사용시간이 만료

  - fork a child : 자식 프로세스 생성

  - wait for an interrupt : 인터럽트 처리 대기

- 사용자와 커널 모드 전환(User and kernel mode switching)

  - 사용자와 커널 모드 전환은 Context Switch가 필수는 아니지만 운영체제에 따라 발생할 수 있습니다.

<br>

### Context Switching의 과정은 어떻게 이루어지나요?

---
<img src="https://blog.kakaocdn.net/dn/cLs4ee/btq6zCgeEaS/eMkhgp9failtca7VYSgbkk/img.png">

1. 요청 발생: 인터럽트 또는 트랩에 의한 요청이 발생.(트랩은 소프트웨어 인터럽트)

2. PCB에 저장: 운영체제는 현재 실행중인 프로세스(P0)의 정보를 PCB에 저장.

3. CPU 할당: 운영체제는 다음 프로세스(P1)의 정보를 PCB에서 가져와 CPU를 할당.

위 과정을 반복적으로 수행한다. 
Context Switching하는 동안 CPU는 아무일도 하지않는 시간이 발생하는데 이를 오버헤드(Overhead)라 하고 오버헤드가 잦아지면 성능이 떨어질 수 있습니다.


다시 말해, <u> Context Switching이 잦아지면 CPU가 일을 멈추는 오버헤드가 증가하여 성능이 떨어질 수 있습니다. </u>

<br>

### 장점

---
- 한 프로세스가 CPU를 독점하지 않고 여러 프로세스가 적절하게 CPU를 사용할 수 있습니다.


<br>

### 단점

---
- Context Switching이 진행되는 동안 CPU는 아무일도 하지 않는 시간이 발생하는데 이를 오버헤드(Overhead)라 하고 이 오버헤드가 잦아지면 성능이 떨어질 수 있습니다.

<br>