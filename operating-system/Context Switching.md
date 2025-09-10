# Context Switching

## 핵심 요약
- **Context Switching**: CPU가 현재 실행 중인 프로세스/스레드의 상태(Context)를 저장하고 다른 프로세스/스레드로 전환하는 과정
- 저장/복원 대상: **레지스터, 프로그램 카운터, 스택 포인터, 메모리 매핑 정보**
- 오버헤드 발생: 전환 자체는 순수 연산이 아님 → **빈번하면 성능 저하**

## 상세 설명
### Context Switching이란?
- 운영체제가 CPU 자원을 효율적으로 분배하기 위해 실행 중인 작업을 교체하는 과정
- **멀티태스킹** 환경에서 필수: 여러 프로세스/스레드가 동시에 실행되는 것처럼 보이게 함
- 전환 시 커널이 현재 실행 중인 Task의 **PCB(Process Control Block)**에 상태를 저장하고, 새 Task의 PCB에서 상태를 불러옴

### 비용(Overhead)
- Context Switching은 유용하지만 공짜가 아님
  - 레지스터 저장/복원
  - 캐시 무효화(Cache flush)
  - TLB(Translation Lookaside Buffer) 갱신
- 이 과정에서 CPU가 **실질적인 유저 작업은 수행하지 않음** → 오버헤드 발생

### 프로세스 vs 스레드 Context Switching
- **프로세스 간 전환**: 독립된 메모리 공간(Code, Data, Heap, Stack) 교체 필요 → 비용 큼
- **스레드 간 전환**: 동일 프로세스 내부 Code/Data/Heap 공유, Stack만 교체 → 비용 작음
