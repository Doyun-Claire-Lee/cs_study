# 교착상태 해결

- 교착상태 해결 방법으로 교착상태 회피라는 방법이 있음.
- 프로세스에게 자원을 할당 할 때 어느정도까지 자원을 할당해야 교착상태가 발생하는지 파악하여 자원할당의 수준을 조절하는 방법
- 전체 자원의 수와 할당된 자원의 수를 기준으로 안정상태와 불안정상태로 나눔
- 불안정상태에 있더라도 무조건 교착상태에 빠지는것이 아닌 교착상태에 빠질 확률이 높아지는 것
- 은행원 알고리즘
- 교착상태의 검출 방법
  1. 가벼운 교착상태 검출: 타이머를 이용하여 일정 시간동안 작업을 진행하지 않는다면 교착상태가 발생했다고 간주함.
     * 일정 시점마다 체크포인트를 만들어 작업을 저장하여 마지막 체크포인트로 롤백하여 교착상태 해결
  2. 무거운 교착상태 검출: 자원할당그래프를 이용하여 현재 운영체제에서 프로세스가 어떤 자원을 사용하고 있는지 모니터링하며 교착상태가 발생하면 해결
     * 자원의 순환구조(?) 가 생기면 교착상태에 빠진것이기 때문에 해당 프로세스를 강제종료하고 마지막 체크포인트로 롤백됨.