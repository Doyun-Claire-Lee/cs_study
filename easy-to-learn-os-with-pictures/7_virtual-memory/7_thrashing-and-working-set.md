# 스레싱과 워킹셋

### 스레싱
- CPU 스케줄링은 CPU사용률을 높이는 것이 목표  
- 동시에 실행하는 프로세스의 수, 멀티프로그래밍 정도를 높이는 것  
- 멀티프로그래밍 정도를 높였으면 프로세스의 필요 공간을 위해 물리메모리에 영역을 할당해야 함  
- 하지만 물리메모리의 크기는 유한하기때문에 일부는 메모리에 올라갈 수 없고 하드디스크의 스왑영역에 저장됨.  
- 멀티프로그래밍 정도가 늘어나는 경우 제한된 물리메모리에 모든 프로그램을 올려야 하므로 당장 필요한 부분의 데이터만 메모리에 올라가게 되고 나머지는 스왑영역에 저장됨.
- 이럴 경우 Page fault가 많이 발생하게 되고, CPU가 작업하는 시간보다 스왑작업에 소요되는 시간이 더 길어져 CPU 사용률이 떨어지게 됨.
- CPU 스케줄러는 CPU 사용률이 낮아지면 더 많은 프로세스를 CPU에 올리고, 이 작업이 반복되면 CPU 사용률이 0에 수렴하게 됨.
> CPU 사용률을 높이려는 행동이 오히려 CPU 사용률을 낮추게 되는 이런 현상을 스레싱이라 함.  
- 스레싱의 근본적인 원인은 물리메모리의 크기 부족
- 그러나 무작정 메모리의 크기를 늘린다고 성능이 좋아지는 것은 아님. 스레싱이 발생하지 않는 경우 메모리의 크기를 늘려도 성능에 영향이 없기 때문


### 워킹셋
- 한 프로세스가 실행될 때 너무 많은 페이지를 할당하면 다른 프로세스가 사용할 페이지가 줄어들기 때문에 효율이 떨어지게 됨.
- 너무 적은 페이지를 할당하면 빈번한 Page fault가 발생하고 스왑요청이 많아 스레싱이 발생하게 됨.
- 이를 해결하기 위해 프로세스가 실행되면 일정량의 페이지를 할당하고, Page fault가 발생하는 경우 더 많은 페이지를 할당하는 방식을 사용
- 반대로 Page fault가 거의 발생하지 않으면 할당한 페이지를 회수함
- 이 과정으로 해당 프로세스에 맞는 적절한 페이지 수가 결정됨.
- 어떠한 페이지를 메모리에 유지할 것인가는 지역성 이론을 따름.
- 현재 메모리에 올라가있는 페이지는 재사용될 확률이 높기 때문에 하나의 세트로 묶어 메모리에 올림
- 이를 워킹셋이라 한다.
- 워킹셋은 프로세스가 준비상태에서 실행상태가 되는 컨텍스트 스위칭 시 사용됨