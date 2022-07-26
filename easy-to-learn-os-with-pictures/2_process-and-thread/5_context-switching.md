# 컨텍스트 스위칭

```
    프로세스를 실행하는 중에 다른 프로세스를 실행하기 위해 
    현재 실행중인 프로세스의 상태를 저장하고 다른 프로세스의 상태값으로 교체하는 작업
```

### 컨텍스트 스위칭이 일어날때 변경되는 PCB의 값
1. 프로세스 상태
2. 프로그램 카운터(다음 실행할 명령어의 주소를 담고있음)
3. 각종 레지스터 값들

### 프로세스A, B 컨텍스트 스위칭 시나리오
1. 프로세스A의 CPU 점유시간 초과
2. 운영체제는 인터럽트를 발생시킴
3. 프로세스A는 하던 작업을 멈추고 현재의 레지스터 값 등을 PCB A에 저장
4. PCB B를 참조하여 이전 프로세스B의 상태로 CPU의 레지스터 값 설정
5. 프로세스B의 점유시간이 경과하면 운영체제는 인터럽트를 발생시키고 해당 과정 반복

### 컨텍스트 스위칭이 발생하는 이유
1. CPU 점유시간의 초과
2. 입출력 요청 발생
3. 다른 종류의 인터럽트 발생