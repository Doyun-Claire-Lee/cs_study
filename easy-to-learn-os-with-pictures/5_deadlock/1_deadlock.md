# 교착상태

- 여러 프로세스가 서로 다른 프로세스의 작업이 끝나기를 기다리다가 아무도 작업을 진행하지 못하는 상태
- 교착상태의 발생이유는 공유자원 때문
- 교착상태의 필요조건
  1. 상호배제: 어떤 프로세스가 자원을 점유했다면 그 자원은 다른 프로세스에게 공유되면 안됨.
  2. 비선점: 다른 프로세스의 리소스를 빼앗을 수 없어야 함.
  3. 점유와 대기: 어떤 프로세스가 리소스A를 가지고 있는 상태에서 리소스B를 기다리는 상태여야 함.
  4. 원형 대기: 점유와 대기를 하는 프로세스들의 관계가 원형을 이루어야 함.