# 컴퓨터 하드웨어의 구조

오늘날 대부분의 컴퓨터는 프로그램 내장방식의 폰 노이만 구조를 사용하고 있음.

```
폰 노이만 구조
 - CPU와 메모리를 버스(데이터를 전달하는 통로)로 연결
 - 프로그램은 메모리에 올려서 실행시킴 -> 프로그램을 메모리에 내장시켰다 해서 프로그램 내장방식이라 부름.
 - 프로그램 변경시 과거의 컴퓨터는 배선을 바꾸어주어야 했지만 폰 노이만 구조는 메모리에 올라가는 소프트웨어만 변경해주면 되기 때문에 간편해짐.
```

1. 메인보드
 - 하드웨어들끼리 연결하는 장치
 - 장치간에 데이터 전송은 메인보드의 버스가 담당함.

2. CPU(Central processing unit)
 - 중앙처리장치. 컴퓨터의 연산을 담당하는 하드웨어
 - CPU의 구조
   - a. 제어장치(Control unit): 모든 장치들의 동작을 지시하고 제어
   - b. 산술논리 연산장치(Arithmetic and logic unit, ALU): 실제로 데이터 연산을 담당
   - c. 레지스터: CPU 내에서 계산을 위해 임시로 보관하는 장치(변수), 프로그램카운터, 메모리 주소 레지스터, 메모리 버퍼 레지스터, 명령어 레지스터 등
 
3. 메모리
 - a. RAM(Random access memory)
   - 랜덤으로 메모리를 읽어도 저장된 위치에 상관 없이 읽는 속도가 같음.
   - 전원이 꺼지면 저장된 데이터가 사라짐(휘발성)
 - b. ROM(Read only memory)
   - 전력이 공급되지 않아도 저장된 데이터가 사라지지 않으나 수정이 불가능함.
   - 컴퓨터 부팅과 관련된 바이오스를 저장하는데 주로 사용됨.