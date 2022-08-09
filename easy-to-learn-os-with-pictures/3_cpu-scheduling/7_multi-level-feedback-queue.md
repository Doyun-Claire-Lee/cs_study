# MLFQ(Multi-level-feedback-queue)

 - Round-robin 알고리즘의 업그레이드 버전
 - CPU Bound Process(CPU 사용률 중시)와 IO Bound Process(응답속도 중시) 두개가 있다고 가정
   - 타임슬라이스가 큰 경우
     - CPU Bound Process가 계속 실행되므로 CPU 사용률은 높아지고 IO사용률은 낮아짐.
   - 타임슬라이스가 작은 경우
     - CPU 사용률과 IO 사용률 둘다 높아지지만 잦은 컨텍스트 스위칭으로 인해 CPU Bound Process에서 오버헤드 발생
    - -> 이러한 문제점들로 인해 MLFQ 탄생!

 - 기본적으로 타임슬라이스를 작게 잡고, CPU Bound Process에게만 타임슬라이스를 크게 적용하는 방식
 - 어떻게 프로세스를 구분하는가? 
    - 스스로 CPU를 반납하는 경우 CPU사용률이 낮으니 IO Bound Process일 확률이 높음
    - 프로세스 실행 도중 스케줄러에 의해 강제로 CPU를 뺏기는 경우 CPU Bound Process일 확률이 높음
 - 우선 순위를 가진 큐를 여러개를 준비하여 우선순위별로 타임슬라이스의 크기를 조정(높을수록 짧게)
 - 오늘날 주로 쓰이는 스케줄링 알고리즘
