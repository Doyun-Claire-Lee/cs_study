# 페이징(고정분할방식)

- 페이지: 일정한 크기로 나누어진 논리주소공간 내의 하나의 영역
- 프레임: 페이지와 동일한 크기로 나누어진 물리주소공간 내의 하나의 영역

### 메모리관리자를 통한 논리주소 -> 물리주소 변환 과정
1. CPU가 메모리관리자에게 논리주소 변환 요청을 보내면 메모리관리자는 해당 논리주소의 페이지와 오프셋을 알아낸다.
2. 메모리관리자 내의 Page Table Base Register를 통해 물리메모리에 존재하는 페이지 테이블을 찾는다.
3. 페이지 번호를 인덱스로 프레임 번호를 알아내어 해당 주소값에 오프셋을 더해 물리주소로 변환한다.
4. 페이지 테이블에 invalid로 표시되어 있는 경우 스왑영역(하드디스크)에 저장되어 있다는 의미

- 페이지 넘버 = 논리주소 / 페이지크기
- 오프셋 = 논리주소 % 페이지크기

> 세그먼테이션과 마찬가지로 운영체제가 컨텍스트 스위칭을 할 때마다 페이지테이블의 내용도 변경된다.


### 세그멘테이션 vs 페이징
- 세그멘테이션은 프로세스마다 세그먼트 크기가 달라 크기를 표현하는 Bound Adress가 필요
- 페이징은 모든 페이지가 동일한 크기이기 때문에 Bound Address가 불필요
- 페이징은 이러한 특징 때문에 외부단편화는 발생하지 않지만 내부단편화가 발생
- 세그멘테이션은 크기를 가변적으로 정할 수 있기 때문에 논리적인 단위(코드, 데이터, 스택, 힙 영역)로 나누어 세그먼트 지정 가능
- 페이징은 크기가 정해져 있기 때문에 논리적인 단위로 나누는 것이 불가능함
- 페이징에서 각 프로세스마다 페이지테이블을 가지고 있기 때문에 페이지 테이블의 크기를 고려해야 함. 
- 페이지테이블의 크기가 너무 클 경우 물리메모리 내에 많은 영역을 차지하여 실제 프로세스 실행에 필요한 메모리가 부족할 수 있음.

